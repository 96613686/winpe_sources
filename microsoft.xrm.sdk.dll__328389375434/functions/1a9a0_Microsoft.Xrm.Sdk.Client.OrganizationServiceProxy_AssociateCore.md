# Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::AssociateCore

- ea: `0x1a9a0`
- end: `0x1aa6d`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::AssociateCore`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1ac60`

## callees

- `0x7ab0`
- `0x1a050`
- `0x1a9a0`

## pseudocode

```c

```

## disassembly

```asm
0x1a9a0  ldloca.s 0
0x1a9a2  initobj  valuetype [mscorlib]System.Nullable`1<bool>
0x1a9a8  ldc.i4.0
0x1a9a9  stloc.1
0x1a9aa  ldarg.0
0x1a9ab  newobj   instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContextInitializer::.ctor(class Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy proxy)
0x1a9b0  stloc.2
0x1a9b1  ldarg.0
0x1a9b2  call     instance class Microsoft.Xrm.Sdk.Client.ServiceChannel`1<var<u1>> class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class Microsoft.Xrm.Sdk.IOrganizationService>::get_ServiceChannel()
0x1a9b7  callvirt instance var<u1> class Microsoft.Xrm.Sdk.Client.ServiceChannel`1<class Microsoft.Xrm.Sdk.IOrganizationService>::get_Channel()
0x1a9bc  ldarg.1
0x1a9bd  ldarg.2
0x1a9be  ldarg.3
0x1a9bf  ldarg.s  4
0x1a9c1  callvirt instance void Microsoft.Xrm.Sdk.IOrganizationService::Associate(string entityName, valuetype [mscorlib]System.Guid entityId, class Microsoft.Xrm.Sdk.Relationship relationship, class Microsoft.Xrm.Sdk.EntityReferenceCollection relatedEntities)
0x1a9c6  leave.s  loc_1A9D2
0x1a9c8  ldloc.2
0x1a9c9  brfalse.s loc_1A9D1
0x1a9cb  ldloc.2
0x1a9cc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1a9d1  endfinally
0x1a9d2  leave    loc_1AA6C
0x1a9d7  stloc.3
0x1a9d8  ldc.i4.1
0x1a9d9  stloc.1
0x1a9da  ldarg.0
0x1a9db  ldloc.3
0x1a9dc  ldloc.0
0x1a9dd  call     instance valuetype [mscorlib]System.Nullable`1<bool> class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class Microsoft.Xrm.Sdk.IOrganizationService>::ShouldRetry(class [System.ServiceModel]System.ServiceModel.Security.MessageSecurityException, valuetype [mscorlib]System.Nullable`1<bool>)
0x1a9e2  stloc.0
0x1a9e3  ldloca.s 0
0x1a9e5  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x1a9ea  brtrue.s loc_1A9EE
0x1a9ec  rethrow
0x1a9ee  leave.s  loc_1AA57
0x1a9f0  pop
0x1a9f1  ldc.i4.1
0x1a9f2  stloc.1
0x1a9f3  ldarg.0
0x1a9f4  ldloc.0
0x1a9f5  call     instance bool class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class Microsoft.Xrm.Sdk.IOrganizationService>::HandleFailover(valuetype [mscorlib]System.Nullable`1<bool>)
0x1a9fa  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x1a9ff  stloc.0
0x1aa00  ldloca.s 0
0x1aa02  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x1aa07  brtrue.s loc_1AA0B
0x1aa09  rethrow
0x1aa0b  leave.s  loc_1AA57
0x1aa0d  pop
0x1aa0e  ldc.i4.1
0x1aa0f  stloc.1
0x1aa10  ldarg.0
0x1aa11  ldloc.0
0x1aa12  call     instance bool class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class Microsoft.Xrm.Sdk.IOrganizationService>::HandleFailover(valuetype [mscorlib]System.Nullable`1<bool>)
0x1aa17  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x1aa1c  stloc.0
0x1aa1d  ldloca.s 0
0x1aa1f  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x1aa24  brtrue.s loc_1AA28
0x1aa26  rethrow
0x1aa28  leave.s  loc_1AA57
0x1aa2a  stloc.s  4
0x1aa2c  ldc.i4.1
0x1aa2d  stloc.1
0x1aa2e  ldarg.0
0x1aa2f  ldloc.s  4
0x1aa31  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x1aa36  ldloc.0
0x1aa37  call     instance valuetype [mscorlib]System.Nullable`1<bool> class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class Microsoft.Xrm.Sdk.IOrganizationService>::HandleFailover(class Microsoft.Xrm.Sdk.BaseServiceFault, valuetype [mscorlib]System.Nullable`1<bool>)
0x1aa3c  stloc.0
0x1aa3d  ldloca.s 0
0x1aa3f  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x1aa44  brtrue.s loc_1AA48
0x1aa46  rethrow
0x1aa48  leave.s  loc_1AA57
0x1aa4a  pop
0x1aa4b  ldc.i4.1
0x1aa4c  stloc.1
0x1aa4d  rethrow
0x1aa4f  ldarg.0
0x1aa50  ldloc.1
0x1aa51  callvirt instance void class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class Microsoft.Xrm.Sdk.IOrganizationService>::CloseChannel(bool)
0x1aa56  endfinally
0x1aa57  ldloca.s 0
0x1aa59  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x1aa5e  brfalse.s loc_1AA6C
0x1aa60  ldloca.s 0
0x1aa62  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x1aa67  brtrue   loc_1A9A8
0x1aa6c  ret
```
