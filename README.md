# Xiaomi Mi Band Data Export
Export data from [Xiaomi](https://xiaomi.com/) Mi Band in the most automated way possible.

## Theory
According to the [GDPR](https://en.wikipedia.org/wiki/General_Data_Protection_Regulation) law we have to have our data
accessible in order to download them. For this Xiaomi enabled a [website](https://user.huami.com/gdpr/v2/index.html).

There are several ways to log in.

The simplest thing would be, once the session is started, use the elements inspector of the web browser to obtain
the variables of 2 cookies:
- userid
- apptoken

With these values a `POST request` has to be made that will ask **Huami** for the data.
This will compress them in a **zip file** and **send us an email** with the UUID of the file.

Once the UUID is obtained, we will have to make another `GET request` to obtain the **download URL** of the zip file
and the **password encryption** of it.

Once the zip file is unzipped, we will have a list of folders and within them the **csv files** with our private information.

    ├─ ACTIVITY/
    │  ├─ ACTIVITY_*.csv
    ├─ ACTIVITY_MINUTE/
    │  ├─ ACTIVITY_MINUTE_*.csv
    ├─ ACTIVITY_STAGE/
    │  ├─ ACTIVITY_STAGE_*.csv
    ├─ BODY/
    │  ├─ BODY_*.csv
    ├─ HEARTRATE/
    │  ├─ HEARTRATE_*.csv
    ├─ HEARTRATE_AUTO/
    │  ├─ HEARTRATE_AUTO_*.csv
    ├─ SLEEP/
    │  ├─ SLEEP_*.csv
    ├─ SPORT/
    │  ├─ SPORT_*.csv
    ├─ USER/
    │  └─ USER_*.csv

## License
Licensed under the [MIT license](http://opensource.org/licenses/MIT)

Read [LICENSE](LICENSE) for more information
