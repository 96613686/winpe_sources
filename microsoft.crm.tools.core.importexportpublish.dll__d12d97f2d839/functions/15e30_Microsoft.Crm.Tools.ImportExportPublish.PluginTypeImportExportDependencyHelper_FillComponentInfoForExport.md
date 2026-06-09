# Microsoft.Crm.Tools.ImportExportPublish.PluginTypeImportExportDependencyHelper::FillComponentInfoForExport

- ea: `0x15e30`
- end: `0x15f7c`
- name: `Microsoft.Crm.Tools.ImportExportPublish.PluginTypeImportExportDependencyHelper::FillComponentInfoForExport`
- size: `332`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## string_xrefs

- `0x15ea4`: `publickeytoken`
- `0x15f19`: `publickeytoken`
- `0x15e30`: `PluginType`
- `0x15e42`: `PluginType`
- `0x15eaf`: `PluginType`

## pseudocode

```c

```

## disassembly

```asm
0x15e30  ldstr    aPlugintype// "PluginType"
0x15e35  ldarg.2
0x15e36  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x15e3b  ldarg.1
0x15e3c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::get_ObjectId()
0x15e41  stloc.0
0x15e42  ldstr    aPlugintype// "PluginType"
0x15e47  ldarg.2
0x15e48  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x15e4d  stloc.1
0x15e4e  ldloc.1
0x15e4f  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x15e54  ldstr    aName// "name"
0x15e59  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x15e5e  ldloc.1
0x15e5f  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x15e64  ldstr    aTypename// "typename"
0x15e69  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x15e6e  ldloc.1
0x15e6f  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x15e74  ldstr    aAssemblyname// "assemblyname"
0x15e79  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x15e7e  ldloc.1
0x15e7f  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x15e84  ldstr    aVersion// "version"
0x15e89  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x15e8e  ldloc.1
0x15e8f  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x15e94  ldstr    aCulture// "culture"
0x15e99  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x15e9e  ldloc.1
0x15e9f  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x15ea4  ldstr    aPublickeytoken// "publickeytoken"
0x15ea9  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x15eae  ldloc.0
0x15eaf  ldstr    aPlugintype// "PluginType"
0x15eb4  ldarg.2
0x15eb5  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x15eba  ldloc.1
0x15ebb  ldarg.2
0x15ebc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x15ec1  dup
0x15ec2  ldstr    aName// "name"
0x15ec7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x15ecc  isinst   [mscorlib]System.String
0x15ed1  stloc.2
0x15ed2  dup
0x15ed3  ldstr    aTypename// "typename"
0x15ed8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x15edd  isinst   [mscorlib]System.String
0x15ee2  stloc.3
0x15ee3  dup
0x15ee4  ldstr    aAssemblyname// "assemblyname"
0x15ee9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x15eee  isinst   [mscorlib]System.String
0x15ef3  stloc.s  4
0x15ef5  dup
0x15ef6  ldstr    aVersion// "version"
0x15efb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x15f00  isinst   [mscorlib]System.String
0x15f05  stloc.s  5
0x15f07  dup
0x15f08  ldstr    aCulture// "culture"
0x15f0d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x15f12  isinst   [mscorlib]System.String
0x15f17  stloc.s  6
0x15f19  ldstr    aPublickeytoken// "publickeytoken"
0x15f1e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x15f23  isinst   [mscorlib]System.String
0x15f28  stloc.s  7
0x15f2a  ldloc.s  4
0x15f2c  ldloc.s  5
0x15f2e  ldloc.s  6
0x15f30  ldloc.s  7
0x15f32  newobj   instance void [Microsoft.Crm]Microsoft.Crm.CrmPluginAssemblyMetadata::.ctor(string, string, string, string)
0x15f37  stloc.s  8
0x15f39  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15f3e  ldstr    a01_0// "{0}, {1}"
0x15f43  ldc.i4.2
0x15f44  newarr   [mscorlib]System.Object
0x15f49  dup
0x15f4a  ldc.i4.0
0x15f4b  ldloc.3
0x15f4c  stelem.ref
0x15f4d  dup
0x15f4e  ldc.i4.1
0x15f4f  ldloc.s  8
0x15f51  callvirt instance string [mscorlib]System.Object::ToString()
0x15f56  stelem.ref
0x15f57  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x15f5c  stloc.s  9
0x15f5e  ldarg.1
0x15f5f  ldloc.2
0x15f60  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::set_DisplayName(string)
0x15f65  ldarg.1
0x15f66  ldloc.s  9
0x15f68  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::set_SchemaName(string)
0x15f6d  ldarg.1
0x15f6e  ldloc.0
0x15f6f  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::set_ObjectId(valuetype [mscorlib]System.Guid)
0x15f74  ldarg.1
0x15f75  ldc.i4.1
0x15f76  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::set_Resolved(bool)
0x15f7b  ret
```
