# Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::CreateCore

- ea: `0x1a580`
- end: `0x1a651`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::CreateCore`
- size: `209`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1ac10`

## callees

- `0x7a60`
- `0x1a050`
- `0x1a580`

## pseudocode

```c

```

## disassembly

```asm
0x1a580  ldloca.s 0
0x1a582  initobj  valuetype [mscorlib]System.Nullable`1<bool>
0x1a588  ldc.i4.0
0x1a589  stloc.1
0x1a58a  ldarg.0
0x1a58b  newobj   instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContextInitializer::.ctor(class Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy proxy)
0x1a590  stloc.2
0x1a591  ldarg.0
0x1a592  call     instance class Microsoft.Xrm.Sdk.Client.ServiceChannel`1<var<u1>> class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class Microsoft.Xrm.Sdk.IOrganizationService>::get_ServiceChannel()
0x1a597  callvirt instance var<u1> class Microsoft.Xrm.Sdk.Client.ServiceChannel`1<class Microsoft.Xrm.Sdk.IOrganizationService>::get_Channel()
0x1a59c  ldarg.1
0x1a59d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Xrm.Sdk.IOrganizationService::Create(class Microsoft.Xrm.Sdk.Entity entity)
0x1a5a2  stloc.3
0x1a5a3  leave    loc_1A64F
0x1a5a8  ldloc.2
0x1a5a9  brfalse.s loc_1A5B1
0x1a5ab  ldloc.2
0x1a5ac  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1a5b1  endfinally
0x1a5b2  stloc.s  4
0x1a5b4  ldc.i4.1
0x1a5b5  stloc.1
0x1a5b6  ldarg.0
0x1a5b7  ldloc.s  4
0x1a5b9  ldloc.0
0x1a5ba  call     instance valuetype [mscorlib]System.Nullable`1<bool> class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class Microsoft.Xrm.Sdk.IOrganizationService>::ShouldRetry(class [System.ServiceModel]System.ServiceModel.Security.MessageSecurityException, valuetype [mscorlib]System.Nullable`1<bool>)
0x1a5bf  stloc.0
0x1a5c0  ldloca.s 0
0x1a5c2  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x1a5c7  brtrue.s loc_1A5CB
0x1a5c9  rethrow
0x1a5cb  leave.s  loc_1A634
0x1a5cd  pop
0x1a5ce  ldc.i4.1
0x1a5cf  stloc.1
0x1a5d0  ldarg.0
0x1a5d1  ldloc.0
0x1a5d2  call     instance bool class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class Microsoft.Xrm.Sdk.IOrganizationService>::HandleFailover(valuetype [mscorlib]System.Nullable`1<bool>)
0x1a5d7  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x1a5dc  stloc.0
0x1a5dd  ldloca.s 0
0x1a5df  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x1a5e4  brtrue.s loc_1A5E8
0x1a5e6  rethrow
0x1a5e8  leave.s  loc_1A634
0x1a5ea  pop
0x1a5eb  ldc.i4.1
0x1a5ec  stloc.1
0x1a5ed  ldarg.0
0x1a5ee  ldloc.0
0x1a5ef  call     instance bool class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class Microsoft.Xrm.Sdk.IOrganizationService>::HandleFailover(valuetype [mscorlib]System.Nullable`1<bool>)
0x1a5f4  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x1a5f9  stloc.0
0x1a5fa  ldloca.s 0
0x1a5fc  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x1a601  brtrue.s loc_1A605
0x1a603  rethrow
0x1a605  leave.s  loc_1A634
0x1a607  stloc.s  5
0x1a609  ldc.i4.1
0x1a60a  stloc.1
0x1a60b  ldarg.0
0x1a60c  ldloc.s  5
0x1a60e  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x1a613  ldloc.0
0x1a614  call     instance valuetype [mscorlib]System.Nullable`1<bool> class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class Microsoft.Xrm.Sdk.IOrganizationService>::HandleFailover(class Microsoft.Xrm.Sdk.BaseServiceFault, valuetype [mscorlib]System.Nullable`1<bool>)
0x1a619  stloc.0
0x1a61a  ldloca.s 0
0x1a61c  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x1a621  brtrue.s loc_1A625
0x1a623  rethrow
0x1a625  leave.s  loc_1A634
0x1a627  pop
0x1a628  ldc.i4.1
0x1a629  stloc.1
0x1a62a  rethrow
0x1a62c  ldarg.0
0x1a62d  ldloc.1
0x1a62e  callvirt instance void class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class Microsoft.Xrm.Sdk.IOrganizationService>::CloseChannel(bool)
0x1a633  endfinally
0x1a634  ldloca.s 0
0x1a636  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x1a63b  brfalse.s loc_1A649
0x1a63d  ldloca.s 0
0x1a63f  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x1a644  brtrue   loc_1A588
0x1a649  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1a64e  ret
0x1a64f  ldloc.3
0x1a650  ret
```
