# Microsoft.Crm.Tools.ImportExportPublish.SdkMessageProcessingStepExportHandler::AddPluginTypeNameAndId

- ea: `0x85f50`
- end: `0x8608e`
- name: `Microsoft.Crm.Tools.ImportExportPublish.SdkMessageProcessingStepExportHandler::AddPluginTypeNameAndId`
- size: `318`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x85a60`

## string_xrefs

- `0x85ff3`: `publickeytoken`
- `0x8605f`: `PluginTypeId`
- `0x85f50`: `PluginType`
- `0x85f71`: `PluginType`
- `0x85f8e`: `PluginType`
- `0x85f61`: `plugintypeid`
- `0x8603a`: `PluginTypeName`

## pseudocode

```c

```

## disassembly

```asm
0x85f50  ldstr    aPlugintype// "PluginType"
0x85f55  ldarg.0
0x85f56  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SdkMessageProcessingStepExportHandler::_context
0x85f5b  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x85f60  ldarg.1
0x85f61  ldstr    aPlugintypeid_0// "plugintypeid"
0x85f66  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x85f6b  unbox.any [mscorlib]System.Guid
0x85f70  stloc.0
0x85f71  ldstr    aPlugintype// "PluginType"
0x85f76  ldarg.0
0x85f77  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SdkMessageProcessingStepExportHandler::_context
0x85f7c  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x85f81  stloc.1
0x85f82  ldloc.1
0x85f83  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x85f88  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddAllColumns()
0x85f8d  ldloc.0
0x85f8e  ldstr    aPlugintype// "PluginType"
0x85f93  ldarg.0
0x85f94  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SdkMessageProcessingStepExportHandler::_context
0x85f99  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x85f9e  stloc.2
0x85f9f  ldloc.2
0x85fa0  ldloc.1
0x85fa1  ldarg.0
0x85fa2  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SdkMessageProcessingStepExportHandler::_context
0x85fa7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x85fac  dup
0x85fad  ldstr    aTypename// "typename"
0x85fb2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x85fb7  isinst   [mscorlib]System.String
0x85fbc  stloc.3
0x85fbd  dup
0x85fbe  ldstr    aAssemblyname// "assemblyname"
0x85fc3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x85fc8  isinst   [mscorlib]System.String
0x85fcd  stloc.s  4
0x85fcf  dup
0x85fd0  ldstr    aVersion// "version"
0x85fd5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x85fda  isinst   [mscorlib]System.String
0x85fdf  stloc.s  5
0x85fe1  dup
0x85fe2  ldstr    aCulture// "culture"
0x85fe7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x85fec  isinst   [mscorlib]System.String
0x85ff1  stloc.s  6
0x85ff3  ldstr    aPublickeytoken// "publickeytoken"
0x85ff8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x85ffd  isinst   [mscorlib]System.String
0x86002  stloc.s  7
0x86004  ldloc.s  4
0x86006  ldloc.s  5
0x86008  ldloc.s  6
0x8600a  ldloc.s  7
0x8600c  newobj   instance void [Microsoft.Crm]Microsoft.Crm.CrmPluginAssemblyMetadata::.ctor(string, string, string, string)
0x86011  callvirt instance string [mscorlib]System.Object::ToString()
0x86016  stloc.s  8
0x86018  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8601d  ldstr    a01_0// "{0}, {1}"
0x86022  ldc.i4.2
0x86023  newarr   [mscorlib]System.Object
0x86028  dup
0x86029  ldc.i4.0
0x8602a  ldloc.3
0x8602b  stelem.ref
0x8602c  dup
0x8602d  ldc.i4.1
0x8602e  ldloc.s  8
0x86030  stelem.ref
0x86031  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x86036  stloc.s  9
0x86038  ldarg.2
0x86039  ldc.i4.1
0x8603a  ldstr    aPlugintypename// "PluginTypeName"
0x8603f  ldsfld   string [mscorlib]System.String::Empty
0x86044  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::CreateNode(valuetype [System.Xml]System.Xml.XmlNodeType, string, string)
0x86049  stloc.s  0xA
0x8604b  ldloc.s  0xA
0x8604d  ldloc.s  9
0x8604f  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x86054  ldarg.3
0x86055  ldloc.s  0xA
0x86057  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x8605c  pop
0x8605d  ldarg.2
0x8605e  ldc.i4.1
0x8605f  ldstr    aPlugintypeid// "PluginTypeId"
0x86064  ldsfld   string [mscorlib]System.String::Empty
0x86069  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::CreateNode(valuetype [System.Xml]System.Xml.XmlNodeType, string, string)
0x8606e  stloc.s  0xB
0x86070  ldloc.s  0xB
0x86072  ldloca.s 0
0x86074  constrained. [mscorlib]System.Guid
0x8607a  callvirt instance string [mscorlib]System.Object::ToString()
0x8607f  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x86084  ldarg.3
0x86085  ldloc.s  0xB
0x86087  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x8608c  pop
0x8608d  ret
```
