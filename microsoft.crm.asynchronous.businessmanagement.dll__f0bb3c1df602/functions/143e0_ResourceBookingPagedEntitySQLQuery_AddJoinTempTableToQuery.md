# ResourceBookingPagedEntitySQLQuery::AddJoinTempTableToQuery

- ea: `0x143e0`
- end: `0x143f9`
- name: `ResourceBookingPagedEntitySQLQuery::AddJoinTempTableToQuery`
- size: `25`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x147b0`
- `0x14860`
- `0x149a0`
- `0x14cd0`

## callees

- `0x14320`

## pseudocode

```c

```

## disassembly

```asm
0x143e0  ldarg.2
0x143e1  ldstr    aJoin0On0Bookab// "JOIN #{0} ON #{0}.BookableResourceId = "...
0x143e6  ldarg.0
0x143e7  call     instance string ResourceBookingPagedEntitySQLQuery::get_TempTableName()
0x143ec  call     string [mscorlib]System.String::Format(string, object)
0x143f1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x143f6  pop
0x143f7  ldarg.2
0x143f8  ret
```
