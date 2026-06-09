# Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateRoleAsync_0

- ea: `0x5930`
- end: `0x5970`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateRoleAsync_0`
- size: `64`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x5920`

## callees

- `0x5930`

## string_xrefs

- `0x594b`: `CreateRole`

## pseudocode

```c

```

## disassembly

```asm
0x5930  ldarg.0
0x5931  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateRoleOperationCompleted
0x5936  brtrue.s loc_594A
0x5938  ldarg.0
0x5939  ldarg.0
0x593a  ldftn    instance void Microsoft.Crm.ReportingServices2010.ReportingService2010::OnCreateRoleOperationCompleted(object arg)
0x5940  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x5945  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateRoleOperationCompleted
0x594a  ldarg.0
0x594b  ldstr    aCreaterole// "CreateRole"
0x5950  ldc.i4.3
0x5951  newarr   [mscorlib]System.Object
0x5956  dup
0x5957  ldc.i4.0
0x5958  ldarg.1
0x5959  stelem.ref
0x595a  dup
0x595b  ldc.i4.1
0x595c  ldarg.2
0x595d  stelem.ref
0x595e  dup
0x595f  ldc.i4.2
0x5960  ldarg.3
0x5961  stelem.ref
0x5962  ldarg.0
0x5963  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateRoleOperationCompleted
0x5968  ldarg.s  4
0x596a  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x596f  ret
```
