# Microsoft.Crm.Sandbox.SandboxWorkerAccountManager::Start

- ea: `0x51e0`
- end: `0x527f`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerAccountManager::Start`
- size: `159`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x140`

## callees

- `0x51e0`
- `0x5280`
- `0x5380`
- `0x56a0`

## string_xrefs

- `0x51e7`: `SandboxWorkerAccountManager.Start: The Sandbox Processing Service is running on a domain controller. Sandbox Worker Account Isolation requires the Sandbox Processing Service to be run on a domain member as it needs to create local users. Please make sure that this computer is not a domain controller if Sandbox Worker Account Isolation is enabled.`
- `0x5221`: `SandboxWorkerAccountManager.Start: Could not find the 'SandboxWorkerProcess' group. Please create it in your local active directory. It is required to enable worker account isolation.`

## pseudocode

```c

```

## disassembly

```asm
0x51e0  call     bool Microsoft.Crm.Sandbox.SandboxWorkerAccountManager::IsDomainController()
0x51e5  brfalse.s loc_520E
0x51e7  ldstr    aSandboxworkera// "SandboxWorkerAccountManager.Start: The "...
0x51ec  stloc.0
0x51ed  ldnull
0x51ee  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x51f3  ldc.i4.s 0x21
0x51f5  ldloc.0
0x51f6  ldc.i4.0
0x51f7  newarr   [mscorlib]System.Object
0x51fc  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5201  ldloc.0
0x5202  call     void Microsoft.Crm.Sandbox.SandboxWorkerAccountManager::WriteEventLogEntry(string errorMessage)
0x5207  ldloc.0
0x5208  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x520d  throw
0x520e  ldc.i4.0
0x520f  newobj   instance void [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.PrincipalContext::.ctor(valuetype [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.ContextType)
0x5214  ldc.i4.1
0x5215  ldstr    aSandboxworkerp// "SandboxWorkerProcess"
0x521a  call     class [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.GroupPrincipal [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.GroupPrincipal::FindByIdentity(class [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.PrincipalContext, valuetype [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.IdentityType, string)
0x521f  brtrue.s loc_5248
0x5221  ldstr    aSandboxworkera_0// "SandboxWorkerAccountManager.Start: Coul"...
0x5226  stloc.1
0x5227  ldnull
0x5228  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x522d  ldc.i4.s 0x21
0x522f  ldloc.1
0x5230  ldc.i4.0
0x5231  newarr   [mscorlib]System.Object
0x5236  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x523b  ldloc.1
0x523c  call     void Microsoft.Crm.Sandbox.SandboxWorkerAccountManager::WriteEventLogEntry(string errorMessage)
0x5241  ldloc.1
0x5242  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x5247  throw
0x5248  ldc.i4.0
0x5249  ldc.i4.1
0x524a  call     T0x2B000004
0x524f  call     void Microsoft.Crm.Sandbox.SandboxWorkerAccountManager::TryAddAccounts(int32 minReadyAccounts)
0x5254  ldnull
0x5255  ldftn    void Microsoft.Crm.Sandbox.SandboxWorkerAccountManager::BackgroundThread(object minReadyAccounts)
0x525b  newobj   instance void [mscorlib]System.Threading.ParameterizedThreadStart::.ctor(object, native int)
0x5260  newobj   instance void [mscorlib]System.Threading.Thread::.ctor(class [mscorlib]System.Threading.ParameterizedThreadStart)
0x5265  stsfld   class [mscorlib]System.Threading.Thread Microsoft.Crm.Sandbox.SandboxWorkerAccountManager::_backgroundThread
0x526a  ldsfld   class [mscorlib]System.Threading.Thread Microsoft.Crm.Sandbox.SandboxWorkerAccountManager::_backgroundThread
0x526f  ldsfld   int32 Microsoft.Crm.Sandbox.SandboxWorkerAccountManager::_minReadyAccounts
0x5274  box      [mscorlib]System.Int32
0x5279  callvirt instance void [mscorlib]System.Threading.Thread::Start(object)
0x527e  ret
```
