# Microsoft.Crm.Sandbox.SandboxHost::AuthenticateCaller

- ea: `0x49d0`
- end: `0x4ad3`
- name: `Microsoft.Crm.Sandbox.SandboxHost::AuthenticateCaller`
- size: `259`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x3e00`
- `0x4670`

## callees

- `0x49d0`
- `0x4e50`

## string_xrefs

- `0x49fd`: `AuthenticateCaller: Well Known SID - access allowed: {0}`
- `0x4a2b`: `AuthenticateCaller: Caller is in PrivUserGroup - access allowed: {0}`
- `0x4a84`: `Access Denied. Reference number for administrators or support: #`

## pseudocode

```c

```

## disassembly

```asm
0x49d0  call     class [System.ServiceModel]System.ServiceModel.ServiceSecurityContext [System.ServiceModel]System.ServiceModel.ServiceSecurityContext::get_Current()
0x49d5  callvirt instance class [mscorlib]System.Security.Principal.WindowsIdentity [System.ServiceModel]System.ServiceModel.ServiceSecurityContext::get_WindowsIdentity()
0x49da  stloc.0
0x49db  ldloc.0
0x49dc  callvirt instance class [mscorlib]System.Security.Principal.SecurityIdentifier [mscorlib]System.Security.Principal.WindowsIdentity::get_User()
0x49e1  stloc.1
0x49e2  ldloc.1
0x49e3  ldc.i4.s 0x16
0x49e5  callvirt instance bool [mscorlib]System.Security.Principal.SecurityIdentifier::IsWellKnown(valuetype [mscorlib]System.Security.Principal.WellKnownSidType)
0x49ea  brtrue.s loc_49F6
0x49ec  ldloc.1
0x49ed  ldc.i4.s 0x18
0x49ef  callvirt instance bool [mscorlib]System.Security.Principal.SecurityIdentifier::IsWellKnown(valuetype [mscorlib]System.Security.Principal.WellKnownSidType)
0x49f4  brfalse.s loc_4A17
0x49f6  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x49fb  ldc.i4.s 0x21
0x49fd  ldstr    aAuthenticateca// "AuthenticateCaller: Well Known SID - ac"...
0x4a02  ldc.i4.1
0x4a03  newarr   [mscorlib]System.Object
0x4a08  dup
0x4a09  ldc.i4.0
0x4a0a  ldloc.0
0x4a0b  callvirt instance string [mscorlib]System.Security.Claims.ClaimsIdentity::get_Name()
0x4a10  stelem.ref
0x4a11  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4a16  ret
0x4a17  ldloc.0
0x4a18  call     unsigned int8[] Microsoft.Crm.Sandbox.SandboxHost::get_PrivUserGroupSid()
0x4a1d  call     bool [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::IsIdentityInGroup(class [mscorlib]System.Security.Principal.WindowsIdentity, unsigned int8[])
0x4a22  brfalse.s loc_4A45
0x4a24  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4a29  ldc.i4.s 0x21
0x4a2b  ldstr    aAuthenticateca_0// "AuthenticateCaller: Caller is in PrivUs"...
0x4a30  ldc.i4.1
0x4a31  newarr   [mscorlib]System.Object
0x4a36  dup
0x4a37  ldc.i4.0
0x4a38  ldloc.0
0x4a39  callvirt instance string [mscorlib]System.Security.Claims.ClaimsIdentity::get_Name()
0x4a3e  stelem.ref
0x4a3f  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4a44  ret
0x4a45  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::.ctor()
0x4a4a  stloc.s  4
0x4a4c  ldloc.s  4
0x4a4e  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::get_EventSource()
0x4a53  ldc.i4.1
0x4a54  ldc.i4   0xC0004F04
0x4a59  conv.u8
0x4a5a  ldc.i4.2
0x4a5b  newarr   [mscorlib]System.Object
0x4a60  dup
0x4a61  ldc.i4.0
0x4a62  call     string [mscorlib]System.Environment::get_MachineName()
0x4a67  stelem.ref
0x4a68  dup
0x4a69  ldc.i4.1
0x4a6a  ldloc.0
0x4a6b  callvirt instance string [mscorlib]System.Security.Claims.ClaimsIdentity::get_Name()
0x4a70  stelem.ref
0x4a71  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::WriteEntry(string, valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0x4a76  leave.s  loc_4A84
0x4a78  ldloc.s  4
0x4a7a  brfalse.s loc_4A83
0x4a7c  ldloc.s  4
0x4a7e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4a83  endfinally
0x4a84  ldstr    aAccessDeniedRe// "Access Denied. Reference number for adm"...
0x4a89  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::get_ReferenceId()
0x4a8e  call     string [mscorlib]System.String::Concat(string, string)
0x4a93  stloc.2
0x4a94  ldloc.2
0x4a95  ldstr    asc_12434// ": "
0x4a9a  ldloc.0
0x4a9b  callvirt instance string [mscorlib]System.Security.Claims.ClaimsIdentity::get_Name()
0x4aa0  ldstr    aIsNotInPrivuse// " is not in PrivUserGroup"
0x4aa5  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x4aaa  stloc.3
0x4aab  ldnull
0x4aac  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4ab1  ldc.i4.s 0x21
0x4ab3  ldstr    a0// "{0}"
0x4ab8  ldc.i4.1
0x4ab9  newarr   [mscorlib]System.Object
0x4abe  dup
0x4abf  ldc.i4.0
0x4ac0  ldloc.3
0x4ac1  stelem.ref
0x4ac2  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4ac7  ldloc.2
0x4ac8  ldc.i4   0x80048405
0x4acd  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x4ad2  throw
```
