# Microsoft.Crm.Workflow.ObjectModel.WorkflowAssemblyResolverHelper::RetrieveActivityNameAndGroupName

- ea: `0x1b2d0`
- end: `0x1b372`
- name: `Microsoft.Crm.Workflow.ObjectModel.WorkflowAssemblyResolverHelper::RetrieveActivityNameAndGroupName`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x5710`

## callees

- `0x6900`
- `0x1b280`
- `0x1b2d0`

## string_xrefs

- `0x1b30d`: `service`

## pseudocode

```c

```

## disassembly

```asm
0x1b2d0  ldarg.s  4
0x1b2d2  brtrue.s loc_1B2E4
0x1b2d4  ldstr    aArgumentCannot// "Argument cannot be null"
0x1b2d9  ldstr    aContext// "context"
0x1b2de  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string, string)
0x1b2e3  throw
0x1b2e4  ldarg.2
0x1b2e5  ldsfld   string [mscorlib]System.String::Empty
0x1b2ea  stind.ref
0x1b2eb  ldarg.3
0x1b2ec  ldsfld   string [mscorlib]System.String::Empty
0x1b2f1  stind.ref
0x1b2f2  ldarg.0
0x1b2f3  ldarg.1
0x1b2f4  ldc.i4.0
0x1b2f5  ldarg.s  5
0x1b2f7  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression Microsoft.Crm.Workflow.ObjectModel.WorkflowAssemblyResolverHelper::CreatePluginQueryFromTypeName(string assemblyQualifiedTypeName, bool includeNonDesignerActivities, bool ignoreWeb)
0x1b2fc  stloc.0
0x1b2fd  ldarg.s  4
0x1b2ff  ldc.i4.0
0x1b300  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Workflow.ICommonWorkflowContext::CreateSdkService(bool asAdminUser)
0x1b305  dup
0x1b306  brtrue.s loc_1B318
0x1b308  ldstr    aArgumentCannot// "Argument cannot be null"
0x1b30d  ldstr    aService// "service"
0x1b312  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string, string)
0x1b317  throw
0x1b318  ldloc.0
0x1b319  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase)
0x1b31e  stloc.1
0x1b31f  ldloc.1
0x1b320  brfalse.s loc_1B370
0x1b322  ldloc.1
0x1b323  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x1b328  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x1b32d  ldc.i4.0
0x1b32e  ble.s    loc_1B370
0x1b330  ldloc.1
0x1b331  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x1b336  ldc.i4.0
0x1b337  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Item(!!T0)
0x1b33c  stloc.2
0x1b33d  ldarg.2
0x1b33e  ldloc.2
0x1b33f  ldstr    aName// "name"
0x1b344  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1b349  isinst   [mscorlib]System.String
0x1b34e  stind.ref
0x1b34f  ldloc.2
0x1b350  ldstr    aWorkflowactivi// "workflowactivitygroupname"
0x1b355  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x1b35a  brfalse.s loc_1B36E
0x1b35c  ldarg.3
0x1b35d  ldloc.2
0x1b35e  ldstr    aWorkflowactivi// "workflowactivitygroupname"
0x1b363  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1b368  isinst   [mscorlib]System.String
0x1b36d  stind.ref
0x1b36e  ldc.i4.1
0x1b36f  ret
0x1b370  ldc.i4.0
0x1b371  ret
```
