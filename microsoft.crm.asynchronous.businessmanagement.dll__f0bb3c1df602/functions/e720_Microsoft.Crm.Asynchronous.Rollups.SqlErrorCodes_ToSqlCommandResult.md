# Microsoft.Crm.Asynchronous.Rollups.SqlErrorCodes::ToSqlCommandResult

- ea: `0xe720`
- end: `0xe76c`
- name: `Microsoft.Crm.Asynchronous.Rollups.SqlErrorCodes::ToSqlCommandResult`
- size: `76`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xcb40`
- `0xcd90`
- `0xe770`
- `0xed30`

## callees

- `0xe720`

## pseudocode

```c

```

## disassembly

```asm
0xe720  ldarg.0
0xe721  callvirt instance int32 [System.Data]System.Data.SqlClient.SqlException::get_Number()
0xe726  stloc.0
0xe727  ldloc.0
0xe728  ldc.i4   0x4B5
0xe72d  bgt.s    loc_E746
0xe72f  ldloc.0
0xe730  ldc.i4.s 0xFE
0xe732  beq.s    loc_E764
0xe734  ldloc.0
0xe735  ldc.i4   0xD0
0xe73a  beq.s    loc_E762
0xe73c  ldloc.0
0xe73d  ldc.i4   0x4B5
0xe742  beq.s    loc_E766
0xe744  br.s     loc_E76A
0xe746  ldloc.0
0xe747  ldc.i4   0xA29
0xe74c  beq.s    loc_E760
0xe74e  ldloc.0
0xe74f  ldc.i4   0xA43
0xe754  beq.s    loc_E760
0xe756  ldloc.0
0xe757  ldc.i4   0xAFC
0xe75c  beq.s    loc_E768
0xe75e  br.s     loc_E76A
0xe760  ldc.i4.2
0xe761  ret
0xe762  ldc.i4.0
0xe763  ret
0xe764  ldc.i4.3
0xe765  ret
0xe766  ldc.i4.4
0xe767  ret
0xe768  ldc.i4.5
0xe769  ret
0xe76a  ldc.i4.6
0xe76b  ret
```
