# Microsoft.Crm.ObjectModel.OrganizationManagementHelper::UpdateOrganizationReferences

- ea: `0xce2e0`
- end: `0xce607`
- name: `Microsoft.Crm.ObjectModel.OrganizationManagementHelper::UpdateOrganizationReferences`
- size: `807`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callees

- `0xce2e0`
- `0xce610`
- `0xce660`
- `0xce6e0`
- `0xce780`
- `0xce820`
- `0xce860`
- `0xce8a0`
- `0xcecc0`
- `0xced00`
- `0x238810`
- `0x238830`
- `0x238850`
- `0x238870`

## string_xrefs

- `0xce324`: `UpdateOrganizationReferences`
- `0xce329`: `UpdateOrganizationReferences`
- `0xce410`: `PrepareOrgForMigration completed`
- `0xce449`: `UpdateBusinessUnits completed`
- `0xce49c`: `BeginOrgMigration completed`
- `0xce4b4`: `UpdateOrgIdReferences`
- `0xce4e5`: `UpdateOrgIdReferences completed`
- `0xce52a`: `UpdateSystemUserPrincipals completed`
- `0xce56f`: `UpdatePrincipalObjectAccess completed`
- `0xce5a8`: `RemoveOldOrg completed`
- `0xce5b6`: `UpdateOrganizationReferences completed: `
- `0xce5d3`: `UpdateOrganizationReferences failed: `

## pseudocode

```c

```

## disassembly

