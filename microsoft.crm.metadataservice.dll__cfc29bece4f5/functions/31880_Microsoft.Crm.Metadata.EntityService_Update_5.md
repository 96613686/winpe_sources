# Microsoft.Crm.Metadata.EntityService::Update_5

- ea: `0x31880`
- end: `0x31963`
- name: `Microsoft.Crm.Metadata.EntityService::Update_5`
- size: `227`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x317d0`
- `0x31850`

## callees

- `0x29080`
- `0x31880`
- `0x31980`
- `0x3cea0`
- `0x3d040`
- `0x3d0c0`
- `0x5a810`

## string_xrefs

- `0x318e2`: `UpdateEntity`
- `0x318e7`: `UpdateEntity`
- `0x318bd`: `prvWriteEntity`

## pseudocode

```c

```

## disassembly

```asm
0x31880  ldarg.1
0x31881  ldstr    aEntityid_0// "entityId"
0x31886  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x3188b  ldarg.2
0x3188c  ldstr    aEntityinfo// "entityInfo"
0x31891  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x31896  ldarg.s  4
0x31898  ldstr    aMetadatahelper// "metadataHelper"
0x3189d  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x318a2  ldarg.s  5
0x318a4  ldstr    aContext// "context"
0x318a9  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x318ae  ldarg.s  5
0x318b0  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x318b5  pop
0x318b6  ldarg.s  5
0x318b8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x318bd  ldstr    aPrvwriteentity// "prvWriteEntity"
0x318c2  ldarg.s  5
0x318c4  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.CustomizationSecurityCache::GetPrivilegeIdFromName(string privilegeName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x318c9  ldarg.s  5
0x318cb  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x318d0  ldarg.s  5
0x318d2  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::StartTransactionIfRequired()
0x318d7  stloc.0
0x318d8  ldarg.s  5
0x318da  ldc.i4.1
0x318db  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.AutoAddRootsContextModifier::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, valuetype [Microsoft.Crm.Core]Microsoft.Crm.AddRootsOption)
0x318e0  stloc.1
0x318e1  ldarg.1
0x318e2  ldstr    aUpdateentity// "UpdateEntity"
0x318e7  ldstr    aUpdateentity// "UpdateEntity"
0x318ec  ldarg.2
0x318ed  callvirt instance bool Microsoft.Crm.Metadata.EntityUpdateInfo::get_IsAuditEnabled()
0x318f2  ldarg.s  5
0x318f4  call     void Microsoft.Crm.Metadata.AuditHelper::InvokeAuditMetadataPlugin(valuetype [mscorlib]System.Guid targetId, string messageName, string requestName, bool isAuditEnabled, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x318f9  ldarg.0
0x318fa  ldarg.1
0x318fb  ldarg.2
0x318fc  ldarg.s  5
0x318fe  ldarg.s  4
0x31900  ldarg.3
0x31901  call     instance void Microsoft.Crm.Metadata.EntityService::UpdateNoPrivilegeChecks(valuetype [mscorlib]System.Guid entityId, class Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, bool mergeLabels)
0x31906  ldarg.s  5
0x31908  ldc.i4.4
0x31909  ldarg.1
0x3190a  ldc.i4.1
0x3190b  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::AddDependencyOperation(valuetype [Microsoft.Crm.Core]Microsoft.Crm.DependencyOperationType, valuetype [mscorlib]System.Guid, int32)
0x31910  ldloc.0
0x31911  brfalse.s loc_3191A
0x31913  ldarg.s  5
0x31915  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::CommitTransaction()
0x3191a  ldarg.1
0x3191b  ldarg.2
0x3191c  callvirt instance bool Microsoft.Crm.Metadata.EntityUpdateInfo::get_IsVisibleInMobileClient()
0x31921  ldarg.2
0x31922  callvirt instance bool Microsoft.Crm.Metadata.EntityUpdateInfo::get_IsInteractionCentricEnabled()
0x31927  ldarg.s  5
0x31929  call     void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ApplicationMetadataInvalidationTrigger::TriggerEntityMetadataUpdateInvalidation(valuetype [mscorlib]System.Guid, bool, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x3192e  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModuleMetadataChangeNotifier [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModuleMetadataChangeNotifier::get_Instance()
0x31933  ldarg.1
0x31934  ldarg.2
0x31935  callvirt instance bool Microsoft.Crm.Metadata.EntityUpdateInfo::get_IsVisibleInMobileClient()
0x3193a  ldarg.2
0x3193b  callvirt instance bool Microsoft.Crm.Metadata.EntityUpdateInfo::get_IsInteractionCentricEnabled()
0x31940  ldarg.s  5
0x31942  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModuleMetadataChangeNotifier::NotifyEntityMetadataChange(valuetype [mscorlib]System.Guid, bool, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x31947  leave.s  loc_31953
0x31949  ldloc.1
0x3194a  brfalse.s loc_31952
0x3194c  ldloc.1
0x3194d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x31952  endfinally
0x31953  leave.s  loc_31962
0x31955  pop
0x31956  ldloc.0
0x31957  brfalse.s loc_31960
0x31959  ldarg.s  5
0x3195b  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::RollbackTransaction()
0x31960  rethrow
0x31962  ret
```
