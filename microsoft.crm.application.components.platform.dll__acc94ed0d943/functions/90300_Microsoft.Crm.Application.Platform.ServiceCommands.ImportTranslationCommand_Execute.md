# Microsoft.Crm.Application.Platform.ServiceCommands.ImportTranslationCommand::Execute

- ea: `0x90300`
- end: `0x90347`
- name: `Microsoft.Crm.Application.Platform.ServiceCommands.ImportTranslationCommand::Execute`
- size: `71`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x5a130`

## callees

- `0x90300`
- `0x90e70`

## string_xrefs

- `0x90305`: `ImportTranslationCommand{0}.Import`
- `0x9032c`: `ImportTranslationCommand{0}.Import`

## pseudocode

```c

```

## disassembly

```asm
0x90300  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x90305  ldstr    aImporttranslat// "ImportTranslationCommand{0}.Import"
0x9030a  ldc.i4.1
0x9030b  newarr   [mscorlib]System.Object
0x90310  dup
0x90311  ldc.i4.0
0x90312  ldarg.0
0x90313  stelem.ref
0x90314  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x90319  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x9031e  ldarg.0
0x9031f  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::XrmExecuteInternal()
0x90324  pop
0x90325  leave.s  loc_90346
0x90327  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9032c  ldstr    aImporttranslat// "ImportTranslationCommand{0}.Import"
0x90331  ldc.i4.1
0x90332  newarr   [mscorlib]System.Object
0x90337  dup
0x90338  ldc.i4.0
0x90339  ldarg.0
0x9033a  stelem.ref
0x9033b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x90340  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x90345  endfinally
0x90346  ret
```
