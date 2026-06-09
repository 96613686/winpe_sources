# Microsoft.Crm.WebServices.TranslationImportExportService::ExportTranslations

- ea: `0xf170`
- end: `0xf1ed`
- name: `Microsoft.Crm.WebServices.TranslationImportExportService::ExportTranslations`
- size: `125`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xd7f0`
- `0xe900`

## callees

- `0xf170`
- `0xf1f0`

## pseudocode

```c

```

## disassembly

```asm
0xf170  ldarg.0
0xf171  ldarg.2
0xf172  ldarg.3
0xf173  call     instance string Microsoft.Crm.WebServices.TranslationImportExportService::ExportTranslationsInternal(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, string solutionName)
0xf178  stloc.0
0xf179  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf17e  ldstr    aExportBegin0Ex// "Export_BEGIN_{0}.ExportTranslations().Z"...
0xf183  ldc.i4.1
0xf184  newarr   [mscorlib]System.Object
0xf189  dup
0xf18a  ldc.i4.0
0xf18b  ldarg.0
0xf18c  stelem.ref
0xf18d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xf192  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0xf197  newobj   instance void [Microsoft.Crm]Microsoft.Crm.CrmZip::.ctor()
0xf19c  stloc.1
0xf19d  ldloc.1
0xf19e  ldarg.1
0xf19f  ldc.i4.2
0xf1a0  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0xf1a5  call     class [System]System.Uri [WindowsBase]System.IO.Packaging.PackUriHelper::CreatePartUri(class [System]System.Uri)
0xf1aa  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0xf1af  ldloc.0
0xf1b0  callvirt instance unsigned int8[] [mscorlib]System.Text.Encoding::GetBytes(string)
0xf1b5  callvirt instance void [Microsoft.Crm]Microsoft.Crm.CrmZip::AddPart(class [System]System.Uri, unsigned int8[])
0xf1ba  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf1bf  ldstr    aExportEnd0Expo// "Export_END_{0}.ExportTranslations().Zip"
0xf1c4  ldc.i4.1
0xf1c5  newarr   [mscorlib]System.Object
0xf1ca  dup
0xf1cb  ldc.i4.0
0xf1cc  ldarg.0
0xf1cd  stelem.ref
0xf1ce  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xf1d3  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0xf1d8  ldloc.1
0xf1d9  callvirt instance unsigned int8[] [Microsoft.Crm]Microsoft.Crm.CrmZip::GetZip()
0xf1de  stloc.2
0xf1df  leave.s  loc_F1EB
0xf1e1  ldloc.1
0xf1e2  brfalse.s loc_F1EA
0xf1e4  ldloc.1
0xf1e5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf1ea  endfinally
0xf1eb  ldloc.2
0xf1ec  ret
```
