# Microsoft.Crm.Tools.ImportExportPublish.ImportXml::RunImport_0

- ea: `0x67880`
- end: `0x67988`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportXml::RunImport_0`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x67560`

## callees

- `0x66e00`
- `0x670f0`
- `0x67880`
- `0x67990`
- `0x67ea0`
- `0x680f0`
- `0x7b7e0`
- `0x7b860`
- `0x7b9c0`
- `0x7bbf0`

## string_xrefs

- `0x67882`: `ImportXml.RunImport()`
- `0x678f8`: `GetComponents`
- `0x67934`: `ModifyXml`

## pseudocode

```c

```

## disassembly

```asm
0x67880  ldnull
0x67881  stloc.0
0x67882  ldstr    aImportxmlRunim// "ImportXml.RunImport()"
0x67887  ldc.i4.1
0x67888  call     class [Microsoft.Crm.Core]Microsoft.Crm.CounterList [Microsoft.Crm.Core]Microsoft.Crm.CounterList::CreateAndStart(string, bool)
0x6788d  stloc.1
0x6788e  ldloc.1
0x6788f  ldc.i4.2
0x67890  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CounterList::set_LevelOfTrace(valuetype [System]System.Diagnostics.TraceLevel)
0x67895  ldloc.1
0x67896  ldstr    aLoadimportdocu// "LoadImportDocument"
0x6789b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Counter [Microsoft.Crm.Core]Microsoft.Crm.CounterList::InitStepCounter(string)
0x678a0  stloc.3
0x678a1  ldarg.0
0x678a2  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler Microsoft.Crm.Tools.ImportExportPublish.ImportXml::rootHandler
0x678a7  ldc.i4.0
0x678a8  ldc.i4.1
0x678a9  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::LoadAndValidateImportDocument(bool validate, [opt] bool hasSolutionManifest)
0x678ae  ldarg.0
0x678af  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler Microsoft.Crm.Tools.ImportExportPublish.ImportXml::rootHandler
0x678b4  callvirt instance bool Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::IsUpgradeRequired()
0x678b9  brfalse.s loc_678EB
0x678bb  ldarg.0
0x678bc  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler Microsoft.Crm.Tools.ImportExportPublish.ImportXml::rootHandler
0x678c1  callvirt instance bool Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::IsUpgradeValid()
0x678c6  brtrue.s loc_678D4
0x678c8  ldarg.0
0x678c9  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler Microsoft.Crm.Tools.ImportExportPublish.ImportXml::rootHandler
0x678ce  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmException Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::GenerateImportSolutionPackageNotValidException()
0x678d3  throw
0x678d4  ldarg.0
0x678d5  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportXml::RunFileUpgradeAndXSDValidationHandlers()
0x678da  ldarg.0
0x678db  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportXml::parameterXmlDoc
0x678e0  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x678e5  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x678ea  stloc.0
0x678eb  leave.s  loc_678F7
0x678ed  ldloc.3
0x678ee  brfalse.s loc_678F6
0x678f0  ldloc.3
0x678f1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x678f6  endfinally
0x678f7  ldloc.1
0x678f8  ldstr    aGetcomponents// "GetComponents"
0x678fd  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Counter [Microsoft.Crm.Core]Microsoft.Crm.CounterList::InitStepCounter(string)
0x67902  stloc.3
0x67903  ldarg.0
0x67904  ldarg.0
0x67905  ldc.i4.0
0x67906  ldc.i4.0
0x67907  call     instance string Microsoft.Crm.Tools.ImportExportPublish.ImportXml::GetComponentsList(bool checkMissingDependencies, bool includeUpgradeInfo)
0x6790c  stfld    string Microsoft.Crm.Tools.ImportExportPublish.ImportXml::parameterXml
0x67911  ldarg.0
0x67912  ldfld    bool Microsoft.Crm.Tools.ImportExportPublish.ImportXml::_skipProductUpdateDependencies
0x67917  brfalse.s loc_67925
0x67919  ldarg.0
0x6791a  ldarg.0
0x6791b  call     instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.MissingComponent[] Microsoft.Crm.Tools.ImportExportPublish.ImportXml::RetrieveMissingComponents()
0x67920  stfld    class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.MissingComponent[] Microsoft.Crm.Tools.ImportExportPublish.ImportXml::_missingComponents
0x67925  leave.s  loc_67931
0x67927  ldloc.3
0x67928  brfalse.s loc_67930
0x6792a  ldloc.3
0x6792b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x67930  endfinally
0x67931  ldnull
0x67932  stloc.2
0x67933  ldloc.1
0x67934  ldstr    aModifyxml// "ModifyXml"
0x67939  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Counter [Microsoft.Crm.Core]Microsoft.Crm.CounterList::InitStepCounter(string)
0x6793e  stloc.3
0x6793f  ldarg.0
0x67940  ldloc.0
0x67941  call     instance string[] Microsoft.Crm.Tools.ImportExportPublish.ImportXml::ModifyXml(class [System.Xml]System.Xml.XmlDocument doc2)
0x67946  stloc.2
0x67947  leave.s  loc_67953
0x67949  ldloc.3
0x6794a  brfalse.s loc_67952
0x6794c  ldloc.3
0x6794d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x67952  endfinally
0x67953  ldloc.1
0x67954  ldstr    aRunimport// "RunImport"
0x67959  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Counter [Microsoft.Crm.Core]Microsoft.Crm.CounterList::InitStepCounter(string)
0x6795e  stloc.3
0x6795f  ldarg.0
0x67960  ldloc.2
0x67961  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportXml::RunImport(string[] ImportEntities)
0x67966  leave.s  loc_67972
0x67968  ldloc.3
0x67969  brfalse.s loc_67971
0x6796b  ldloc.3
0x6796c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x67971  endfinally
0x67972  ldarg.0
0x67973  ldloc.2
0x67974  ldlen
0x67975  conv.i4
0x67976  stfld    int32 Microsoft.Crm.Tools.ImportExportPublish.ImportXml::_entityCount
0x6797b  leave.s  loc_67987
0x6797d  ldloc.1
0x6797e  brfalse.s loc_67986
0x67980  ldloc.1
0x67981  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x67986  endfinally
0x67987  ret
```
