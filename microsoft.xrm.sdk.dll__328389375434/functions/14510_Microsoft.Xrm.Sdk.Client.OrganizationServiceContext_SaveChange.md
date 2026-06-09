# Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::SaveChange

- ea: `0x14510`
- end: `0x14536`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::SaveChange`
- size: `38`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x141d0`
- `0x146c0`
- `0x247e0`

## callees

- `0x7ec0`
- `0x7ee0`
- `0x140d0`
- `0x14510`

## pseudocode

```c

```

## disassembly

```asm
0x14510  ldarg.0
0x14511  ldarg.1
0x14512  call     instance class Microsoft.Xrm.Sdk.OrganizationResponse Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::Execute(class Microsoft.Xrm.Sdk.OrganizationRequest request)
0x14517  stloc.1
0x14518  ldarg.1
0x14519  ldloc.1
0x1451a  newobj   instance void Microsoft.Xrm.Sdk.SaveChangesResult::.ctor(class Microsoft.Xrm.Sdk.OrganizationRequest request, class Microsoft.Xrm.Sdk.OrganizationResponse response)
0x1451f  stloc.0
0x14520  leave.s  loc_1452D
0x14522  stloc.2
0x14523  ldarg.1
0x14524  ldloc.2
0x14525  newobj   instance void Microsoft.Xrm.Sdk.SaveChangesResult::.ctor(class Microsoft.Xrm.Sdk.OrganizationRequest request, class [mscorlib]System.Exception error)
0x1452a  stloc.0
0x1452b  leave.s  loc_1452D
0x1452d  ldarg.2
0x1452e  ldloc.0
0x1452f  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Xrm.Sdk.SaveChangesResult>::Add(var<u1>)
0x14534  ldloc.0
0x14535  ret
```
