# Microsoft.Crm.MultiTenantPackageDeployment.CrmTraceListener::LogTrace_0

- ea: `0xa50`
- end: `0xaa3`
- name: `Microsoft.Crm.MultiTenantPackageDeployment.CrmTraceListener::LogTrace_0`
- size: `83`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xa30`

## callees

- `0xa50`

## pseudocode

```c

```

## disassembly

```asm
0xa50  ldarg.s  4
0xa52  ldc.i4.1
0xa53  sub
0xa54  switch   loc_A6A, loc_A79, loc_A87, loc_A95
0xa69  ret
0xa6a  ldarg.1
0xa6b  ldarg.2
0xa6c  ldarg.3
0xa6d  ldarg.s  5
0xa6f  ldarg.s  6
0xa71  ldarg.s  7
0xa73  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, int32, string, object[])
0xa78  ret
0xa79  ldarg.2
0xa7a  ldarg.3
0xa7b  ldarg.s  5
0xa7d  ldarg.s  6
0xa7f  ldarg.s  7
0xa81  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, int32, string, object[])
0xa86  ret
0xa87  ldarg.2
0xa88  ldarg.3
0xa89  ldarg.s  5
0xa8b  ldarg.s  6
0xa8d  ldarg.s  7
0xa8f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, int32, string, object[])
0xa94  ret
0xa95  ldarg.2
0xa96  ldarg.3
0xa97  ldarg.s  5
0xa99  ldarg.s  6
0xa9b  ldarg.s  7
0xa9d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, int32, string, object[])
0xaa2  ret
```
