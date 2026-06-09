# Microsoft.Crm.Common.Application.Platform.Queue::CheckActiveMembersForQueue

- ea: `0x4830`
- end: `0x48d0`
- name: `Microsoft.Crm.Common.Application.Platform.Queue::CheckActiveMembersForQueue`
- size: `160`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x4830`

## pseudocode

```c

```

## disassembly

```asm
0x4830  ldstr    aQueuemembershi// "queuemembership"
0x4835  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0x483a  stloc.0
0x483b  ldloc.0
0x483c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0x4841  ldc.i4.2
0x4842  newarr   [mscorlib]System.String
0x4847  dup
0x4848  ldc.i4.0
0x4849  ldstr    aQueueid// "queueid"
0x484e  stelem.ref
0x484f  dup
0x4850  ldc.i4.1
0x4851  ldstr    aSystemuserid// "systemuserid"
0x4856  stelem.ref
0x4857  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumns(string[])
0x485c  ldloc.0
0x485d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x4862  ldstr    aQueueid// "queueid"
0x4867  ldc.i4.0
0x4868  ldc.i4.1
0x4869  newarr   [mscorlib]System.Object
0x486e  dup
0x486f  ldc.i4.0
0x4870  ldarg.0
0x4871  box      [mscorlib]System.Guid
0x4876  stelem.ref
0x4877  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0x487c  ldloc.0
0x487d  ldstr    aSystemuser// "systemuser"
0x4882  ldstr    aSystemuserid// "systemuserid"
0x4887  ldstr    aSystemuserid// "systemuserid"
0x488c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::AddLink(string, string, string)
0x4891  pop
0x4892  ldloc.0
0x4893  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_LinkEntities()
0x4898  ldc.i4.0
0x4899  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity>::get_Item(!!T0)
0x489e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity::get_LinkCriteria()
0x48a3  ldstr    aIsdisabled// "isdisabled"
0x48a8  ldc.i4.0
0x48a9  ldc.i4.1
0x48aa  newarr   [mscorlib]System.Object
0x48af  dup
0x48b0  ldc.i4.0
0x48b1  ldc.i4.0
0x48b2  box      [mscorlib]System.Boolean
0x48b7  stelem.ref
0x48b8  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0x48bd  ldloc.0
0x48be  ldarg.1
0x48bf  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x48c4  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x48c9  ldc.i4.0
0x48ca  ble.s    loc_48CE
0x48cc  ldc.i4.1
0x48cd  ret
0x48ce  ldc.i4.0
0x48cf  ret
```
