# Microsoft.Crm.ScaleGroupApi.Controllers.UserSecurityRoleController::Put

- ea: `0x4e70`
- end: `0x4f44`
- name: `Microsoft.Crm.ScaleGroupApi.Controllers.UserSecurityRoleController::Put`
- size: `212`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x15a0`
- `0x15c0`
- `0x15e0`
- `0x4e70`
- `0x4f50`
- `0x4fd0`

## pseudocode

```c

```

## disassembly

```asm
0x4e70  ldarg.1
0x4e71  ldarg.2
0x4e72  call     valuetype [mscorlib]System.Guid Microsoft.Crm.ScaleGroupApi.Controllers.UserSecurityRoleController::GetCrmUserId(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid directoryObjectId)
0x4e77  stloc.0
0x4e78  ldarg.3
0x4e79  callvirt instance string Microsoft.Crm.ScaleGroupApi.Models.SGUserSecurityRole::get_Roles()
0x4e7e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4e83  brtrue.s loc_4EC3
0x4e85  call     class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.IInProcessOrganizationServiceFactory [Microsoft.Crm.Extensibility]Microsoft.Crm.Extensibility.InprocessServiceFactory::get_Instance()
0x4e8a  ldarg.1
0x4e8b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4e90  newobj   instance void [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken::.ctor()
0x4e95  call     class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOrigin [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOrigin::get_WebServiceApi()
0x4e9a  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken::.ctor(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOrigin)
0x4e9f  ldnull
0x4ea0  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.IInProcessOrganizationServiceFactory::CreateInstance(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken, class [mscorlib]System.Reflection.Assembly)
0x4ea5  stloc.1
0x4ea6  ldarg.1
0x4ea7  ldarg.3
0x4ea8  callvirt instance string Microsoft.Crm.ScaleGroupApi.Models.SGUserSecurityRole::get_Roles()
0x4ead  ldloc.0
0x4eae  ldloc.1
0x4eaf  call     void [Microsoft.Crm]Microsoft.Crm.UserScenarioRole.UserScenarioRoleManager::AssignCsvOfRolesToUserUsingSdk(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService)
0x4eb4  leave    loc_4F43
0x4eb9  ldloc.1
0x4eba  brfalse.s loc_4EC2
0x4ebc  ldloc.1
0x4ebd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4ec2  endfinally
0x4ec3  ldarg.3
0x4ec4  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ScaleGroupApi.Models.SGUserSecurityRole::get_SecurityRoleId()
0x4ec9  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4ece  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x4ed3  brfalse.s loc_4F36
0x4ed5  call     class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.IInProcessOrganizationServiceFactory [Microsoft.Crm.Extensibility]Microsoft.Crm.Extensibility.InprocessServiceFactory::get_Instance()
0x4eda  ldarg.1
0x4edb  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4ee0  newobj   instance void [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken::.ctor()
0x4ee5  call     class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOrigin [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOrigin::get_WebServiceApi()
0x4eea  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken::.ctor(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOrigin)
0x4eef  ldnull
0x4ef0  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.IInProcessOrganizationServiceFactory::CreateInstance(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken, class [mscorlib]System.Reflection.Assembly)
0x4ef5  stloc.2
0x4ef6  ldarg.3
0x4ef7  callvirt instance int32 Microsoft.Crm.ScaleGroupApi.Models.SGUserSecurityRole::get_UserScenarioRole()
0x4efc  ldarg.1
0x4efd  ldloc.2
0x4efe  ldc.i4.1
0x4eff  call     valuetype [mscorlib]System.Guid[] [Microsoft.Crm]Microsoft.Crm.UserScenarioRole.UserScenarioRoleManager::GetSystemRoleIds(int32, valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService, bool)
0x4f04  stloc.3
0x4f05  ldc.i4.0
0x4f06  stloc.s  4
0x4f08  br.s     loc_4F23
0x4f0a  ldloc.3
0x4f0b  ldloc.s  4
0x4f0d  ldelem   [mscorlib]System.Guid
0x4f12  stloc.s  5
0x4f14  ldarg.1
0x4f15  ldloc.s  5
0x4f17  ldloc.0
0x4f18  call     void Microsoft.Crm.ScaleGroupApi.Controllers.UserSecurityRoleController::AssignRoleToUserUsingSdk(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid roleId, valuetype [mscorlib]System.Guid crmUserId)
0x4f1d  ldloc.s  4
0x4f1f  ldc.i4.1
0x4f20  add
0x4f21  stloc.s  4
0x4f23  ldloc.s  4
0x4f25  ldloc.3
0x4f26  ldlen
0x4f27  conv.i4
0x4f28  blt.s    loc_4F0A
0x4f2a  leave.s  loc_4F43
0x4f2c  ldloc.2
0x4f2d  brfalse.s loc_4F35
0x4f2f  ldloc.2
0x4f30  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4f35  endfinally
0x4f36  ldarg.1
0x4f37  ldarg.3
0x4f38  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ScaleGroupApi.Models.SGUserSecurityRole::get_SecurityRoleId()
0x4f3d  ldloc.0
0x4f3e  call     void Microsoft.Crm.ScaleGroupApi.Controllers.UserSecurityRoleController::AssignRoleToUserUsingSdk(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid roleId, valuetype [mscorlib]System.Guid crmUserId)
0x4f43  ret
```
