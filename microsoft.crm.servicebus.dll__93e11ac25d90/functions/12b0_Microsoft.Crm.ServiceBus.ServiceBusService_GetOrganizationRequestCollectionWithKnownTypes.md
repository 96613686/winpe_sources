# Microsoft.Crm.ServiceBus.ServiceBusService::GetOrganizationRequestCollectionWithKnownTypes

- ea: `0x12b0`
- end: `0x130c`
- name: `Microsoft.Crm.ServiceBus.ServiceBusService::GetOrganizationRequestCollectionWithKnownTypes`
- size: `92`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1190`

## callees

- `0x12b0`
- `0x1310`

## pseudocode

```c

```

## disassembly

```asm
0x12b0  ldarg.0
0x12b1  brfalse.s loc_12BC
0x12b3  ldarg.0
0x12b4  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest>::get_Count()
0x12b9  ldc.i4.1
0x12ba  bge.s    loc_12BE
0x12bc  ldnull
0x12bd  ret
0x12be  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequestCollection::.ctor()
0x12c3  stloc.0
0x12c4  ldarg.0
0x12c5  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest>::GetEnumerator()
0x12ca  stloc.1
0x12cb  br.s     loc_12EB
0x12cd  ldloc.1
0x12ce  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest>::get_Current()
0x12d3  stloc.2
0x12d4  ldloc.2
0x12d5  brfalse.s loc_12EB
0x12d7  ldloc.2
0x12d8  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x12dd  call     bool Microsoft.Crm.ServiceBus.ServiceBusService::IsKnownType(class [mscorlib]System.Type valueType)
0x12e2  brfalse.s loc_12EB
0x12e4  ldloc.0
0x12e5  ldloc.2
0x12e6  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest>::Add(var<u1>)
0x12eb  ldloc.1
0x12ec  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x12f1  brtrue.s loc_12CD
0x12f3  leave.s  loc_12FF
0x12f5  ldloc.1
0x12f6  brfalse.s loc_12FE
0x12f8  ldloc.1
0x12f9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12fe  endfinally
0x12ff  ldloc.0
0x1300  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest>::get_Count()
0x1305  ldc.i4.0
0x1306  bgt.s    loc_130A
0x1308  ldnull
0x1309  ret
0x130a  ldloc.0
0x130b  ret
```
