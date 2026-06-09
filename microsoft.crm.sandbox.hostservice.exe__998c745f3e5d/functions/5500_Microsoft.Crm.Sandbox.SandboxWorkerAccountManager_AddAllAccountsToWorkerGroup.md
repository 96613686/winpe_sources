# Microsoft.Crm.Sandbox.SandboxWorkerAccountManager::AddAllAccountsToWorkerGroup

- ea: `0x5500`
- end: `0x5590`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerAccountManager::AddAllAccountsToWorkerGroup`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x5380`

## callees

- `0x51b0`
- `0x5500`

## string_xrefs

- `0x551d`: `SandboxWorkerAccountManager.AddAllAccountsToWorkerGroup: Could not find the SandboxWorkerProcess group. Please create it in your local active directory before continuing`
- `0x5579`: `SandboxWorkerAccountManager.AddAllAccountsToWorkerGroup: Could not add newly created users to the SandboxWorkerProcess group. Exception : {0}`

## pseudocode

```c

```

## disassembly

```asm
0x5500  ldc.i4.0
0x5501  newobj   instance void [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.PrincipalContext::.ctor(valuetype [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.ContextType)
0x5506  ldc.i4.1
0x5507  ldstr    aSandboxworkerp// "SandboxWorkerProcess"
0x550c  call     class [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.GroupPrincipal [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.GroupPrincipal::FindByIdentity(class [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.PrincipalContext, valuetype [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.IdentityType, string)
0x5511  stloc.0
0x5512  ldloc.0
0x5513  brtrue.s loc_552D
0x5515  ldnull
0x5516  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x551b  ldc.i4.s 0x21
0x551d  ldstr    aSandboxworkera_5// "SandboxWorkerAccountManager.AddAllAccou"...
0x5522  ldc.i4.0
0x5523  newarr   [mscorlib]System.Object
0x5528  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x552d  nop
0x552e  ldarg.0
0x552f  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.SandboxWorkerAccount>::GetEnumerator()
0x5534  stloc.1
0x5535  br.s     loc_5550
0x5537  ldloca.s 1
0x5539  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Sandbox.SandboxWorkerAccount>::get_Current()
0x553e  stloc.2
0x553f  ldloc.0
0x5540  callvirt instance class [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.PrincipalCollection [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.GroupPrincipal::get_Members()
0x5545  ldloc.2
0x5546  callvirt instance class [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.UserPrincipal Microsoft.Crm.Sandbox.SandboxWorkerAccount::get_UserPrincipal()
0x554b  callvirt instance void [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.PrincipalCollection::Add(class [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.UserPrincipal)
0x5550  ldloca.s 1
0x5552  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Sandbox.SandboxWorkerAccount>::MoveNext()
0x5557  brtrue.s loc_5537
0x5559  leave.s  loc_5569
0x555b  ldloca.s 1
0x555d  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Sandbox.SandboxWorkerAccount>
0x5563  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5568  endfinally
0x5569  ldloc.0
0x556a  callvirt instance void [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.Principal::Save()
0x556f  leave.s  loc_558F
0x5571  stloc.3
0x5572  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5577  ldc.i4.s 0x21
0x5579  ldstr    aSandboxworkera_6// "SandboxWorkerAccountManager.AddAllAccou"...
0x557e  ldc.i4.1
0x557f  newarr   [mscorlib]System.Object
0x5584  dup
0x5585  ldc.i4.0
0x5586  ldloc.3
0x5587  stelem.ref
0x5588  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x558d  leave.s  loc_558F
0x558f  ret
```
