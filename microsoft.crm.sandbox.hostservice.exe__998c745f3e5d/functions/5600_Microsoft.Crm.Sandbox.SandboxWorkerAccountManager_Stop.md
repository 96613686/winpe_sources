# Microsoft.Crm.Sandbox.SandboxWorkerAccountManager::Stop

- ea: `0x5600`
- end: `0x569c`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerAccountManager::Stop`
- size: `156`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x5600`

## string_xrefs

- `0x5663`: `SandboxWorkerAccountManager.Stop: Unable to delete {0} from the SandboxWorkerProcessGroup. Exception : {1}`

## pseudocode

```c

```

## disassembly

```asm
0x5600  ldsfld   class [mscorlib]System.Threading.Thread Microsoft.Crm.Sandbox.SandboxWorkerAccountManager::_backgroundThread
0x5605  brfalse.s loc_561C
0x5607  ldsfld   class [mscorlib]System.Threading.AutoResetEvent Microsoft.Crm.Sandbox.SandboxWorkerAccountManager::_autoEventBackgroundThread
0x560c  callvirt instance bool [mscorlib]System.Threading.EventWaitHandle::Set()
0x5611  pop
0x5612  ldsfld   class [mscorlib]System.Threading.Thread Microsoft.Crm.Sandbox.SandboxWorkerAccountManager::_backgroundThread
0x5617  callvirt instance void [mscorlib]System.Threading.Thread::Join()
0x561c  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.UserPrincipal> Microsoft.Crm.Sandbox.SandboxWorkerAccountManager::_createdUsers
0x5621  call     T0x2B000005
0x5626  brfalse.s loc_569B
0x5628  ldc.i4.0
0x5629  newobj   instance void [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.PrincipalContext::.ctor(valuetype [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.ContextType)
0x562e  ldc.i4.1
0x562f  ldstr    aSandboxworkerp// "SandboxWorkerProcess"
0x5634  call     class [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.GroupPrincipal [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.GroupPrincipal::FindByIdentity(class [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.PrincipalContext, valuetype [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.IdentityType, string)
0x5639  brfalse.s loc_569B
0x563b  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.UserPrincipal> Microsoft.Crm.Sandbox.SandboxWorkerAccountManager::_createdUsers
0x5640  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.UserPrincipal>::GetEnumerator()
0x5645  stloc.0
0x5646  br.s     loc_5682
0x5648  ldloca.s 0
0x564a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.UserPrincipal>::get_Current()
0x564f  stloc.1
0x5650  ldloc.1
0x5651  brfalse.s loc_5659
0x5653  ldloc.1
0x5654  callvirt instance void [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.Principal::Delete()
0x5659  leave.s  loc_5682
0x565b  stloc.2
0x565c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5661  ldc.i4.s 0x21
0x5663  ldstr    aSandboxworkera_8// "SandboxWorkerAccountManager.Stop: Unabl"...
0x5668  ldc.i4.2
0x5669  newarr   [mscorlib]System.Object
0x566e  dup
0x566f  ldc.i4.0
0x5670  ldloc.1
0x5671  callvirt instance string [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.Principal::get_Name()
0x5676  stelem.ref
0x5677  dup
0x5678  ldc.i4.1
0x5679  ldloc.2
0x567a  stelem.ref
0x567b  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5680  leave.s  loc_5682
0x5682  ldloca.s 0
0x5684  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.UserPrincipal>::MoveNext()
0x5689  brtrue.s loc_5648
0x568b  leave.s  loc_569B
0x568d  ldloca.s 0
0x568f  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.UserPrincipal>
0x5695  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x569a  endfinally
0x569b  ret
```
