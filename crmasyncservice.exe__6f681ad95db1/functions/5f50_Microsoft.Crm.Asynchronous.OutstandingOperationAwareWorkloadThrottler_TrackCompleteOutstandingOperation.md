# Microsoft.Crm.Asynchronous.OutstandingOperationAwareWorkloadThrottler::TrackCompleteOutstandingOperation

- ea: `0x5f50`
- end: `0x5f9d`
- name: `Microsoft.Crm.Asynchronous.OutstandingOperationAwareWorkloadThrottler::TrackCompleteOutstandingOperation`
- size: `77`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x5f50`

## pseudocode

```c

```

## disassembly

```asm
0x5f50  ldarg.0
0x5f51  ldfld    object Microsoft.Crm.Asynchronous.OutstandingOperationAwareWorkloadThrottler::_syncRoot
0x5f56  stloc.0
0x5f57  ldc.i4.0
0x5f58  stloc.1
0x5f59  ldloc.0
0x5f5a  ldloca.s 1
0x5f5c  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x5f61  ldarg.0
0x5f62  ldarg.0
0x5f63  ldfld    int32 Microsoft.Crm.Asynchronous.OutstandingOperationAwareWorkloadThrottler::_totalOutstandingOperations
0x5f68  ldc.i4.1
0x5f69  sub
0x5f6a  stfld    int32 Microsoft.Crm.Asynchronous.OutstandingOperationAwareWorkloadThrottler::_totalOutstandingOperations
0x5f6f  ldc.i4.0
0x5f70  stloc.2
0x5f71  ldarg.0
0x5f72  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, int32> Microsoft.Crm.Asynchronous.OutstandingOperationAwareWorkloadThrottler::_outstandingOperationsByOrganization
0x5f77  ldarg.1
0x5f78  ldloca.s 2
0x5f7a  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, int32>::TryGetValue(var<u1>, !!T0)
0x5f7f  brfalse.s loc_5F90
0x5f81  ldarg.0
0x5f82  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, int32> Microsoft.Crm.Asynchronous.OutstandingOperationAwareWorkloadThrottler::_outstandingOperationsByOrganization
0x5f87  ldarg.1
0x5f88  ldloc.2
0x5f89  ldc.i4.1
0x5f8a  sub
0x5f8b  callvirt instance void class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, int32>::set_Item(var<u1>, !!T0)
0x5f90  leave.s  loc_5F9C
0x5f92  ldloc.1
0x5f93  brfalse.s loc_5F9B
0x5f95  ldloc.0
0x5f96  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x5f9b  endfinally
0x5f9c  ret
```
