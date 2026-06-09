# Microsoft.Crm.Sandbox.SandboxWorkerAccountManager::CreateLocalAccount

- ea: `0x5470`
- end: `0x54fd`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerAccountManager::CreateLocalAccount`
- size: `141`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x5380`

## callees

- `0x5170`
- `0x51c0`
- `0x5470`
- `0x56a0`

## string_xrefs

- `0x54c2`: `SandboxWorkerAccountManager.CreateLocalAccount: Error creating user {0} - Exception : {1}`
- `0x54e2`: `SandboxWorkerAccountManager.CreateLocalAccount: The Sandbox Processing Service is unable to create a local windows account due to an UnauthorizedAccessException: {0}. Please make sure the account running Sandbox Service has administrative privileges on the machine.`

## pseudocode

```c

```

## disassembly

```asm
0x5470  ldc.i4.0
0x5471  newobj   instance void [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.PrincipalContext::.ctor(valuetype [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.ContextType)
0x5476  stloc.0
0x5477  ldarg.0
0x5478  ldarg.1
0x5479  newobj   instance void Microsoft.Crm.Sandbox.SandboxWorkerAccount::.ctor(string username, string password)
0x547e  stloc.1
0x547f  ldloc.0
0x5480  newobj   instance void [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.UserPrincipal::.ctor(class [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.PrincipalContext)
0x5485  stloc.2
0x5486  ldloc.2
0x5487  ldarg.1
0x5488  callvirt instance void [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.AuthenticablePrincipal::SetPassword(string)
0x548d  ldloc.2
0x548e  ldarg.0
0x548f  callvirt instance void [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.Principal::set_Name(string)
0x5494  ldloc.2
0x5495  ldstr    aSandboxWorkerP// "Sandbox Worker Process Account"
0x549a  callvirt instance void [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.Principal::set_Description(string)
0x549f  ldloc.2
0x54a0  ldc.i4.1
0x54a1  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x54a6  callvirt instance void [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.AuthenticablePrincipal::set_Enabled(valuetype [mscorlib]System.Nullable`1<bool>)
0x54ab  ldloc.2
0x54ac  callvirt instance void [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.Principal::Save()
0x54b1  ldloc.1
0x54b2  ldloc.2
0x54b3  callvirt instance void Microsoft.Crm.Sandbox.SandboxWorkerAccount::set_UserPrincipal(class [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.UserPrincipal value)
0x54b8  leave.s  loc_54FB
0x54ba  stloc.3
0x54bb  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x54c0  ldc.i4.s 0x21
0x54c2  ldstr    aSandboxworkera_3// "SandboxWorkerAccountManager.CreateLocal"...
0x54c7  ldc.i4.2
0x54c8  newarr   [mscorlib]System.Object
0x54cd  dup
0x54ce  ldc.i4.0
0x54cf  ldarg.0
0x54d0  stelem.ref
0x54d1  dup
0x54d2  ldc.i4.1
0x54d3  ldloc.3
0x54d4  stelem.ref
0x54d5  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x54da  ldloc.3
0x54db  isinst   [mscorlib]System.UnauthorizedAccessException
0x54e0  brfalse.s loc_54F9
0x54e2  ldstr    aSandboxworkera_4// "SandboxWorkerAccountManager.CreateLocal"...
0x54e7  ldloc.3
0x54e8  call     string [mscorlib]System.String::Format(string, object)
0x54ed  dup
0x54ee  call     void Microsoft.Crm.Sandbox.SandboxWorkerAccountManager::WriteEventLogEntry(string errorMessage)
0x54f3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x54f8  throw
0x54f9  leave.s  loc_54FB
0x54fb  ldloc.1
0x54fc  ret
```
