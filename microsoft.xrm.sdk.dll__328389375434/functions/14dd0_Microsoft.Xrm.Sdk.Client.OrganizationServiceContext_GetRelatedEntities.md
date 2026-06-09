# Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::GetRelatedEntities

- ea: `0x14dd0`
- end: `0x14e56`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::GetRelatedEntities`
- size: `134`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callers

- `0x133c0`

## callees

- `0x30c0`
- `0x3b90`
- `0x3bc0`
- `0x3c90`
- `0x4330`
- `0x8cd0`
- `0x8ce0`
- `0x9990`
- `0x9ad0`
- `0x12870`
- `0x128c0`
- `0x12910`
- `0x12980`
- `0x129c0`
- `0x140d0`
- `0x14dd0`
- `0x14e60`

## pseudocode

```c

```

## disassembly

```asm
0x14dd0  ldarg.0
0x14dd1  ldarg.1
0x14dd2  ldarg.2
0x14dd3  call     instance string Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::GetRelatedEntityName(class Microsoft.Xrm.Sdk.Entity entity, class Microsoft.Xrm.Sdk.Relationship relationship)
0x14dd8  stloc.0
0x14dd9  newobj   instance void Microsoft.Xrm.Sdk.RelationshipQueryCollection::.ctor()
0x14dde  dup
0x14ddf  ldarg.2
0x14de0  ldloc.0
0x14de1  newobj   instance void Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string entityName)
0x14de6  dup
0x14de7  ldc.i4.1
0x14de8  newobj   instance void Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(bool allColumns)
0x14ded  callvirt instance void Microsoft.Xrm.Sdk.Query.QueryExpression::set_ColumnSet(class Microsoft.Xrm.Sdk.Query.ColumnSet value)
0x14df2  callvirt instance void class Microsoft.Xrm.Sdk.DataCollection`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.Query.QueryBase>::Add(var<u1>, !!T0)
0x14df7  stloc.1
0x14df8  ldarg.1
0x14df9  callvirt instance string Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x14dfe  ldarg.1
0x14dff  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Xrm.Sdk.Entity::get_Id()
0x14e04  newobj   instance void Microsoft.Xrm.Sdk.EntityReference::.ctor(string logicalName, valuetype [mscorlib]System.Guid id)
0x14e09  stloc.2
0x14e0a  newobj   instance void Microsoft.Xrm.Sdk.Messages.RetrieveRequest::.ctor()
0x14e0f  dup
0x14e10  ldloc.2
0x14e11  callvirt instance void Microsoft.Xrm.Sdk.Messages.RetrieveRequest::set_Target(class Microsoft.Xrm.Sdk.EntityReference value)
0x14e16  dup
0x14e17  newobj   instance void Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor()
0x14e1c  callvirt instance void Microsoft.Xrm.Sdk.Messages.RetrieveRequest::set_ColumnSet(class Microsoft.Xrm.Sdk.Query.ColumnSet value)
0x14e21  dup
0x14e22  ldloc.1
0x14e23  callvirt instance void Microsoft.Xrm.Sdk.Messages.RetrieveRequest::set_RelatedEntitiesQuery(class Microsoft.Xrm.Sdk.RelationshipQueryCollection value)
0x14e28  stloc.3
0x14e29  ldarg.0
0x14e2a  ldloc.3
0x14e2b  call     instance class Microsoft.Xrm.Sdk.OrganizationResponse Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::Execute(class Microsoft.Xrm.Sdk.OrganizationRequest request)
0x14e30  isinst   Microsoft.Xrm.Sdk.Messages.RetrieveResponse
0x14e35  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.Messages.RetrieveResponse::get_Entity()
0x14e3a  callvirt instance class Microsoft.Xrm.Sdk.RelatedEntityCollection Microsoft.Xrm.Sdk.Entity::get_RelatedEntities()
0x14e3f  stloc.s  4
0x14e41  ldloc.s  4
0x14e43  ldarg.2
0x14e44  callvirt instance bool class Microsoft.Xrm.Sdk.DataCollection`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>::Contains(var<u1>)
0x14e49  brtrue.s loc_14E4D
0x14e4b  ldnull
0x14e4c  ret
0x14e4d  ldloc.s  4
0x14e4f  ldarg.2
0x14e50  callvirt instance var<u1> class Microsoft.Xrm.Sdk.DataCollection`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.EntityCollection>::get_Item(void)
0x14e55  ret
```
