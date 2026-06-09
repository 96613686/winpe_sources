# RetrieveListByObjectCommand::DecorateQuery

- ea: `0x9f580`
- end: `0x9f808`
- name: `RetrieveListByObjectCommand::DecorateQuery`
- size: `648`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x2fb90`
- `0x2fba0`
- `0x59710`
- `0x5be20`
- `0x6a0d0`
- `0x6a2a0`
- `0x9caf0`
- `0x9cb20`
- `0x9cbb0`
- `0x9f580`
- `0x9f810`

## string_xrefs

- `0x9f620`: `isListFetchXmlEmpty`
- `0x9f75e`: `isListFetchXmlEmpty`
- `0x9f789`: `isListFetchXmlEmpty`
- `0x9f5b7`: `createdfromcode`
- `0x9f5f9`: `createdfromcode`

## pseudocode

```c

```

## disassembly

```asm
0x9f580  ldstr    aList// "list"
0x9f585  callvirt instance string [mscorlib]System.Object::ToString()
0x9f58a  ldarg.0
0x9f58b  call     instance class [System]System.Collections.Specialized.NameValueCollection ApiCommand::get_Parameters()
0x9f590  ldstr    aOid// "oId"
0x9f595  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x9f59a  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x9f59f  ldc.i4.3
0x9f5a0  newarr   [mscorlib]System.String
0x9f5a5  dup
0x9f5a6  ldc.i4.0
0x9f5a7  ldstr    aQuery// "query"
0x9f5ac  stelem.ref
0x9f5ad  dup
0x9f5ae  ldc.i4.1
0x9f5af  ldstr    aType// "type"
0x9f5b4  stelem.ref
0x9f5b5  dup
0x9f5b6  ldc.i4.2
0x9f5b7  ldstr    aCreatedfromcod// "createdfromcode"
0x9f5bc  stelem.ref
0x9f5bd  ldarg.0
0x9f5be  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext ApiCommand::get_OrganizationContext()
0x9f5c3  call     class Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Platform.DataSource::Retrieve(string entityName, valuetype [mscorlib]System.Guid entityId, string[] columns, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x9f5c8  stloc.0
0x9f5c9  ldloc.0
0x9f5ca  ldstr    aType// "type"
0x9f5cf  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x9f5d4  unbox.any [mscorlib]System.Boolean
0x9f5d9  brfalse  loc_9F799
0x9f5de  ldloc.0
0x9f5df  ldstr    aQuery// "query"
0x9f5e4  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x9f5e9  castclass [mscorlib]System.String
0x9f5ee  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x9f5f3  brtrue   loc_9F783
0x9f5f8  ldloc.0
0x9f5f9  ldstr    aCreatedfromcod// "createdfromcode"
0x9f5fe  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x9f603  unbox.any [mscorlib]System.Int32
0x9f608  ldarg.0
0x9f609  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression ApiCommand::get_EntityQuery()
0x9f60e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Entity()
0x9f613  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x9f618  beq.s    loc_9F630
0x9f61a  ldarg.0
0x9f61b  call     instance class [System]System.Collections.Specialized.NameValueCollection ApiCommand::get_Parameters()
0x9f620  ldstr    aIslistfetchxml// "isListFetchXmlEmpty"
0x9f625  ldstr    aTrue// "true"
0x9f62a  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Set(string, string)
0x9f62f  ret
0x9f630  ldloc.0
0x9f631  ldstr    aQuery// "query"
0x9f636  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x9f63b  castclass [mscorlib]System.String
0x9f640  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9f645  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Security.UserInformation::get_UserId()
0x9f64a  ldarg.0
0x9f64b  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext ApiCommand::get_OrganizationContext()
0x9f650  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x9f655  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.UserAndOrganizationContext::.ctor(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x9f65a  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::FromFetch(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x9f65f  stloc.1
0x9f660  ldloc.1
0x9f661  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x9f666  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpressionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::get_Conditions()
0x9f66b  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression>::get_Count()
0x9f670  ldc.i4.0
0x9f671  bgt.s    loc_9F686
0x9f673  ldloc.1
0x9f674  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x9f679  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpressionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::get_Filters()
0x9f67e  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression>::get_Count()
0x9f683  ldc.i4.0
0x9f684  ble.s    loc_9F69C
0x9f686  ldarg.0
0x9f687  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression ApiCommand::get_EntityQuery()
0x9f68c  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x9f691  ldloc.1
0x9f692  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x9f697  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddFilter(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression)
0x9f69c  ldloc.1
0x9f69d  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Distinct()
0x9f6a2  brfalse.s loc_9F6B0
0x9f6a4  ldarg.0
0x9f6a5  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression ApiCommand::get_EntityQuery()
0x9f6aa  ldc.i4.1
0x9f6ab  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::set_Distinct(bool)
0x9f6b0  ldloc.1
0x9f6b1  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpressionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_LinkedEntities()
0x9f6b6  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression>::GetEnumerator()
0x9f6bb  stloc.2
0x9f6bc  br.s     loc_9F73C
0x9f6be  ldloca.s 2
0x9f6c0  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression>::get_Current()
0x9f6c5  stloc.3
0x9f6c6  ldarg.0
0x9f6c7  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression ApiCommand::get_EntityQuery()
0x9f6cc  ldloc.3
0x9f6cd  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_EntityName()
0x9f6d2  ldloc.3
0x9f6d3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_LinkFromAttribute()
0x9f6d8  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x9f6dd  ldloc.3
0x9f6de  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_LinkToAttribute()
0x9f6e3  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x9f6e8  ldloc.3
0x9f6e9  callvirt instance valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_ConditionOperator()
0x9f6ee  ldloc.3
0x9f6ef  callvirt instance valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.JoinOperator [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_JoinOperator()
0x9f6f4  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::AddLinkEntity(string, string, string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.JoinOperator)
0x9f6f9  stloc.s  4
0x9f6fb  ldloc.3
0x9f6fc  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_LinkCriteria()
0x9f701  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpressionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::get_Conditions()
0x9f706  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression>::get_Count()
0x9f70b  ldc.i4.0
0x9f70c  bgt.s    loc_9F721
0x9f70e  ldloc.3
0x9f70f  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_LinkCriteria()
0x9f714  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpressionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::get_Filters()
0x9f719  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression>::get_Count()
0x9f71e  ldc.i4.0
0x9f71f  ble.s    loc_9F733
0x9f721  ldloc.s  4
0x9f723  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_LinkCriteria()
0x9f728  ldloc.3
0x9f729  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_LinkCriteria()
0x9f72e  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddFilter(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression)
0x9f733  ldarg.0
0x9f734  ldloc.3
0x9f735  ldloc.s  4
0x9f737  call     instance void RetrieveListByObjectCommand::CloneEntityExpression(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression fromLinkEntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression toLinkEntityExpression)
0x9f73c  ldloca.s 2
0x9f73e  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression>::MoveNext()
0x9f743  brtrue   loc_9F6BE
0x9f748  leave.s  loc_9F758
0x9f74a  ldloca.s 2
0x9f74c  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression>
0x9f752  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9f757  endfinally
0x9f758  ldarg.0
0x9f759  call     instance class [System]System.Collections.Specialized.NameValueCollection ApiCommand::get_Parameters()
0x9f75e  ldstr    aIslistfetchxml// "isListFetchXmlEmpty"
0x9f763  ldstr    aFalse// "false"
0x9f768  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Set(string, string)
0x9f76d  ldarg.0
0x9f76e  call     instance class [System]System.Collections.Specialized.NameValueCollection ApiCommand::get_Parameters()
0x9f773  ldstr    aRelname// "relName"
0x9f778  ldsfld   string [mscorlib]System.String::Empty
0x9f77d  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Set(string, string)
0x9f782  ret
0x9f783  ldarg.0
0x9f784  call     instance class [System]System.Collections.Specialized.NameValueCollection ApiCommand::get_Parameters()
0x9f789  ldstr    aIslistfetchxml// "isListFetchXmlEmpty"
0x9f78e  ldstr    aTrue// "true"
0x9f793  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Set(string, string)
0x9f798  ret
0x9f799  ldarg.0
0x9f79a  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression ApiCommand::get_EntityQuery()
0x9f79f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Entity()
0x9f7a4  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x9f7a9  ldarg.0
0x9f7aa  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext ApiCommand::get_OrganizationContext()
0x9f7af  newobj   instance void Microsoft.Crm.Application.Platform.EntityType::.ctor(string logicalName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x9f7b4  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Application.Platform.EntityType::get_Metadata()
0x9f7b9  stloc.s  5
0x9f7bb  ldarg.0
0x9f7bc  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression ApiCommand::get_EntityQuery()
0x9f7c1  ldstr    aListmember_0// "ListMember"
0x9f7c6  ldstr    aEntityid// "entityid"
0x9f7cb  ldloc.s  5
0x9f7cd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x9f7d2  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x9f7d7  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::AddLinkEntity(string, string, string)
0x9f7dc  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_LinkCriteria()
0x9f7e1  ldstr    aListid// "listid"
0x9f7e6  ldc.i4.0
0x9f7e7  ldarg.0
0x9f7e8  call     instance class [System]System.Collections.Specialized.NameValueCollection ApiCommand::get_Parameters()
0x9f7ed  ldstr    aOid// "oId"
0x9f7f2  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x9f7f7  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x9f7fc  box      [mscorlib]System.Guid
0x9f801  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x9f806  pop
0x9f807  ret
```
