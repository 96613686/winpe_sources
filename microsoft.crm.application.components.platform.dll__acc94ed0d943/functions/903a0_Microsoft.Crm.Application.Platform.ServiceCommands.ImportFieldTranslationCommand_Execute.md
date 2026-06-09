# Microsoft.Crm.Application.Platform.ServiceCommands.ImportFieldTranslationCommand::Execute

- ea: `0x903a0`
- end: `0x903f4`
- name: `Microsoft.Crm.Application.Platform.ServiceCommands.ImportFieldTranslationCommand::Execute`
- size: `84`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x5a140`

## callees

- `0x903a0`
- `0x90e70`

## string_xrefs

- `0x903a7`: `ImportFieldTranslationCommand{0}.Import`
- `0x903d3`: `ImportFieldTranslationCommand{0}.Import`

## pseudocode

```c

```

## disassembly

```asm
0x903a0  ldnull
0x903a1  stloc.0
0x903a2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x903a7  ldstr    aImportfieldtra_0// "ImportFieldTranslationCommand{0}.Import"
0x903ac  ldc.i4.1
0x903ad  newarr   [mscorlib]System.Object
0x903b2  dup
0x903b3  ldc.i4.0
0x903b4  ldarg.0
0x903b5  stelem.ref
0x903b6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x903bb  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x903c0  ldarg.0
0x903c1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::XrmExecuteInternal()
0x903c6  isinst   [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ImportFieldTranslationResponse
0x903cb  stloc.0
0x903cc  leave.s  loc_903ED
0x903ce  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x903d3  ldstr    aImportfieldtra_0// "ImportFieldTranslationCommand{0}.Import"
0x903d8  ldc.i4.1
0x903d9  newarr   [mscorlib]System.Object
0x903de  dup
0x903df  ldc.i4.0
0x903e0  ldarg.0
0x903e1  stelem.ref
0x903e2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x903e7  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x903ec  endfinally
0x903ed  ldloc.0
0x903ee  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ImportFieldTranslationResponse::get_JobId()
0x903f3  ret
```
