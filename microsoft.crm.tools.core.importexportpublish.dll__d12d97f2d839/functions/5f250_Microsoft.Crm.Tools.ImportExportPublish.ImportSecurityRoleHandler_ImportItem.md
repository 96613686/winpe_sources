# Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::ImportItem

- ea: `0x5f250`
- end: `0x5fa2c`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::ImportItem`
- size: `2012`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x4c9a0`
- `0x520f0`
- `0x5f250`
- `0x5fa30`
- `0x5fb80`
- `0x5fc10`
- `0x5ff80`
- `0x60000`
- `0x600c0`
- `0x63db0`
- `0x63df0`
- `0x971b0`

## string_xrefs

- `0x5f314`: `roletemplateid`
- `0x5f349`: `roletemplateid`
- `0x5f389`: `roletemplateid`
- `0x5f40e`: `roletemplateid`
- `0x5f445`: `roletemplateid`
- `0x5f471`: `roletemplateid`
- `0x5f75e`: `roletemplateid`
- `0x5f2ae`: `privilegeid`
- `0x5f7a1`: `RolePrivileges/RolePrivilege`
- `0x5f868`: `Role Import: WARNING Role '{0}'. The Privilege '{1}' does not exist in the database. Skipping Import of this Privilege.`

## pseudocode

```c

```

## disassembly

