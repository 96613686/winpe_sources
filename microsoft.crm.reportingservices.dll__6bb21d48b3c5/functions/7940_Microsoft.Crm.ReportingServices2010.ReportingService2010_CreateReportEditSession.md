# Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateReportEditSession

- ea: `0x7940`
- end: `0x7972`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateReportEditSession`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x7941`: `CreateReportEditSession`

## pseudocode

```c

```

## disassembly

```asm
0x7940  ldarg.0
0x7941  ldstr    aCreatereported// "CreateReportEditSession"
0x7946  ldc.i4.3
0x7947  newarr   [mscorlib]System.Object
0x794c  dup
0x794d  ldc.i4.0
0x794e  ldarg.1
0x794f  stelem.ref
0x7950  dup
0x7951  ldc.i4.1
0x7952  ldarg.2
0x7953  stelem.ref
0x7954  dup
0x7955  ldc.i4.2
0x7956  ldarg.3
0x7957  stelem.ref
0x7958  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x795d  stloc.0
0x795e  ldarg.s  4
0x7960  ldloc.0
0x7961  ldc.i4.1
0x7962  ldelem.ref
0x7963  castclass class Microsoft.Crm.ReportingServices2010.Warning[]
0x7968  stind.ref
0x7969  ldloc.0
0x796a  ldc.i4.0
0x796b  ldelem.ref
0x796c  castclass [mscorlib]System.String
0x7971  ret
```
