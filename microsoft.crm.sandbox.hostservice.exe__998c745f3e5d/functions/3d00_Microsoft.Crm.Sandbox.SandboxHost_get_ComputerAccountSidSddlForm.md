# Microsoft.Crm.Sandbox.SandboxHost::get_ComputerAccountSidSddlForm

- ea: `0x3d00`
- end: `0x3df6`
- name: `Microsoft.Crm.Sandbox.SandboxHost::get_ComputerAccountSidSddlForm`
- size: `246`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x3e00`

## callees

- `0x3d00`

## string_xrefs

- `0x3d11`: `SandboxHost.ComputerAccountSidSddlForm: enter`
- `0x3d39`: `SandboxHost.ComputerAccountSidSddlForm: domain.Name: {0}`
- `0x3d7f`: `SandboxHost.ComputerAccountSidSddlForm: account: {0}`
- `0x3dcc`: `SandboxHost.ComputerAccountSidSddlForm: _computerAccountSidSddlForm: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x3d00  ldsfld   string Microsoft.Crm.Sandbox.SandboxHost::_computerAccountSidSddlForm
0x3d05  brtrue   loc_3DF0
0x3d0a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3d0f  ldc.i4.s 0x26
0x3d11  ldstr    aSandboxhostCom// "SandboxHost.ComputerAccountSidSddlForm:"...
0x3d16  ldc.i4.0
0x3d17  newarr   [mscorlib]System.Object
0x3d1c  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3d21  call     class [System.DirectoryServices]System.DirectoryServices.ActiveDirectory.Domain [System.DirectoryServices]System.DirectoryServices.ActiveDirectory.Domain::GetComputerDomain()
0x3d26  stloc.0
0x3d27  ldloc.0
0x3d28  ldstr    aDomain// "domain"
0x3d2d  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x3d32  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3d37  ldc.i4.s 0x26
0x3d39  ldstr    aSandboxhostCom_0// "SandboxHost.ComputerAccountSidSddlForm:"...
0x3d3e  ldc.i4.1
0x3d3f  newarr   [mscorlib]System.Object
0x3d44  dup
0x3d45  ldc.i4.0
0x3d46  ldloc.0
0x3d47  callvirt instance string [System.DirectoryServices]System.DirectoryServices.ActiveDirectory.ActiveDirectoryPartition::get_Name()
0x3d4c  stelem.ref
0x3d4d  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3d52  ldloc.0
0x3d53  callvirt instance string [System.DirectoryServices]System.DirectoryServices.ActiveDirectory.ActiveDirectoryPartition::get_Name()
0x3d58  call     string [mscorlib]System.Environment::get_MachineName()
0x3d5d  ldstr    asc_14876// "$"
0x3d62  call     string [mscorlib]System.String::Concat(string, string)
0x3d67  newobj   instance void [mscorlib]System.Security.Principal.NTAccount::.ctor(string, string)
0x3d6c  stloc.1
0x3d6d  ldloc.1
0x3d6e  ldstr    aAccount// "account"
0x3d73  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x3d78  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3d7d  ldc.i4.s 0x26
0x3d7f  ldstr    aSandboxhostCom_1// "SandboxHost.ComputerAccountSidSddlForm:"...
0x3d84  ldc.i4.1
0x3d85  newarr   [mscorlib]System.Object
0x3d8a  dup
0x3d8b  ldc.i4.0
0x3d8c  ldloc.1
0x3d8d  stelem.ref
0x3d8e  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3d93  ldloc.1
0x3d94  ldtoken  [mscorlib]System.Security.Principal.SecurityIdentifier
0x3d99  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d9e  callvirt instance class [mscorlib]System.Security.Principal.IdentityReference [mscorlib]System.Security.Principal.IdentityReference::Translate(class [mscorlib]System.Type)
0x3da3  castclass [mscorlib]System.Security.Principal.SecurityIdentifier
0x3da8  stloc.2
0x3da9  ldloc.2
0x3daa  ldstr    aSid// "sid"
0x3daf  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x3db4  ldloc.1
0x3db5  ldstr    asc_1473C// ";"
0x3dba  ldloc.2
0x3dbb  call     string [mscorlib]System.String::Concat(object, object, object)
0x3dc0  stsfld   string Microsoft.Crm.Sandbox.SandboxHost::_computerAccountSidSddlForm
0x3dc5  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3dca  ldc.i4.s 0x26
0x3dcc  ldstr    aSandboxhostCom_2// "SandboxHost.ComputerAccountSidSddlForm:"...
0x3dd1  ldc.i4.1
0x3dd2  newarr   [mscorlib]System.Object
0x3dd7  dup
0x3dd8  ldc.i4.0
0x3dd9  ldsfld   string Microsoft.Crm.Sandbox.SandboxHost::_computerAccountSidSddlForm
0x3dde  stelem.ref
0x3ddf  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3de4  leave.s  loc_3DF0
0x3de6  ldloc.0
0x3de7  brfalse.s loc_3DEF
0x3de9  ldloc.0
0x3dea  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3def  endfinally
0x3df0  ldsfld   string Microsoft.Crm.Sandbox.SandboxHost::_computerAccountSidSddlForm
0x3df5  ret
```
