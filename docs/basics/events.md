---
sidebar_position: 3
---

# Events

You might need to adjust your events with some properties

    export interface CalendarEvent {
        id: string;
        startAt: string;
        endAt: string;
        timezoneStartAt: string; // optional
        summary: string;
        color: string;
        [key: string]: any;
    }

According to your needs, you can set timezone for each event and also set default timezone with "timezone" prop in IANA format.
If you don't provide timezone prop, your system default timezone will be used.

You can keep other event properties, those will be ignored.

# Events data
Breaking change after upgrading from versions 0.6.5 and older:
Kalend now accepts only array of events, you don't need to format them to dates like before

    const events = [
                    {
                        id: 1,
                        startAt: '2021-11-21T18:00:00.000Z',
                        endAt: '2021-11-21T19:00:00.000Z',
                        timezoneStartAt: 'Europe/Berlin', // optional
                        summary: 'test',
                        color: 'blue',
                        calendarID: 'work'
                    },
                    {
                        id: 2,
                        startAt: '2021-11-21T18:00:00.000Z',
                        endAt: '2021-11-21T19:00:00.000Z',
                        timezoneStartAt: 'Europe/Berlin', // optional
                        summary: 'test',
                        color: 'blue',
                    }
            ]

# Task event 

From version 0.17.0 you can define event as "task" with two new properties:

- **type** will add radio icon to the event to show different event type. There are two valid enums:

```
enum CALENDAR_EVENT_TYPE {
    EVENT = 'EVENT',
    TASK = 'TASK',
}
```
- **isTaskChecked** will change radio icon to filled version if set to true.

Example:

```
{
    id: 2,
    startAt: '2021-11-21T18:00:00.000Z',
    endAt: '2021-11-21T19:00:00.000Z',
    summary: 'test',
    type: CALENDAR_EVENT_TYPE.TASK,
    isTaskChecked: true
}

```
