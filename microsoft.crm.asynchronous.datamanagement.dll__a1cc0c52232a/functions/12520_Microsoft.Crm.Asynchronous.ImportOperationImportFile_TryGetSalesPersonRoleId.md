# Microsoft.Crm.Asynchronous.ImportOperationImportFile::TryGetSalesPersonRoleId

- ea: `0x12520`
- end: `0x1260e`
- name: `Microsoft.Crm.Asynchronous.ImportOperationImportFile::TryGetSalesPersonRoleId`
- size: `238`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x11a20`

## callees

- `0x12520`

## string_xrefs

- `0x12549`: `roletemplateid`
- `0x125f1`: `Could not retrieve SalesPerson Role - cannot create SystemUser/Team`

## pseudocode

```c

```

## disassembly

```asm
0x12520  ldloca.s 0
0x12522  ldstr    aA4be89ff7c354d// "{A4BE89FF-7C35-4D69-9900-999C3F603E6F}"
0x12527  call     instance void [mscorlib]System.Guid::.ctor(string)
0x1252c  ldstr    aRole// "role"
0x12531  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0x12536  stloc.1
0x12537  ldloc.1
0x12538  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x1253d  ldc.i4.0
0x1253e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0x12543  ldloc.1
0x12544  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x12549  ldstr    aRoletemplateid// "roletemplateid"
0x1254e  ldc.i4.0
0x1254f  ldc.i4.1
0x12550  newarr   [mscorlib]System.Object
0x12555  dup
0x12556  ldc.i4.0
0x12557  ldloc.0
0x12558  box      [mscorlib]System.Guid
0x1255d  stelem.ref
0x1255e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0x12563  ldloc.1
0x12564  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x12569  ldstr    aBusinessunitid// "businessunitid"
0x1256e  ldc.i4.0
0x1256f  ldc.i4.1
0x12570  newarr   [mscorlib]System.Object
0x12575  dup
0x12576  ldc.i4.0
0x12577  ldarg.1
0x12578  box      [mscorlib]System.Guid
0x1257d  stelem.ref
0x1257e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0x12583  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleRequest::.ctor()
0x12588  stloc.2
0x12589  ldloc.2
0x1258a  ldloc.1
0x1258b  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleRequest::set_Query(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase)
0x12590  ldarg.0
0x12591  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.ImportOperation::_crmService
0x12596  ldloc.2
0x12597  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x1259c  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleResponse
0x125a1  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleResponse::get_EntityCollection()
0x125a6  stloc.3
0x125a7  ldloc.3
0x125a8  brfalse.s loc_125E3
0x125aa  ldloc.3
0x125ab  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x125b0  brfalse.s loc_125E3
0x125b2  ldloc.3
0x125b3  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x125b8  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x125bd  ldc.i4.1
0x125be  bne.un.s loc_125E3
0x125c0  ldarg.2
0x125c1  ldloc.3
0x125c2  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x125c7  ldc.i4.0
0x125c8  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Item(!!T0)
0x125cd  ldstr    aRoleid// "roleid"
0x125d2  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x125d7  unbox.any [mscorlib]System.Guid
0x125dc  stobj    [mscorlib]System.Guid
0x125e1  ldc.i4.1
0x125e2  ret
0x125e3  ldnull
0x125e4  ldarg.0
0x125e5  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0x125ea  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x125ef  ldc.i4.s 0x18
0x125f1  ldstr    aCouldNotRetrie_1// "Could not retrieve SalesPerson Role - c"...
0x125f6  ldc.i4.0
0x125f7  newarr   [mscorlib]System.Object
0x125fc  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x12601  ldarg.2
0x12602  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x12607  stobj    [mscorlib]System.Guid
0x1260c  ldc.i4.0
0x1260d  ret
```
