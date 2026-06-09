# Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::LoadProperty_1

- ea: `0x134b0`
- end: `0x1355a`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::LoadProperty_1`
- size: `170`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x13300`

## callees

- `0x24a0`
- `0x3880`
- `0x3b90`
- `0x3bc0`
- `0x3c00`
- `0x4330`
- `0x8d00`
- `0x12870`
- `0x128c0`
- `0x12980`
- `0x129c0`
- `0x13170`
- `0x134b0`
- `0x140d0`
- `0x15070`

## pseudocode

```c

```

## disassembly

```asm
0x134b0  ldarg.0
0x134b1  call     instance valuetype Microsoft.Xrm.Sdk.Client.MergeOption Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::get_MergeOption()
0x134b6  ldc.i4.3
0x134b7  beq.s    loc_134D8
0x134b9  ldarg.0
0x134ba  ldarg.1
0x134bb  ldstr    aEntity// "entity"
0x134c0  call     instance class Microsoft.Xrm.Sdk.EntityDescriptor Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::EnsureTracked(class Microsoft.Xrm.Sdk.Entity entity, string parameterName)
0x134c5  callvirt instance valuetype Microsoft.Xrm.Sdk.EntityStates Microsoft.Xrm.Sdk.Descriptor::get_State()
0x134ca  ldc.i4.4
0x134cb  bne.un.s loc_134D8
0x134cd  ldstr    aTheContextCanN_0// "The context can not load the related co"...
0x134d2  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x134d7  throw
0x134d8  ldarg.2
0x134d9  callvirt instance string Microsoft.Xrm.Sdk.AttributeLogicalNameAttribute::get_LogicalName()
0x134de  stloc.0
0x134df  newobj   instance void Microsoft.Xrm.Sdk.Messages.RetrieveRequest::.ctor()
0x134e4  stloc.1
0x134e5  ldloc.1
0x134e6  ldarg.1
0x134e7  callvirt instance string Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x134ec  ldarg.1
0x134ed  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Xrm.Sdk.Entity::get_Id()
0x134f2  newobj   instance void Microsoft.Xrm.Sdk.EntityReference::.ctor(string logicalName, valuetype [mscorlib]System.Guid id)
0x134f7  callvirt instance void Microsoft.Xrm.Sdk.Messages.RetrieveRequest::set_Target(class Microsoft.Xrm.Sdk.EntityReference value)
0x134fc  ldloc.1
0x134fd  ldc.i4.1
0x134fe  newarr   [mscorlib]System.String
0x13503  dup
0x13504  ldc.i4.0
0x13505  ldloc.0
0x13506  stelem.ref
0x13507  newobj   instance void Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[] columns)
0x1350c  callvirt instance void Microsoft.Xrm.Sdk.Messages.RetrieveRequest::set_ColumnSet(class Microsoft.Xrm.Sdk.Query.ColumnSet value)
0x13511  ldarg.0
0x13512  ldloc.1
0x13513  call     instance class Microsoft.Xrm.Sdk.OrganizationResponse Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::Execute(class Microsoft.Xrm.Sdk.OrganizationRequest request)
0x13518  castclass Microsoft.Xrm.Sdk.Messages.RetrieveResponse
0x1351d  stloc.2
0x1351e  ldloc.2
0x1351f  brfalse.s loc_13559
0x13521  ldloc.2
0x13522  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.Messages.RetrieveResponse::get_Entity()
0x13527  brfalse.s loc_13559
0x13529  ldloc.2
0x1352a  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.Messages.RetrieveResponse::get_Entity()
0x1352f  callvirt instance class Microsoft.Xrm.Sdk.AttributeCollection Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x13534  ldloc.0
0x13535  callvirt instance bool class Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x1353a  brfalse.s loc_13559
0x1353c  ldarg.1
0x1353d  callvirt instance class Microsoft.Xrm.Sdk.AttributeCollection Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x13542  ldloc.0
0x13543  ldloc.2
0x13544  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.Messages.RetrieveResponse::get_Entity()
0x13549  callvirt instance class Microsoft.Xrm.Sdk.AttributeCollection Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x1354e  ldloc.0
0x1354f  callvirt instance var<u1> class Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x13554  callvirt instance void class Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x13559  ret
```
