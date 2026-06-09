# Microsoft.Crm.Tools.Admin.BusinessProvisioningActionManager::GetActionsForCreateInternal

- ea: `0xd3c0`
- end: `0xd5bd`
- name: `Microsoft.Crm.Tools.Admin.BusinessProvisioningActionManager::GetActionsForCreateInternal`
- size: `509`
- prototype: ``
- caller_count: `1`
- callee_count: `39`
- tags: `broker_com_uri`

## callers

- `0xd290`

## callees

- `0xdd90`
- `0xdeb0`
- `0xdef0`
- `0xe030`
- `0xe100`
- `0xe200`
- `0xe240`
- `0xe280`
- `0xe2c0`
- `0xe350`
- `0xe8c0`
- `0xe900`
- `0xe9d0`
- `0xea10`
- `0xea50`
- `0xeaa0`
- `0xeaf0`
- `0xebb0`
- `0xec50`
- `0xeca0`
- `0xecf0`
- `0xed40`
- `0xeda0`
- `0xede0`
- `0xee20`
- `0xee70`
- `0xeeb0`
- `0xeef0`
- `0xef30`
- `0xef80`
- `0xefd0`
- `0xf050`
- `0xf0a0`
- `0xf240`
- `0xf460`
- `0xfb40`
- `0xfc40`
- `0xfdf0`
- `0xfe40`

## pseudocode

```c

```

## disassembly