```asm
0x5f250  ldarg.0
0x5f251  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::VerifyRoleAccessPrivileges()
0x5f256  ldarg.0
0x5f257  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::GetRootBusinessUnitId()
0x5f25c  stloc.0
0x5f25d  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.RoleService::.ctor()
0x5f262  stloc.1
0x5f263  ldarg.0
0x5f264  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::privilegeNameMapping
0x5f269  callvirt instance int32 [mscorlib]System.Collections.Hashtable::get_Count()
0x5f26e  brtrue   loc_5F4CA
0x5f273  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PrivilegeService::.ctor()
0x5f278  ldarg.0
0x5f279  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::context
0x5f27e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PrivilegeServiceInternal`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ProvisioningOff>::RetrievePrivilegeSet(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5f283  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x5f288  stloc.s  0xA
0x5f28a  br.s     loc_5F2D0
0x5f28c  ldloc.s  0xA
0x5f28e  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5f293  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Privilege
0x5f298  stloc.s  0xB
0x5f29a  ldarg.0
0x5f29b  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::privilegeNameMapping
0x5f2a0  ldloc.s  0xB
0x5f2a2  ldstr    aName// "name"
0x5f2a7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5f2ac  ldloc.s  0xB
0x5f2ae  ldstr    aPrivilegeid// "privilegeid"
0x5f2b3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5f2b8  unbox.any [mscorlib]System.Guid
0x5f2bd  stloc.s  0xC
0x5f2bf  ldloca.s 0xC
0x5f2c1  ldstr    aB// "B"
0x5f2c6  call     instance string [mscorlib]System.Guid::ToString(string)
0x5f2cb  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x5f2d0  ldloc.s  0xA
0x5f2d2  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5f2d7  brtrue.s loc_5F28C
0x5f2d9  leave.s  loc_5F2F0
0x5f2db  ldloc.s  0xA
0x5f2dd  isinst   [mscorlib]System.IDisposable
0x5f2e2  stloc.s  0xD
0x5f2e4  ldloc.s  0xD
0x5f2e6  brfalse.s loc_5F2EF
0x5f2e8  ldloc.s  0xD
0x5f2ea  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5f2ef  endfinally
0x5f2f0  ldarg.0
0x5f2f1  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::context
0x5f2f6  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Role::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5f2fb  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x5f300  ldarg.0
0x5f301  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::context
0x5f306  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x5f30b  stloc.s  8
0x5f30d  ldloc.s  8
0x5f30f  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x5f314  ldstr    aRoletemplateid// "roletemplateid"
0x5f319  ldc.i4.s 0xD
0x5f31b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0x5f320  pop
0x5f321  ldloc.s  8
0x5f323  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x5f328  ldstr    aBusinessunitid// "businessunitid"
0x5f32d  ldc.i4.0
0x5f32e  ldloc.0
0x5f32f  box      [mscorlib]System.Guid
0x5f334  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x5f339  pop
0x5f33a  ldloc.s  8
0x5f33c  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x5f341  ldc.i4.2
0x5f342  newarr   [mscorlib]System.String
0x5f347  dup
0x5f348  ldc.i4.0
0x5f349  ldstr    aRoletemplateid// "roletemplateid"
0x5f34e  stelem.ref
0x5f34f  dup
0x5f350  ldc.i4.1
0x5f351  ldstr    aRoleid// "roleid"
0x5f356  stelem.ref
0x5f357  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x5f35c  ldloc.1
0x5f35d  ldloc.s  8
0x5f35f  ldarg.0
0x5f360  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::context
0x5f365  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5f36a  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x5f36f  stloc.s  0xA
0x5f371  br.s     loc_5F3CA
0x5f373  ldloc.s  0xA
0x5f375  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5f37a  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x5f37f  stloc.s  0xE
0x5f381  ldarg.0
0x5f382  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::roleTemplateIdRoleIdMapping
0x5f387  ldloc.s  0xE
0x5f389  ldstr    aRoletemplateid// "roletemplateid"
0x5f38e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5f393  unbox.any [mscorlib]System.Guid
0x5f398  stloc.s  0xC
0x5f39a  ldloca.s 0xC
0x5f39c  ldstr    aB// "B"
0x5f3a1  call     instance string [mscorlib]System.Guid::ToString(string)
0x5f3a6  ldloc.s  0xE
0x5f3a8  ldstr    aRoleid// "roleid"
0x5f3ad  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5f3b2  unbox.any [mscorlib]System.Guid
0x5f3b7  stloc.s  0xC
0x5f3b9  ldloca.s 0xC
0x5f3bb  ldstr    aB// "B"
0x5f3c0  call     instance string [mscorlib]System.Guid::ToString(string)
0x5f3c5  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x5f3ca  ldloc.s  0xA
0x5f3cc  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5f3d1  brtrue.s loc_5F373
0x5f3d3  leave.s  loc_5F3EA
0x5f3d5  ldloc.s  0xA
0x5f3d7  isinst   [mscorlib]System.IDisposable
0x5f3dc  stloc.s  0xD
0x5f3de  ldloc.s  0xD
0x5f3e0  brfalse.s loc_5F3E9
0x5f3e2  ldloc.s  0xD
0x5f3e4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5f3e9  endfinally
0x5f3ea  ldarg.0
0x5f3eb  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::context
0x5f3f0  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.RoleTemplate::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5f3f5  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x5f3fa  ldarg.0
0x5f3fb  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::context
0x5f400  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x5f405  stloc.s  9
0x5f407  ldloc.s  8
0x5f409  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x5f40e  ldstr    aRoletemplateid// "roletemplateid"
0x5f413  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x5f418  ldloc.1
0x5f419  ldloc.s  9
0x5f41b  ldarg.0
0x5f41c  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::context
0x5f421  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5f426  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x5f42b  stloc.s  0xA
0x5f42d  br.s     loc_5F4A7
0x5f42f  ldloc.s  0xA
0x5f431  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5f436  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x5f43b  stloc.s  0xF
0x5f43d  ldarg.0
0x5f43e  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::roleTemplateIdRoleIdMapping
0x5f443  ldloc.s  0xF
0x5f445  ldstr    aRoletemplateid// "roletemplateid"
0x5f44a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5f44f  unbox.any [mscorlib]System.Guid
0x5f454  stloc.s  0xC
0x5f456  ldloca.s 0xC
0x5f458  ldstr    aB// "B"
0x5f45d  call     instance string [mscorlib]System.Guid::ToString(string)
0x5f462  callvirt instance bool [mscorlib]System.Collections.Hashtable::Contains(object)
0x5f467  brtrue.s loc_5F4A7
0x5f469  ldarg.0
0x5f46a  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::roleTemplateIdRoleIdMapping
0x5f46f  ldloc.s  0xF
0x5f471  ldstr    aRoletemplateid// "roletemplateid"
0x5f476  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5f47b  unbox.any [mscorlib]System.Guid
0x5f480  stloc.s  0xC
0x5f482  ldloca.s 0xC
0x5f484  ldstr    aB// "B"
0x5f489  call     instance string [mscorlib]System.Guid::ToString(string)
0x5f48e  ldloca.s 0xC
0x5f490  dup
0x5f491  initobj  [mscorlib]System.Guid
0x5f497  constrained. [mscorlib]System.Guid
0x5f49d  callvirt instance string [mscorlib]System.Object::ToString()
0x5f4a2  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x5f4a7  ldloc.s  0xA
0x5f4a9  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5f4ae  brtrue   loc_5F42F
0x5f4b3  leave.s  loc_5F4CA
0x5f4b5  ldloc.s  0xA
0x5f4b7  isinst   [mscorlib]System.IDisposable
0x5f4bc  stloc.s  0xD
0x5f4be  ldloc.s  0xD
0x5f4c0  brfalse.s loc_5F4C9
0x5f4c2  ldloc.s  0xD
0x5f4c4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5f4c9  endfinally
0x5f4ca  ldarg.0
0x5f4cb  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::importDocument
0x5f4d0  ldarg.0
0x5f4d1  ldfld    string Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::roleid
0x5f4d6  call     class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Tools.ImportExportPublish.ImportExportUtils::GetRoleNodeById(class [System.Xml]System.Xml.XmlDocument importDocument, string id)
0x5f4db  stloc.2
0x5f4dc  ldloc.2
0x5f4dd  brtrue.s loc_5F4E4
0x5f4df  leave    loc_5FA2B
0x5f4e4  ldarg.0
0x5f4e5  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportHelper Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::_importHelper
0x5f4ea  ldloc.2
0x5f4eb  ldstr    aName// "name"
0x5f4f0  ldstr    aName// "name"
0x5f4f5  ldloca.s 3
0x5f4f7  callvirt instance bool Microsoft.Crm.Tools.ImportExportPublish.ImportHelper::TryGetLocalizedLabelForImportXmlNodeAttribute(class [System.Xml]System.Xml.XmlNode importXmlNode, string xmlNodeAttributeName, string localizedLabelAttributeName, [out] string& labelForAttributeValue)
0x5f4fc  pop
0x5f4fd  ldarg.0
0x5f4fe  ldfld    bool Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::_isInternalSolution
0x5f503  brfalse  loc_5F5DA
0x5f508  call     class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::InternalOOBRoleTemplates()
0x5f50d  ldarg.0
0x5f50e  ldfld    string Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::roleid
0x5f513  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x5f518  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Contains(var<u1>)
0x5f51d  brfalse  loc_5F5DA
0x5f522  ldarg.0
0x5f523  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::roleTemplateIdRoleIdMapping
0x5f528  ldarg.0
0x5f529  ldfld    string Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::roleid
0x5f52e  callvirt instance bool [mscorlib]System.Collections.Hashtable::Contains(object)
0x5f533  brtrue   loc_5F5DA
0x5f538  ldarg.0
0x5f539  ldarg.0
0x5f53a  ldfld    string Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::roleid
0x5f53f  stfld    string Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::templateid
0x5f544  ldarg.0
0x5f545  ldstr    asc_9B374// "{"
0x5f54a  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x5f54f  stloc.s  0xC
0x5f551  ldloca.s 0xC
0x5f553  constrained. [mscorlib]System.Guid
0x5f559  callvirt instance string [mscorlib]System.Object::ToString()
0x5f55e  ldstr    asc_9B378// "}"
0x5f563  call     string [mscorlib]System.String::Concat(string, string, string)
0x5f568  stfld    string Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::roleid
0x5f56d  ldarg.0
0x5f56e  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::roleTemplateIdRoleIdMapping
0x5f573  ldarg.0
0x5f574  ldfld    string Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::templateid
0x5f579  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x5f57e  stloc.s  0xC
0x5f580  ldloca.s 0xC
0x5f582  ldstr    aB// "B"
0x5f587  call     instance string [mscorlib]System.Guid::ToString(string)
0x5f58c  ldarg.0
0x5f58d  ldfld    string Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::roleid
0x5f592  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x5f597  ldarg.0
0x5f598  ldarg.0
0x5f599  ldfld    string Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::templateid
0x5f59e  ldloc.3
0x5f59f  ldarg.0
0x5f5a0  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::context
0x5f5a5  ldc.i4.0
0x5f5a6  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::ImportRoleTemplate(string roleTemplateId, string roleName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [opt] bool upgrading)
0x5f5ab  ldc.i4.s 0x14
0x5f5ad  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.IImportExportDependencyHelper [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ImportExportDependencyHelperFactory::RetrieveHelper(int32)
0x5f5b2  ldarg.0
0x5f5b3  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::importDocument
0x5f5b8  ldsfld   string [mscorlib]System.String::Empty
0x5f5bd  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5f5c2  ldarg.0
0x5f5c3  ldfld    string Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::templateid
0x5f5c8  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x5f5cd  ldarg.0
0x5f5ce  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::context
0x5f5d3  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.IImportExportDependencyHelper::CheckForRootComponent(class [System.Xml]System.Xml.XmlDocument, string, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5f5d8  br.s     loc_5F649
0x5f5da  ldarg.0
0x5f5db  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::roleTemplateIdRoleIdMapping
0x5f5e0  ldarg.0
0x5f5e1  ldfld    string Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::roleid
0x5f5e6  callvirt instance bool [mscorlib]System.Collections.Hashtable::ContainsKey(object)
0x5f5eb  brfalse.s loc_5F61C
0x5f5ed  ldc.i4.s 0x14
0x5f5ef  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.IImportExportDependencyHelper [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ImportExportDependencyHelperFactory::RetrieveHelper(int32)
0x5f5f4  ldarg.0
0x5f5f5  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::importDocument
0x5f5fa  ldsfld   string [mscorlib]System.String::Empty
0x5f5ff  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5f604  ldarg.0
0x5f605  ldfld    string Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::roleid
0x5f60a  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x5f60f  ldarg.0
0x5f610  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::context
0x5f615  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.IImportExportDependencyHelper::CheckForRootComponent(class [System.Xml]System.Xml.XmlDocument, string, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5f61a  br.s     loc_5F649
0x5f61c  ldc.i4.s 0x14
0x5f61e  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.IImportExportDependencyHelper [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ImportExportDependencyHelperFactory::RetrieveHelper(int32)
0x5f623  ldarg.0
0x5f624  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::importDocument
0x5f629  ldsfld   string [mscorlib]System.String::Empty
0x5f62e  ldarg.0
0x5f62f  ldfld    string Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::roleid
0x5f634  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x5f639  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5f63e  ldarg.0
0x5f63f  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::context
0x5f644  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.IImportExportDependencyHelper::CheckForRootComponent(class [System.Xml]System.Xml.XmlDocument, string, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
  ... truncated ...
```
