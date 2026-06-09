# Microsoft.Xrm.Sdk.Query.QueryExpressionVisitorBase::VisitLinkEntity

- ea: `0x9cb0`
- end: `0x9da4`
- name: `Microsoft.Xrm.Sdk.Query.QueryExpressionVisitorBase::VisitLinkEntity`
- size: `244`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `broker_com_uri`

## callees

- `0x9290`
- `0x92f0`
- `0x9300`
- `0x9310`
- `0x9320`
- `0x9330`
- `0x9340`
- `0x9350`
- `0x9360`
- `0x9370`
- `0x9380`
- `0x9390`
- `0x93a0`
- `0x93b0`
- `0x93e0`
- `0x9400`
- `0x9410`
- `0x9420`
- `0x9470`
- `0x94a0`
- `0x94b0`
- `0x9cb0`
- `0x9dc0`
- `0x9e60`

## pseudocode

```c

```

## disassembly

```asm
0x9cb0  ldarg.0
0x9cb1  ldarg.1
0x9cb2  callvirt instance class Microsoft.Xrm.Sdk.Query.FilterExpression Microsoft.Xrm.Sdk.Query.LinkEntity::get_LinkCriteria()
0x9cb7  callvirt instance class Microsoft.Xrm.Sdk.Query.FilterExpression Microsoft.Xrm.Sdk.Query.QueryExpressionVisitorBase::VisitFilterExpression(class Microsoft.Xrm.Sdk.Query.FilterExpression filter)
0x9cbc  stloc.0
0x9cbd  ldarg.0
0x9cbe  ldarg.1
0x9cbf  callvirt instance class Microsoft.Xrm.Sdk.DataCollection`1<class Microsoft.Xrm.Sdk.Query.OrderExpression> Microsoft.Xrm.Sdk.Query.LinkEntity::get_Orders()
0x9cc4  ldarg.0
0x9cc5  dup
0x9cc6  ldvirtftn instance class Microsoft.Xrm.Sdk.Query.OrderExpression Microsoft.Xrm.Sdk.Query.QueryExpressionVisitorBase::VisitOrderExpression(class Microsoft.Xrm.Sdk.Query.OrderExpression order)
0x9ccc  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Xrm.Sdk.Query.OrderExpression, class Microsoft.Xrm.Sdk.Query.OrderExpression>::.ctor(object, native int)
0x9cd1  call     T0x2B000015
0x9cd6  stloc.1
0x9cd7  ldarg.0
0x9cd8  ldarg.1
0x9cd9  callvirt instance class Microsoft.Xrm.Sdk.DataCollection`1<class Microsoft.Xrm.Sdk.Query.LinkEntity> Microsoft.Xrm.Sdk.Query.LinkEntity::get_LinkEntities()
0x9cde  ldarg.0
0x9cdf  dup
0x9ce0  ldvirtftn instance class Microsoft.Xrm.Sdk.Query.LinkEntity Microsoft.Xrm.Sdk.Query.QueryExpressionVisitorBase::VisitLinkEntity(class Microsoft.Xrm.Sdk.Query.LinkEntity linkEntity)
0x9ce6  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Xrm.Sdk.Query.LinkEntity, class Microsoft.Xrm.Sdk.Query.LinkEntity>::.ctor(object, native int)
0x9ceb  call     T0x2B000016
0x9cf0  stloc.2
0x9cf1  ldarg.0
0x9cf2  ldarg.1
0x9cf3  callvirt instance class Microsoft.Xrm.Sdk.Query.ColumnSet Microsoft.Xrm.Sdk.Query.LinkEntity::get_Columns()
0x9cf8  callvirt instance class Microsoft.Xrm.Sdk.Query.ColumnSet Microsoft.Xrm.Sdk.Query.QueryExpressionVisitorBase::VisitColumnSet(class Microsoft.Xrm.Sdk.Query.ColumnSet columnSet)
0x9cfd  stloc.3
0x9cfe  ldloc.2
0x9cff  ldarg.1
0x9d00  callvirt instance class Microsoft.Xrm.Sdk.DataCollection`1<class Microsoft.Xrm.Sdk.Query.LinkEntity> Microsoft.Xrm.Sdk.Query.LinkEntity::get_LinkEntities()
0x9d05  bne.un.s loc_9D24
0x9d07  ldloc.0
0x9d08  ldarg.1
0x9d09  callvirt instance class Microsoft.Xrm.Sdk.Query.FilterExpression Microsoft.Xrm.Sdk.Query.LinkEntity::get_LinkCriteria()
0x9d0e  bne.un.s loc_9D24
0x9d10  ldloc.1
0x9d11  ldarg.1
0x9d12  callvirt instance class Microsoft.Xrm.Sdk.DataCollection`1<class Microsoft.Xrm.Sdk.Query.OrderExpression> Microsoft.Xrm.Sdk.Query.LinkEntity::get_Orders()
0x9d17  bne.un.s loc_9D24
0x9d19  ldloc.3
0x9d1a  ldarg.1
0x9d1b  callvirt instance class Microsoft.Xrm.Sdk.Query.ColumnSet Microsoft.Xrm.Sdk.Query.LinkEntity::get_Columns()
0x9d20  bne.un.s loc_9D24
0x9d22  ldarg.1
0x9d23  ret
0x9d24  newobj   instance void Microsoft.Xrm.Sdk.Query.LinkEntity::.ctor()
0x9d29  dup
0x9d2a  ldarg.1
0x9d2b  callvirt instance string Microsoft.Xrm.Sdk.Query.LinkEntity::get_LinkFromEntityName()
0x9d30  callvirt instance void Microsoft.Xrm.Sdk.Query.LinkEntity::set_LinkFromEntityName(string value)
0x9d35  dup
0x9d36  ldarg.1
0x9d37  callvirt instance string Microsoft.Xrm.Sdk.Query.LinkEntity::get_LinkToEntityName()
0x9d3c  callvirt instance void Microsoft.Xrm.Sdk.Query.LinkEntity::set_LinkToEntityName(string value)
0x9d41  dup
0x9d42  ldarg.1
0x9d43  callvirt instance string Microsoft.Xrm.Sdk.Query.LinkEntity::get_LinkFromAttributeName()
0x9d48  callvirt instance void Microsoft.Xrm.Sdk.Query.LinkEntity::set_LinkFromAttributeName(string value)
0x9d4d  dup
0x9d4e  ldarg.1
0x9d4f  callvirt instance string Microsoft.Xrm.Sdk.Query.LinkEntity::get_LinkToAttributeName()
0x9d54  callvirt instance void Microsoft.Xrm.Sdk.Query.LinkEntity::set_LinkToAttributeName(string value)
0x9d59  dup
0x9d5a  ldarg.1
0x9d5b  callvirt instance valuetype Microsoft.Xrm.Sdk.Query.JoinOperator Microsoft.Xrm.Sdk.Query.LinkEntity::get_JoinOperator()
0x9d60  callvirt instance void Microsoft.Xrm.Sdk.Query.LinkEntity::set_JoinOperator(valuetype Microsoft.Xrm.Sdk.Query.JoinOperator value)
0x9d65  dup
0x9d66  ldloc.0
0x9d67  callvirt instance void Microsoft.Xrm.Sdk.Query.LinkEntity::set_LinkCriteria(class Microsoft.Xrm.Sdk.Query.FilterExpression value)
0x9d6c  dup
0x9d6d  ldloc.3
0x9d6e  callvirt instance void Microsoft.Xrm.Sdk.Query.LinkEntity::set_Columns(class Microsoft.Xrm.Sdk.Query.ColumnSet value)
0x9d73  dup
0x9d74  ldarg.1
0x9d75  callvirt instance string Microsoft.Xrm.Sdk.Query.LinkEntity::get_EntityAlias()
0x9d7a  callvirt instance void Microsoft.Xrm.Sdk.Query.LinkEntity::set_EntityAlias(string value)
0x9d7f  dup
0x9d80  ldarg.1
0x9d81  callvirt instance class [System.Runtime.Serialization]System.Runtime.Serialization.ExtensionDataObject Microsoft.Xrm.Sdk.Query.LinkEntity::get_ExtensionData()
0x9d86  callvirt instance void Microsoft.Xrm.Sdk.Query.LinkEntity::set_ExtensionData(class [System.Runtime.Serialization]System.Runtime.Serialization.ExtensionDataObject value)
0x9d8b  dup
0x9d8c  callvirt instance class Microsoft.Xrm.Sdk.DataCollection`1<class Microsoft.Xrm.Sdk.Query.OrderExpression> Microsoft.Xrm.Sdk.Query.LinkEntity::get_Orders()
0x9d91  ldloc.1
0x9d92  callvirt instance void class Microsoft.Xrm.Sdk.DataCollection`1<class Microsoft.Xrm.Sdk.Query.OrderExpression>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x9d97  dup
0x9d98  callvirt instance class Microsoft.Xrm.Sdk.DataCollection`1<class Microsoft.Xrm.Sdk.Query.LinkEntity> Microsoft.Xrm.Sdk.Query.LinkEntity::get_LinkEntities()
0x9d9d  ldloc.2
0x9d9e  callvirt instance void class Microsoft.Xrm.Sdk.DataCollection`1<class Microsoft.Xrm.Sdk.Query.LinkEntity>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x9da3  ret
```
