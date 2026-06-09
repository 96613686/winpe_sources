# Microsoft.Crm.Sdk.InProcessCrmService::ReportException

- ea: `0x3170`
- end: `0x31f5`
- name: `Microsoft.Crm.Sdk.InProcessCrmService::ReportException`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x3130`

## callees

- `0x3170`

## string_xrefs

- `0x3178`: `non-plugin non- CrmException detected - report will be sent to Watson:{0}{1}`

## pseudocode

```c

```

## disassembly

```asm
0x3170  ldnull
0x3171  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x3176  ldc.i4.s 0x1A
0x3178  ldstr    aNonPluginNonCr// "non-plugin non- CrmException detected -"...
0x317d  ldc.i4.2
0x317e  newarr   [mscorlib]System.Object
0x3183  dup
0x3184  ldc.i4.0
0x3185  call     string [mscorlib]System.Environment::get_NewLine()
0x318a  stelem.ref
0x318b  dup
0x318c  ldc.i4.1
0x318d  ldarg.0
0x318e  stelem.ref
0x318f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3194  ldsfld   string [mscorlib]System.String::Empty
0x3199  stloc.0
0x319a  call     bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.StaticSoapContext::get_IsEmpty()
0x319f  brtrue.s loc_31DE
0x31a1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x31a6  ldstr    aHttpheader0Add// "HttpHeader = {0}, Address = {1}, Method"...
0x31ab  ldc.i4.3
0x31ac  newarr   [mscorlib]System.Object
0x31b1  dup
0x31b2  ldc.i4.0
0x31b3  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SoapContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.StaticSoapContext::get_CurrentSoapContext()
0x31b8  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SoapContext::get_HttpHeader()
0x31bd  stelem.ref
0x31be  dup
0x31bf  ldc.i4.1
0x31c0  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SoapContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.StaticSoapContext::get_CurrentSoapContext()
0x31c5  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SoapContext::get_Address()
0x31ca  stelem.ref
0x31cb  dup
0x31cc  ldc.i4.2
0x31cd  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SoapContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.StaticSoapContext::get_CurrentSoapContext()
0x31d2  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SoapContext::get_CrmMethodName()
0x31d7  stelem.ref
0x31d8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x31dd  stloc.0
0x31de  ldarg.0
0x31df  ldloc.0
0x31e0  ldc.i4.0
0x31e1  newarr   [mscorlib]System.Object
0x31e6  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Watson.ExceptionManager::ReportException(class [mscorlib]System.Exception, string, object[])
0x31eb  pop
0x31ec  ldc.i4.1
0x31ed  ldarg.0
0x31ee  call     string [Microsoft.Crm.Core]Microsoft.Crm.MiniDump::CreateDump(valuetype [Microsoft.Crm.Core]Microsoft.Crm.MiniDumpReasons, class [mscorlib]System.Exception)
0x31f3  pop
0x31f4  ret
```
