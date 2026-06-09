# TransactionLogDataComparer::Compare

- ea: `0xf950`
- end: `0xf972`
- name: `TransactionLogDataComparer::Compare`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0xa400`
- `0xf950`

## pseudocode

```c

```

## disassembly

```asm
0xf950  ldarg.1
0xf951  callvirt instance float64 Microsoft.Crm.Asynchronous.TransactionLogData::get_TLogUsage()
0xf956  ldarg.2
0xf957  callvirt instance float64 Microsoft.Crm.Asynchronous.TransactionLogData::get_TLogUsage()
0xf95c  ble.un.s loc_F960
0xf95e  ldc.i4.m1
0xf95f  ret
0xf960  ldarg.1
0xf961  callvirt instance float64 Microsoft.Crm.Asynchronous.TransactionLogData::get_TLogUsage()
0xf966  ldarg.2
0xf967  callvirt instance float64 Microsoft.Crm.Asynchronous.TransactionLogData::get_TLogUsage()
0xf96c  bge.un.s loc_F970
0xf96e  ldc.i4.1
0xf96f  ret
0xf970  ldc.i4.0
0xf971  ret
```
