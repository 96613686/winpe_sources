# Microsoft.Crm.Tools.ImportExportPublish.PluginAssemblyImportExportDependencyHelper::FillComponentInfoForExport

- ea: `0x15ab0`
- end: `0x15b96`
- name: `Microsoft.Crm.Tools.ImportExportPublish.PluginAssemblyImportExportDependencyHelper::FillComponentInfoForExport`
- size: `230`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## string_xrefs

- `0x15ab0`: `PluginAssembly`
- `0x15ac2`: `PluginAssembly`
- `0x15b0f`: `PluginAssembly`
- `0x15b04`: `publickeytoken`
- `0x15b55`: `publickeytoken`

## pseudocode

```c

```

## disassembly

```asm
0x15ab0  ldstr    aPluginassembly_0// "PluginAssembly"
0x15ab5  ldarg.2
0x15ab6  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x15abb  ldarg.1
0x15abc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::get_ObjectId()
0x15ac1  stloc.0
0x15ac2  ldstr    aPluginassembly_0// "PluginAssembly"
0x15ac7  ldarg.2
0x15ac8  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x15acd  stloc.1
0x15ace  ldloc.1
0x15acf  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x15ad4  ldstr    aName// "name"
0x15ad9  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x15ade  ldloc.1
0x15adf  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x15ae4  ldstr    aVersion// "version"
0x15ae9  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x15aee  ldloc.1
0x15aef  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x15af4  ldstr    aCulture// "culture"
0x15af9  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x15afe  ldloc.1
0x15aff  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x15b04  ldstr    aPublickeytoken// "publickeytoken"
0x15b09  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x15b0e  ldloc.0
0x15b0f  ldstr    aPluginassembly_0// "PluginAssembly"
0x15b14  ldarg.2
0x15b15  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x15b1a  ldloc.1
0x15b1b  ldarg.2
0x15b1c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x15b21  dup
0x15b22  ldstr    aName// "name"
0x15b27  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x15b2c  isinst   [mscorlib]System.String
0x15b31  stloc.2
0x15b32  dup
0x15b33  ldstr    aVersion// "version"
0x15b38  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x15b3d  isinst   [mscorlib]System.String
0x15b42  stloc.3
0x15b43  dup
0x15b44  ldstr    aCulture// "culture"
0x15b49  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x15b4e  isinst   [mscorlib]System.String
0x15b53  stloc.s  4
0x15b55  ldstr    aPublickeytoken// "publickeytoken"
0x15b5a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x15b5f  isinst   [mscorlib]System.String
0x15b64  stloc.s  5
0x15b66  ldloc.2
0x15b67  ldloc.3
0x15b68  ldloc.s  4
0x15b6a  ldloc.s  5
0x15b6c  newobj   instance void [Microsoft.Crm]Microsoft.Crm.CrmPluginAssemblyMetadata::.ctor(string, string, string, string)
0x15b71  stloc.s  6
0x15b73  ldarg.1
0x15b74  ldloc.2
0x15b75  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::set_DisplayName(string)
0x15b7a  ldarg.1
0x15b7b  ldloc.s  6
0x15b7d  callvirt instance string [mscorlib]System.Object::ToString()
0x15b82  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::set_SchemaName(string)
0x15b87  ldarg.1
0x15b88  ldloc.0
0x15b89  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::set_ObjectId(valuetype [mscorlib]System.Guid)
0x15b8e  ldarg.1
0x15b8f  ldc.i4.1
0x15b90  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::set_Resolved(bool)
0x15b95  ret
```
