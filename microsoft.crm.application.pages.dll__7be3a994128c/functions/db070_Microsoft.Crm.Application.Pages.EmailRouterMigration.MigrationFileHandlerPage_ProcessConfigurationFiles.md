# Microsoft.Crm.Application.Pages.EmailRouterMigration.MigrationFileHandlerPage::ProcessConfigurationFiles

- ea: `0xdb070`
- end: `0xdb2a6`
- name: `Microsoft.Crm.Application.Pages.EmailRouterMigration.MigrationFileHandlerPage::ProcessConfigurationFiles`
- size: `566`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0xdad80`

## callees

- `0x70870`
- `0x70880`
- `0x70890`
- `0x70a60`
- `0x70c10`
- `0x70ff0`
- `0xdb070`
- `0xdb3f0`

## string_xrefs

- `0xdb1e3`: `Microsoft.Crm.Tools.EmailAgent.SystemState.xml`
- `0xdb201`: `EncryptionKey.xml`
- `0xdb1b6`: `Microsoft.Crm.Tools.EmailAgent.xml`
- `0xdb189`: `Attempt made to migrate a file with size {0}`
- `0xdb27e`: `Email Router Migration : Attempt to process 0 files.`

## pseudocode

```c

```

## disassembly

```asm
0xdb070  ldarg.0
0xdb071  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xdb076  callvirt instance class [System.Web]System.Web.HttpFileCollection [System.Web]System.Web.HttpRequest::get_Files()
0xdb07b  stloc.0
0xdb07c  ldc.i4   0x2000000
0xdb081  stloc.1
0xdb082  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0xdb087  ldstr    aEmailroutermig_1// "EmailRouterMigrationMaxAllowedFileSizeI"...
0xdb08c  ldc.i4.0
0xdb08d  callvirt T0x2B00000C
0xdb092  stloc.2
0xdb093  ldloca.s 2
0xdb095  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xdb09a  brfalse.s loc_DB0B0
0xdb09c  ldloca.s 2
0xdb09e  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0xdb0a3  ldc.i4   0x400
0xdb0a8  mul
0xdb0a9  ldc.i4   0x400
0xdb0ae  mul
0xdb0af  stloc.1
0xdb0b0  ldarg.0
0xdb0b1  newobj   instance void Microsoft.Crm.Web.Tools.EmailRouterMigration.EmailRouterFileProcessor::.ctor()
0xdb0b6  stfld    class Microsoft.Crm.Web.Tools.EmailRouterMigration.EmailRouterFileProcessor Microsoft.Crm.Application.Pages.EmailRouterMigration.MigrationFileHandlerPage::routerFileProcessor
0xdb0bb  ldloc.0
0xdb0bc  brfalse  loc_DB276
0xdb0c1  ldloc.0
0xdb0c2  callvirt instance int32 [System]System.Collections.Specialized.NameObjectCollectionBase::get_Count()
0xdb0c7  ldc.i4.0
0xdb0c8  ble      loc_DB276
0xdb0cd  ldc.i4.0
0xdb0ce  stloc.3
0xdb0cf  ldnull
0xdb0d0  stloc.s  4
0xdb0d2  ldc.i4.0
0xdb0d3  stloc.s  5
0xdb0d5  br       loc_DB267
0xdb0da  ldloc.s  5
0xdb0dc  ldc.i4.3
0xdb0dd  rem
0xdb0de  brtrue.s loc_DB0FC
0xdb0e0  ldarg.0
0xdb0e1  ldfld    class Microsoft.Crm.Web.Tools.EmailRouterMigration.EmailRouterFileProcessor Microsoft.Crm.Application.Pages.EmailRouterMigration.MigrationFileHandlerPage::routerFileProcessor
0xdb0e6  dup
0xdb0e7  callvirt instance int32 Microsoft.Crm.Web.Tools.EmailRouterMigration.EmailRouterFileProcessor::get_CurrentRouterNumber()
0xdb0ec  stloc.s  0xB
0xdb0ee  ldloc.s  0xB
0xdb0f0  ldc.i4.1
0xdb0f1  add
0xdb0f2  callvirt instance void Microsoft.Crm.Web.Tools.EmailRouterMigration.EmailRouterFileProcessor::set_CurrentRouterNumber(int32 value)
0xdb0f7  ldc.i4.0
0xdb0f8  stloc.3
0xdb0f9  ldnull
0xdb0fa  stloc.s  4
0xdb0fc  ldloc.0
0xdb0fd  ldloc.s  5
0xdb0ff  callvirt instance class [System.Web]System.Web.HttpPostedFile [System.Web]System.Web.HttpFileCollection::get_Item(int32)
0xdb104  stloc.s  6
0xdb106  ldloc.s  6
0xdb108  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpPostedFile::get_InputStream()
0xdb10d  stloc.s  7
0xdb10f  ldloc.s  6
0xdb111  callvirt instance string [System.Web]System.Web.HttpPostedFile::get_FileName()
0xdb116  stloc.s  8
0xdb118  ldloc.s  8
0xdb11a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xdb11f  brtrue   loc_DB261
0xdb124  ldloc.s  8
0xdb126  call     string [mscorlib]System.IO.Path::GetFileName(string)
0xdb12b  stloc.s  9
0xdb12d  ldloc.s  6
0xdb12f  callvirt instance int32 [System.Web]System.Web.HttpPostedFile::get_ContentLength()
0xdb134  stloc.s  0xA
0xdb136  ldloc.s  0xA
0xdb138  brtrue.s loc_DB174
0xdb13a  ldnull
0xdb13b  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0xdb140  ldc.i4.s 0x14
0xdb142  ldstr    aEmailRouterMig// "Email Router Migration. File Content Le"...
0xdb147  ldc.i4.1
0xdb148  newarr   [mscorlib]System.Object
0xdb14d  dup
0xdb14e  ldc.i4.0
0xdb14f  ldloc.s  9
0xdb151  stelem.ref
0xdb152  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xdb157  ldloc.s  9
0xdb159  ldarg.0
0xdb15a  ldfld    class Microsoft.Crm.Web.Tools.EmailRouterMigration.EmailRouterFileProcessor Microsoft.Crm.Application.Pages.EmailRouterMigration.MigrationFileHandlerPage::routerFileProcessor
0xdb15f  callvirt instance int32 Microsoft.Crm.Web.Tools.EmailRouterMigration.EmailRouterFileProcessor::get_CurrentRouterNumber()
0xdb164  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.EmailRouterMigration.EmailRouterMigrationUtility::ConstructErrorMessage(string, int32)
0xdb169  ldc.i4   0x8005F032
0xdb16e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xdb173  throw
0xdb174  ldloc.s  0xA
0xdb176  ldc.i4.0
0xdb177  blt.s    loc_DB17E
0xdb179  ldloc.s  0xA
0xdb17b  ldloc.1
0xdb17c  ble.s    loc_DB1B4
0xdb17e  ldnull
0xdb17f  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0xdb184  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0xdb189  ldstr    aAttemptMadeToM// "Attempt made to migrate a file with siz"...
0xdb18e  ldc.i4.1
0xdb18f  newarr   [mscorlib]System.Object
0xdb194  dup
0xdb195  ldc.i4.0
0xdb196  ldloc.s  0xA
0xdb198  box      [mscorlib]System.Int32
0xdb19d  stelem.ref
0xdb19e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xdb1a3  ldc.i4   0x8005F031
0xdb1a8  ldc.i4.0
0xdb1a9  newarr   [mscorlib]System.Object
0xdb1ae  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0xdb1b3  throw
0xdb1b4  ldloc.s  9
0xdb1b6  ldstr    aMicrosoftCrmTo_0// "Microsoft.Crm.Tools.EmailAgent.xml"
0xdb1bb  ldc.i4.5
0xdb1bc  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xdb1c1  brfalse.s loc_DB1E1
0xdb1c3  ldloc.3
0xdb1c4  brfalse.s loc_DB1D8
0xdb1c6  ldarg.0
0xdb1c7  ldfld    class Microsoft.Crm.Web.Tools.EmailRouterMigration.EmailRouterFileProcessor Microsoft.Crm.Application.Pages.EmailRouterMigration.MigrationFileHandlerPage::routerFileProcessor
0xdb1cc  ldloc.s  7
0xdb1ce  callvirt instance void Microsoft.Crm.Web.Tools.EmailRouterMigration.EmailRouterFileProcessor::ProcessAgentFile(class [mscorlib]System.IO.Stream stream)
0xdb1d3  br       loc_DB261
0xdb1d8  ldloc.s  7
0xdb1da  stloc.s  4
0xdb1dc  br       loc_DB261
0xdb1e1  ldloc.s  9
0xdb1e3  ldstr    aMicrosoftCrmTo// "Microsoft.Crm.Tools.EmailAgent.SystemSt"...
0xdb1e8  ldc.i4.5
0xdb1e9  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xdb1ee  brfalse.s loc_DB1FF
0xdb1f0  ldarg.0
0xdb1f1  ldfld    class Microsoft.Crm.Web.Tools.EmailRouterMigration.EmailRouterFileProcessor Microsoft.Crm.Application.Pages.EmailRouterMigration.MigrationFileHandlerPage::routerFileProcessor
0xdb1f6  ldloc.s  7
0xdb1f8  callvirt instance void Microsoft.Crm.Web.Tools.EmailRouterMigration.EmailRouterFileProcessor::ProcessSystemStateFile(class [mscorlib]System.IO.Stream stream)
0xdb1fd  br.s     loc_DB261
0xdb1ff  ldloc.s  9
0xdb201  ldstr    aEncryptionkeyX// "EncryptionKey.xml"
0xdb206  ldc.i4.5
0xdb207  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xdb20c  brfalse.s loc_DB233
0xdb20e  ldarg.0
0xdb20f  ldfld    class Microsoft.Crm.Web.Tools.EmailRouterMigration.EmailRouterFileProcessor Microsoft.Crm.Application.Pages.EmailRouterMigration.MigrationFileHandlerPage::routerFileProcessor
0xdb214  ldloc.s  7
0xdb216  callvirt instance void Microsoft.Crm.Web.Tools.EmailRouterMigration.EmailRouterFileProcessor::ProcessEncryptionFile(class [mscorlib]System.IO.Stream stream)
0xdb21b  ldc.i4.1
0xdb21c  stloc.3
0xdb21d  ldloc.s  4
0xdb21f  brfalse.s loc_DB261
0xdb221  ldarg.0
0xdb222  ldfld    class Microsoft.Crm.Web.Tools.EmailRouterMigration.EmailRouterFileProcessor Microsoft.Crm.Application.Pages.EmailRouterMigration.MigrationFileHandlerPage::routerFileProcessor
0xdb227  ldloc.s  4
0xdb229  callvirt instance void Microsoft.Crm.Web.Tools.EmailRouterMigration.EmailRouterFileProcessor::ProcessAgentFile(class [mscorlib]System.IO.Stream stream)
0xdb22e  ldnull
0xdb22f  stloc.s  4
0xdb231  br.s     loc_DB261
0xdb233  ldnull
0xdb234  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0xdb239  ldc.i4.s 0x14
0xdb23b  ldstr    aEmailRouterMig_0// "Email Router Migration : File Not suppo"...
0xdb240  ldc.i4.1
0xdb241  newarr   [mscorlib]System.Object
0xdb246  dup
0xdb247  ldc.i4.0
0xdb248  ldloc.s  9
0xdb24a  stelem.ref
0xdb24b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xdb250  ldc.i4   0x80040216
0xdb255  ldc.i4.0
0xdb256  newarr   [mscorlib]System.Object
0xdb25b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0xdb260  throw
0xdb261  ldloc.s  5
0xdb263  ldc.i4.1
0xdb264  add
0xdb265  stloc.s  5
0xdb267  ldloc.s  5
0xdb269  ldloc.0
0xdb26a  callvirt instance int32 [System]System.Collections.Specialized.NameObjectCollectionBase::get_Count()
0xdb26f  blt      loc_DB0DA
0xdb274  br.s     loc_DB29F
0xdb276  ldnull
0xdb277  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0xdb27c  ldc.i4.s 0x14
0xdb27e  ldstr    aEmailRouterMig_1// "Email Router Migration : Attempt to pro"...
0xdb283  ldc.i4.0
0xdb284  newarr   [mscorlib]System.Object
0xdb289  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xdb28e  ldc.i4   0x80040216
0xdb293  ldc.i4.0
0xdb294  newarr   [mscorlib]System.Object
0xdb299  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0xdb29e  throw
0xdb29f  ldarg.0
0xdb2a0  call     instance void Microsoft.Crm.Application.Pages.EmailRouterMigration.MigrationFileHandlerPage::GenerateResponseForClient()
0xdb2a5  ret
```
