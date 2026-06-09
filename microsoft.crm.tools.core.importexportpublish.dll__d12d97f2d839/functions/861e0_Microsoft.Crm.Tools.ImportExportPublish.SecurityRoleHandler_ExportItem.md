# Microsoft.Crm.Tools.ImportExportPublish.SecurityRoleHandler::ExportItem

- ea: `0x861e0`
- end: `0x86469`
- name: `Microsoft.Crm.Tools.ImportExportPublish.SecurityRoleHandler::ExportItem`
- size: `649`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x3b380`
- `0x3b3c0`
- `0x861e0`
- `0x86470`

## string_xrefs

- `0x862f1`: `roletemplateid`
- `0x86281`: `ImportExportXml/SolutionManifest/RootComponents/RootComponent[@type='{0}' and @id='{1}']`
- `0x86359`: `ImportExportXml/SolutionManifest/RootComponents/RootComponent[@type='{0}' and @id='{1}']`

## pseudocode

```c

```

## disassembly

```asm
0x861e0  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.RoleService::.ctor()
0x861e5  stloc.0
0x861e6  ldloca.s 1
0x861e8  ldarg.0
0x861e9  ldfld    string Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::entityName
0x861ee  call     instance void [mscorlib]System.Guid::.ctor(string)
0x861f3  ldstr    aRole// "Role"
0x861f8  ldarg.0
0x861f9  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SecurityRoleHandler::exc
0x861fe  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x86203  ldloc.1
0x86204  ldstr    aRole// "Role"
0x86209  ldarg.0
0x8620a  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SecurityRoleHandler::exc
0x8620f  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x86214  stloc.2
0x86215  ldloc.2
0x86216  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_EntityMetadata()
0x8621b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x86220  ldarg.0
0x86221  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SecurityRoleHandler::exc
0x86226  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x8622b  stloc.3
0x8622c  ldloc.3
0x8622d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x86232  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddAllColumns()
0x86237  ldloc.2
0x86238  ldloc.3
0x86239  ldarg.0
0x8623a  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SecurityRoleHandler::exc
0x8623f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x86244  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Role
0x86249  stloc.s  4
0x8624b  ldloc.0
0x8624c  ldloc.1
0x8624d  ldarg.0
0x8624e  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SecurityRoleHandler::exc
0x86253  callvirt instance bool class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.RoleServiceInternal`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ProvisioningOff>::IsSystemAdministratorRole(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x86258  brtrue.s loc_86269
0x8625a  ldloc.0
0x8625b  ldloc.1
0x8625c  ldarg.0
0x8625d  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SecurityRoleHandler::exc
0x86262  callvirt instance bool class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.RoleServiceInternal`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ProvisioningOff>::IsSupportUserRole(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x86267  brfalse.s loc_862D8
0x86269  ldloc.s  4
0x8626b  ldstr    aRoleid// "roleid"
0x86270  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x86275  unbox.any [mscorlib]System.Guid
0x8627a  stloc.s  9
0x8627c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x86281  ldstr    aImportexportxm_125// "ImportExportXml/SolutionManifest/RootCo"...
0x86286  ldc.i4.2
0x86287  newarr   [mscorlib]System.Object
0x8628c  dup
0x8628d  ldc.i4.0
0x8628e  ldc.i4.s 0x14
0x86290  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x86295  call     string [mscorlib]System.Convert::ToString(int32, class [mscorlib]System.IFormatProvider)
0x8629a  stelem.ref
0x8629b  dup
0x8629c  ldc.i4.1
0x8629d  ldloca.s 9
0x8629f  ldstr    aB// "B"
0x862a4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x862a9  call     instance string [mscorlib]System.Guid::ToString(string, class [mscorlib]System.IFormatProvider)
0x862ae  stelem.ref
0x862af  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x862b4  stloc.s  0xA
0x862b6  ldarg.1
0x862b7  ldloc.s  0xA
0x862b9  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x862be  stloc.s  0xB
0x862c0  ldloc.s  0xB
0x862c2  brfalse.s loc_862D3
0x862c4  ldloc.s  0xB
0x862c6  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x862cb  ldloc.s  0xB
0x862cd  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x862d2  pop
0x862d3  leave    loc_86468
0x862d8  ldloc.0
0x862d9  ldloc.1
0x862da  ldarg.0
0x862db  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SecurityRoleHandler::exc
0x862e0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.RoleServiceInternal`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ProvisioningOff>::RetrieveRolePrivilegesCollection(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x862e5  stloc.s  5
0x862e7  ldloca.s 6
0x862e9  initobj  [mscorlib]System.Guid
0x862ef  ldloc.s  4
0x862f1  ldstr    aRoletemplateid// "roletemplateid"
0x862f6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x862fb  stloc.s  7
0x862fd  ldloc.s  7
0x862ff  brfalse.s loc_8630A
0x86301  ldloc.s  7
0x86303  unbox.any [mscorlib]System.Guid
0x86308  stloc.s  6
0x8630a  ldarg.1
0x8630b  ldstr    aRole// "Role"
0x86310  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x86315  stloc.s  8
0x86317  ldloc.s  6
0x86319  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8631e  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x86323  brfalse.s loc_8633C
0x86325  ldloc.s  8
0x86327  ldstr    aId// "id"
0x8632c  ldarg.0
0x8632d  ldfld    string Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::entityName
0x86332  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x86337  br       loc_863E2
0x8633c  ldloc.s  8
0x8633e  ldstr    aId// "id"
0x86343  ldloca.s 6
0x86345  ldstr    aB// "B"
0x8634a  call     instance string [mscorlib]System.Guid::ToString(string)
0x8634f  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x86354  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x86359  ldstr    aImportexportxm_125// "ImportExportXml/SolutionManifest/RootCo"...
0x8635e  ldc.i4.2
0x8635f  newarr   [mscorlib]System.Object
0x86364  dup
0x86365  ldc.i4.0
0x86366  ldc.i4.s 0x14
0x86368  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8636d  call     string [mscorlib]System.Convert::ToString(int32, class [mscorlib]System.IFormatProvider)
0x86372  stelem.ref
0x86373  dup
0x86374  ldc.i4.1
0x86375  ldloca.s 1
0x86377  ldstr    aB// "B"
0x8637c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x86381  call     instance string [mscorlib]System.Guid::ToString(string, class [mscorlib]System.IFormatProvider)
0x86386  stelem.ref
0x86387  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8638c  stloc.s  0xC
0x8638e  ldarg.1
0x8638f  ldloc.s  0xC
0x86391  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x86396  stloc.s  0xD
0x86398  ldloc.s  0xD
0x8639a  brfalse.s loc_863E2
0x8639c  ldarg.1
0x8639d  ldstr    aParentid// "parentId"
0x863a2  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x863a7  stloc.s  0xE
0x863a9  ldloc.s  0xE
0x863ab  ldloca.s 6
0x863ad  ldstr    aB// "B"
0x863b2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x863b7  call     instance string [mscorlib]System.Guid::ToString(string, class [mscorlib]System.IFormatProvider)
0x863bc  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x863c1  ldloc.s  0xD
0x863c3  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x863c8  ldloc.s  0xE
0x863ca  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x863cf  pop
0x863d0  ldloc.s  0xD
0x863d2  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x863d7  ldstr    aId// "id"
0x863dc  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::RemoveNamedItem(string)
0x863e1  pop
0x863e2  ldloc.s  8
0x863e4  ldstr    aName// "name"
0x863e9  ldloc.s  4
0x863eb  ldstr    aName// "name"
0x863f0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x863f5  callvirt instance string [mscorlib]System.Object::ToString()
0x863fa  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x863ff  ldarg.0
0x86400  ldloc.s  5
0x86402  ldarg.1
0x86403  ldloc.0
0x86404  ldloc.s  8
0x86406  ldloc.s  4
0x86408  call     instance void Microsoft.Crm.Tools.ImportExportPublish.SecurityRoleHandler::GenerateNodes(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection rolePrivileges, class [System.Xml]System.Xml.XmlDocument XDoc, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.RoleService r, class [System.Xml]System.Xml.XmlElement roleNode, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Role role)
0x8640d  ldarg.0
0x8640e  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer Microsoft.Crm.Tools.ImportExportPublish.SecurityRoleHandler::tracer
0x86413  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x86418  ldstr    aRoleExportSucc// "Role export: Success, role id {0}"
0x8641d  ldc.i4.1
0x8641e  newarr   [mscorlib]System.Object
0x86423  dup
0x86424  ldc.i4.0
0x86425  ldarg.0
0x86426  ldfld    string Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::entityName
0x8642b  stelem.ref
0x8642c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x86431  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ExportTracer::AddSuccess(string successMessage)
0x86436  leave.s  loc_86468
0x86438  stloc.s  0xF
0x8643a  ldarg.0
0x8643b  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer Microsoft.Crm.Tools.ImportExportPublish.SecurityRoleHandler::tracer
0x86440  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x86445  ldstr    aRoleExportFail// "Role export: FAILURE, role id {0}"
0x8644a  ldc.i4.1
0x8644b  newarr   [mscorlib]System.Object
0x86450  dup
0x86451  ldc.i4.0
0x86452  ldarg.0
0x86453  ldfld    string Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::entityName
0x86458  stelem.ref
0x86459  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8645e  ldloc.s  0xF
0x86460  ldc.i4.3
0x86461  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ExportTracer::AddError(string errorMessage, class [mscorlib]System.Exception errorException, int32 severity)
0x86466  rethrow
0x86468  ret
```