```asm
0xd3c0  ldarg.0
0xd3c1  ldarg.1
0xd3c2  ldc.i4.0
0xd3c3  newobj   instance void Microsoft.Crm.Tools.Admin.SetReadCommittedSnapshotIsolation::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd3c8  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd3cd  ldarg.0
0xd3ce  ldarg.1
0xd3cf  ldc.i4.5
0xd3d0  newobj   instance void Microsoft.Crm.Tools.Admin.ProvisionBusinessAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd3d5  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd3da  ldarg.0
0xd3db  ldarg.1
0xd3dc  ldc.i4.0
0xd3dd  newobj   instance void Microsoft.Crm.Tools.Admin.SetOrganizationVersionAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd3e2  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd3e7  ldarg.0
0xd3e8  ldarg.1
0xd3e9  ldc.i4.1
0xd3ea  newobj   instance void Microsoft.Crm.Tools.Admin.RestoreFullTextIndexesAndConstraintsAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd3ef  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd3f4  ldarg.0
0xd3f5  ldarg.1
0xd3f6  ldc.i4.1
0xd3f7  newobj   instance void Microsoft.Crm.Tools.Admin.CreateDefaultSolutionPublisherAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd3fc  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd401  ldarg.0
0xd402  ldarg.1
0xd403  ldc.i4.1
0xd404  newobj   instance void Microsoft.Crm.Tools.Admin.CreateDefaultSysAdminFieldSecurityProfile::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd409  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd40e  ldarg.0
0xd40f  ldarg.1
0xd410  ldc.i4.1
0xd411  newobj   instance void Microsoft.Crm.Tools.Admin.PopulateDefaultSysAdminFieldSecurityProfile::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd416  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd41b  ldarg.0
0xd41c  ldarg.1
0xd41d  ldc.i4.3
0xd41e  newobj   instance void Microsoft.Crm.Tools.Admin.MarkApplicationMetadataInvalidAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd423  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd428  ldarg.0
0xd429  ldarg.1
0xd42a  ldc.i4.7
0xd42b  newobj   instance void Microsoft.Crm.Tools.Admin.ImportDefaultDataAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd430  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd435  ldarg.0
0xd436  ldarg.1
0xd437  ldc.i4.3
0xd438  newobj   instance void Microsoft.Crm.Tools.Admin.PublishDefaultDataAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd43d  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd442  ldarg.0
0xd443  ldarg.1
0xd444  ldc.i4.1
0xd445  newobj   instance void Microsoft.Crm.Tools.Admin.PopulateDefaultDataForGoalManagement::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd44a  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd44f  ldarg.0
0xd450  ldarg.1
0xd451  ldc.i4.1
0xd452  newobj   instance void Microsoft.Crm.Tools.Admin.PopulateDefaultDataForMultiEntitySearch::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd457  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd45c  ldarg.0
0xd45d  ldarg.1
0xd45e  ldc.i4.1
0xd45f  newobj   instance void Microsoft.Crm.Tools.Admin.ImportDisplayStringsAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd464  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd469  ldarg.0
0xd46a  ldarg.1
0xd46b  ldc.i4.1
0xd46c  newobj   instance void Microsoft.Crm.Tools.Admin.PopulateBaseOrganizationLanguagePackAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd471  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd476  ldarg.0
0xd477  ldarg.1
0xd478  ldc.i4.1
0xd479  newobj   instance void Microsoft.Crm.Tools.Admin.AsyncOperationFullTextCatalogIndexSetupAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd47e  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd483  ldarg.0
0xd484  ldarg.1
0xd485  ldc.i4.1
0xd486  newobj   instance void Microsoft.Crm.Tools.Admin.AsyncOperationUpdateKnowledgeArticleStatesSetupAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd48b  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd490  ldarg.0
0xd491  ldarg.1
0xd492  ldc.i4.1
0xd493  newobj   instance void Microsoft.Crm.Tools.Admin.AsyncOperationRecurringSeriesExpansionSetupAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd498  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd49d  ldarg.0
0xd49e  ldarg.1
0xd49f  ldc.i4.1
0xd4a0  newobj   instance void Microsoft.Crm.Tools.Admin.BulkDeleteAsyncOperationSetupAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd4a5  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd4aa  ldarg.0
0xd4ab  ldarg.1
0xd4ac  ldc.i4.1
0xd4ad  newobj   instance void Microsoft.Crm.Tools.Admin.BulkDeleteExpanderEventSetupAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd4b2  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd4b7  ldarg.0
0xd4b8  ldarg.1
0xd4b9  ldc.i4.1
0xd4ba  newobj   instance void Microsoft.Crm.Tools.Admin.BulkDeleteSyncWorkflowProcessSessionsSetupAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd4bf  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd4c4  ldarg.0
0xd4c5  ldarg.1
0xd4c6  ldc.i4.1
0xd4c7  newobj   instance void Microsoft.Crm.Tools.Admin.GoalRollupAsyncOperationSetupAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd4cc  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd4d1  ldarg.0
0xd4d2  ldarg.1
0xd4d3  ldc.i4.1
0xd4d4  newobj   instance void Microsoft.Crm.Tools.Admin.PostToYammerAsyncOperationSetupAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd4d9  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd4de  ldarg.0
0xd4df  ldarg.1
0xd4e0  ldc.i4.1
0xd4e1  newobj   instance void Microsoft.Crm.Tools.Admin.AsyncOperationResourceBookingSyncSetupAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd4e6  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd4eb  ldarg.0
0xd4ec  ldarg.1
0xd4ed  ldc.i4.1
0xd4ee  newobj   instance void Microsoft.Crm.Tools.Admin.AsyncOperationCleanupSolutionComponentsOperation::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd4f3  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd4f8  ldarg.0
0xd4f9  ldarg.1
0xd4fa  ldc.i4.1
0xd4fb  newobj   instance void Microsoft.Crm.Tools.Admin.AsyncOperationALMAnomalyDetectionOperation::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd500  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd505  ldarg.0
0xd506  ldarg.1
0xd507  ldc.i4.1
0xd508  newobj   instance void Microsoft.Crm.Tools.Admin.SetFiscalSettingsAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd50d  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd512  ldarg.0
0xd513  ldarg.1
0xd514  ldc.i4.1
0xd515  newobj   instance void Microsoft.Crm.Tools.Admin.SetTokenKeyAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd51a  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd51f  ldarg.0
0xd520  ldarg.1
0xd521  ldc.i4.1
0xd522  newobj   instance void Microsoft.Crm.Tools.Admin.SetBaseCurrencyAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd527  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd52c  ldarg.0
0xd52d  ldarg.1
0xd52e  ldc.i4.1
0xd52f  newobj   instance void Microsoft.Crm.Tools.Admin.SetTrackingTokenAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd534  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd539  ldarg.0
0xd53a  ldarg.1
0xd53b  ldc.i4.1
0xd53c  newobj   instance void Microsoft.Crm.Tools.Admin.UpdateDefaultCrmNameAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd541  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd546  ldarg.0
0xd547  ldarg.1
0xd548  ldc.i4.1
0xd549  newobj   instance void Microsoft.Crm.Tools.Admin.CreateActiveSolutionApplicationRibbonComponent::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd54e  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd553  ldarg.0
0xd554  ldarg.1
0xd555  ldc.i4.5
0xd556  newobj   instance void Microsoft.Crm.Tools.Admin.SetIsManaged::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd55b  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd560  ldarg.0
0xd561  ldarg.1
0xd562  ldc.i4.1
0xd563  newobj   instance void Microsoft.Crm.Tools.Admin.LanguageLocaleDataPopulationAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd568  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd56d  ldarg.0
0xd56e  ldarg.1
0xd56f  ldc.i4.1
0xd570  newobj   instance void Microsoft.Crm.Tools.Admin.ActionCardAsyncOperationSetupAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd575  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd57a  ldarg.0
0xd57b  ldarg.1
0xd57c  ldc.i4.2
0xd57d  newobj   instance void Microsoft.Crm.Tools.Admin.PopulateSolutionComponentAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd582  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd587  ldarg.0
0xd588  ldarg.1
0xd589  ldc.i4.5
0xd58a  newobj   instance void Microsoft.Crm.Tools.Admin.PopulateDependencyNodesAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd58f  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd594  ldarg.0
0xd595  ldarg.1
0xd596  ldc.i4.8
0xd597  newobj   instance void Microsoft.Crm.Tools.Admin.PopulateDependenciesAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd59c  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd5a1  ldarg.0
0xd5a2  ldarg.1
0xd5a3  ldc.i4.1
0xd5a4  newobj   instance void Microsoft.Crm.Tools.Admin.UpdateRollupFields::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd5a9  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd5ae  ldarg.0
0xd5af  ldarg.1
0xd5b0  ldc.i4.1
0xd5b1  newobj   instance void Microsoft.Crm.Tools.Admin.NavigationPropertyNameDataPopulationAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0xd5b6  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0xd5bb  ldarg.0
0xd5bc  ret
```
