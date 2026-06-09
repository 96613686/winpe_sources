# Microsoft.Crm.Sandbox.InternalSandboxSdkClientManager::TryUpdateServerOutageHistory

- ea: `0xc10`
- end: `0xc49`
- name: `Microsoft.Crm.Sandbox.InternalSandboxSdkClientManager::TryUpdateServerOutageHistory`
- size: `57`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0xb90`
- `0xbb0`

## callees

- `0xc10`

## pseudocode

```c

```

## disassembly

```asm
0xc10  ldsfld   class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.Sandbox.InternalSandboxSdkClientManager::_serverLock
0xc15  ldc.i4.0
0xc16  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmLockSlim::.ctor(class [System.Core]System.Threading.ReaderWriterLockSlim, valuetype [Microsoft.Crm.Core]Microsoft.Crm.LockMode)
0xc1b  stloc.0
0xc1c  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.DateTime> Microsoft.Crm.Sandbox.InternalSandboxSdkClientManager::_serverOutageHistory
0xc21  ldarg.0
0xc22  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.DateTime>::ContainsKey(var<u1>)
0xc27  brfalse.s loc_C39
0xc29  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.DateTime> Microsoft.Crm.Sandbox.InternalSandboxSdkClientManager::_serverOutageHistory
0xc2e  ldarg.0
0xc2f  ldarg.1
0xc30  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.DateTime>::set_Item(var<u1>, !!T0)
0xc35  ldc.i4.1
0xc36  stloc.1
0xc37  leave.s  loc_C47
0xc39  leave.s  loc_C45
0xc3b  ldloc.0
0xc3c  brfalse.s loc_C44
0xc3e  ldloc.0
0xc3f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc44  endfinally
0xc45  ldc.i4.0
0xc46  ret
0xc47  ldloc.1
0xc48  ret
```
