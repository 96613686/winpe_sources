# Microsoft.Crm.Asynchronous.ImportDataAccess::ExecuteSqlCommandWithNoExpectedRecords

- ea: `0x4540`
- end: `0x4552`
- name: `Microsoft.Crm.Asynchronous.ImportDataAccess::ExecuteSqlCommandWithNoExpectedRecords`
- size: `18`
- prototype: ``
- caller_count: `19`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x3ca0`
- `0x3d00`
- `0x3d80`
- `0x3df0`
- `0x3e70`
- `0x3ec0`
- `0x3f30`
- `0x3f90`
- `0x3fd0`
- `0x40c0`
- `0x4140`
- `0x41e0`
- `0x4240`
- `0x42b0`
- `0x45a0`
- `0x45f0`
- `0x4630`
- `0x4690`
- `0x5660`

## pseudocode

```c

```

## disassembly

```asm
0x4540  ldarg.0
0x4541  ldarg.1
0x4542  ldloca.s 0
0x4544  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x454a  ldloc.0
0x454b  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand, valuetype [mscorlib]System.Nullable`1<int32>)
0x4550  pop
0x4551  ret
```
