# <>c__DisplayClass55_0::<TryCheckPrivilege>b__0

- ea: `0x8fe90`
- end: `0x90133`
- name: `<>c__DisplayClass55_0::<TryCheckPrivilege>b__0`
- size: `675`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x62390`
- `0x625b0`
- `0x632b0`
- `0x64c90`
- `0x8fe90`

## string_xrefs

- `0x8ff09`: `Privilege`
- `0x8fea6`: `privilege`
- `0x8fed7`: `AccessMode`
- `0x8ff43`: `BusinessId`
- `0x8ffbc`: `PrivilegeIndex`
- `0x9001c`: `IdentityUserPrivilegeIndex`
- `0x90033`: `IdentityUserAccessMode`
- `0x90084`: `IdentityUserBusinessId`

## pseudocode

```c

```

## disassembly

```asm
0x8fe90  ldarg.0
0x8fe91  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass55_0::user
0x8fe96  ldstr    aUser// "user"
0x8fe9b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x8fea0  ldarg.0
0x8fea1  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass55_0::privilege
0x8fea6  ldstr    aPrivilege_0// "privilege"
0x8feab  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x8feb0  ldarg.0
0x8feb1  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass55_0::context
0x8feb6  ldstr    aContext// "context"
0x8febb  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x8fec0  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache::Instance()
0x8fec5  ldarg.0
0x8fec6  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass55_0::user
0x8fecb  ldarg.0
0x8fecc  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass55_0::context
0x8fed1  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser>::LookupEntry(void, var<u1>)
0x8fed6  stloc.0
0x8fed7  ldstr    aAccessmode_1// "AccessMode"
0x8fedc  ldloc.0
0x8fedd  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_AccessMode()
0x8fee2  stloc.s  4
0x8fee4  ldloca.s 4
0x8fee6  call     instance string [mscorlib]System.Int32::ToString()
0x8feeb  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x8fef0  ldstr    aUserlicensetyp// "UserLicenseType"
0x8fef5  ldloc.0
0x8fef6  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_UserLicenseType()
0x8fefb  stloc.s  4
0x8fefd  ldloca.s 4
0x8feff  call     instance string [mscorlib]System.Int32::ToString()
0x8ff04  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x8ff09  ldstr    aPrivilege// "Privilege"
0x8ff0e  ldarg.0
0x8ff0f  ldflda   valuetype [mscorlib]System.Guid <>c__DisplayClass55_0::privilege
0x8ff14  constrained. [mscorlib]System.Guid
0x8ff1a  callvirt instance string [mscorlib]System.Object::ToString()
0x8ff1f  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x8ff24  ldstr    aSystemuserid_2// "SystemUserId"
0x8ff29  ldloc.0
0x8ff2a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0x8ff2f  stloc.s  5
0x8ff31  ldloca.s 5
0x8ff33  constrained. [mscorlib]System.Guid
0x8ff39  callvirt instance string [mscorlib]System.Object::ToString()
0x8ff3e  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x8ff43  ldstr    aBusinessid_0// "BusinessId"
0x8ff48  ldloc.0
0x8ff49  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_BusinessId()
0x8ff4e  stloc.s  5
0x8ff50  ldloca.s 5
0x8ff52  constrained. [mscorlib]System.Guid
0x8ff58  callvirt instance string [mscorlib]System.Object::ToString()
0x8ff5d  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x8ff62  ldstr    aUserorganizati// "UserOrganizationId"
0x8ff67  ldloc.0
0x8ff68  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0x8ff6d  stloc.s  5
0x8ff6f  ldloca.s 5
0x8ff71  constrained. [mscorlib]System.Guid
0x8ff77  callvirt instance string [mscorlib]System.Object::ToString()
0x8ff7c  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x8ff81  ldloc.0
0x8ff82  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_IsSystemUser()
0x8ff87  brfalse.s loc_8FFA9
0x8ff89  ldstr    aIssystemuser// "IsSystemUser"
0x8ff8e  ldstr    aTrue// "true"
0x8ff93  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x8ff98  ldstr    aReturnvalue// "ReturnValue"
0x8ff9d  ldstr    a0_3// "0"
0x8ffa2  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x8ffa7  ldc.i4.0
0x8ffa8  ret
0x8ffa9  ldloc.0
0x8ffaa  ldarg.0
0x8ffab  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass55_0::privilege
0x8ffb0  ldarg.0
0x8ffb1  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass55_0::context
0x8ffb6  call     int32 Microsoft.Crm.BusinessEntities.SecurityLibrary::RetrievePrivilegeForUser(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser user, valuetype [mscorlib]System.Guid privilege, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x8ffbb  stloc.1
0x8ffbc  ldstr    aPrivilegeindex// "PrivilegeIndex"
0x8ffc1  ldloca.s 1
0x8ffc3  call     instance string [mscorlib]System.Int32::ToString()
0x8ffc8  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x8ffcd  ldarg.0
0x8ffce  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass55_0::user
0x8ffd3  ldarg.0
0x8ffd4  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass55_0::privilege
0x8ffd9  ldarg.0
0x8ffda  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass55_0::context
0x8ffdf  call     void Microsoft.Crm.BusinessEntities.SecurityLibrary::LogPrivilegeCheck(valuetype [mscorlib]System.Guid principalId, valuetype [mscorlib]System.Guid privilegeId, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x8ffe4  ldc.i4.0
0x8ffe5  ldloc.1
0x8ffe6  ble.s    loc_90006
0x8ffe8  ldstr    aReturnvalue// "ReturnValue"
0x8ffed  ldc.i4   0x80040220
0x8fff2  stloc.s  4
0x8fff4  ldloca.s 4
0x8fff6  call     instance string [mscorlib]System.Int32::ToString()
0x8fffb  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x90000  ldc.i4   0x80040220
0x90005  ret
0x90006  ldnull
0x90007  stloc.2
0x90008  ldarg.0
0x90009  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass55_0::privilege
0x9000e  ldloca.s 2
0x90010  ldarg.0
0x90011  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass55_0::context
0x90016  call     int32 Microsoft.Crm.BusinessEntities.SecurityLibrary::TryRetrievePrivilegeForCaller(valuetype [mscorlib]System.Guid privilege, [out] class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser& identityUser, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x9001b  stloc.3
0x9001c  ldstr    aIdentityuserpr// "IdentityUserPrivilegeIndex"
0x90021  ldloca.s 3
0x90023  call     instance string [mscorlib]System.Int32::ToString()
0x90028  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x9002d  ldloc.2
0x9002e  brfalse  loc_900C2
0x90033  ldstr    aIdentityuserac// "IdentityUserAccessMode"
0x90038  ldloc.2
0x90039  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_AccessMode()
0x9003e  stloc.s  4
0x90040  ldloca.s 4
0x90042  call     instance string [mscorlib]System.Int32::ToString()
0x90047  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x9004c  ldstr    aIdentityuserli// "IdentityUserLicenseType"
0x90051  ldloc.2
0x90052  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_UserLicenseType()
0x90057  stloc.s  4
0x90059  ldloca.s 4
0x9005b  call     instance string [mscorlib]System.Int32::ToString()
0x90060  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x90065  ldstr    aIdentityusersy// "IdentityUserSystemUserId"
0x9006a  ldloc.2
0x9006b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0x90070  stloc.s  5
0x90072  ldloca.s 5
0x90074  constrained. [mscorlib]System.Guid
0x9007a  callvirt instance string [mscorlib]System.Object::ToString()
0x9007f  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x90084  ldstr    aIdentityuserbu// "IdentityUserBusinessId"
0x90089  ldloc.2
0x9008a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_BusinessId()
0x9008f  stloc.s  5
0x90091  ldloca.s 5
0x90093  constrained. [mscorlib]System.Guid
0x90099  callvirt instance string [mscorlib]System.Object::ToString()
0x9009e  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x900a3  ldstr    aIdentityuseror// "IdentityUserOrganizationId"
0x900a8  ldloc.2
0x900a9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0x900ae  stloc.s  5
0x900b0  ldloca.s 5
0x900b2  constrained. [mscorlib]System.Guid
0x900b8  callvirt instance string [mscorlib]System.Object::ToString()
0x900bd  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x900c2  ldc.i4.0
0x900c3  ldloc.3
0x900c4  ble.s    loc_90122
0x900c6  ldloc.2
0x900c7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0x900cc  ldarg.0
0x900cd  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass55_0::context
0x900d2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x900d7  ldarg.0
0x900d8  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass55_0::context
0x900dd  call     bool Microsoft.Crm.BusinessEntities.SecurityLibrary::IsMemberOfPrivUserGroup(valuetype [mscorlib]System.Guid userId, valuetype [mscorlib]System.Guid organizationId, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x900e2  brfalse.s loc_90104
0x900e4  ldstr    aIdentityuseris// "IdentityUserIsMemberOfPrivUserGroup"
0x900e9  ldstr    aTrue// "true"
0x900ee  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x900f3  ldstr    aReturnvalue// "ReturnValue"
0x900f8  ldstr    a0_3// "0"
0x900fd  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x90102  ldc.i4.0
0x90103  ret
0x90104  ldstr    aReturnvalue// "ReturnValue"
0x90109  ldc.i4   0x80040220
0x9010e  stloc.s  4
0x90110  ldloca.s 4
0x90112  call     instance string [mscorlib]System.Int32::ToString()
0x90117  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x9011c  ldc.i4   0x80040220
0x90121  ret
0x90122  ldstr    aReturnvalue// "ReturnValue"
0x90127  ldstr    a0_3// "0"
0x9012c  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x90131  ldc.i4.0
0x90132  ret
```
