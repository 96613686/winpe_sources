# Microsoft.Crm.CrmDbConnection::Open

- ea: `0xd2f0`
- end: `0xd34a`
- name: `Microsoft.Crm.CrmDbConnection::Open`
- size: `90`
- prototype: ``
- caller_count: `35`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x8880`
- `0x8c00`
- `0x9d30`
- `0x9df0`
- `0x9ea0`
- `0x9f70`
- `0xa060`
- `0xa170`
- `0xe570`
- `0x102f0`
- `0x12310`
- `0x156d0`
- `0x15d20`
- `0x15e40`
- `0x15f20`
- `0x16210`
- `0x162c0`
- `0x164d0`
- `0x16750`
- `0x37bc0`
- `0x38410`
- `0x3f370`
- `0x3f530`
- `0x3f700`
- `0x454b0`
- `0x4b110`
- `0x4b340`
- `0x4d6d0`
- `0x603c0`
- `0x61780`
- `0x61da0`
- `0x61fa0`
- `0x62120`
- `0x63b70`
- `0x63cd0`

## callees

- `0xd2f0`
- `0xdc90`
- `0x1b8d0`
- `0x352e0`

## string_xrefs

- `0xd2fd`: `Open - Encountered disposed CrmDbConnection when it should not be disposed`
- `0xd331`: `OpenCount should be greater than zero`

## pseudocode

```c

```

## disassembly

```asm
0xd2f0  ldarg.0
0xd2f1  ldfld    bool Microsoft.Crm.CrmDbConnection::_disposed
0xd2f6  brfalse.s loc_D308
0xd2f8  ldstr    aCrmdbconnectio// "CrmDbConnection"
0xd2fd  ldstr    aOpenEncountere// "Open - Encountered disposed CrmDbConnec"...
0xd302  newobj   instance void Microsoft.Crm.CrmObjectDisposedException::.ctor(string objectName, string message)
0xd307  throw
0xd308  ldarg.0
0xd309  ldfld    int32 Microsoft.Crm.CrmDbConnection::_openCount
0xd30e  brtrue.s loc_D328
0xd310  newobj   instance void Microsoft.Crm.AutoReimpersonator::.ctor()
0xd315  stloc.0
0xd316  ldarg.0
0xd317  call     instance void Microsoft.Crm.CrmDbConnection::GetCreateAndOpenConnection()
0xd31c  leave.s  loc_D33B
0xd31e  ldloc.0
0xd31f  brfalse.s loc_D327
0xd321  ldloc.0
0xd322  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd327  endfinally
0xd328  ldarg.0
0xd329  ldfld    int32 Microsoft.Crm.CrmDbConnection::_openCount
0xd32e  ldc.i4.0
0xd32f  cgt
0xd331  ldstr    aOpencountShoul// "OpenCount should be greater than zero"
0xd336  call     void [System]System.Diagnostics.Trace::Assert(bool, string)
0xd33b  ldarg.0
0xd33c  ldarg.0
0xd33d  ldfld    int32 Microsoft.Crm.CrmDbConnection::_openCount
0xd342  ldc.i4.1
0xd343  add
0xd344  stfld    int32 Microsoft.Crm.CrmDbConnection::_openCount
0xd349  ret
```
