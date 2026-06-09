# Microsoft.Crm.Reporting.ReportServer::get_RandomOrganizationContext

- ea: `0x4840`
- end: `0x4858`
- name: `Microsoft.Crm.Reporting.ReportServer::get_RandomOrganizationContext`
- size: `24`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x4800`
- `0x8340`
- `0x8370`
- `0x8410`

## pseudocode

```c

```

## disassembly

```asm
0x4840  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x4845  stloc.0
0x4846  ldloca.s 0
0x4848  ldstr    aN_0// "N"
0x484d  call     instance string [mscorlib]System.Guid::ToString(string)
0x4852  newobj   instance void [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext::.ctor(string)
0x4857  ret
```
