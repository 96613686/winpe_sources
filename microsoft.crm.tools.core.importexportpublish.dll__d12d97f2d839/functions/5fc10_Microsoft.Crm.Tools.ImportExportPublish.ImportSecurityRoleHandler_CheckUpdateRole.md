# Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::CheckUpdateRole

- ea: `0x5fc10`
- end: `0x5ff7c`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::CheckUpdateRole`
- size: `876`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x5f250`

## callees

- `0x35730`
- `0x508e0`
- `0x50d00`
- `0x52050`
- `0x52610`
- `0x5fc10`
- `0x686f0`

## string_xrefs

- `0x5fd50`: `The following role was undeleted during the import process: {0}`
- `0x5fde5`: `Cannot import security role with Id [{0}] and name [{1}]. The specified security role does not belong to the root business unit.`
- `0x5fe2a`: `Cannot import security role with Id [{0}] and name [{1}]. The specified security role is a 'System Administrator' or 'Support User' role, which cannot be updated.`
- `0x5fe52`: `Cannot import security role with Id [{0}] and name [{1}]. The specified security role is not a root role. Only root roles can be updated.`
- `0x5fee9`: `Found another Security Role with the same name. Name: '{0}'.  Id = {1}`
- `0x5ff59`: `Cannot import security role with Id [{0}] and name [{1}]. A security role with the same name but different Id already exists.`

## pseudocode

```c

```

## disassembly

