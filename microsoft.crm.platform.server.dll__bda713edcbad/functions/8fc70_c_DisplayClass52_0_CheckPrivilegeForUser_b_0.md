# <>c__DisplayClass52_0::<CheckPrivilegeForUser>b__0

- ea: `0x8fc70`
- end: `0x8fe6f`
- name: `<>c__DisplayClass52_0::<CheckPrivilegeForUser>b__0`
- size: `511`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x621a0`
- `0x636d0`
- `0x64c90`
- `0x64dc0`
- `0x8fc70`

## string_xrefs

- `0x8fcaa`: `Privilege`
- `0x8fc70`: `AccessMode`
- `0x8fd03`: `BusinessId`
- `0x8fd5c`: `SecLib::CheckPrivilegeForUser failed - no roles are assigned to user. Returned hr = {0}, User: {1}`
- `0x8fdc9`: `PrivilegeIndex`
- `0x8fdde`: `UserPrivilegeIndexDepth`

## pseudocode

```c

```

## disassembly

```asm
0x8fc70  ldstr    aAccessmode_1// "AccessMode"
0x8fc75  ldarg.0
0x8fc76  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser <>c__DisplayClass52_0::user
0x8fc7b  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_AccessMode()
0x8fc80  stloc.1
0x8fc81  ldloca.s 1
0x8fc83  call     instance string [mscorlib]System.Int32::ToString()
0x8fc88  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x8fc8d  ldstr    aUserlicensetyp// "UserLicenseType"
0x8fc92  ldarg.0
0x8fc93  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser <>c__DisplayClass52_0::user
0x8fc98  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_UserLicenseType()
0x8fc9d  stloc.1
0x8fc9e  ldloca.s 1
0x8fca0  call     instance string [mscorlib]System.Int32::ToString()
0x8fca5  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x8fcaa  ldstr    aPrivilege// "Privilege"
0x8fcaf  ldarg.0
0x8fcb0  ldflda   valuetype [mscorlib]System.Guid <>c__DisplayClass52_0::privilege
0x8fcb5  constrained. [mscorlib]System.Guid
0x8fcbb  callvirt instance string [mscorlib]System.Object::ToString()
0x8fcc0  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x8fcc5  ldstr    aRequireddepth// "RequiredDepth"
0x8fcca  ldarg.0
0x8fccb  ldflda   valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth <>c__DisplayClass52_0::requiredDepth
0x8fcd0  constrained. [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth
0x8fcd6  callvirt instance string [mscorlib]System.Object::ToString()
0x8fcdb  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x8fce0  ldstr    aSystemuserid_2// "SystemUserId"
0x8fce5  ldarg.0
0x8fce6  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser <>c__DisplayClass52_0::user
0x8fceb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0x8fcf0  stloc.2
0x8fcf1  ldloca.s 2
0x8fcf3  constrained. [mscorlib]System.Guid
0x8fcf9  callvirt instance string [mscorlib]System.Object::ToString()
0x8fcfe  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x8fd03  ldstr    aBusinessid_0// "BusinessId"
0x8fd08  ldarg.0
0x8fd09  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser <>c__DisplayClass52_0::user
0x8fd0e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_BusinessId()
0x8fd13  stloc.2
0x8fd14  ldloca.s 2
0x8fd16  constrained. [mscorlib]System.Guid
0x8fd1c  callvirt instance string [mscorlib]System.Object::ToString()
0x8fd21  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x8fd26  ldstr    aUserorganizati// "UserOrganizationId"
0x8fd2b  ldarg.0
0x8fd2c  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser <>c__DisplayClass52_0::user
0x8fd31  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0x8fd36  stloc.2
0x8fd37  ldloca.s 2
0x8fd39  constrained. [mscorlib]System.Guid
0x8fd3f  callvirt instance string [mscorlib]System.Object::ToString()
0x8fd44  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x8fd49  ldarg.0
0x8fd4a  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser <>c__DisplayClass52_0::user
0x8fd4f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege[] [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_Privileges()
0x8fd54  ldlen
0x8fd55  brtrue.s loc_8FD97
0x8fd57  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8fd5c  ldstr    aSeclibCheckpri_1// "SecLib::CheckPrivilegeForUser failed - "...
0x8fd61  ldc.i4.2
0x8fd62  newarr   [mscorlib]System.Object
0x8fd67  dup
0x8fd68  ldc.i4.0
0x8fd69  ldc.i4   0x80042F09
0x8fd6e  box      [mscorlib]System.Int32
0x8fd73  stelem.ref
0x8fd74  dup
0x8fd75  ldc.i4.1
0x8fd76  ldarg.0
0x8fd77  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser <>c__DisplayClass52_0::user
0x8fd7c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0x8fd81  box      [mscorlib]System.Guid
0x8fd86  stelem.ref
0x8fd87  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8fd8c  ldc.i4   0x80042F09
0x8fd91  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmSecurityException::.ctor(string, int32)
0x8fd96  throw
0x8fd97  ldarg.0
0x8fd98  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser <>c__DisplayClass52_0::user
0x8fd9d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0x8fda2  ldarg.0
0x8fda3  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass52_0::context
0x8fda8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x8fdad  call     void Microsoft.Crm.BusinessEntities.SecurityLibrary::VerifyUserOrganization(valuetype [mscorlib]System.Guid userOrgId, valuetype [mscorlib]System.Guid contextOrgId)
0x8fdb2  ldarg.0
0x8fdb3  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser <>c__DisplayClass52_0::user
0x8fdb8  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege[] [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_Privileges()
0x8fdbd  ldarg.0
0x8fdbe  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass52_0::privilege
0x8fdc3  call     int32 Microsoft.Crm.BusinessEntities.SecurityLibrary::GetPrivilegeIndex(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege[] privileges, valuetype [mscorlib]System.Guid privilege)
0x8fdc8  stloc.0
0x8fdc9  ldstr    aPrivilegeindex// "PrivilegeIndex"
0x8fdce  ldloca.s 0
0x8fdd0  call     instance string [mscorlib]System.Int32::ToString()
0x8fdd5  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x8fdda  ldloc.0
0x8fddb  ldc.i4.m1
0x8fddc  ble.s    loc_8FE02
0x8fdde  ldstr    aUserprivilegei// "UserPrivilegeIndexDepth"
0x8fde3  ldarg.0
0x8fde4  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser <>c__DisplayClass52_0::user
0x8fde9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege[] [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_Privileges()
0x8fdee  ldloc.0
0x8fdef  ldelem.ref
0x8fdf0  callvirt instance valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege::get_Depth()
0x8fdf5  stloc.1
0x8fdf6  ldloca.s 1
0x8fdf8  call     instance string [mscorlib]System.Int32::ToString()
0x8fdfd  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x8fe02  ldarg.0
0x8fe03  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser <>c__DisplayClass52_0::user
0x8fe08  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0x8fe0d  ldarg.0
0x8fe0e  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass52_0::privilege
0x8fe13  ldarg.0
0x8fe14  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass52_0::context
0x8fe19  call     void Microsoft.Crm.BusinessEntities.SecurityLibrary::LogPrivilegeCheck(valuetype [mscorlib]System.Guid principalId, valuetype [mscorlib]System.Guid privilegeId, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x8fe1e  ldc.i4.0
0x8fe1f  ldloc.0
0x8fe20  bgt.s    loc_8FE3C
0x8fe22  ldarg.0
0x8fe23  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser <>c__DisplayClass52_0::user
0x8fe28  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege[] [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_Privileges()
0x8fe2d  ldloc.0
0x8fe2e  ldelem.ref
0x8fe2f  callvirt instance valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege::get_Depth()
0x8fe34  ldarg.0
0x8fe35  ldfld    valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth <>c__DisplayClass52_0::requiredDepth
0x8fe3a  bge.s    loc_8FE6E
0x8fe3c  ldarg.0
0x8fe3d  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser <>c__DisplayClass52_0::user
0x8fe42  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0x8fe47  ldarg.0
0x8fe48  ldfld    valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth <>c__DisplayClass52_0::requiredDepth
0x8fe4d  ldarg.0
0x8fe4e  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass52_0::privilege
0x8fe53  ldarg.0
0x8fe54  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser <>c__DisplayClass52_0::user
0x8fe59  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_BusinessId()
0x8fe5e  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege::.ctor(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x8fe63  ldarg.0
0x8fe64  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass52_0::context
0x8fe69  call     void Microsoft.Crm.BusinessEntities.SecurityLibrary::ThrowPrivilegeDeniedException(valuetype [mscorlib]System.Guid userId, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege rolePrivilege, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x8fe6e  ret
```
