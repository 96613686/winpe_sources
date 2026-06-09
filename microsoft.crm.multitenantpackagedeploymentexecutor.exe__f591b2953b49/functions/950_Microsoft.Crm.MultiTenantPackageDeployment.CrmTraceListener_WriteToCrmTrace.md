# Microsoft.Crm.MultiTenantPackageDeployment.CrmTraceListener::WriteToCrmTrace

- ea: `0x950`
- end: `0x99d`
- name: `Microsoft.Crm.MultiTenantPackageDeployment.CrmTraceListener::WriteToCrmTrace`
- size: `77`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x8f0`
- `0x930`
- `0x940`

## callees

- `0x8a0`
- `0x8b0`
- `0x9a0`
- `0x9b0`
- `0xa30`

## pseudocode

```c

```

## disassembly

```asm
0x950  ldarg.1
0x951  call     valuetype [System]System.Diagnostics.TraceLevel Microsoft.Crm.MultiTenantPackageDeployment.CrmTraceListener::EventTypeToCrmLevel(valuetype [System]System.Diagnostics.TraceEventType eventType)
0x956  stloc.0
0x957  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x95c  ldarg.0
0x95d  callvirt instance string Microsoft.Crm.MultiTenantPackageDeployment.CrmTraceListener::get_MessagePattern()
0x962  ldc.i4.1
0x963  newarr   [mscorlib]System.Object
0x968  dup
0x969  ldc.i4.0
0x96a  ldarg.2
0x96b  stelem.ref
0x96c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x971  stloc.1
0x972  ldarg.0
0x973  ldnull
0x974  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x979  ldarg.0
0x97a  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory Microsoft.Crm.MultiTenantPackageDeployment.CrmTraceListener::get_TraceCategory()
0x97f  ldloc.0
0x980  ldstr    a0// "{0}"
0x985  ldc.i4.1
0x986  newarr   [mscorlib]System.Object
0x98b  dup
0x98c  ldc.i4.0
0x98d  ldloc.1
0x98e  stelem.ref
0x98f  call     instance void Microsoft.Crm.MultiTenantPackageDeployment.CrmTraceListener::LogTrace(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x994  ldarg.0
0x995  ldloc.0
0x996  ldloc.1
0x997  callvirt instance void Microsoft.Crm.MultiTenantPackageDeployment.CrmTraceListener::OnWriteToCrmTrace(valuetype [System]System.Diagnostics.TraceLevel level, string message)
0x99c  ret
```