```asm
0x5fc10  ldarg.0
0x5fc11  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::roleTemplateIdRoleIdMapping
0x5fc16  ldarg.0
0x5fc17  ldfld    string Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::roleid
0x5fc1c  callvirt instance bool [mscorlib]System.Collections.Hashtable::Contains(object)
0x5fc21  brfalse.s loc_5FC86
0x5fc23  ldloca.s 3
0x5fc25  ldarg.0
0x5fc26  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::roleTemplateIdRoleIdMapping
0x5fc2b  ldarg.0
0x5fc2c  ldfld    string Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::roleid
0x5fc31  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x5fc36  callvirt instance string [mscorlib]System.Object::ToString()
0x5fc3b  call     instance void [mscorlib]System.Guid::.ctor(string)
0x5fc40  ldloc.3
0x5fc41  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5fc46  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x5fc4b  brfalse.s loc_5FC74
0x5fc4d  ldarg.0
0x5fc4e  ldarg.0
0x5fc4f  ldfld    string Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::roleid
0x5fc54  stfld    string Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::templateid
0x5fc59  ldarg.0
0x5fc5a  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x5fc5f  stloc.s  4
0x5fc61  ldloca.s 4
0x5fc63  ldstr    aB// "B"
0x5fc68  call     instance string [mscorlib]System.Guid::ToString(string)
0x5fc6d  stfld    string Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::roleid
0x5fc72  ldnull
0x5fc73  ret
0x5fc74  ldarg.0
0x5fc75  ldloca.s 3
0x5fc77  ldstr    aB// "B"
0x5fc7c  call     instance string [mscorlib]System.Guid::ToString(string)
0x5fc81  stfld    string Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::roleid
0x5fc86  ldarg.0
0x5fc87  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::context
0x5fc8c  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Role::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5fc91  stloc.0
0x5fc92  ldloca.s 1
0x5fc94  ldarg.0
0x5fc95  ldfld    string Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::roleid
0x5fc9a  call     instance void [mscorlib]System.Guid::.ctor(string)
0x5fc9f  ldarg.0
0x5fca0  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportHelper Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::_importHelper
0x5fca5  ldarg.1
0x5fca6  ldstr    aRole// "Role"
0x5fcab  ldstr    aRoleid// "roleid"
0x5fcb0  ldloc.1
0x5fcb1  ldarg.0
0x5fcb2  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::context
0x5fcb7  ldc.i4.0
0x5fcb8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.Tools.ImportExportPublish.ImportHelper::TryGetEntity(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject service, string platformName, string idColumnName, valuetype [mscorlib]System.Guid primaryId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [opt] bool retrieveDeleted)
0x5fcbd  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Role
0x5fcc2  stloc.2
0x5fcc3  ldarg.2
0x5fcc4  dup
0x5fcc5  brtrue.s loc_5FCCD
0x5fcc7  pop
0x5fcc8  ldsfld   string [mscorlib]System.String::Empty
0x5fccd  starg.s  2
0x5fccf  ldloc.2
0x5fcd0  brtrue   loc_5FDA9
0x5fcd5  ldc.i4.1
0x5fcd6  stloc.s  5
0x5fcd8  ldarg.0
0x5fcd9  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportHelper Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::_importHelper
0x5fcde  ldarg.1
0x5fcdf  ldstr    aRole// "Role"
0x5fce4  ldstr    aRoleid// "roleid"
0x5fce9  ldloc.1
0x5fcea  ldarg.0
0x5fceb  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::context
0x5fcf0  ldloc.s  5
0x5fcf2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.Tools.ImportExportPublish.ImportHelper::TryGetEntity(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject service, string platformName, string idColumnName, valuetype [mscorlib]System.Guid primaryId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [opt] bool retrieveDeleted)
0x5fcf7  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Role
0x5fcfc  stloc.s  6
0x5fcfe  ldloc.s  6
0x5fd00  brfalse  loc_5FDA9
0x5fd05  ldstr    aRole// "Role"
0x5fd0a  ldarg.0
0x5fd0b  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::context
0x5fd10  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x5fd15  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::.ctor(string, valuetype [mscorlib]System.Guid)
0x5fd1a  stloc.s  7
0x5fd1c  ldloc.s  7
0x5fd1e  ldloc.s  6
0x5fd20  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity)
0x5fd25  pop
0x5fd26  ldc.i4.0
0x5fd27  stloc.s  8
0x5fd29  ldarg.0
0x5fd2a  ldloc.s  7
0x5fd2c  ldloc.s  6
0x5fd2e  ldarg.0
0x5fd2f  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::context
0x5fd34  ldloc.s  8
0x5fd36  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::CanEntityComponentBeUndeleted(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection latestComponentStateCollection, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [opt] bool checkCanBeDeletedPRoperty)
0x5fd3b  brfalse.s loc_5FDA9
0x5fd3d  ldarg.1
0x5fd3e  ldloc.s  6
0x5fd40  ldarg.0
0x5fd41  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::context
0x5fd46  callvirt instance void class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.RoleServiceInternal`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ProvisioningOff>::Undelete(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5fd4b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5fd50  ldstr    aTheFollowingRo// "The following role was undeleted during"...
0x5fd55  ldc.i4.1
0x5fd56  newarr   [mscorlib]System.Object
0x5fd5b  dup
0x5fd5c  ldc.i4.0
0x5fd5d  ldarg.2
0x5fd5e  stelem.ref
0x5fd5f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5fd64  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x5fd69  stloc.s  9
0x5fd6b  ldarg.0
0x5fd6c  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::_parent
0x5fd71  ldarg.0
0x5fd72  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::GetParameterXPath()
0x5fd77  ldstr    aWarning// "warning"
0x5fd7c  ldloc.s  9
0x5fd7e  ldc.i4.0
0x5fd7f  ldc.i4.0
0x5fd80  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportXml::UpdateProgress(string path, string result, class [mscorlib]System.Exception ex, bool isProcessed, [opt] int32 errorCode)
0x5fd85  ldarg.0
0x5fd86  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportHelper Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::_importHelper
0x5fd8b  ldarg.1
0x5fd8c  ldstr    aRole// "Role"
0x5fd91  ldstr    aRoleid// "roleid"
0x5fd96  ldloc.1
0x5fd97  ldarg.0
0x5fd98  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::context
0x5fd9d  ldc.i4.0
0x5fd9e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.Tools.ImportExportPublish.ImportHelper::TryGetEntity(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject service, string platformName, string idColumnName, valuetype [mscorlib]System.Guid primaryId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [opt] bool retrieveDeleted)
0x5fda3  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Role
0x5fda8  stloc.2
0x5fda9  ldloc.2
0x5fdaa  brfalse  loc_5FE75
0x5fdaf  ldloc.2
0x5fdb0  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Role
0x5fdb5  stloc.s  0xA
0x5fdb7  ldloc.s  0xA
0x5fdb9  ldstr    aParentroleid// "parentroleid"
0x5fdbe  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5fdc3  brtrue   loc_5FE4D
0x5fdc8  ldloc.s  0xA
0x5fdca  ldstr    aBusinessunitid// "businessunitid"
0x5fdcf  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5fdd4  stloc.s  0xB
0x5fdd6  ldarg.3
0x5fdd7  ldloc.s  0xB
0x5fdd9  unbox.any [mscorlib]System.Guid
0x5fdde  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x5fde3  brfalse.s loc_5FDFC
0x5fde5  ldstr    aCannotImportSe_0// "Cannot import security role with Id [{0"...
0x5fdea  ldarg.0
0x5fdeb  ldfld    string Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::roleid
0x5fdf0  ldarg.2
0x5fdf1  call     string [mscorlib]System.String::Format(string, object, object)
0x5fdf6  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ImportRoleException::.ctor(string message)
0x5fdfb  throw
0x5fdfc  ldarg.0
0x5fdfd  ldfld    bool Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::_isInternalSolution
0x5fe02  brtrue.s loc_5FE22
0x5fe04  ldarg.1
0x5fe05  ldloc.1
0x5fe06  ldarg.0
0x5fe07  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::context
0x5fe0c  callvirt instance bool class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.RoleServiceInternal`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ProvisioningOff>::IsSystemAdministratorRole(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5fe11  brtrue.s loc_5FE25
0x5fe13  ldarg.1
0x5fe14  ldloc.1
0x5fe15  ldarg.0
0x5fe16  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::context
0x5fe1b  callvirt instance bool class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.RoleServiceInternal`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ProvisioningOff>::IsSupportUserRole(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5fe20  brtrue.s loc_5FE25
0x5fe22  ldloc.s  0xA
0x5fe24  ret
0x5fe25  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5fe2a  ldstr    aCannotImportSe_1// "Cannot import security role with Id [{0"...
0x5fe2f  ldc.i4.2
0x5fe30  newarr   [mscorlib]System.Object
0x5fe35  dup
0x5fe36  ldc.i4.0
0x5fe37  ldarg.0
0x5fe38  ldfld    string Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::roleid
0x5fe3d  stelem.ref
0x5fe3e  dup
0x5fe3f  ldc.i4.1
0x5fe40  ldarg.2
0x5fe41  stelem.ref
0x5fe42  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5fe47  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ImportRoleException::.ctor(string message)
0x5fe4c  throw
0x5fe4d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5fe52  ldstr    aCannotImportSe_2// "Cannot import security role with Id [{0"...
0x5fe57  ldc.i4.2
0x5fe58  newarr   [mscorlib]System.Object
0x5fe5d  dup
0x5fe5e  ldc.i4.0
0x5fe5f  ldarg.0
0x5fe60  ldfld    string Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::roleid
0x5fe65  stelem.ref
0x5fe66  dup
0x5fe67  ldc.i4.1
0x5fe68  ldarg.2
0x5fe69  stelem.ref
0x5fe6a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5fe6f  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ImportRoleException::.ctor(string message)
0x5fe74  throw
0x5fe75  ldloc.0
0x5fe76  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x5fe7b  ldarg.0
0x5fe7c  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::context
0x5fe81  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x5fe86  stloc.s  0xC
0x5fe88  ldloc.s  0xC
0x5fe8a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x5fe8f  ldstr    aName// "name"
0x5fe94  ldc.i4.0
0x5fe95  ldarg.2
0x5fe96  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x5fe9b  pop
0x5fe9c  ldarg.1
0x5fe9d  ldloc.s  0xC
0x5fe9f  ldarg.0
0x5fea0  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::context
0x5fea5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5feaa  stloc.s  0xD
0x5feac  ldloc.s  0xD
0x5feae  brfalse.s loc_5FEB9
0x5feb0  ldloc.s  0xD
0x5feb2  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x5feb7  brtrue.s loc_5FEBB
0x5feb9  ldnull
0x5feba  ret
0x5febb  ldarg.0
0x5febc  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportHelper Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::_importHelper
0x5fec1  callvirt instance bool Microsoft.Crm.Tools.ImportExportPublish.ImportHelper::get_LookupNameMatches()
0x5fec6  brfalse  loc_5FF54
0x5fecb  ldloc.s  0xD
0x5fecd  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x5fed2  stloc.s  0xE
0x5fed4  br.s     loc_5FF32
0x5fed6  ldloc.s  0xE
0x5fed8  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5fedd  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Role
0x5fee2  stloc.s  0xF
0x5fee4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5fee9  ldstr    aFoundAnotherSe// "Found another Security Role with the sa"...
0x5feee  ldc.i4.2
0x5feef  newarr   [mscorlib]System.Object
0x5fef4  dup
0x5fef5  ldc.i4.0
0x5fef6  ldarg.2
0x5fef7  stelem.ref
0x5fef8  dup
0x5fef9  ldc.i4.1
0x5fefa  ldloc.s  0xF
0x5fefc  ldstr    aRoleid// "roleid"
0x5ff01  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5ff06  callvirt instance string [mscorlib]System.Object::ToString()
0x5ff0b  stelem.ref
0x5ff0c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5ff11  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x5ff16  stloc.s  0x10
0x5ff18  ldarg.0
0x5ff19  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::_parent
0x5ff1e  ldarg.0
0x5ff1f  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::GetParameterXPath()
0x5ff24  ldstr    aWarning// "warning"
0x5ff29  ldloc.s  0x10
0x5ff2b  ldc.i4.1
0x5ff2c  ldc.i4.0
0x5ff2d  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportXml::UpdateProgress(string path, string result, class [mscorlib]System.Exception ex, bool isProcessed, [opt] int32 errorCode)
0x5ff32  ldloc.s  0xE
0x5ff34  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5ff39  brtrue.s loc_5FED6
0x5ff3b  leave.s  loc_5FF52
0x5ff3d  ldloc.s  0xE
0x5ff3f  isinst   [mscorlib]System.IDisposable
0x5ff44  stloc.s  0x11
0x5ff46  ldloc.s  0x11
0x5ff48  brfalse.s loc_5FF51
0x5ff4a  ldloc.s  0x11
0x5ff4c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5ff51  endfinally
0x5ff52  ldnull
0x5ff53  ret
0x5ff54  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5ff59  ldstr    aCannotImportSe_3// "Cannot import security role with Id [{0"...
0x5ff5e  ldc.i4.2
0x5ff5f  newarr   [mscorlib]System.Object
0x5ff64  dup
0x5ff65  ldc.i4.0
0x5ff66  ldarg.0
0x5ff67  ldfld    string Microsoft.Crm.Tools.ImportExportPublish.ImportSecurityRoleHandler::roleid
0x5ff6c  stelem.ref
0x5ff6d  dup
  ... truncated ...
```
