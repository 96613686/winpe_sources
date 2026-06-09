# Microsoft.Crm.Sandbox.SandboxWorkerManager::CheckServiceAccount

- ea: `0x88d0`
- end: `0x8c58`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerManager::CheckServiceAccount`
- size: `904`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0xc9f0`

## callees

- `0x4e50`
- `0x4e70`
- `0x88d0`

## string_xrefs

- `0x88fa`: `SandboxWorkerManager.CheckServiceAccount: enter`
- `0x892a`: `_serviceAccountIdentity`
- `0x8976`: `SandboxWorkerManager.CheckServiceAccount: _serviceAccountIdentity.Name: {0}`
- `0x89e3`: `SandboxHost.PrivUserGroupSid`
- `0x8a2f`: `SandboxWorkerManager.CheckServiceAccount: _privUserGroupName: {0}`
- `0x8a90`: `SandboxWorkerManager.CheckServiceAccount: _sqlAccessGroupName: {0}`
- `0x8ac7`: `_localAdminGroupSid`
- `0x8b06`: `SandboxWorkerManager.CheckServiceAccount: _localAdminGroupName: {0}`
- `0x8b7e`: ` (SQLAccessGroup)`
- `0x8c40`: `SandboxWorkerManager.CheckServiceAccount: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x88d0  ldc.i4.s 0xB
0x88d2  ldc.i4.1
0x88d3  call     T0x2B000001
0x88d8  ldc.i4.0
0x88d9  cgt
0x88db  brfalse.s loc_88EE
0x88dd  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x88e2  ldsfld   valuetype [mscorlib]System.DateTime Microsoft.Crm.Sandbox.SandboxWorkerManager::_timeToCheck
0x88e7  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x88ec  brfalse.s loc_88F3
0x88ee  leave    loc_8C57
0x88f3  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x88f8  ldc.i4.s 0x21
0x88fa  ldstr    aSandboxworkerm_93// "SandboxWorkerManager.CheckServiceAccoun"...
0x88ff  ldc.i4.0
0x8900  newarr   [mscorlib]System.Object
0x8905  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x890a  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x890f  stloc.3
0x8910  ldloca.s 3
0x8912  ldc.r8   24.0
0x891b  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddHours(float64)
0x8920  stsfld   valuetype [mscorlib]System.DateTime Microsoft.Crm.Sandbox.SandboxWorkerManager::_timeToCheck
0x8925  ldsfld   class [mscorlib]System.Security.Principal.WindowsIdentity Microsoft.Crm.Sandbox.SandboxWorkerManager::_serviceAccountIdentity
0x892a  ldstr    aServiceaccount_0// "_serviceAccountIdentity"
0x892f  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x8934  ldsfld   class [mscorlib]System.Security.Principal.WindowsIdentity Microsoft.Crm.Sandbox.SandboxWorkerManager::_serviceAccountIdentity
0x8939  callvirt instance class [mscorlib]System.Security.Principal.SecurityIdentifier [mscorlib]System.Security.Principal.WindowsIdentity::get_User()
0x893e  ldc.i4.s 0x18
0x8940  callvirt instance bool [mscorlib]System.Security.Principal.SecurityIdentifier::IsWellKnown(valuetype [mscorlib]System.Security.Principal.WellKnownSidType)
0x8945  brtrue.s loc_896D
0x8947  ldsfld   class [mscorlib]System.Security.Principal.WindowsIdentity Microsoft.Crm.Sandbox.SandboxWorkerManager::_serviceAccountIdentity
0x894c  callvirt instance class [mscorlib]System.Security.Principal.SecurityIdentifier [mscorlib]System.Security.Principal.WindowsIdentity::get_User()
0x8951  ldc.i4.s 0x17
0x8953  callvirt instance bool [mscorlib]System.Security.Principal.SecurityIdentifier::IsWellKnown(valuetype [mscorlib]System.Security.Principal.WellKnownSidType)
0x8958  brtrue.s loc_896D
0x895a  ldsfld   class [mscorlib]System.Security.Principal.WindowsIdentity Microsoft.Crm.Sandbox.SandboxWorkerManager::_serviceAccountIdentity
0x895f  callvirt instance class [mscorlib]System.Security.Principal.SecurityIdentifier [mscorlib]System.Security.Principal.WindowsIdentity::get_User()
0x8964  ldc.i4.s 0x16
0x8966  callvirt instance bool [mscorlib]System.Security.Principal.SecurityIdentifier::IsWellKnown(valuetype [mscorlib]System.Security.Principal.WellKnownSidType)
0x896b  br.s     loc_896E
0x896d  ldc.i4.1
0x896e  stloc.0
0x896f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8974  ldc.i4.s 0x21
0x8976  ldstr    aSandboxworkerm_94// "SandboxWorkerManager.CheckServiceAccoun"...
0x897b  ldc.i4.1
0x897c  newarr   [mscorlib]System.Object
0x8981  dup
0x8982  ldc.i4.0
0x8983  ldsfld   class [mscorlib]System.Security.Principal.WindowsIdentity Microsoft.Crm.Sandbox.SandboxWorkerManager::_serviceAccountIdentity
0x8988  callvirt instance string [mscorlib]System.Security.Claims.ClaimsIdentity::get_Name()
0x898d  stelem.ref
0x898e  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8993  ldloc.0
0x8994  brfalse.s loc_89DE
0x8996  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::.ctor()
0x899b  stloc.s  4
0x899d  ldloc.s  4
0x899f  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::get_EventSource()
0x89a4  ldc.i4.2
0x89a5  ldc.i4   0x80004F1F
0x89aa  conv.u8
0x89ab  ldc.i4.2
0x89ac  newarr   [mscorlib]System.Object
0x89b1  dup
0x89b2  ldc.i4.0
0x89b3  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::get_ProcessInfo()
0x89b8  stelem.ref
0x89b9  dup
0x89ba  ldc.i4.1
0x89bb  ldsfld   class [mscorlib]System.Security.Principal.WindowsIdentity Microsoft.Crm.Sandbox.SandboxWorkerManager::_serviceAccountIdentity
0x89c0  callvirt instance string [mscorlib]System.Security.Claims.ClaimsIdentity::get_Name()
0x89c5  stelem.ref
0x89c6  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::WriteEntry(string, valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0x89cb  leave.s  loc_89D9
0x89cd  ldloc.s  4
0x89cf  brfalse.s loc_89D8
0x89d1  ldloc.s  4
0x89d3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x89d8  endfinally
0x89d9  leave    loc_8C57
0x89de  call     unsigned int8[] Microsoft.Crm.Sandbox.SandboxHost::get_PrivUserGroupSid()
0x89e3  ldstr    aSandboxhostPri// "SandboxHost.PrivUserGroupSid"
0x89e8  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x89ed  ldsfld   string Microsoft.Crm.Sandbox.SandboxWorkerManager::_privUserGroupName
0x89f2  brtrue.s loc_8A47
0x89f4  call     unsigned int8[] Microsoft.Crm.Sandbox.SandboxHost::get_PrivUserGroupSid()
0x89f9  ldc.i4.0
0x89fa  newobj   instance void [mscorlib]System.Security.Principal.SecurityIdentifier::.ctor(unsigned int8[], int32)
0x89ff  ldtoken  [mscorlib]System.Security.Principal.NTAccount
0x8a04  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8a09  callvirt instance class [mscorlib]System.Security.Principal.IdentityReference [mscorlib]System.Security.Principal.IdentityReference::Translate(class [mscorlib]System.Type)
0x8a0e  castclass [mscorlib]System.Security.Principal.NTAccount
0x8a13  dup
0x8a14  ldstr    aAccount// "account"
0x8a19  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x8a1e  callvirt instance string [mscorlib]System.Object::ToString()
0x8a23  stsfld   string Microsoft.Crm.Sandbox.SandboxWorkerManager::_privUserGroupName
0x8a28  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8a2d  ldc.i4.s 0x21
0x8a2f  ldstr    aSandboxworkerm_95// "SandboxWorkerManager.CheckServiceAccoun"...
0x8a34  ldc.i4.1
0x8a35  newarr   [mscorlib]System.Object
0x8a3a  dup
0x8a3b  ldc.i4.0
0x8a3c  ldsfld   string Microsoft.Crm.Sandbox.SandboxWorkerManager::_privUserGroupName
0x8a41  stelem.ref
0x8a42  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8a47  ldsfld   string Microsoft.Crm.Sandbox.SandboxWorkerManager::_sqlAccessGroupName
0x8a4c  brtrue.s loc_8AA8
0x8a4e  call     unsigned int8[] Microsoft.Crm.Sandbox.SandboxHost::get_SqlAccessGroupSid()
0x8a53  brfalse.s loc_8AA8
0x8a55  call     unsigned int8[] Microsoft.Crm.Sandbox.SandboxHost::get_SqlAccessGroupSid()
0x8a5a  ldc.i4.0
0x8a5b  newobj   instance void [mscorlib]System.Security.Principal.SecurityIdentifier::.ctor(unsigned int8[], int32)
0x8a60  ldtoken  [mscorlib]System.Security.Principal.NTAccount
0x8a65  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8a6a  callvirt instance class [mscorlib]System.Security.Principal.IdentityReference [mscorlib]System.Security.Principal.IdentityReference::Translate(class [mscorlib]System.Type)
0x8a6f  castclass [mscorlib]System.Security.Principal.NTAccount
0x8a74  dup
0x8a75  ldstr    aAccount// "account"
0x8a7a  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x8a7f  callvirt instance string [mscorlib]System.Object::ToString()
0x8a84  stsfld   string Microsoft.Crm.Sandbox.SandboxWorkerManager::_sqlAccessGroupName
0x8a89  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8a8e  ldc.i4.s 0x21
0x8a90  ldstr    aSandboxworkerm_96// "SandboxWorkerManager.CheckServiceAccoun"...
0x8a95  ldc.i4.1
0x8a96  newarr   [mscorlib]System.Object
0x8a9b  dup
0x8a9c  ldc.i4.0
0x8a9d  ldsfld   string Microsoft.Crm.Sandbox.SandboxWorkerManager::_sqlAccessGroupName
0x8aa2  stelem.ref
0x8aa3  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8aa8  ldsfld   class [mscorlib]System.Security.Principal.SecurityIdentifier Microsoft.Crm.Sandbox.SandboxWorkerManager::_localAdminGroupSid
0x8aad  ldnull
0x8aae  call     bool [mscorlib]System.Security.Principal.SecurityIdentifier::op_Equality(class [mscorlib]System.Security.Principal.SecurityIdentifier, class [mscorlib]System.Security.Principal.SecurityIdentifier)
0x8ab3  brfalse.s loc_8B1E
0x8ab5  ldc.i4.s 0x1A
0x8ab7  ldnull
0x8ab8  newobj   instance void [mscorlib]System.Security.Principal.SecurityIdentifier::.ctor(valuetype [mscorlib]System.Security.Principal.WellKnownSidType, class [mscorlib]System.Security.Principal.SecurityIdentifier)
0x8abd  stsfld   class [mscorlib]System.Security.Principal.SecurityIdentifier Microsoft.Crm.Sandbox.SandboxWorkerManager::_localAdminGroupSid
0x8ac2  ldsfld   class [mscorlib]System.Security.Principal.SecurityIdentifier Microsoft.Crm.Sandbox.SandboxWorkerManager::_localAdminGroupSid
0x8ac7  ldstr    aLocaladmingrou// "_localAdminGroupSid"
0x8acc  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x8ad1  ldsfld   class [mscorlib]System.Security.Principal.SecurityIdentifier Microsoft.Crm.Sandbox.SandboxWorkerManager::_localAdminGroupSid
0x8ad6  ldtoken  [mscorlib]System.Security.Principal.NTAccount
0x8adb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8ae0  callvirt instance class [mscorlib]System.Security.Principal.IdentityReference [mscorlib]System.Security.Principal.IdentityReference::Translate(class [mscorlib]System.Type)
0x8ae5  castclass [mscorlib]System.Security.Principal.NTAccount
0x8aea  dup
0x8aeb  ldstr    aAccount// "account"
0x8af0  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x8af5  callvirt instance string [mscorlib]System.Object::ToString()
0x8afa  stsfld   string Microsoft.Crm.Sandbox.SandboxWorkerManager::_localAdminGroupName
0x8aff  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8b04  ldc.i4.s 0x21
0x8b06  ldstr    aSandboxworkerm_97// "SandboxWorkerManager.CheckServiceAccoun"...
0x8b0b  ldc.i4.1
0x8b0c  newarr   [mscorlib]System.Object
0x8b11  dup
0x8b12  ldc.i4.0
0x8b13  ldsfld   string Microsoft.Crm.Sandbox.SandboxWorkerManager::_localAdminGroupName
0x8b18  stelem.ref
0x8b19  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8b1e  ldnull
0x8b1f  stloc.1
0x8b20  ldsfld   class [mscorlib]System.Security.Principal.WindowsIdentity Microsoft.Crm.Sandbox.SandboxWorkerManager::_serviceAccountIdentity
0x8b25  call     unsigned int8[] Microsoft.Crm.Sandbox.SandboxHost::get_PrivUserGroupSid()
0x8b2a  call     bool [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::IsIdentityInGroup(class [mscorlib]System.Security.Principal.WindowsIdentity, unsigned int8[])
0x8b2f  brfalse.s loc_8B51
0x8b31  ldloc.1
0x8b32  brfalse.s loc_8B40
0x8b34  ldloc.1
0x8b35  ldstr    asc_1CB3A// "; "
0x8b3a  call     string [mscorlib]System.String::Concat(string, string)
0x8b3f  stloc.1
0x8b40  ldloc.1
0x8b41  ldsfld   string Microsoft.Crm.Sandbox.SandboxWorkerManager::_privUserGroupName
0x8b46  ldstr    aPrivusergroup// " (PrivUserGroup)"
0x8b4b  call     string [mscorlib]System.String::Concat(string, string, string)
0x8b50  stloc.1
0x8b51  call     unsigned int8[] Microsoft.Crm.Sandbox.SandboxHost::get_SqlAccessGroupSid()
0x8b56  brfalse.s loc_8B89
0x8b58  ldsfld   class [mscorlib]System.Security.Principal.WindowsIdentity Microsoft.Crm.Sandbox.SandboxWorkerManager::_serviceAccountIdentity
0x8b5d  call     unsigned int8[] Microsoft.Crm.Sandbox.SandboxHost::get_SqlAccessGroupSid()
0x8b62  call     bool [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::IsIdentityInGroup(class [mscorlib]System.Security.Principal.WindowsIdentity, unsigned int8[])
0x8b67  brfalse.s loc_8B89
0x8b69  ldloc.1
0x8b6a  brfalse.s loc_8B78
0x8b6c  ldloc.1
0x8b6d  ldstr    asc_1CB3A// "; "
0x8b72  call     string [mscorlib]System.String::Concat(string, string)
0x8b77  stloc.1
0x8b78  ldloc.1
0x8b79  ldsfld   string Microsoft.Crm.Sandbox.SandboxWorkerManager::_sqlAccessGroupName
0x8b7e  ldstr    aSqlaccessgroup_0// " (SQLAccessGroup)"
0x8b83  call     string [mscorlib]System.String::Concat(string, string, string)
0x8b88  stloc.1
0x8b89  ldnull
0x8b8a  stloc.2
0x8b8b  ldsfld   class [mscorlib]System.Security.Principal.SecurityIdentifier Microsoft.Crm.Sandbox.SandboxWorkerManager::_localAdminGroupSid
0x8b90  ldnull
0x8b91  call     bool [mscorlib]System.Security.Principal.SecurityIdentifier::op_Inequality(class [mscorlib]System.Security.Principal.SecurityIdentifier, class [mscorlib]System.Security.Principal.SecurityIdentifier)
0x8b96  brfalse.s loc_8BB4
0x8b98  ldsfld   class [mscorlib]System.Security.Principal.SecurityIdentifier Microsoft.Crm.Sandbox.SandboxWorkerManager::_localAdminGroupSid
0x8b9d  callvirt instance int32 [mscorlib]System.Security.Principal.SecurityIdentifier::get_BinaryLength()
0x8ba2  newarr   [mscorlib]System.Byte
0x8ba7  stloc.2
0x8ba8  ldsfld   class [mscorlib]System.Security.Principal.SecurityIdentifier Microsoft.Crm.Sandbox.SandboxWorkerManager::_localAdminGroupSid
0x8bad  ldloc.2
0x8bae  ldc.i4.0
0x8baf  callvirt instance void [mscorlib]System.Security.Principal.SecurityIdentifier::GetBinaryForm(unsigned int8[], int32)
0x8bb4  ldloc.2
0x8bb5  brfalse.s loc_8BE4
0x8bb7  ldsfld   class [mscorlib]System.Security.Principal.WindowsIdentity Microsoft.Crm.Sandbox.SandboxWorkerManager::_serviceAccountIdentity
0x8bbc  ldloc.2
0x8bbd  call     bool [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::IsIdentityInGroup(class [mscorlib]System.Security.Principal.WindowsIdentity, unsigned int8[])
0x8bc2  brfalse.s loc_8BE4
0x8bc4  ldloc.1
0x8bc5  brfalse.s loc_8BD3
0x8bc7  ldloc.1
0x8bc8  ldstr    asc_1CB3A// "; "
0x8bcd  call     string [mscorlib]System.String::Concat(string, string)
0x8bd2  stloc.1
0x8bd3  ldloc.1
0x8bd4  ldsfld   string Microsoft.Crm.Sandbox.SandboxWorkerManager::_localAdminGroupName
0x8bd9  ldstr    aLocalAdministr// " (Local Administrators)"
0x8bde  call     string [mscorlib]System.String::Concat(string, string, string)
0x8be3  stloc.1
0x8be4  ldloc.1
0x8be5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8bea  brtrue.s loc_8C33
0x8bec  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::.ctor()
0x8bf1  stloc.s  5
0x8bf3  ldloc.s  5
0x8bf5  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::get_EventSource()
0x8bfa  ldc.i4.2
0x8bfb  ldc.i4   0x80004F1D
0x8c00  conv.u8
0x8c01  ldc.i4.3
0x8c02  newarr   [mscorlib]System.Object
0x8c07  dup
0x8c08  ldc.i4.0
0x8c09  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::get_ProcessInfo()
0x8c0e  stelem.ref
0x8c0f  dup
0x8c10  ldc.i4.1
0x8c11  ldsfld   class [mscorlib]System.Security.Principal.WindowsIdentity Microsoft.Crm.Sandbox.SandboxWorkerManager::_serviceAccountIdentity
0x8c16  callvirt instance string [mscorlib]System.Security.Claims.ClaimsIdentity::get_Name()
0x8c1b  stelem.ref
0x8c1c  dup
0x8c1d  ldc.i4.2
0x8c1e  ldloc.1
0x8c1f  stelem.ref
0x8c20  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::WriteEntry(string, valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0x8c25  leave.s  loc_8C33
0x8c27  ldloc.s  5
0x8c29  brfalse.s loc_8C32
0x8c2b  ldloc.s  5
0x8c2d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8c32  endfinally
0x8c33  leave.s  loc_8C57
0x8c35  stloc.s  6
0x8c37  ldloc.s  6
0x8c39  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8c3e  ldc.i4.s 0x21
0x8c40  ldstr    aSandboxworkerm_98// "SandboxWorkerManager.CheckServiceAccoun"...
0x8c45  ldc.i4.1
0x8c46  newarr   [mscorlib]System.Object
0x8c4b  dup
0x8c4c  ldc.i4.0
0x8c4d  ldloc.s  6
0x8c4f  stelem.ref
0x8c50  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8c55  leave.s  loc_8C57
0x8c57  ret
```
