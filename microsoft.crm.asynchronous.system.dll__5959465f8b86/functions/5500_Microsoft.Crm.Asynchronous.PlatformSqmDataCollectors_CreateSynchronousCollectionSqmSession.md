# Microsoft.Crm.Asynchronous.PlatformSqmDataCollectors::CreateSynchronousCollectionSqmSession

- ea: `0x5500`
- end: `0x582a`
- name: `Microsoft.Crm.Asynchronous.PlatformSqmDataCollectors::CreateSynchronousCollectionSqmSession`
- size: `810`
- prototype: ``
- caller_count: `1`
- callee_count: `35`
- tags: `broker_com_uri`

## callers

- `0x5490`

## callees

- `0x4330`
- `0x4370`
- `0x43b0`
- `0x4450`
- `0x4490`
- `0x44e0`
- `0x45b0`
- `0x45f0`
- `0x4630`
- `0x46a0`
- `0x4730`
- `0x47a0`
- `0x4980`
- `0x4b50`
- `0x4b90`
- `0x4bd0`
- `0x4c30`
- `0x4ca0`
- `0x4ce0`
- `0x4d50`
- `0x4dd0`
- `0x4e60`
- `0x4ea0`
- `0x4ee0`
- `0x4f20`
- `0x51c0`
- `0x5200`
- `0x5240`
- `0x5280`
- `0x52c0`
- `0x5300`
- `0x5340`
- `0x5380`
- `0x53c0`
- `0x5400`

## pseudocode

```c

```

## disassembly

