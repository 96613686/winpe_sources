# Microsoft.Crm.Sandbox.SandboxHostSids::IsCallerAllowed_0

- ea: `0x1ec0`
- end: `0x1f9a`
- name: `Microsoft.Crm.Sandbox.SandboxHostSids::IsCallerAllowed_0`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x5180`

## callees

- `0x1ec0`

## string_xrefs

- `0x1ec1`: `Privilege User Group Member`
- `0x1f90`: `Privilege User Group Member`
- `0x1f05`: `SandboxHostSids.IsCallerAllowed: not authenticated: Privilege User Group Member`
- `0x1f6f`: `SandboxHostSids.IsCallerAllowed: not authenticated: Privilege User Group Member`

## pseudocode

```c

```

## disassembly

```asm
0x1ec0  ldarg.1
0x1ec1  ldstr    aPrivilegeUserG// "Privilege User Group Member"
0x1ec6  stind.ref
0x1ec7  ldarg.2
0x1ec8  ldstr    aNotAuthenticat// "Not Authenticated"
0x1ecd  stind.ref
0x1ece  call     class [System.ServiceModel]System.ServiceModel.ServiceSecurityContext [System.ServiceModel]System.ServiceModel.ServiceSecurityContext::get_Current()
0x1ed3  callvirt instance class [mscorlib]System.Security.Principal.WindowsIdentity [System.ServiceModel]System.ServiceModel.ServiceSecurityContext::get_WindowsIdentity()
0x1ed8  stloc.0
0x1ed9  ldloc.0
0x1eda  ldstr    aCalleridentity// "callerIdentity"
0x1edf  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1ee4  ldsfld   object Microsoft.Crm.Sandbox.SandboxHostSids::_lockObject
0x1ee9  stloc.1
0x1eea  ldc.i4.0
0x1eeb  stloc.2
0x1eec  ldloc.1
0x1eed  ldloca.s 2
0x1eef  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x1ef4  ldloc.0
0x1ef5  callvirt instance bool [mscorlib]System.Security.Claims.ClaimsIdentity::get_IsAuthenticated()
0x1efa  brtrue.s loc_1F19
0x1efc  ldnull
0x1efd  ldarg.0
0x1efe  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkContext::get_OrganizationId()
0x1f03  ldc.i4.s 0x28
0x1f05  ldstr    aSandboxhostsid_5// "SandboxHostSids.IsCallerAllowed: not au"...
0x1f0a  ldc.i4.0
0x1f0b  newarr   [mscorlib]System.Object
0x1f10  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1f15  ldc.i4.0
0x1f16  stloc.3
0x1f17  leave.s  loc_1F98
0x1f19  ldloc.0
0x1f1a  ldarg.0
0x1f1b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkContext::get_OrganizationId()
0x1f20  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x1f25  call     bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGroupForOrganization(class [mscorlib]System.Security.Principal.WindowsIdentity, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1f2a  brtrue.s loc_1F83
0x1f2c  call     class [Microsoft.Crm.Core]Microsoft.Crm.IUserInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.UserInfoProvider::get_Instance()
0x1f31  ldarg.0
0x1f32  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkContext::get_OrganizationId()
0x1f37  ldloc.0
0x1f38  callvirt instance class [mscorlib]System.Security.Principal.SecurityIdentifier [mscorlib]System.Security.Principal.WindowsIdentity::get_User()
0x1f3d  call     string [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.ActiveDirectoryUserInformation::GetUserToken(class [mscorlib]System.Security.Principal.SecurityIdentifier)
0x1f42  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IUserInfoProvider::GetCrmUserId(valuetype [mscorlib]System.Guid, string)
0x1f47  stloc.s  4
0x1f49  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1f4e  ldloc.s  4
0x1f50  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1f55  brtrue.s loc_1F66
0x1f57  ldloc.s  4
0x1f59  ldarg.0
0x1f5a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkContext::get_UserId()
0x1f5f  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1f64  brfalse.s loc_1F83
0x1f66  ldnull
0x1f67  ldarg.0
0x1f68  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkContext::get_OrganizationId()
0x1f6d  ldc.i4.s 0x28
0x1f6f  ldstr    aSandboxhostsid_5// "SandboxHostSids.IsCallerAllowed: not au"...
0x1f74  ldc.i4.0
0x1f75  newarr   [mscorlib]System.Object
0x1f7a  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1f7f  ldc.i4.0
0x1f80  stloc.3
0x1f81  leave.s  loc_1F98
0x1f83  leave.s  loc_1F8F
0x1f85  ldloc.2
0x1f86  brfalse.s loc_1F8E
0x1f88  ldloc.1
0x1f89  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x1f8e  endfinally
0x1f8f  ldarg.2
0x1f90  ldstr    aPrivilegeUserG// "Privilege User Group Member"
0x1f95  stind.ref
0x1f96  ldc.i4.1
0x1f97  ret
0x1f98  ldloc.3
0x1f99  ret
```
