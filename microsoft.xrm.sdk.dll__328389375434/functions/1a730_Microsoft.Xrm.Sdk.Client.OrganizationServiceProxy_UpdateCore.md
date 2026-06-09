# Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::UpdateCore

- ea: `0x1a730`
- end: `0x1a7f9`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::UpdateCore`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1ac30`

## callees

- `0x7a80`
- `0x1a050`
- `0x1a730`

## pseudocode

```c

```

## disassembly

```asm
0x1a730  ldloca.s 0
0x1a732  initobj  valuetype [mscorlib]System.Nullable`1<bool>
0x1a738  ldc.i4.0
0x1a739  stloc.1
0x1a73a  ldarg.0
0x1a73b  newobj   instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContextInitializer::.ctor(class Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy proxy)
0x1a740  stloc.2
0x1a741  ldarg.0
0x1a742  call     instance class Microsoft.Xrm.Sdk.Client.ServiceChannel`1<var<u1>> class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class Microsoft.Xrm.Sdk.IOrganizationService>::get_ServiceChannel()
0x1a747  callvirt instance var<u1> class Microsoft.Xrm.Sdk.Client.ServiceChannel`1<class Microsoft.Xrm.Sdk.IOrganizationService>::get_Channel()
0x1a74c  ldarg.1
0x1a74d  callvirt instance void Microsoft.Xrm.Sdk.IOrganizationService::Update(class Microsoft.Xrm.Sdk.Entity entity)
0x1a752  leave.s  loc_1A75E
0x1a754  ldloc.2
0x1a755  brfalse.s loc_1A75D
0x1a757  ldloc.2
0x1a758  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1a75d  endfinally
0x1a75e  leave    loc_1A7F8
0x1a763  stloc.3
0x1a764  ldc.i4.1
0x1a765  stloc.1
0x1a766  ldarg.0
0x1a767  ldloc.3
0x1a768  ldloc.0
0x1a769  call     instance valuetype [mscorlib]System.Nullable`1<bool> class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class Microsoft.Xrm.Sdk.IOrganizationService>::ShouldRetry(class [System.ServiceModel]System.ServiceModel.Security.MessageSecurityException, valuetype [mscorlib]System.Nullable`1<bool>)
0x1a76e  stloc.0
0x1a76f  ldloca.s 0
0x1a771  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x1a776  brtrue.s loc_1A77A
0x1a778  rethrow
0x1a77a  leave.s  loc_1A7E3
0x1a77c  pop
0x1a77d  ldc.i4.1
0x1a77e  stloc.1
0x1a77f  ldarg.0
0x1a780  ldloc.0
0x1a781  call     instance bool class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class Microsoft.Xrm.Sdk.IOrganizationService>::HandleFailover(valuetype [mscorlib]System.Nullable`1<bool>)
0x1a786  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x1a78b  stloc.0
0x1a78c  ldloca.s 0
0x1a78e  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x1a793  brtrue.s loc_1A797
0x1a795  rethrow
0x1a797  leave.s  loc_1A7E3
0x1a799  pop
0x1a79a  ldc.i4.1
0x1a79b  stloc.1
0x1a79c  ldarg.0
0x1a79d  ldloc.0
0x1a79e  call     instance bool class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class Microsoft.Xrm.Sdk.IOrganizationService>::HandleFailover(valuetype [mscorlib]System.Nullable`1<bool>)
0x1a7a3  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x1a7a8  stloc.0
0x1a7a9  ldloca.s 0
0x1a7ab  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x1a7b0  brtrue.s loc_1A7B4
0x1a7b2  rethrow
0x1a7b4  leave.s  loc_1A7E3
0x1a7b6  stloc.s  4
0x1a7b8  ldc.i4.1
0x1a7b9  stloc.1
0x1a7ba  ldarg.0
0x1a7bb  ldloc.s  4
0x1a7bd  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x1a7c2  ldloc.0
0x1a7c3  call     instance valuetype [mscorlib]System.Nullable`1<bool> class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class Microsoft.Xrm.Sdk.IOrganizationService>::HandleFailover(class Microsoft.Xrm.Sdk.BaseServiceFault, valuetype [mscorlib]System.Nullable`1<bool>)
0x1a7c8  stloc.0
0x1a7c9  ldloca.s 0
0x1a7cb  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x1a7d0  brtrue.s loc_1A7D4
0x1a7d2  rethrow
0x1a7d4  leave.s  loc_1A7E3
0x1a7d6  pop
0x1a7d7  ldc.i4.1
0x1a7d8  stloc.1
0x1a7d9  rethrow
0x1a7db  ldarg.0
0x1a7dc  ldloc.1
0x1a7dd  callvirt instance void class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class Microsoft.Xrm.Sdk.IOrganizationService>::CloseChannel(bool)
0x1a7e2  endfinally
0x1a7e3  ldloca.s 0
0x1a7e5  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x1a7ea  brfalse.s loc_1A7F8
0x1a7ec  ldloca.s 0
0x1a7ee  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x1a7f3  brtrue   loc_1A738
0x1a7f8  ret
```
