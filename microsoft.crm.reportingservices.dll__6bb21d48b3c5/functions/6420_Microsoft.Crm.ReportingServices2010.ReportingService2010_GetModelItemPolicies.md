# Microsoft.Crm.ReportingServices2010.ReportingService2010::GetModelItemPolicies

- ea: `0x6420`
- end: `0x644d`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::GetModelItemPolicies`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x6421`: `GetModelItemPolicies`

## pseudocode

```c

```

## disassembly

```asm
0x6420  ldarg.0
0x6421  ldstr    aGetmodelitempo// "GetModelItemPolicies"
0x6426  ldc.i4.2
0x6427  newarr   [mscorlib]System.Object
0x642c  dup
0x642d  ldc.i4.0
0x642e  ldarg.1
0x642f  stelem.ref
0x6430  dup
0x6431  ldc.i4.1
0x6432  ldarg.2
0x6433  stelem.ref
0x6434  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x6439  stloc.0
0x643a  ldarg.3
0x643b  ldloc.0
0x643c  ldc.i4.1
0x643d  ldelem.ref
0x643e  unbox.any [mscorlib]System.Boolean
0x6443  stind.i1
0x6444  ldloc.0
0x6445  ldc.i4.0
0x6446  ldelem.ref
0x6447  castclass class Microsoft.Crm.ReportingServices2010.Policy[]
0x644c  ret
```
