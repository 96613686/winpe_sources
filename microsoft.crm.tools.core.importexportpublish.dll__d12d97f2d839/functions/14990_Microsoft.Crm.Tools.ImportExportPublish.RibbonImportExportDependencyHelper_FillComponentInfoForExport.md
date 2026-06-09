# Microsoft.Crm.Tools.ImportExportPublish.RibbonImportExportDependencyHelper::FillComponentInfoForExport

- ea: `0x14990`
- end: `0x14bd1`
- name: `Microsoft.Crm.Tools.ImportExportPublish.RibbonImportExportDependencyHelper::FillComponentInfoForExport`
- size: `577`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14990`
- `0x14d70`
- `0x14e10`
- `0x14e60`
- `0x395c0`

## string_xrefs

- `0x149d0`: `RibbonCommand`
- `0x149dd`: `command`
- `0x149f3`: `command`
- `0x14a1c`: `contextgroupxml`
- `0x14a32`: `contextgroupxml`
- `0x14a68`: `RibbonDiffXml`

## pseudocode

```c

```

## disassembly

```asm
0x14990  ldnull
0x14991  stloc.1
0x14992  ldarg.1
0x14993  callvirt instance int32 [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::get_ComponentType()
0x14998  stloc.s  4
0x1499a  ldloc.s  4
0x1499c  ldc.i4.s 0x30
0x1499e  sub
0x1499f  switch   loc_149C9, loc_14A08, loc_14A47, loc_14B3D, loc_14ADA, loc_14B3D, loc_14B3D, loc_14A73
0x149c4  br       loc_14B3D
0x149c9  ldarg.0
0x149ca  ldarg.1
0x149cb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::get_ObjectId()
0x149d0  ldstr    aRibboncommand// "RibbonCommand"
0x149d5  ldc.i4.2
0x149d6  newarr   [mscorlib]System.String
0x149db  dup
0x149dc  ldc.i4.0
0x149dd  ldstr    aCommand// "command"
0x149e2  stelem.ref
0x149e3  dup
0x149e4  ldc.i4.1
0x149e5  ldstr    aEntity// "entity"
0x149ea  stelem.ref
0x149eb  ldarg.2
0x149ec  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.Tools.ImportExportPublish.RibbonImportExportDependencyHelper::FetchRibbonEntity(valuetype [mscorlib]System.Guid objectId, string platformName, string[] columns, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x149f1  stloc.1
0x149f2  ldloc.1
0x149f3  ldstr    aCommand// "command"
0x149f8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x149fd  castclass [mscorlib]System.String
0x14a02  stloc.0
0x14a03  br       loc_14B5D
0x14a08  ldarg.0
0x14a09  ldarg.1
0x14a0a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::get_ObjectId()
0x14a0f  ldstr    aRibboncontextg// "RibbonContextGroup"
0x14a14  ldc.i4.2
0x14a15  newarr   [mscorlib]System.String
0x14a1a  dup
0x14a1b  ldc.i4.0
0x14a1c  ldstr    aContextgroupxm// "contextgroupxml"
0x14a21  stelem.ref
0x14a22  dup
0x14a23  ldc.i4.1
0x14a24  ldstr    aEntity// "entity"
0x14a29  stelem.ref
0x14a2a  ldarg.2
0x14a2b  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.Tools.ImportExportPublish.RibbonImportExportDependencyHelper::FetchRibbonEntity(valuetype [mscorlib]System.Guid objectId, string platformName, string[] columns, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x14a30  stloc.1
0x14a31  ldloc.1
0x14a32  ldstr    aContextgroupxm// "contextgroupxml"
0x14a37  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x14a3c  castclass [mscorlib]System.String
0x14a41  stloc.0
0x14a42  br       loc_14B5D
0x14a47  ldarg.0
0x14a48  ldarg.1
0x14a49  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::get_ObjectId()
0x14a4e  ldstr    aRibboncustomiz// "RibbonCustomization"
0x14a53  ldc.i4.1
0x14a54  newarr   [mscorlib]System.String
0x14a59  dup
0x14a5a  ldc.i4.0
0x14a5b  ldstr    aEntity// "entity"
0x14a60  stelem.ref
0x14a61  ldarg.2
0x14a62  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.Tools.ImportExportPublish.RibbonImportExportDependencyHelper::FetchRibbonEntity(valuetype [mscorlib]System.Guid objectId, string platformName, string[] columns, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x14a67  stloc.1
0x14a68  ldstr    aRibbondiffxml// "RibbonDiffXml"
0x14a6d  stloc.0
0x14a6e  br       loc_14B5D
0x14a73  ldarg.0
0x14a74  ldarg.1
0x14a75  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::get_ObjectId()
0x14a7a  ldstr    aRibbondiff// "RibbonDiff"
0x14a7f  ldc.i4.3
0x14a80  newarr   [mscorlib]System.String
0x14a85  dup
0x14a86  ldc.i4.0
0x14a87  ldstr    aDifftype// "difftype"
0x14a8c  stelem.ref
0x14a8d  dup
0x14a8e  ldc.i4.1
0x14a8f  ldstr    aDiffid// "diffid"
0x14a94  stelem.ref
0x14a95  dup
0x14a96  ldc.i4.2
0x14a97  ldstr    aEntity// "entity"
0x14a9c  stelem.ref
0x14a9d  ldarg.2
0x14a9e  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.Tools.ImportExportPublish.RibbonImportExportDependencyHelper::FetchRibbonEntity(valuetype [mscorlib]System.Guid objectId, string platformName, string[] columns, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x14aa3  stloc.1
0x14aa4  ldarg.0
0x14aa5  ldloc.1
0x14aa6  ldstr    aDifftype// "difftype"
0x14aab  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x14ab0  unbox.any [mscorlib]System.Int32
0x14ab5  call     instance string Microsoft.Crm.Tools.ImportExportPublish.RibbonImportExportDependencyHelper::GetDiffNodeNameFromType(int32 diffType)
0x14aba  ldstr    asc_CD6F2// ":"
0x14abf  ldloc.1
0x14ac0  ldstr    aDiffid// "diffid"
0x14ac5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x14aca  castclass [mscorlib]System.String
0x14acf  call     string [mscorlib]System.String::Concat(string, string, string)
0x14ad4  stloc.0
0x14ad5  br       loc_14B5D
0x14ada  ldarg.0
0x14adb  ldarg.1
0x14adc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::get_ObjectId()
0x14ae1  ldstr    aRibbonrule// "RibbonRule"
0x14ae6  ldc.i4.3
0x14ae7  newarr   [mscorlib]System.String
0x14aec  dup
0x14aed  ldc.i4.0
0x14aee  ldstr    aRuletype// "ruletype"
0x14af3  stelem.ref
0x14af4  dup
0x14af5  ldc.i4.1
0x14af6  ldstr    aRuleid// "ruleid"
0x14afb  stelem.ref
0x14afc  dup
0x14afd  ldc.i4.2
0x14afe  ldstr    aEntity// "entity"
0x14b03  stelem.ref
0x14b04  ldarg.2
0x14b05  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.Tools.ImportExportPublish.RibbonImportExportDependencyHelper::FetchRibbonEntity(valuetype [mscorlib]System.Guid objectId, string platformName, string[] columns, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x14b0a  stloc.1
0x14b0b  ldloc.1
0x14b0c  ldstr    aRuletype// "ruletype"
0x14b11  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x14b16  unbox.any [mscorlib]System.Int32
0x14b1b  call     string Microsoft.Crm.Tools.ImportExportPublish.RibbonImportExportDependencyHelper::GetRuleNodeNameFromType(int32 ruleType)
0x14b20  ldstr    asc_CD6F2// ":"
0x14b25  ldloc.1
0x14b26  ldstr    aRuleid// "ruleid"
0x14b2b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x14b30  castclass [mscorlib]System.String
0x14b35  call     string [mscorlib]System.String::Concat(string, string, string)
0x14b3a  stloc.0
0x14b3b  br.s     loc_14B5D
0x14b3d  ldc.i4.0
0x14b3e  ldstr    aNotExpectingTh// "Not expecting that any {0} entities are"...
0x14b43  ldc.i4.1
0x14b44  newarr   [mscorlib]System.Object
0x14b49  dup
0x14b4a  ldc.i4.0
0x14b4b  ldarg.1
0x14b4c  callvirt instance int32 [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::get_ComponentType()
0x14b51  call     string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.SolutionComponentTypeMap::RetrievePlatformName(int32)
0x14b56  stelem.ref
0x14b57  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string, object[])
0x14b5c  ret
0x14b5d  ldloc.1
0x14b5e  ldstr    aEntity// "entity"
0x14b63  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x14b68  castclass [mscorlib]System.String
0x14b6d  dup
0x14b6e  brtrue.s loc_14B76
0x14b70  pop
0x14b71  ldsfld   string [mscorlib]System.String::Empty
0x14b76  stloc.2
0x14b77  ldarg.1
0x14b78  ldloc.2
0x14b79  ldstr    asc_CD6F2// ":"
0x14b7e  ldloc.0
0x14b7f  call     string [mscorlib]System.String::Concat(string, string, string)
0x14b84  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::set_SchemaName(string)
0x14b89  ldarg.1
0x14b8a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x14b8f  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::set_ObjectId(valuetype [mscorlib]System.Guid)
0x14b94  ldarg.1
0x14b95  ldloc.1
0x14b96  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x14b9b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x14ba0  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::set_ParentSchemaName(string)
0x14ba5  ldarg.2
0x14ba6  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x14bab  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_LanguageCode()
0x14bb0  stloc.3
0x14bb1  ldarg.1
0x14bb2  ldloc.3
0x14bb3  ldloc.1
0x14bb4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x14bb9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedName()
0x14bbe  ldarg.2
0x14bbf  call     string Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::GetLabel(int32 languageCode, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection labels, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x14bc4  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::set_ParentDisplayName(string)
0x14bc9  ldarg.1
0x14bca  ldc.i4.1
0x14bcb  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::set_Resolved(bool)
0x14bd0  ret
```
