# Microsoft.Crm.Service.ObjectModel.SLAService::InternalSetState

- ea: `0x9fc0`
- end: `0xa26d`
- name: `Microsoft.Crm.Service.ObjectModel.SLAService::InternalSetState`
- size: `685`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x9fc0`
- `0xa340`
- `0xa710`
- `0xa8e0`
- `0xa980`
- `0xac00`
- `0xac70`
- `0xacd0`
- `0xad70`
- `0xb430`

## pseudocode

```c

```

## disassembly

```asm
0x9fc0  ldarg.s  4
0x9fc2  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.SLA
0x9fc7  stloc.0
0x9fc8  ldc.i4.0
0x9fc9  stloc.1
0x9fca  ldarg.0
0x9fcb  ldarg.1
0x9fcc  ldarg.s  5
0x9fce  call     instance void Microsoft.Crm.Service.ObjectModel.SLAService::CheckForOwnerOfSLA(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x9fd3  ldstr    aIncident_0// "incident"
0x9fd8  stloc.2
0x9fd9  ldc.i4.0
0x9fda  stloc.3
0x9fdb  ldloc.0
0x9fdc  ldstr    aObjecttypecode// "objecttypecode"
0x9fe1  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x9fe6  brtrue.s loc_A015
0x9fe8  ldloc.0
0x9fe9  ldstr    aObjecttypecode// "objecttypecode"
0x9fee  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x9ff3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9ff8  call     int32 [mscorlib]System.Convert::ToInt32(object, class [mscorlib]System.IFormatProvider)
0x9ffd  stloc.3
0x9ffe  ldarg.s  5
0xa000  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xa005  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0xa00a  stloc.s  4
0xa00c  ldloc.3
0xa00d  ldloc.s  4
0xa00f  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ObjectServiceUtility::GetEntityLogicalNameFromObjectTypeCode(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa014  stloc.2
0xa015  ldarg.2
0xa016  ldc.i4.1
0xa017  bne.un   loc_A0DC
0xa01c  ldloc.0
0xa01d  ldstr    aStatecode// "statecode"
0xa022  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xa027  unbox.any [mscorlib]System.Int32
0xa02c  ldc.i4.1
0xa02d  bne.un.s loc_A040
0xa02f  ldc.i4   0x8004F861
0xa034  ldc.i4.0
0xa035  newarr   [mscorlib]System.Object
0xa03a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0xa03f  throw
0xa040  ldarg.0
0xa041  ldloc.3
0xa042  ldarg.s  5
0xa044  call     instance bool Microsoft.Crm.Service.ObjectModel.SLAService::IsSlaEnabledForEntity(int32 regardingObjectTypeCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xa049  brtrue.s loc_A05C
0xa04b  ldc.i4   0x80055003
0xa050  ldc.i4.0
0xa051  newarr   [mscorlib]System.Object
0xa056  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0xa05b  throw
0xa05c  ldarg.0
0xa05d  ldloc.3
0xa05e  ldarg.s  5
0xa060  call     instance bool Microsoft.Crm.Service.ObjectModel.SLAService::IsMaximumEntitiesWithActiveSLALimitReached(int32 objectTypeCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xa065  brfalse.s loc_A078
0xa067  ldc.i4   0x8004F897
0xa06c  ldc.i4.0
0xa06d  newarr   [mscorlib]System.Object
0xa072  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0xa077  throw
0xa078  ldloc.2
0xa079  ldstr    aIncident_0// "incident"
0xa07e  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xa083  brfalse.s loc_A0A6
0xa085  ldarg.1
0xa086  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0xa08b  ldloc.3
0xa08c  ldarg.s  5
0xa08e  call     bool Microsoft.Crm.Service.ObjectModel.SLAService::CheckMaximumSLAKPILimitReachedOnline(valuetype [mscorlib]System.Guid slaId, int32 objectTypeCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xa093  brfalse.s loc_A0A6
0xa095  ldc.i4   0x8004F898
0xa09a  ldc.i4.0
0xa09b  newarr   [mscorlib]System.Object
0xa0a0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0xa0a5  throw
0xa0a6  ldloc.2
0xa0a7  ldarg.1
0xa0a8  ldarg.s  5
0xa0aa  ldc.i4.0
0xa0ab  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.IWorkflowAuthorService Microsoft.Crm.Service.ObjectModel.WorkflowAuthorServiceFactory::Create(string entityName, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, valuetype [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowAuthorType type)
0xa0b0  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.IWorkflowAuthorService::AuthorWorkflow()
0xa0b5  ldarg.1
0xa0b6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_EntityMetadata()
0xa0bb  ldarg.s  5
0xa0bd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xa0c2  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityClassFactory::CreateInstance(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, valuetype [mscorlib]System.Guid)
0xa0c7  starg.s  4
0xa0c9  ldarg.0
0xa0ca  ldarg.1
0xa0cb  ldarg.s  5
0xa0cd  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.Service.ObjectModel.SLAService::RetrieveSLARecord(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xa0d2  starg.s  4
0xa0d4  ldarg.s  4
0xa0d6  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.SLA
0xa0db  stloc.0
0xa0dc  nop
0xa0dd  ldarg.s  5
0xa0df  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Transaction()
0xa0e4  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::StartTransaction()
0xa0e9  ldarg.2
0xa0ea  ldc.i4.1
0xa0eb  bne.un.s loc_A142
0xa0ed  ldloc.0
0xa0ee  ldstr    aStatecode// "statecode"
0xa0f3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xa0f8  unbox.any [mscorlib]System.Int32
0xa0fd  ldc.i4.1
0xa0fe  bne.un.s loc_A111
0xa100  ldc.i4   0x8004F861
0xa105  ldc.i4.0
0xa106  newarr   [mscorlib]System.Object
0xa10b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0xa110  throw
0xa111  ldarg.s  5
0xa113  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ObjectServiceUtility::IsSLAFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa118  brfalse.s loc_A132
0xa11a  ldarg.0
0xa11b  ldloc.3
0xa11c  ldarg.s  5
0xa11e  call     instance bool Microsoft.Crm.Service.ObjectModel.SLAService::IsActiveSLAExistOnTargetEntity(int32 objectTypeCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xa123  brtrue.s loc_A132
0xa125  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SlaPluginRegistrationHelper::.ctor()
0xa12a  ldarg.s  5
0xa12c  ldloc.3
0xa12d  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SlaPluginRegistrationHelper::RegisterGolbalSLAPlugIn(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, int32)
0xa132  ldarg.0
0xa133  ldarg.1
0xa134  ldarg.2
0xa135  ldarg.3
0xa136  ldarg.s  4
0xa138  ldarg.s  5
0xa13a  call     instance bool Microsoft.Crm.Service.ObjectModel.SLAService::SetStateRuleandWorkflow(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, int32 newState, int32 newStatusCode, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity originalEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xa13f  stloc.1
0xa140  br.s     loc_A1C0
0xa142  ldloc.0
0xa143  ldstr    aStatecode// "statecode"
0xa148  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xa14d  unbox.any [mscorlib]System.Int32
0xa152  brtrue.s loc_A165
0xa154  ldc.i4   0x8004F862
0xa159  ldc.i4.0
0xa15a  newarr   [mscorlib]System.Object
0xa15f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0xa164  throw
0xa165  ldloc.0
0xa166  ldstr    aIsdefault// "isdefault"
0xa16b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xa170  unbox.any [mscorlib]System.Boolean
0xa175  brfalse.s loc_A191
0xa177  ldloc.0
0xa178  ldstr    aIsdefault// "isdefault"
0xa17d  ldc.i4.0
0xa17e  box      [mscorlib]System.Boolean
0xa183  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xa188  ldarg.0
0xa189  ldloc.0
0xa18a  ldarg.s  5
0xa18c  call     instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::UpdateEntityInternal(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xa191  ldarg.0
0xa192  ldarg.1
0xa193  ldarg.2
0xa194  ldarg.3
0xa195  ldarg.s  4
0xa197  ldarg.s  5
0xa199  call     instance bool Microsoft.Crm.Service.ObjectModel.SLAService::SetStateRuleandWorkflow(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, int32 newState, int32 newStatusCode, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity originalEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xa19e  stloc.1
0xa19f  ldarg.s  5
0xa1a1  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ObjectServiceUtility::IsSLAFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa1a6  brfalse.s loc_A1C0
0xa1a8  ldarg.0
0xa1a9  ldloc.3
0xa1aa  ldarg.s  5
0xa1ac  call     instance bool Microsoft.Crm.Service.ObjectModel.SLAService::IsActiveSLAExistOnTargetEntity(int32 objectTypeCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xa1b1  brtrue.s loc_A1C0
0xa1b3  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SlaPluginRegistrationHelper::.ctor()
0xa1b8  ldarg.s  5
0xa1ba  ldloc.3
0xa1bb  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SlaPluginRegistrationHelper::DeregisterGolbalSLAPlugIn(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, int32)
0xa1c0  ldarg.s  5
0xa1c2  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Transaction()
0xa1c7  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::CommitTransaction()
0xa1cc  leave    loc_A25F
0xa1d1  stloc.s  5
0xa1d3  ldarg.s  5
0xa1d5  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Transaction()
0xa1da  ldc.i4.0
0xa1db  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::RollbackTransaction(bool)
0xa1e0  ldloc.0
0xa1e1  ldstr    aWorkflowid// "workflowid"
0xa1e6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xa1eb  callvirt instance string [mscorlib]System.Object::ToString()
0xa1f0  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowService::.ctor()
0xa1f5  stloc.s  6
0xa1f7  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xa1fc  ldstr    aWorkflow// "Workflow"
0xa201  ldarg.s  5
0xa203  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xa208  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid)
0xa20d  stloc.s  7
0xa20f  ldloc.s  6
0xa211  ldloc.s  7
0xa213  ldarg.s  5
0xa215  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Delete(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xa21a  ldloc.0
0xa21b  ldstr    aWorkflowid// "workflowid"
0xa220  ldnull
0xa221  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xa226  ldarg.0
0xa227  ldloc.0
0xa228  ldarg.s  5
0xa22a  call     instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::UpdateEntityInternal(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xa22f  ldloc.s  5
0xa231  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0xa236  ldc.i4   0x80045016
0xa23b  bne.un.s loc_A24D
0xa23d  ldstr    aYouDonTHaveThe// "You don't have the required permissions"...
0xa242  ldc.i4   0x8004F875
0xa247  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xa24c  throw
0xa24d  ldloc.s  5
0xa24f  callvirt instance string [mscorlib]System.Exception::get_Message()
0xa254  ldc.i4   0x8004F863
0xa259  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xa25e  throw
0xa25f  ldarg.2
0xa260  brtrue.s loc_A26B
0xa262  ldarg.0
0xa263  ldarg.1
0xa264  ldarg.s  5
0xa266  call     instance void Microsoft.Crm.Service.ObjectModel.SLAService::DeleteSLAWorkflow(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xa26b  ldloc.1
0xa26c  ret
```