```asm
0xce2e0  newobj   instance void <>c__DisplayClass0_0::.ctor()
0xce2e5  stloc.0
0xce2e6  ldloc.0
0xce2e7  ldarg.1
0xce2e8  stfld    string <>c__DisplayClass0_0::newFriendlyName
0xce2ed  ldloc.0
0xce2ee  ldarg.0
0xce2ef  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass0_0::newOrganizationId
0xce2f4  ldarg.2
0xce2f5  ldstr    aContext// "context"
0xce2fa  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xce2ff  ldarg.2
0xce300  callvirt instance class [System.Data]System.Data.IDbTransaction [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext::get_SqlTransaction()
0xce305  ldstr    aContextSqltran// "context.SqlTransaction"
0xce30a  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xce30f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xce314  stloc.1
0xce315  ldnull
0xce316  stloc.2
0xce317  call     class [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.IAuditHistory [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.AuditHistory::NewService()
0xce31c  stloc.2
0xce31d  ldloc.2
0xce31e  ldloc.0
0xce31f  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass0_0::newOrganizationId
0xce324  ldstr    aUpdateorganiza// "UpdateOrganizationReferences"
0xce329  ldstr    aUpdateorganiza// "UpdateOrganizationReferences"
0xce32e  ldstr    aStarted// "started"
0xce333  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.IAuditHistory::CreateEntry(valuetype [mscorlib]System.Guid, string, string, string)
0xce338  stloc.1
0xce339  ldarg.2
0xce33a  callvirt instance class [System.Data]System.Data.IDbTransaction [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext::get_SqlTransaction()
0xce33f  callvirt instance valuetype [System.Data]System.Data.IsolationLevel [System.Data]System.Data.IDbTransaction::get_IsolationLevel()
0xce344  ldc.i4   0x100000
0xce349  bne.un   loc_CE606
0xce34e  newobj   instance void <>c__DisplayClass0_1::.ctor()
0xce353  stloc.3
0xce354  ldloc.3
0xce355  ldloc.0
0xce356  stfld    class <>c__DisplayClass0_0 <>c__DisplayClass0_1::CS$<>8__locals1
0xce35b  ldloc.3
0xce35c  ldarg.2
0xce35d  ldc.i4.1
0xce35e  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext::CreateSqlCommand(bool)
0xce363  stfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass0_1::command
0xce368  newobj   instance void <>c__DisplayClass0_2::.ctor()
0xce36d  stloc.s  4
0xce36f  ldloc.s  4
0xce371  ldloc.3
0xce372  stfld    class <>c__DisplayClass0_1 <>c__DisplayClass0_2::CS$<>8__locals2
0xce377  ldloc.s  4
0xce379  ldfld    class <>c__DisplayClass0_1 <>c__DisplayClass0_2::CS$<>8__locals2
0xce37e  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass0_1::command
0xce383  ldarg.2
0xce384  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xce389  call     int32 [Microsoft.Crm]Microsoft.Crm.Timeouts::GetExtendedSqlTimeoutInSeconds(valuetype [mscorlib]System.Guid)
0xce38e  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandTimeout(int32)
0xce393  ldarg.2
0xce394  ldarg.2
0xce395  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext::get_Connection()
0xce39a  ldarg.3
0xce39b  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.ObjectModel.OrganizationManagementHelper::LoadMetadataCache(class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context, class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection connection, bool loadMetadataForMetadataFromOrgDB)
0xce3a0  stloc.s  5
0xce3a2  ldloc.s  4
0xce3a4  ldloc.s  4
0xce3a6  ldfld    class <>c__DisplayClass0_1 <>c__DisplayClass0_2::CS$<>8__locals2
0xce3ab  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass0_1::command
0xce3b0  call     valuetype [mscorlib]System.Guid Microsoft.Crm.ObjectModel.OrganizationManagementHelper::GetCurrentOrganizationId(class [System.Data]System.Data.IDbCommand command)
0xce3b5  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass0_2::oldOrganizationId
0xce3ba  ldloc.s  4
0xce3bc  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass0_2::oldOrganizationId
0xce3c1  ldstr    aOldorganizatio// "oldOrganizationId"
0xce3c6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0xce3cb  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0xce3d0  stloc.s  6
0xce3d2  newobj   instance void <>c__DisplayClass0_3::.ctor()
0xce3d7  stloc.s  7
0xce3d9  ldloc.s  7
0xce3db  ldloc.s  4
0xce3dd  stfld    class <>c__DisplayClass0_2 <>c__DisplayClass0_3::CS$<>8__locals3
0xce3e2  ldloc.s  7
0xce3e4  ldfld    class <>c__DisplayClass0_2 <>c__DisplayClass0_3::CS$<>8__locals3
0xce3e9  ldfld    class <>c__DisplayClass0_1 <>c__DisplayClass0_2::CS$<>8__locals2
0xce3ee  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass0_1::command
0xce3f3  ldloc.s  7
0xce3f5  ldfld    class <>c__DisplayClass0_2 <>c__DisplayClass0_3::CS$<>8__locals3
0xce3fa  ldfld    class <>c__DisplayClass0_1 <>c__DisplayClass0_2::CS$<>8__locals2
0xce3ff  ldfld    class <>c__DisplayClass0_0 <>c__DisplayClass0_1::CS$<>8__locals1
0xce404  ldfld    string <>c__DisplayClass0_0::newFriendlyName
0xce409  call     void Microsoft.Crm.ObjectModel.OrganizationManagementHelper::PrepareOrgForMigration(class [System.Data]System.Data.IDbCommand command, string newFriendlyName)
0xce40e  ldloc.s  6
0xce410  ldstr    aPrepareorgform// "PrepareOrgForMigration completed"
0xce415  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0xce41a  pop
0xce41b  ldloc.s  7
0xce41d  ldfld    class <>c__DisplayClass0_2 <>c__DisplayClass0_3::CS$<>8__locals3
0xce422  ldfld    class <>c__DisplayClass0_1 <>c__DisplayClass0_2::CS$<>8__locals2
0xce427  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass0_1::command
0xce42c  ldloc.s  7
0xce42e  ldfld    class <>c__DisplayClass0_2 <>c__DisplayClass0_3::CS$<>8__locals3
0xce433  ldfld    class <>c__DisplayClass0_1 <>c__DisplayClass0_2::CS$<>8__locals2
0xce438  ldfld    class <>c__DisplayClass0_0 <>c__DisplayClass0_1::CS$<>8__locals1
0xce43d  ldfld    string <>c__DisplayClass0_0::newFriendlyName
0xce442  call     void Microsoft.Crm.ObjectModel.OrganizationManagementHelper::UpdateBusinessUnits(class [System.Data]System.Data.IDbCommand command, string newFriendlyName)
0xce447  ldloc.s  6
0xce449  ldstr    aUpdatebusiness// "UpdateBusinessUnits completed"
0xce44e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0xce453  pop
0xce454  ldloc.s  7
0xce456  ldloc.s  5
0xce458  ldstr    aOrganization// "Organization"
0xce45d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string)
0xce462  stfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata <>c__DisplayClass0_3::entity
0xce467  ldloc.s  7
0xce469  ldfld    class <>c__DisplayClass0_2 <>c__DisplayClass0_3::CS$<>8__locals3
0xce46e  ldfld    class <>c__DisplayClass0_1 <>c__DisplayClass0_2::CS$<>8__locals2
0xce473  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass0_1::command
0xce478  ldloc.s  7
0xce47a  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata <>c__DisplayClass0_3::entity
0xce47f  ldloc.s  7
0xce481  ldfld    class <>c__DisplayClass0_2 <>c__DisplayClass0_3::CS$<>8__locals3
0xce486  ldfld    class <>c__DisplayClass0_1 <>c__DisplayClass0_2::CS$<>8__locals2
0xce48b  ldfld    class <>c__DisplayClass0_0 <>c__DisplayClass0_1::CS$<>8__locals1
0xce490  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass0_0::newOrganizationId
0xce495  call     void Microsoft.Crm.ObjectModel.OrganizationManagementHelper::BeginOrgMigration(class [System.Data]System.Data.IDbCommand command, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entity, valuetype [mscorlib]System.Guid newOrganizationId)
0xce49a  ldloc.s  6
0xce49c  ldstr    aBeginorgmigrat// "BeginOrgMigration completed"
0xce4a1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0xce4a6  pop
0xce4a7  ldloc.s  7
0xce4a9  ldftn    instance void <>c__DisplayClass0_3::<UpdateOrganizationReferences>b__0()
0xce4af  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0xce4b4  ldstr    aUpdateorgidref// "UpdateOrgIdReferences"
0xce4b9  ldloc.s  7
0xce4bb  ldfld    class <>c__DisplayClass0_2 <>c__DisplayClass0_3::CS$<>8__locals3
0xce4c0  ldfld    class <>c__DisplayClass0_1 <>c__DisplayClass0_2::CS$<>8__locals2
0xce4c5  ldfld    class <>c__DisplayClass0_0 <>c__DisplayClass0_1::CS$<>8__locals1
0xce4ca  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass0_0::newOrganizationId
0xce4cf  ldc.r8   30.0
0xce4d8  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0xce4dd  ldc.i4.3
0xce4de  call     void Microsoft.Crm.ObjectModel.OrganizationManagementHelper::DoWithRetry(class [mscorlib]System.Action action, string actionName, valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.TimeSpan sleepPeriod, int32 tryCount)
0xce4e3  ldloc.s  6
0xce4e5  ldstr    aUpdateorgidref_0// "UpdateOrgIdReferences completed"
0xce4ea  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0xce4ef  pop
0xce4f0  ldloc.s  7
0xce4f2  ldfld    class <>c__DisplayClass0_2 <>c__DisplayClass0_3::CS$<>8__locals3
0xce4f7  ldfld    class <>c__DisplayClass0_1 <>c__DisplayClass0_2::CS$<>8__locals2
0xce4fc  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass0_1::command
0xce501  ldloc.s  7
0xce503  ldfld    class <>c__DisplayClass0_2 <>c__DisplayClass0_3::CS$<>8__locals3
0xce508  ldfld    class <>c__DisplayClass0_1 <>c__DisplayClass0_2::CS$<>8__locals2
0xce50d  ldfld    class <>c__DisplayClass0_0 <>c__DisplayClass0_1::CS$<>8__locals1
0xce512  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass0_0::newOrganizationId
0xce517  ldloc.s  7
0xce519  ldfld    class <>c__DisplayClass0_2 <>c__DisplayClass0_3::CS$<>8__locals3
0xce51e  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass0_2::oldOrganizationId
0xce523  call     void Microsoft.Crm.ObjectModel.OrganizationManagementHelper::UpdateSystemUserPrincipals(class [System.Data]System.Data.IDbCommand command, valuetype [mscorlib]System.Guid newOrganizationId, valuetype [mscorlib]System.Guid oldOrganizationId)
0xce528  ldloc.s  6
0xce52a  ldstr    aUpdatesystemus// "UpdateSystemUserPrincipals completed"
0xce52f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0xce534  pop
0xce535  ldloc.s  7
0xce537  ldfld    class <>c__DisplayClass0_2 <>c__DisplayClass0_3::CS$<>8__locals3
0xce53c  ldfld    class <>c__DisplayClass0_1 <>c__DisplayClass0_2::CS$<>8__locals2
0xce541  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass0_1::command
0xce546  ldloc.s  7
0xce548  ldfld    class <>c__DisplayClass0_2 <>c__DisplayClass0_3::CS$<>8__locals3
0xce54d  ldfld    class <>c__DisplayClass0_1 <>c__DisplayClass0_2::CS$<>8__locals2
0xce552  ldfld    class <>c__DisplayClass0_0 <>c__DisplayClass0_1::CS$<>8__locals1
0xce557  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass0_0::newOrganizationId
0xce55c  ldloc.s  7
0xce55e  ldfld    class <>c__DisplayClass0_2 <>c__DisplayClass0_3::CS$<>8__locals3
0xce563  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass0_2::oldOrganizationId
0xce568  call     void Microsoft.Crm.ObjectModel.OrganizationManagementHelper::UpdatePrincipalObjectAccess(class [System.Data]System.Data.IDbCommand command, valuetype [mscorlib]System.Guid newOrganizationId, valuetype [mscorlib]System.Guid oldOrganizationId)
0xce56d  ldloc.s  6
0xce56f  ldstr    aUpdateprincipa// "UpdatePrincipalObjectAccess completed"
0xce574  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0xce579  pop
0xce57a  ldloc.s  7
0xce57c  ldfld    class <>c__DisplayClass0_2 <>c__DisplayClass0_3::CS$<>8__locals3
0xce581  ldfld    class <>c__DisplayClass0_1 <>c__DisplayClass0_2::CS$<>8__locals2
0xce586  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass0_1::command
0xce58b  ldloc.s  7
0xce58d  ldfld    class <>c__DisplayClass0_2 <>c__DisplayClass0_3::CS$<>8__locals3
0xce592  ldfld    class <>c__DisplayClass0_1 <>c__DisplayClass0_2::CS$<>8__locals2
0xce597  ldfld    class <>c__DisplayClass0_0 <>c__DisplayClass0_1::CS$<>8__locals1
0xce59c  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass0_0::newOrganizationId
0xce5a1  call     void Microsoft.Crm.ObjectModel.OrganizationManagementHelper::RemoveOldOrg(class [System.Data]System.Data.IDbCommand command, valuetype [mscorlib]System.Guid newOrganizationId)
0xce5a6  ldloc.s  6
0xce5a8  ldstr    aRemoveoldorgCo// "RemoveOldOrg completed"
0xce5ad  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0xce5b2  pop
0xce5b3  ldloc.2
0xce5b4  ldloc.1
0xce5b5  ldc.i4.1
0xce5b6  ldstr    aUpdateorganiza_0// "UpdateOrganizationReferences completed:"...
0xce5bb  ldloc.s  6
0xce5bd  callvirt instance string [mscorlib]System.Object::ToString()
0xce5c2  call     string [mscorlib]System.String::Concat(string, string)
0xce5c7  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.IAuditHistory::CompleteEntry(valuetype [mscorlib]System.Guid, bool, string)
0xce5cc  leave.s  loc_CE606
0xce5ce  stloc.s  8
0xce5d0  ldloc.2
0xce5d1  ldloc.1
0xce5d2  ldc.i4.0
0xce5d3  ldstr    aUpdateorganiza_1// "UpdateOrganizationReferences failed: "
0xce5d8  ldloc.s  6
0xce5da  callvirt instance string [mscorlib]System.Object::ToString()
0xce5df  ldloc.s  8
0xce5e1  callvirt instance string [mscorlib]System.Object::ToString()
0xce5e6  call     string [mscorlib]System.String::Concat(string, string, string)
0xce5eb  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.IAuditHistory::CompleteEntry(valuetype [mscorlib]System.Guid, bool, string)
0xce5f0  rethrow
0xce5f2  ldloc.3
0xce5f3  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass0_1::command
0xce5f8  brfalse.s loc_CE605
0xce5fa  ldloc.3
0xce5fb  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass0_1::command
0xce600  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xce605  endfinally
0xce606  ret
```
