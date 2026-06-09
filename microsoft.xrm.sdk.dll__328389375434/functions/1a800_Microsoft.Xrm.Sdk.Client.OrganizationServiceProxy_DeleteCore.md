# Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::DeleteCore

- ea: `0x1a800`
- end: `0x1a8ca`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::DeleteCore`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1ac40`

## callees

- `0x7a90`
- `0x1a050`
- `0x1a800`

## pseudocode

```c

```

## disassembly

```asm
0x1a800  ldloca.s 0
0x1a802  initobj  valuetype [mscorlib]System.Nullable`1<bool>
0x1a808  ldc.i4.0
0x1a809  stloc.1
0x1a80a  ldarg.0
0x1a80b  newobj   instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContextInitializer::.ctor(class Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy proxy)
0x1a810  stloc.2
0x1a811  ldarg.0
0x1a812  call     instance class Microsoft.Xrm.Sdk.Client.ServiceChannel`1<var<u1>> class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class Microsoft.Xrm.Sdk.IOrganizationService>::get_ServiceChannel()
0x1a817  callvirt instance var<u1> class Microsoft.Xrm.Sdk.Client.ServiceChannel`1<class Microsoft.Xrm.Sdk.IOrganizationService>::get_Channel()
0x1a81c  ldarg.1
0x1a81d  ldarg.2
0x1a81e  callvirt instance void Microsoft.Xrm.Sdk.IOrganizationService::Delete(string entityName, valuetype [mscorlib]System.Guid id)
0x1a823  leave.s  loc_1A82F
0x1a825  ldloc.2
0x1a826  brfalse.s loc_1A82E
0x1a828  ldloc.2
0x1a829  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1a82e  endfinally
0x1a82f  leave    loc_1A8C9
0x1a834  stloc.3
0x1a835  ldc.i4.1
0x1a836  stloc.1
0x1a837  ldarg.0
0x1a838  ldloc.3
0x1a839  ldloc.0
0x1a83a  call     instance valuetype [mscorlib]System.Nullable`1<bool> class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class Microsoft.Xrm.Sdk.IOrganizationService>::ShouldRetry(class [System.ServiceModel]System.ServiceModel.Security.MessageSecurityException, valuetype [mscorlib]System.Nullable`1<bool>)
0x1a83f  stloc.0
0x1a840  ldloca.s 0
0x1a842  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x1a847  brtrue.s loc_1A84B
0x1a849  rethrow
0x1a84b  leave.s  loc_1A8B4
0x1a84d  pop
0x1a84e  ldc.i4.1
0x1a84f  stloc.1
0x1a850  ldarg.0
0x1a851  ldloc.0
0x1a852  call     instance bool class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class Microsoft.Xrm.Sdk.IOrganizationService>::HandleFailover(valuetype [mscorlib]System.Nullable`1<bool>)
0x1a857  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x1a85c  stloc.0
0x1a85d  ldloca.s 0
0x1a85f  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x1a864  brtrue.s loc_1A868
0x1a866  rethrow
0x1a868  leave.s  loc_1A8B4
0x1a86a  pop
0x1a86b  ldc.i4.1
0x1a86c  stloc.1
0x1a86d  ldarg.0
0x1a86e  ldloc.0
0x1a86f  call     instance bool class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class Microsoft.Xrm.Sdk.IOrganizationService>::HandleFailover(valuetype [mscorlib]System.Nullable`1<bool>)
0x1a874  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x1a879  stloc.0
0x1a87a  ldloca.s 0
0x1a87c  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x1a881  brtrue.s loc_1A885
0x1a883  rethrow
0x1a885  leave.s  loc_1A8B4
0x1a887  stloc.s  4
0x1a889  ldc.i4.1
0x1a88a  stloc.1
0x1a88b  ldarg.0
0x1a88c  ldloc.s  4
0x1a88e  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x1a893  ldloc.0
0x1a894  call     instance valuetype [mscorlib]System.Nullable`1<bool> class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class Microsoft.Xrm.Sdk.IOrganizationService>::HandleFailover(class Microsoft.Xrm.Sdk.BaseServiceFault, valuetype [mscorlib]System.Nullable`1<bool>)
0x1a899  stloc.0
0x1a89a  ldloca.s 0
0x1a89c  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x1a8a1  brtrue.s loc_1A8A5
0x1a8a3  rethrow
0x1a8a5  leave.s  loc_1A8B4
0x1a8a7  pop
0x1a8a8  ldc.i4.1
0x1a8a9  stloc.1
0x1a8aa  rethrow
0x1a8ac  ldarg.0
0x1a8ad  ldloc.1
0x1a8ae  callvirt instance void class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class Microsoft.Xrm.Sdk.IOrganizationService>::CloseChannel(bool)
0x1a8b3  endfinally
0x1a8b4  ldloca.s 0
0x1a8b6  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x1a8bb  brfalse.s loc_1A8C9
0x1a8bd  ldloca.s 0
0x1a8bf  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x1a8c4  brtrue   loc_1A808
0x1a8c9  ret
```
