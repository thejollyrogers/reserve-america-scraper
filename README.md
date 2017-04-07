Scrape Reserve America
======================

Scrape Reserve America for your favorite campsite

Usage
-----

Run the script with a few environment variables like so:

```sh
> pip install -r requirements.txt
> export CAMPGROUND="https://www.reserveamerica.com/camping/big-basin-redwoods-sp/r/campgroundDetails.do?contractCode=CA&parkId=120009"
> export LENGTH=2
> export DATE="04/14/2017"
> ./scraper.py
```

Then the scraper will search the given campsite for the date with the length of stay.

Or, you can set up the script to run under cron, and notify you on macOS using the provided [`cron.sh`](./cron.sh) script. An example is:

```cron
*/15 * * * * CAMPGROUND="https://www.reserveamerica.com/camping/big-basin-redwoods-sp/r/campgroundDetails.do?contractCode=CA&parkId=120009" LENGTH=2 DATE="04/14/2017" ~/reserve-america-scraper/cron.sh 2>&1 > /dev/null
```

Note that the `cron.sh` expects you to `export RESERVE_AMERICA_VENV_BASE` to your virtual environment
e.g.

```sh
> export RESERVE_AMERICA_VENV_BASE='path/to/your/virtualenv';
```

Also, make sure that you have `terminal-notifier` installed. That's easy to do with Homebrew:

```sh
> brew install terminal-notifier
```

License
-------

[MIT](./LICENSE)
