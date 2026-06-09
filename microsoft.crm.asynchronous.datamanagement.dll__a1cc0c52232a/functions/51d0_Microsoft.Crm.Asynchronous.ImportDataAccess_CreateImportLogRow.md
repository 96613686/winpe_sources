# Microsoft.Crm.Asynchronous.ImportDataAccess::CreateImportLogRow

- ea: `0x51d0`
- end: `0x51e7`
- name: `Microsoft.Crm.Asynchronous.ImportDataAccess::CreateImportLogRow`
- size: `23`
- prototype: ``
- caller_count: `23`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xbe90`
- `0xe550`
- `0xf190`
- `0x10100`
- `0x10ec0`
- `0x11a20`
- `0x120b0`
- `0x14370`
- `0x14cb0`
- `0x15220`
- `0x15b80`
- `0x15d20`
- `0x163d0`
- `0x16bf0`
- `0x17910`
- `0x18840`
- `0x18f40`
- `0x19370`
- `0x1ab90`
- `0x1b470`
- `0x1baf0`
- `0x1c8f0`
- `0x1d050`

## callees

- `0x51f0`

## pseudocode

```c

```

## disassembly

```asm
0x51d0  ldarg.0
0x51d1  ldarg.1
0x51d2  ldarg.2
0x51d3  ldarg.3
0x51d4  ldarg.s  4
0x51d6  ldarg.s  5
0x51d8  ldarg.s  6
0x51da  ldarg.s  7
0x51dc  ldarg.s  8
0x51de  ldarg.s  9
0x51e0  ldc.i4.0
0x51e1  call     instance void Microsoft.Crm.Asynchronous.ImportDataAccess::CreateImportLogRow(valuetype [mscorlib]System.Guid ownerId, valuetype [mscorlib]System.Guid businessUnitId, valuetype [mscorlib]System.Guid importFileId, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> importDataId, int32 logPhaseCode, string headerColumn, string columnValue, valuetype [mscorlib]System.Nullable`1<int32> errorNumber, string additionalInfo, int32 errorType)
0x51e6  ret
```
