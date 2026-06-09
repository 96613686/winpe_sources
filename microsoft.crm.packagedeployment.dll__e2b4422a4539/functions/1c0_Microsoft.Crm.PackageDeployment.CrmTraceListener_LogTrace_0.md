# Microsoft.Crm.PackageDeployment.CrmTraceListener::LogTrace_0

- ea: `0x1c0`
- end: `0x213`
- name: `Microsoft.Crm.PackageDeployment.CrmTraceListener::LogTrace_0`
- size: `83`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1a0`

## callees

- `0x1c0`

## pseudocode

```c

```

## disassembly

```asm
0x1c0  ldarg.s  4
0x1c2  ldc.i4.1
0x1c3  sub
0x1c4  switch   loc_1DA, loc_1E9, loc_1F7, loc_205
0x1d9  ret
0x1da  ldarg.1
0x1db  ldarg.2
0x1dc  ldarg.3
0x1dd  ldarg.s  5
0x1df  ldarg.s  6
0x1e1  ldarg.s  7
0x1e3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, int32, string, object[])
0x1e8  ret
0x1e9  ldarg.2
0x1ea  ldarg.3
0x1eb  ldarg.s  5
0x1ed  ldarg.s  6
0x1ef  ldarg.s  7
0x1f1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, int32, string, object[])
0x1f6  ret
0x1f7  ldarg.2
0x1f8  ldarg.3
0x1f9  ldarg.s  5
0x1fb  ldarg.s  6
0x1fd  ldarg.s  7
0x1ff  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, int32, string, object[])
0x204  ret
0x205  ldarg.2
0x206  ldarg.3
0x207  ldarg.s  5
0x209  ldarg.s  6
0x20b  ldarg.s  7
0x20d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, int32, string, object[])
0x212  ret
```
