# Microsoft.Crm.Workflow.WorkflowContextBase::RetrievePrimaryEntity

- ea: `0x8340`
- end: `0x837b`
- name: `Microsoft.Crm.Workflow.WorkflowContextBase::RetrievePrimaryEntity`
- size: `59`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x8090`
- `0x10830`

## callees

- `0x7330`
- `0x7390`
- `0x73d0`
- `0x8340`
- `0x85e0`

## string_xrefs

- `0x8348`: `Delete`

## pseudocode

```c

```

## disassembly

```asm
0x8340  ldnull
0x8341  stloc.0
0x8342  ldarg.0
0x8343  call     instance string Microsoft.Crm.Workflow.WorkflowContextBase::get_MessageName()
0x8348  ldstr    aDelete// "Delete"
0x834d  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x8352  brfalse.s loc_8367
0x8354  ldnull
0x8355  stloc.1
0x8356  ldarg.0
0x8357  ldnull
0x8358  ldarg.1
0x8359  ldloca.s 1
0x835b  ldnull
0x835c  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Workflow.WorkflowContextHelper::RetrieveEntity(class Microsoft.Crm.Workflow.ICommonWorkflowContext context, class [Microsoft.Crm.Sdk]Microsoft.Crm.Workflow.CrmWorkflow crmWorkflow, class [Microsoft.Crm.Sdk]Microsoft.Crm.Workflow.EntityDependencyBase entityDependency, [out] class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>& faultException, [opt] class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet columnSet)
0x8361  stloc.0
0x8362  ldloc.1
0x8363  brfalse.s loc_8379
0x8365  ldloc.1
0x8366  throw
0x8367  ldarg.0
0x8368  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityImageCollection Microsoft.Crm.Workflow.WorkflowContextBase::get_PreEntityImages()
0x836d  ldarg.0
0x836e  call     instance string Microsoft.Crm.Workflow.WorkflowContextBase::get_PrimaryEntityName()
0x8373  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Item(void)
0x8378  stloc.0
0x8379  ldloc.0
0x837a  ret
```
