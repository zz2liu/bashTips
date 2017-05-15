# bashTips
Bash tips: useful linux shell tips to save your life
### read each line from a file
```
cat file.txt | while read line; do
echo "$line"
done
```
### Split line into fields
```
IN="bla@some.com;john@home.com" 
arrIN=(${IN//;/ })
```
The syntax used inside of the curly braces to replace each ';' character with a ' ' character is called Parameter Expansion.
Gotchas:
- If the original string has spaces, you will need to use IFS:
`IFS=':'; arrIN=($IN); unset IFS;`
- If the original string has spaces and the delimiter is a new line, you can set IFS with:
`IFS=$'\n'; arrIN=($IN); unset IFS;`
