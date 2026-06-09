# Microsoft.Crm.Reporting.RuntimeReportServer::GenerateDescription

- ea: `0x6cd0`
- end: `0x6d05`
- name: `Microsoft.Crm.Reporting.RuntimeReportServer::GenerateDescription`
- size: `53`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x5d40`
- `0x5e40`
- `0x7290`

## callees

- `0x4870`
- `0x6c50`

## pseudocode

```c

```

## disassembly

```asm
0x6cd0  ldarg.0
0x6cd1  call     instance class [mscorlib]System.Resources.ResourceManager Microsoft.Crm.Reporting.ReportServer::get_Resources()
0x6cd6  ldstr    aReportdescript// "ReportDescription.FormatString"
0x6cdb  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0x6ce0  stloc.0
0x6ce1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6ce6  ldloc.0
0x6ce7  ldc.i4.2
0x6ce8  newarr   [mscorlib]System.Object
0x6ced  dup
0x6cee  ldc.i4.0
0x6cef  ldarg.1
0x6cf0  stelem.ref
0x6cf1  dup
0x6cf2  ldc.i4.1
0x6cf3  ldarg.2
0x6cf4  stelem.ref
0x6cf5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6cfa  ldc.i4   0x200
0x6cff  call     string Microsoft.Crm.Reporting.RuntimeReportServer::TrimItemProperty(string value, int32 maxLength)
0x6d04  ret
```
