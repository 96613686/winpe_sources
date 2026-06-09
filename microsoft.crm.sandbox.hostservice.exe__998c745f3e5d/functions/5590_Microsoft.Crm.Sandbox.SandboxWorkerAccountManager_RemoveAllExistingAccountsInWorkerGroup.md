# Microsoft.Crm.Sandbox.SandboxWorkerAccountManager::RemoveAllExistingAccountsInWorkerGroup

- ea: `0x5590`
- end: `0x55fe`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerAccountManager::RemoveAllExistingAccountsInWorkerGroup`
- size: `110`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x70`
- `0x140`

## callees

- `0x5590`

## string_xrefs

- `0x55ca`: `SandboxWorkerAccountManager.RemoveAllExistingAccountsInWorkerGroup: Unable to delete {0} from the SandboxWorkerProcessGroup. Exception : {1}`

## pseudocode

```c

```

## disassembly

```asm
0x5590  ldc.i4.0
0x5591  newobj   instance void [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.PrincipalContext::.ctor(valuetype [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.ContextType)
0x5596  ldc.i4.1
0x5597  ldstr    aSandboxworkerp// "SandboxWorkerProcess"
0x559c  call     class [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.GroupPrincipal [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.GroupPrincipal::FindByIdentity(class [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.PrincipalContext, valuetype [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.IdentityType, string)
0x55a1  stloc.0
0x55a2  ldloc.0
0x55a3  brfalse.s loc_55FD
0x55a5  ldloc.0
0x55a6  callvirt instance class [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.PrincipalCollection [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.GroupPrincipal::get_Members()
0x55ab  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.Principal> [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.PrincipalCollection::GetEnumerator()
0x55b0  stloc.1
0x55b1  br.s     loc_55E9
0x55b3  ldloc.1
0x55b4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.Principal>::get_Current()
0x55b9  stloc.2
0x55ba  ldloc.2
0x55bb  callvirt instance void [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.Principal::Delete()
0x55c0  leave.s  loc_55E9
0x55c2  stloc.3
0x55c3  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x55c8  ldc.i4.s 0x21
0x55ca  ldstr    aSandboxworkera_7// "SandboxWorkerAccountManager.RemoveAllEx"...
0x55cf  ldc.i4.2
0x55d0  newarr   [mscorlib]System.Object
0x55d5  dup
0x55d6  ldc.i4.0
0x55d7  ldloc.2
0x55d8  callvirt instance string [System.DirectoryServices.AccountManagement]System.DirectoryServices.AccountManagement.Principal::get_Name()
0x55dd  stelem.ref
0x55de  dup
0x55df  ldc.i4.1
0x55e0  ldloc.3
0x55e1  stelem.ref
0x55e2  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x55e7  leave.s  loc_55E9
0x55e9  ldloc.1
0x55ea  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x55ef  brtrue.s loc_55B3
0x55f1  leave.s  loc_55FD
0x55f3  ldloc.1
0x55f4  brfalse.s loc_55FC
0x55f6  ldloc.1
0x55f7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x55fc  endfinally
0x55fd  ret
```