```asm
0x5500  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x5505  stloc.0
0x5506  ldloc.0
0x5507  newobj   instance void [Microsoft.Crm]Microsoft.Crm.MemoryInformationCollector::.ctor()
0x550c  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x5511  pop
0x5512  ldloc.0
0x5513  newobj   instance void [Microsoft.Crm]Microsoft.Crm.CPUInformationCollector::.ctor()
0x5518  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x551d  pop
0x551e  ldloc.0
0x551f  newobj   instance void [Microsoft.Crm]Microsoft.Crm.OSInformationCollector::.ctor()
0x5524  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x5529  pop
0x552a  ldloc.0
0x552b  newobj   instance void [Microsoft.Crm]Microsoft.Crm.CrmServerVersionCollector::.ctor()
0x5530  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x5535  pop
0x5536  ldloc.0
0x5537  newobj   instance void [Microsoft.Crm]Microsoft.Crm.SystemUpTimeInformationCollector::.ctor()
0x553c  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x5541  pop
0x5542  ldloc.0
0x5543  newobj   instance void [Microsoft.Crm]Microsoft.Crm.CrmMobileInstallationCollector::.ctor()
0x5548  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x554d  pop
0x554e  ldloc.0
0x554f  ldarg.0
0x5550  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.PlatformSqmDataCollectors::_configuration
0x5555  newobj   instance void Microsoft.Crm.Asynchronous.DatabaseSizeInformationCollector::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration configuration)
0x555a  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x555f  pop
0x5560  ldloc.0
0x5561  ldarg.0
0x5562  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.PlatformSqmDataCollectors::_configuration
0x5567  newobj   instance void Microsoft.Crm.Asynchronous.CrmBuildQFECollector::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration configuration)
0x556c  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x5571  pop
0x5572  ldloc.0
0x5573  ldarg.0
0x5574  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.PlatformSqmDataCollectors::_configuration
0x5579  newobj   instance void Microsoft.Crm.Asynchronous.SqlServerInformationCollector::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration configuration)
0x557e  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x5583  pop
0x5584  ldloc.0
0x5585  newobj   instance void [Microsoft.Crm]Microsoft.Crm.UserDefaultUILanguageCollector::.ctor()
0x558a  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x558f  pop
0x5590  ldloc.0
0x5591  ldarg.0
0x5592  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.PlatformSqmDataCollectors::_configuration
0x5597  newobj   instance void Microsoft.Crm.Asynchronous.AverageSyncTimeCollector::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration configuration)
0x559c  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x55a1  pop
0x55a2  ldloc.0
0x55a3  ldarg.0
0x55a4  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.PlatformSqmDataCollectors::_configuration
0x55a9  newobj   instance void Microsoft.Crm.Asynchronous.DistinctClientSyncsCollector::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration configuration)
0x55ae  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x55b3  pop
0x55b4  ldloc.0
0x55b5  ldarg.0
0x55b6  ldfld    string Microsoft.Crm.Asynchronous.PlatformSqmDataCollectors::deploymentSkuInput
0x55bb  newobj   instance void Microsoft.Crm.Asynchronous.CrmSKUCollector::.ctor(string deploymentSku)
0x55c0  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x55c5  pop
0x55c6  ldloc.0
0x55c7  ldarg.0
0x55c8  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.PlatformSqmDataCollectors::_configuration
0x55cd  newobj   instance void Microsoft.Crm.Asynchronous.CrmGrantedLicenseCountCollector::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration configuration)
0x55d2  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x55d7  pop
0x55d8  ldloc.0
0x55d9  ldarg.0
0x55da  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.PlatformSqmDataCollectors::_configuration
0x55df  newobj   instance void Microsoft.Crm.Asynchronous.ServerOrganizationIdCollector::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration configuration)
0x55e4  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x55e9  pop
0x55ea  ldloc.0
0x55eb  ldarg.0
0x55ec  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.PlatformSqmDataCollectors::_configuration
0x55f1  newobj   instance void Microsoft.Crm.Asynchronous.CustomEntityCountCollector::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration configuration)
0x55f6  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x55fb  pop
0x55fc  ldloc.0
0x55fd  ldarg.0
0x55fe  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.PlatformSqmDataCollectors::_configuration
0x5603  newobj   instance void Microsoft.Crm.Asynchronous.CustomAttributeCountCollector::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration configuration)
0x5608  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x560d  pop
0x560e  ldloc.0
0x560f  ldarg.0
0x5610  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.PlatformSqmDataCollectors::_configuration
0x5615  newobj   instance void Microsoft.Crm.Asynchronous.ObjectCountCollector::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration configuration)
0x561a  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x561f  pop
0x5620  ldloc.0
0x5621  ldarg.0
0x5622  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.PlatformSqmDataCollectors::_configuration
0x5627  newobj   instance void Microsoft.Crm.Asynchronous.RoleCustomizationInformationCollector::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration configuration)
0x562c  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x5631  pop
0x5632  ldloc.0
0x5633  ldarg.0
0x5634  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.PlatformSqmDataCollectors::_configuration
0x5639  newobj   instance void Microsoft.Crm.Asynchronous.ConnectionInformationCollector::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration configuration)
0x563e  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x5643  pop
0x5644  ldloc.0
0x5645  ldarg.0
0x5646  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.PlatformSqmDataCollectors::_configuration
0x564b  newobj   instance void Microsoft.Crm.Asynchronous.QueryCountCollector::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration configuration)
0x5650  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x5655  pop
0x5656  ldloc.0
0x5657  ldarg.0
0x5658  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.PlatformSqmDataCollectors::_configuration
0x565d  newobj   instance void Microsoft.Crm.Asynchronous.AvgCasePerOwningUserCollector::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration configuration)
0x5662  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x5667  pop
0x5668  ldloc.0
0x5669  ldarg.0
0x566a  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.PlatformSqmDataCollectors::_configuration
0x566f  newobj   instance void Microsoft.Crm.Asynchronous.UserStatsCollector::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration configuration)
0x5674  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x5679  pop
0x567a  ldloc.0
0x567b  ldarg.0
0x567c  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.PlatformSqmDataCollectors::_configuration
0x5681  newobj   instance void Microsoft.Crm.Asynchronous.SchedulableResourceInformationCollector::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration configuration)
0x5686  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x568b  pop
0x568c  ldloc.0
0x568d  ldarg.0
0x568e  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.PlatformSqmDataCollectors::_configuration
0x5693  newobj   instance void Microsoft.Crm.Asynchronous.AvgResourceCountPerServiceAppointmentCollector::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration configuration)
0x5698  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x569d  pop
0x569e  ldloc.0
0x569f  ldarg.0
0x56a0  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.PlatformSqmDataCollectors::_configuration
0x56a5  newobj   instance void Microsoft.Crm.Asynchronous.OutlookClientCounter::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration configuration)
0x56aa  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x56af  pop
0x56b0  ldloc.0
0x56b1  ldarg.0
0x56b2  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.PlatformSqmDataCollectors::_configuration
0x56b7  newobj   instance void Microsoft.Crm.Asynchronous.DesktopClientSyncCollector::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration configuration)
0x56bc  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x56c1  pop
0x56c2  ldloc.0
0x56c3  ldarg.0
0x56c4  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.PlatformSqmDataCollectors::_configuration
0x56c9  newobj   instance void Microsoft.Crm.Asynchronous.SrsExecutionLogCollector::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration configuration)
0x56ce  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x56d3  pop
0x56d4  ldloc.0
0x56d5  ldarg.0
0x56d6  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.PlatformSqmDataCollectors::_configuration
0x56db  newobj   instance void Microsoft.Crm.Asynchronous.MarketingListSizeCollector::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration configuration)
0x56e0  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x56e5  pop
0x56e6  ldloc.0
0x56e7  ldarg.0
0x56e8  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.PlatformSqmDataCollectors::_configuration
0x56ed  newobj   instance void Microsoft.Crm.Asynchronous.DeDupParametersCollector::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration configuration)
0x56f2  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x56f7  pop
0x56f8  ldloc.0
0x56f9  ldarg.0
0x56fa  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.PlatformSqmDataCollectors::_configuration
0x56ff  newobj   instance void Microsoft.Crm.Asynchronous.BulkDeleteParametersCollector::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration configuration)
0x5704  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x5709  pop
0x570a  ldloc.0
0x570b  ldarg.0
0x570c  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.PlatformSqmDataCollectors::_configuration
0x5711  newobj   instance void Microsoft.Crm.Asynchronous.DocMgmtParametersCollector::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration configuration)
0x5716  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x571b  pop
0x571c  ldloc.0
0x571d  ldarg.0
0x571e  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.PlatformSqmDataCollectors::_configuration
0x5723  newobj   instance void Microsoft.Crm.Asynchronous.ImportParametersCollector::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration configuration)
0x5728  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x572d  pop
0x572e  ldloc.0
0x572f  ldarg.0
0x5730  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.PlatformSqmDataCollectors::_configuration
0x5735  newobj   instance void Microsoft.Crm.Asynchronous.GoalSQMCollector::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration configuration)
0x573a  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x573f  pop
0x5740  ldloc.0
0x5741  ldarg.0
0x5742  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.PlatformSqmDataCollectors::_configuration
0x5747  newobj   instance void Microsoft.Crm.Asynchronous.MuiInformationCollector::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration configuration)
0x574c  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x5751  pop
0x5752  ldloc.0
0x5753  ldarg.0
0x5754  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.PlatformSqmDataCollectors::_configuration
0x5759  newobj   instance void Microsoft.Crm.Asynchronous.FlsCollector::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration configuration)
0x575e  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x5763  pop
0x5764  ldloc.0
0x5765  ldarg.0
0x5766  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.PlatformSqmDataCollectors::_configuration
0x576b  newobj   instance void Microsoft.Crm.Asynchronous.DisplayStringsCustomizedCollector::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration configuration)
0x5770  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x5775  pop
0x5776  ldloc.0
0x5777  ldarg.0
0x5778  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.PlatformSqmDataCollectors::_configuration
0x577d  newobj   instance void Microsoft.Crm.Asynchronous.SolutionDataCollector::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration configuration)
0x5782  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x5787  pop
0x5788  ldloc.0
0x5789  newobj   instance void [Microsoft.Crm]Microsoft.Crm.NumberOfOrganizationsCollector::.ctor()
0x578e  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x5793  pop
0x5794  ldloc.0
0x5795  newobj   instance void [Microsoft.Crm]Microsoft.Crm.NumberOfServersCollector::.ctor()
0x579a  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x579f  pop
0x57a0  ldloc.0
0x57a1  newobj   instance void [Microsoft.Crm]Microsoft.Crm.ClaimsEnabledCollector::.ctor()
0x57a6  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x57ab  pop
0x57ac  ldloc.0
0x57ad  newobj   instance void [Microsoft.Crm]Microsoft.Crm.ServerEditionCollector::.ctor()
0x57b2  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x57b7  pop
0x57b8  ldloc.0
0x57b9  newobj   instance void [Microsoft.Crm]Microsoft.Crm.IfdStateCollector::.ctor()
0x57be  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x57c3  pop
0x57c4  ldloc.0
0x57c5  ldarg.0
0x57c6  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.PlatformSqmDataCollectors::_configuration
0x57cb  newobj   instance void Microsoft.Crm.Asynchronous.ChartSqmCollector::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration configuration)
0x57d0  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x57d5  pop
0x57d6  ldloc.0
0x57d7  ldarg.0
0x57d8  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.PlatformSqmDataCollectors::_configuration
0x57dd  newobj   instance void Microsoft.Crm.Asynchronous.DashboardSqmCollector::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration configuration)
0x57e2  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x57e7  pop
0x57e8  ldloc.0
0x57e9  ldarg.0
0x57ea  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.PlatformSqmDataCollectors::_configuration
0x57ef  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnectorSqmCollector::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration configuration)
0x57f4  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x57f9  pop
0x57fa  ldloc.0
0x57fb  ldarg.0
0x57fc  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.PlatformSqmDataCollectors::_configuration
0x5801  newobj   instance void Microsoft.Crm.Asynchronous.IsAirMergedSqmCollector::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration configuration)
0x5806  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x580b  pop
0x580c  ldarg.1
0x580d  ldc.i4.3
0x580e  ldloc.0
0x580f  ldtoken  [Microsoft.Crm]Microsoft.Crm.ISqmCollector
0x5814  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5819  callvirt instance class [mscorlib]System.Array [mscorlib]System.Collections.ArrayList::ToArray(class [mscorlib]System.Type)
0x581e  castclass class [Microsoft.Crm]Microsoft.Crm.ISqmCollector[]
0x5823  ldarg.2
0x5824  newobj   instance void [Microsoft.Crm]Microsoft.Crm.SynchronousCollectionSqmSession::.ctor(string, valuetype [Microsoft.Crm]Microsoft.Crm.SqmSessionType, class [Microsoft.Crm]Microsoft.Crm.ISqmCollector[], class [Microsoft.Crm]Microsoft.Crm.ISqmSettings)
0x5829  ret
```
