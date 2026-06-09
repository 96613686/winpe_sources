# Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::ExtractFromCompressedFile

- ea: `0x78030`
- end: `0x78222`
- name: `Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::ExtractFromCompressedFile`
- size: `498`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x77f30`

## callees

- `0x4e030`
- `0x78030`
- `0x78230`

## string_xrefs

- `0x78035`: `Import_BEGIN_{0}.compressedCustomizationFile().Decompress`
- `0x78097`: `/solution.xml`
- `0x780d4`: `/customizations.xml`
- `0x780ff`: `/compatibility.xml`
- `0x781dd`: `Import_END_{0}.compressedCustomizationFile().Decompress`

## pseudocode

```c

```

## disassembly

```asm
0x78030  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x78035  ldstr    aImportBegin0Co// "Import_BEGIN_{0}.compressedCustomizatio"...
0x7803a  ldc.i4.1
0x7803b  newarr   [mscorlib]System.Object
0x78040  dup
0x78041  ldc.i4.0
0x78042  ldarg.0
0x78043  stelem.ref
0x78044  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x78049  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x7804e  ldarg.0
0x7804f  ldarg.1
0x78050  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::customizationImportTemporaryDirectoryName
0x78055  newobj   instance void [Microsoft.Crm]Microsoft.Crm.CrmTemporaryFile::.ctor(unsigned int8[], string)
0x7805a  stfld    class [Microsoft.Crm]Microsoft.Crm.CrmTemporaryFile Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::_customizationFileLocation
0x7805f  ldarg.0
0x78060  ldarg.0
0x78061  ldarg.0
0x78062  ldfld    class [Microsoft.Crm]Microsoft.Crm.CrmTemporaryFile Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::_customizationFileLocation
0x78067  call     instance class [Microsoft.Crm]Microsoft.Crm.CrmUnzip Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::ExtractZipDataFromCustomizationFile(class [Microsoft.Crm]Microsoft.Crm.CrmTemporaryFile customizationFile)
0x7806c  stfld    class [Microsoft.Crm]Microsoft.Crm.CrmUnzip Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::_customizationFileContents
0x78071  ldarg.0
0x78072  ldfld    class [Microsoft.Crm]Microsoft.Crm.CrmUnzip Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::_customizationFileContents
0x78077  callvirt instance class [System]System.Uri[] [Microsoft.Crm]Microsoft.Crm.CrmUnzip::GetDirectory()
0x7807c  stloc.0
0x7807d  ldc.i4.0
0x7807e  stloc.1
0x7807f  br       loc_7812B
0x78084  ldloc.0
0x78085  ldloc.1
0x78086  ldelem.ref
0x78087  stloc.2
0x78088  ldloc.2
0x78089  callvirt instance string [mscorlib]System.Object::ToString()
0x7808e  stloc.3
0x7808f  ldloc.3
0x78090  call     string [System]System.Uri::UnescapeDataString(string)
0x78095  stloc.3
0x78096  ldloc.3
0x78097  ldstr    aSolutionXml_0// "/solution.xml"
0x7809c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x780a1  brfalse.s loc_780D3
0x780a3  ldarg.0
0x780a4  ldfld    string Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::solutionXml
0x780a9  ldsfld   string [mscorlib]System.String::Empty
0x780ae  call     bool [mscorlib]System.String::Equals(string, string)
0x780b3  brfalse.s loc_780D3
0x780b5  ldarg.0
0x780b6  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x780bb  ldarg.0
0x780bc  ldfld    class [Microsoft.Crm]Microsoft.Crm.CrmUnzip Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::_customizationFileContents
0x780c1  ldloc.2
0x780c2  callvirt instance unsigned int8[] [Microsoft.Crm]Microsoft.Crm.CrmUnzip::GetPart(class [System]System.Uri)
0x780c7  callvirt instance string [mscorlib]System.Text.Encoding::GetString(unsigned int8[])
0x780cc  stfld    string Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::solutionXml
0x780d1  br.s     loc_78127
0x780d3  ldloc.3
0x780d4  ldstr    aCustomizations_1// "/customizations.xml"
0x780d9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x780de  brfalse.s loc_780FE
0x780e0  ldarg.0
0x780e1  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x780e6  ldarg.0
0x780e7  ldfld    class [Microsoft.Crm]Microsoft.Crm.CrmUnzip Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::_customizationFileContents
0x780ec  ldloc.2
0x780ed  callvirt instance unsigned int8[] [Microsoft.Crm]Microsoft.Crm.CrmUnzip::GetPart(class [System]System.Uri)
0x780f2  callvirt instance string [mscorlib]System.Text.Encoding::GetString(unsigned int8[])
0x780f7  stfld    string Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::customizationXml
0x780fc  br.s     loc_78127
0x780fe  ldloc.3
0x780ff  ldstr    aCompatibilityX// "/compatibility.xml"
0x78104  call     bool [mscorlib]System.String::op_Equality(string, string)
0x78109  brfalse.s loc_78127
0x7810b  ldarg.0
0x7810c  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x78111  ldarg.0
0x78112  ldfld    class [Microsoft.Crm]Microsoft.Crm.CrmUnzip Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::_customizationFileContents
0x78117  ldloc.2
0x78118  callvirt instance unsigned int8[] [Microsoft.Crm]Microsoft.Crm.CrmUnzip::GetPart(class [System]System.Uri)
0x7811d  callvirt instance string [mscorlib]System.Text.Encoding::GetString(unsigned int8[])
0x78122  stfld    string Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::compatibilityXml
0x78127  ldloc.1
0x78128  ldc.i4.1
0x78129  add
0x7812a  stloc.1
0x7812b  ldloc.1
0x7812c  ldloc.0
0x7812d  ldlen
0x7812e  conv.i4
0x7812f  blt      loc_78084
0x78134  ldarg.0
0x78135  ldarg.0
0x78136  ldfld    class [Microsoft.Crm]Microsoft.Crm.CrmUnzip Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::_customizationFileContents
0x7813b  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.CrmUnzipFileSet::.ctor(class [Microsoft.Crm]Microsoft.Crm.CrmUnzip unzipFile)
0x78140  stfld    class Microsoft.Crm.Tools.ImportExportPublish.IImportFileSet Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::_importFileSet
0x78145  leave    loc_781D8
0x7814a  stloc.s  4
0x7814c  ldloc.s  4
0x7814e  callvirt instance int32 [mscorlib]System.Exception::get_HResult()
0x78153  ldc.i4   0xFFFF
0x78158  and
0x78159  stloc.s  5
0x7815b  ldloc.s  5
0x7815d  ldc.i4.s 0x70
0x7815f  beq.s    loc_78167
0x78161  ldloc.s  5
0x78163  ldc.i4.s 0x27
0x78165  bne.un.s loc_78178
0x78167  ldc.i4   0x80050124
0x7816c  ldc.i4.0
0x7816d  newarr   [mscorlib]System.Object
0x78172  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x78177  throw
0x78178  ldnull
0x78179  ldarg.0
0x7817a  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::context
0x7817f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x78184  ldc.i4.s 0x14
0x78186  ldstr    aImportfileForF// "ImportFile for File: {0} failed with Ex"...
0x7818b  ldc.i4.3
0x7818c  newarr   [mscorlib]System.Object
0x78191  dup
0x78192  ldc.i4.0
0x78193  ldarg.0
0x78194  ldfld    class [Microsoft.Crm]Microsoft.Crm.CrmTemporaryFile Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::_customizationFileLocation
0x78199  brfalse.s loc_781A8
0x7819b  ldarg.0
0x7819c  ldfld    class [Microsoft.Crm]Microsoft.Crm.CrmTemporaryFile Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::_customizationFileLocation
0x781a1  callvirt instance string [Microsoft.Crm]Microsoft.Crm.CrmTemporaryFile::get_FileFullyQualifiedName()
0x781a6  br.s     loc_781AD
0x781a8  ldstr    aNotInitialized// "Not initialized"
0x781ad  stelem.ref
0x781ae  dup
0x781af  ldc.i4.1
0x781b0  ldloc.s  4
0x781b2  callvirt instance string [mscorlib]System.Exception::get_Message()
0x781b7  stelem.ref
0x781b8  dup
0x781b9  ldc.i4.2
0x781ba  ldloc.s  4
0x781bc  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x781c1  stelem.ref
0x781c2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x781c7  ldc.i4   0x80050125
0x781cc  ldc.i4.0
0x781cd  newarr   [mscorlib]System.Object
0x781d2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x781d7  throw
0x781d8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x781dd  ldstr    aImportEnd0Comp// "Import_END_{0}.compressedCustomizationF"...
0x781e2  ldc.i4.1
0x781e3  newarr   [mscorlib]System.Object
0x781e8  dup
0x781e9  ldc.i4.0
0x781ea  ldarg.0
0x781eb  stelem.ref
0x781ec  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x781f1  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x781f6  ldarg.0
0x781f7  ldfld    string Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::solutionXml
0x781fc  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x78201  brtrue.s loc_78210
0x78203  ldarg.0
0x78204  ldfld    string Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::customizationXml
0x78209  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7820e  brfalse.s loc_78221
0x78210  ldc.i4   0x80048060
0x78215  ldc.i4.0
0x78216  newarr   [mscorlib]System.Object
0x7821b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x78220  throw
0x78221  ret
```
