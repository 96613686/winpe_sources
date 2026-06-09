# ResourceBookingPagedEntitySQLQuery::get_TempTableName

- ea: `0x14320`
- end: `0x14331`
- name: `ResourceBookingPagedEntitySQLQuery::get_TempTableName`
- size: `17`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x143e0`
- `0x14710`
- `0x147b0`
- `0x14980`

## callees

- `0x14310`

## string_xrefs

- `0x14320`: `Temp{0}`

## pseudocode

```c

```

## disassembly

```asm
0x14320  ldstr    aTemp0// "Temp{0}"
0x14325  ldarg.0
0x14326  callvirt instance string ResourceBookingPagedEntitySQLQuery::get_Name()
0x1432b  call     string [mscorlib]System.String::Format(string, object)
0x14330  ret
```
