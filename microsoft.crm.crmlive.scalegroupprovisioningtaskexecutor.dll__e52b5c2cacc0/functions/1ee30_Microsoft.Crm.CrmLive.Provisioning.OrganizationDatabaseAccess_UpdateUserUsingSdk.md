# Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::UpdateUserUsingSdk

- ea: `0x1ee30`
- end: `0x1efa3`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::UpdateUserUsingSdk`
- size: `371`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0xe620`
- `0x1ee30`
- `0x1f0d0`
- `0x20c70`
- `0x20d90`
- `0x20dc0`

## string_xrefs

- `0x1ef3e`: `emailrouteraccessapproval`
- `0x1ef50`: `emailrouteraccessapproval`
- `0x1eed2`: `issyncwithdirectory`
- `0x1eedf`: `issyncwithdirectory`
- `0x1eeec`: `issyncwithdirectory`
- `0x1eebb`: `azureactivedirectoryobjectid`
- `0x1ef01`: `azureactivedirectoryobjectid`
- `0x1ef0e`: `azureactivedirectoryobjectid`

## pseudocode

```c

```

## disassembly

```asm
0x1ee30  ldarg.1
0x1ee31  ldstr    aUser// "user"
0x1ee36  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1ee3b  ldarg.2
0x1ee3c  ldstr    aOrgid_0// "OrgId"
0x1ee41  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x1ee46  ldarg.2
0x1ee47  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::GetSystemUserId(valuetype [mscorlib]System.Guid organizationId)
0x1ee4c  stloc.0
0x1ee4d  ldarg.1
0x1ee4e  ldarg.2
0x1ee4f  ldloc.0
0x1ee50  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::ConvertToSdkEntity(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity user, valuetype [mscorlib]System.Guid orgId, valuetype [mscorlib]System.Guid systemUserId)
0x1ee55  stloc.1
0x1ee56  call     class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.IInProcessOrganizationServiceFactory [Microsoft.Crm.Extensibility]Microsoft.Crm.Extensibility.InprocessServiceFactory::get_Instance()
0x1ee5b  ldarg.2
0x1ee5c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1ee61  newobj   instance void [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken::.ctor()
0x1ee66  call     class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOrigin [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOrigin::get_WebServiceApi()
0x1ee6b  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken::.ctor(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOrigin)
0x1ee70  ldnull
0x1ee71  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.IInProcessOrganizationServiceFactory::CreateInstance(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken, class [mscorlib]System.Reflection.Assembly)
0x1ee76  stloc.2
0x1ee77  ldloc.2
0x1ee78  ldstr    aSystemuser_0// "systemuser"
0x1ee7d  ldloc.1
0x1ee7e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x1ee83  ldc.i4.1
0x1ee84  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(bool)
0x1ee89  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::Retrieve(string, valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x1ee8e  stloc.3
0x1ee8f  ldloc.1
0x1ee90  ldloc.3
0x1ee91  call     void Microsoft.Crm.CrmLive.Provisioning.EntityHelper::KeepOnlyChangedAttributes(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity newEntity, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity existingEntity)
0x1ee96  ldloc.1
0x1ee97  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x1ee9c  call     T0x2B00009B
0x1eea1  brfalse  loc_1EF8F
0x1eea6  ldc.i4.0
0x1eea7  stloc.s  4
0x1eea9  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1eeae  stloc.s  5
0x1eeb0  ldloc.1
0x1eeb1  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x1eeb6  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Keys()
0x1eebb  ldstr    aAzureactivedir// "azureactivedirectoryobjectid"
0x1eec0  callvirt instance bool class [mscorlib]System.Collections.Generic.ICollection`1<string>::Contains(var<u1>)
0x1eec5  brfalse.s loc_1EF33
0x1eec7  ldloc.3
0x1eec8  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x1eecd  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Keys()
0x1eed2  ldstr    aIssyncwithdire// "issyncwithdirectory"
0x1eed7  callvirt instance bool class [mscorlib]System.Collections.Generic.ICollection`1<string>::Contains(var<u1>)
0x1eedc  brfalse.s loc_1EEFD
0x1eede  ldloc.3
0x1eedf  ldstr    aIssyncwithdire// "issyncwithdirectory"
0x1eee4  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1eee9  brfalse.s loc_1EEFD
0x1eeeb  ldloc.3
0x1eeec  ldstr    aIssyncwithdire// "issyncwithdirectory"
0x1eef1  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1eef6  unbox.any [mscorlib]System.Boolean
0x1eefb  br.s     loc_1EEFE
0x1eefd  ldc.i4.0
0x1eefe  stloc.s  6
0x1ef00  ldloc.1
0x1ef01  ldstr    aAzureactivedir// "azureactivedirectoryobjectid"
0x1ef06  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1ef0b  brfalse.s loc_1EF33
0x1ef0d  ldloc.1
0x1ef0e  ldstr    aAzureactivedir// "azureactivedirectoryobjectid"
0x1ef13  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1ef18  unbox.any [mscorlib]System.Guid
0x1ef1d  stloc.s  5
0x1ef1f  ldloc.s  5
0x1ef21  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1ef26  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1ef2b  ldloc.s  6
0x1ef2d  and
0x1ef2e  brfalse.s loc_1EF33
0x1ef30  ldc.i4.1
0x1ef31  stloc.s  4
0x1ef33  ldloc.1
0x1ef34  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x1ef39  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Keys()
0x1ef3e  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0x1ef43  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x1ef48  call     T0x2B000012
0x1ef4d  brfalse.s loc_1EF60
0x1ef4f  ldloc.1
0x1ef50  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0x1ef55  ldc.i4.1
0x1ef56  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x1ef5b  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1ef60  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.OsdpSyncContext::.ctor()
0x1ef65  stloc.s  7
0x1ef67  ldloc.2
0x1ef68  ldloc.1
0x1ef69  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::Update(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x1ef6e  leave.s  loc_1EF7C
0x1ef70  ldloc.s  7
0x1ef72  brfalse.s loc_1EF7B
0x1ef74  ldloc.s  7
0x1ef76  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1ef7b  endfinally
0x1ef7c  ldloc.s  4
0x1ef7e  brfalse.s loc_1EF8F
0x1ef80  ldarg.0
0x1ef81  ldarg.2
0x1ef82  ldloc.1
0x1ef83  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x1ef88  ldloc.s  5
0x1ef8a  call     instance void Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::SetUserObjectIdUsingSql(valuetype [mscorlib]System.Guid orgId, valuetype [mscorlib]System.Guid userId, valuetype [mscorlib]System.Guid objectId)
0x1ef8f  leave.s  loc_1EF9B
0x1ef91  ldloc.2
0x1ef92  brfalse.s loc_1EF9A
0x1ef94  ldloc.2
0x1ef95  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1ef9a  endfinally
0x1ef9b  ldarg.1
0x1ef9c  ldarg.2
0x1ef9d  call     void Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::SetStateInConfigDb(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity user, valuetype [mscorlib]System.Guid orgId)
0x1efa2  ret
```
