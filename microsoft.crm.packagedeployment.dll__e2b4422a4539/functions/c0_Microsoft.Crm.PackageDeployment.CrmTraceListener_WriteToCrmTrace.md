# Microsoft.Crm.PackageDeployment.CrmTraceListener::WriteToCrmTrace

- ea: `0xc0`
- end: `0x10d`
- name: `Microsoft.Crm.PackageDeployment.CrmTraceListener::WriteToCrmTrace`
- size: `77`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x60`
- `0xa0`
- `0xb0`

## callees

- `0x10`
- `0x20`
- `0x110`
- `0x120`
- `0x1a0`

## pseudocode

```c

```

## disassembly

```asm
0xc0  ldarg.1
0xc1  call     valuetype [System]System.Diagnostics.TraceLevel Microsoft.Crm.PackageDeployment.CrmTraceListener::EventTypeToCrmLevel(valuetype [System]System.Diagnostics.TraceEventType eventType)
0xc6  stloc.0
0xc7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xcc  ldarg.0
0xcd  callvirt instance string Microsoft.Crm.PackageDeployment.CrmTraceListener::get_MessagePattern()
0xd2  ldc.i4.1
0xd3  newarr   [mscorlib]System.Object
0xd8  dup
0xd9  ldc.i4.0
0xda  ldarg.2
0xdb  stelem.ref
0xdc  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xe1  stloc.1
0xe2  ldarg.0
0xe3  ldnull
0xe4  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0xe9  ldarg.0
0xea  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory Microsoft.Crm.PackageDeployment.CrmTraceListener::get_TraceCategory()
0xef  ldloc.0
0xf0  ldstr    a0// "{0}"
0xf5  ldc.i4.1
0xf6  newarr   [mscorlib]System.Object
0xfb  dup
0xfc  ldc.i4.0
0xfd  ldloc.1
0xfe  stelem.ref
0xff  call     instance void Microsoft.Crm.PackageDeployment.CrmTraceListener::LogTrace(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x104  ldarg.0
0x105  ldloc.0
0x106  ldloc.1
0x107  callvirt instance void Microsoft.Crm.PackageDeployment.CrmTraceListener::OnWriteToCrmTrace(valuetype [System]System.Diagnostics.TraceLevel level, string message)
0x10c  ret
```
