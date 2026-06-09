# Microsoft.Crm.Sdk.LegacySdkAdapterBase::ExecuteInProcessIdentity

- ea: `0x83b0`
- end: `0x83f3`
- name: `Microsoft.Crm.Sdk.LegacySdkAdapterBase::ExecuteInProcessIdentity`
- size: `67`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x3590`
- `0x37c0`
- `0x3b60`
- `0x3c20`
- `0x3cd0`
- `0x3d60`

## callees

- `0x8230`
- `0x8310`
- `0x8390`
- `0x83b0`
- `0x10150`

## pseudocode

```c

```

## disassembly

```asm
0x83b0  call     class [mscorlib]System.Security.Principal.WindowsIdentity [mscorlib]System.Security.Principal.WindowsIdentity::GetCurrent()
0x83b5  stloc.0
0x83b6  ldarg.0
0x83b7  ldloc.0
0x83b8  call     instance void Microsoft.Crm.Sdk.LegacySdkAdapterBase::SetHttpContext(class [mscorlib]System.Security.Principal.WindowsIdentity windowsIdentity)
0x83bd  ldc.i4.1
0x83be  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.AutoReimpersonator::.ctor(bool)
0x83c3  stloc.1
0x83c4  ldarg.1
0x83c5  callvirt instance void ExecuteInProcessIdentityAction::Invoke()
0x83ca  leave.s  loc_83D6
0x83cc  ldloc.1
0x83cd  brfalse.s loc_83D5
0x83cf  ldloc.1
0x83d0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x83d5  endfinally
0x83d6  leave.s  loc_83F2
0x83d8  stloc.2
0x83d9  ldarg.0
0x83da  ldloc.2
0x83db  call     instance void Microsoft.Crm.Sdk.LegacySdkAdapterBase::ProcessException(class [mscorlib]System.Exception e)
0x83e0  rethrow
0x83e2  ldarg.0
0x83e3  call     instance void Microsoft.Crm.Sdk.LegacySdkAdapterBase::ClearHttpContext()
0x83e8  ldloc.0
0x83e9  brfalse.s loc_83F1
0x83eb  ldloc.0
0x83ec  callvirt instance void [mscorlib]System.Security.Principal.WindowsIdentity::Dispose()
0x83f1  endfinally
0x83f2  ret
```
