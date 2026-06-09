# Microsoft.Crm.Tools.ImportExportPublish.ImportXml::RunFileUpgradeAndXSDValidationHandlers

- ea: `0x67ea0`
- end: `0x67f63`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportXml::RunFileUpgradeAndXSDValidationHandlers`
- size: `195`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x66e00`
- `0x67880`

## callees

- `0x67ea0`
- `0x68120`
- `0x7a4b0`
- `0x7bc30`
- `0x7e230`
- `0x7e560`
- `0x7e760`

## string_xrefs

- `0x67eb3`: `<importexportxml progress="0.0">`
- `0x67ef8`: `</importexportxml>`
- `0x67f26`: `importexportxml/solutionManifests/solutionManifest/UniqueName`

## pseudocode

```c

```

## disassembly

```asm
0x67ea0  ldarg.0
0x67ea1  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler Microsoft.Crm.Tools.ImportExportPublish.ImportXml::rootHandler
0x67ea6  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class UpgradePath> Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::RetrieveListOfUpgradeHandlers()
0x67eab  stloc.0
0x67eac  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x67eb1  stloc.1
0x67eb2  ldloc.1
0x67eb3  ldstr    aImportexportxm_186// "<importexportxml progress=\"0.0\">"
0x67eb8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x67ebd  pop
0x67ebe  ldloc.1
0x67ebf  ldarg.0
0x67ec0  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler Microsoft.Crm.Tools.ImportExportPublish.ImportXml::rootHandler
0x67ec5  ldc.i4.0
0x67ec6  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::GetSolutionManifests(bool checkMissingDependencies)
0x67ecb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x67ed0  pop
0x67ed1  ldloc.1
0x67ed2  ldarg.0
0x67ed3  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler Microsoft.Crm.Tools.ImportExportPublish.ImportXml::rootHandler
0x67ed8  ldc.i4.1
0x67ed9  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::GetUpgradeHandlerInfo(bool withImportFlags)
0x67ede  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x67ee3  pop
0x67ee4  ldloc.1
0x67ee5  ldarg.0
0x67ee6  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler Microsoft.Crm.Tools.ImportExportPublish.ImportXml::rootHandler
0x67eeb  ldc.i4.1
0x67eec  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::GetXsdValidationHandlerInfo(bool withImportFlags)
0x67ef1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x67ef6  pop
0x67ef7  ldloc.1
0x67ef8  ldstr    aImportexportxm_187// "</importexportxml>"
0x67efd  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x67f02  pop
0x67f03  ldarg.0
0x67f04  ldloc.1
0x67f05  callvirt instance string [mscorlib]System.Object::ToString()
0x67f0a  stfld    string Microsoft.Crm.Tools.ImportExportPublish.ImportXml::parameterXml
0x67f0f  ldarg.0
0x67f10  ldarg.0
0x67f11  ldfld    string Microsoft.Crm.Tools.ImportExportPublish.ImportXml::parameterXml
0x67f16  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x67f1b  stfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportXml::parameterXmlDoc
0x67f20  ldarg.0
0x67f21  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportXml::parameterXmlDoc
0x67f26  ldstr    aImportexportxm_188// "importexportxml/solutionManifests/solut"...
0x67f2b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x67f30  stloc.2
0x67f31  ldloc.2
0x67f32  brfalse.s loc_67F40
0x67f34  ldarg.0
0x67f35  ldloc.2
0x67f36  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x67f3b  stfld    string Microsoft.Crm.Tools.ImportExportPublish.ImportXml::_solutionName
0x67f40  ldarg.0
0x67f41  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler Microsoft.Crm.Tools.ImportExportPublish.ImportXml::rootHandler
0x67f46  ldloc.0
0x67f47  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::RunFileUpgradeAndXSDValidationHandlers(class [mscorlib]System.Collections.Generic.List`1<class UpgradePath> upgradeHandlers)
0x67f4c  leave.s  loc_67F62
0x67f4e  pop
0x67f4f  ldarg.0
0x67f50  ldarg.0
0x67f51  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportXml::parameterXmlDoc
0x67f56  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x67f5b  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportXml::CreateImportJobEntry(string data)
0x67f60  rethrow
0x67f62  ret
```
