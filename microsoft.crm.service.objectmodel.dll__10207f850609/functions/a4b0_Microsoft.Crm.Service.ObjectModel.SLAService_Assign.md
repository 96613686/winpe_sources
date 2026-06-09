# Microsoft.Crm.Service.ObjectModel.SLAService::Assign

- ea: `0xa4b0`
- end: `0xa61b`
- name: `Microsoft.Crm.Service.ObjectModel.SLAService::Assign`
- size: `363`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0xa4b0`
- `0xa870`
- `0xa8e0`

## pseudocode

```c

```

## disassembly

```asm
0xa4b0  ldc.i4.0
0xa4b1  stloc.0
0xa4b2  ldarg.0
0xa4b3  ldarg.1
0xa4b4  ldarg.3
0xa4b5  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.Service.ObjectModel.SLAService::RetrieveSLARecord(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xa4ba  stloc.1
0xa4bb  ldarg.3
0xa4bc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0xa4c1  box      [mscorlib]System.Guid
0xa4c6  ldarg.2
0xa4c7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_PrincipalId()
0xa4cc  box      [mscorlib]System.Guid
0xa4d1  call     bool [mscorlib]System.Object::Equals(object, object)
0xa4d6  brtrue.s loc_A503
0xa4d8  ldloc.1
0xa4d9  ldstr    aStatecode// "statecode"
0xa4de  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xa4e3  unbox.any [mscorlib]System.Int32
0xa4e8  brfalse.s loc_A503
0xa4ea  ldarg.0
0xa4eb  ldarg.1
0xa4ec  ldc.i4.0
0xa4ed  ldc.i4.1
0xa4ee  ldarg.3
0xa4ef  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::SetState(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, int32, int32, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xa4f4  pop
0xa4f5  ldc.i4.1
0xa4f6  stloc.0
0xa4f7  ldloc.1
0xa4f8  ldstr    aWorkflowid// "workflowid"
0xa4fd  ldnull
0xa4fe  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xa503  ldarg.0
0xa504  ldarg.1
0xa505  ldarg.2
0xa506  ldarg.3
0xa507  call     instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Assign(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityPrincipal, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xa50c  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowService::.ctor()
0xa511  stloc.2
0xa512  ldarg.3
0xa513  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xa518  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.WorkflowEntity::.ctor(valuetype [mscorlib]System.Guid)
0xa51d  stloc.3
0xa51e  ldloc.1
0xa51f  ldstr    aWorkflowid// "workflowid"
0xa524  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xa529  brfalse.s loc_A572
0xa52b  ldloc.1
0xa52c  ldstr    aWorkflowid// "workflowid"
0xa531  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xa536  unbox.any [mscorlib]System.Guid
0xa53b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xa540  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xa545  brfalse.s loc_A572
0xa547  ldloc.0
0xa548  brtrue.s loc_A572
0xa54a  ldloc.1
0xa54b  ldstr    aWorkflowid// "workflowid"
0xa550  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xa555  unbox.any [mscorlib]System.Guid
0xa55a  ldloc.3
0xa55b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0xa560  ldarg.3
0xa561  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa566  stloc.s  4
0xa568  ldloc.2
0xa569  ldloc.s  4
0xa56b  ldarg.2
0xa56c  ldarg.3
0xa56d  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Assign(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityPrincipal, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xa572  ldarg.0
0xa573  ldloc.1
0xa574  ldstr    aSlaid// "slaid"
0xa579  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xa57e  unbox.any [mscorlib]System.Guid
0xa583  ldarg.3
0xa584  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Service.ObjectModel.SLAService::RetrieveSLAItemWorkflows(valuetype [mscorlib]System.Guid SLAId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xa589  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0xa58e  stloc.s  5
0xa590  br.s     loc_A5FA
0xa592  ldloc.s  5
0xa594  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xa599  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0xa59e  stloc.s  6
0xa5a0  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowService::.ctor()
0xa5a5  stloc.2
0xa5a6  ldloc.s  6
0xa5a8  ldstr    aWorkflowid// "workflowid"
0xa5ad  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xa5b2  brfalse.s loc_A5FA
0xa5b4  ldloc.s  6
0xa5b6  ldstr    aWorkflowid// "workflowid"
0xa5bb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xa5c0  unbox.any [mscorlib]System.Guid
0xa5c5  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xa5ca  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xa5cf  brfalse.s loc_A5FA
0xa5d1  ldloc.s  6
0xa5d3  ldstr    aWorkflowid// "workflowid"
0xa5d8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xa5dd  unbox.any [mscorlib]System.Guid
0xa5e2  ldloc.3
0xa5e3  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0xa5e8  ldarg.3
0xa5e9  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa5ee  stloc.s  7
0xa5f0  ldloc.2
0xa5f1  ldloc.s  7
0xa5f3  ldarg.2
0xa5f4  ldarg.3
0xa5f5  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Assign(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityPrincipal, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xa5fa  ldloc.s  5
0xa5fc  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xa601  brtrue.s loc_A592
0xa603  leave.s  loc_A61A
0xa605  ldloc.s  5
0xa607  isinst   [mscorlib]System.IDisposable
0xa60c  stloc.s  8
0xa60e  ldloc.s  8
0xa610  brfalse.s loc_A619
0xa612  ldloc.s  8
0xa614  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa619  endfinally
0xa61a  ret
```
