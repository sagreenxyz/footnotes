# Footnotes

Footnotes is a service and application that provides a timestamp store for individual notes.  The timestamp and uri provide a unique way of tagging information whereby the timestamp tags can be stored in a database.  The storage is a combination of the username and Unix epoch time.  Furthermore, the response can be formatted in terms of a sequential number such as ```www.footnote.com/sagreenxyz/2022-03-13/0024/622e45b0c35ef65062d5d9c2```.  The username is obvious (```sagreenxyz```) as is the date the timestamp was generated (```2022-03-13```).  The this is how the data is stored in the database.  However, the user can get to the same datapoint with ISO

Database record identifier (object ID) only.  User receives this and can retrieve with same.  Note username in URL is optional.

```www.footnote.com/sagreenxyz/622e45b0c35ef65062d5d9c2```
```www.footnote.com/622e45b0c35ef65062d5d9c2```


Sequence is padded to user-specified number of digits.  User receives the first, but can retrieve with either the first or second form.

```www.footnote.com/sagreenxyz/00000476/622e45b0c35ef65062d5d9c2```
```www.footnote.com/sagreenxyz/00000476```

Sequence contains UTC offset, date, and sequence that resets to zero daily.
User can specify if first sequence number is 1 or 0.  User receives the first, but can retrieve with either the first or second form.

```www.footnote.com/sagreenxyz/UTC-5/2022-03-13/0024/622e45b0c35ef65062d5d9c2```
```www.footnote.com/sagreenxyz/UTC-5/2022-03-13/0024```

Note that all 5 formats specify the exact same record.  The database record will be returned as a JSON object, containing the notes the user originally provided, date/timestamp, full-history sequence number, UTC day and day sequence number, and unique object ID.  A UUID can also be generated and stored with the record.

Utility API calls can be provided to interconvert between URL forms for same record.
