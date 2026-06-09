# Microsoft.Crm.CrmLive.Provisioning.FixOrgInfoAction::Do

- ea: `0xb040`
- end: `0xb3a4`
- name: `Microsoft.Crm.CrmLive.Provisioning.FixOrgInfoAction::Do`
- size: `868`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0xb040`
- `0xb4f0`
- `0x1bf90`
- `0x1bfc0`
- `0x1c040`
- `0x1c3b0`

## string_xrefs

- `0xb079`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\Action\SubscriptionRestore\FixOrgInfoAction.cs`
- `0xb179`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\Action\SubscriptionRestore\FixOrgInfoAction.cs`
- `0xb21f`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\Action\SubscriptionRestore\FixOrgInfoAction.cs`
- `0xb293`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\Action\SubscriptionRestore\FixOrgInfoAction.cs`
- `0xb307`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\Action\SubscriptionRestore\FixOrgInfoAction.cs`
- `0xb37c`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\Action\SubscriptionRestore\FixOrgInfoAction.cs`

## pseudocode

```c

```

## disassembly

```asm
0xb040  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0xb045  stloc.0
0xb046  ldloc.0
0xb047  ldstr    aOrganization// "Organization"
0xb04c  ldarg.0
0xb04d  call     instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData Microsoft.Crm.CrmLive.Provisioning.SubscriptionRestoreActionBase::get_RestoreData()
0xb052  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData::get_OrganizationId()
0xb057  box      [mscorlib]System.Guid
0xb05c  ldc.i4.2
0xb05d  newarr   [mscorlib]System.String
0xb062  dup
0xb063  ldc.i4.0
0xb064  ldstr    aSupportusercrm// "SupportUserCrmUserId"
0xb069  stelem.ref
0xb06a  dup
0xb06b  ldc.i4.1
0xb06c  ldstr    aDelegatedadmin// "DelegatedAdminCrmUserId"
0xb071  stelem.ref
0xb072  ldc.i4.s 0x1B
0xb074  ldstr    aDo// "Do"
0xb079  ldstr    aDDbsShDccm2110_12// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0xb07e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveById(string, object, string[], int32, string, string)
0xb083  dup
0xb084  ldstr    aSupportusercrm// "SupportUserCrmUserId"
0xb089  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xb08e  unbox.any [mscorlib]System.Guid
0xb093  stloc.1
0xb094  ldstr    aDelegatedadmin// "DelegatedAdminCrmUserId"
0xb099  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xb09e  unbox.any [mscorlib]System.Guid
0xb0a3  stloc.2
0xb0a4  call     class Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::NewService()
0xb0a9  dup
0xb0aa  ldarg.0
0xb0ab  call     instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData Microsoft.Crm.CrmLive.Provisioning.SubscriptionRestoreActionBase::get_RestoreData()
0xb0b0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData::get_OrganizationId()
0xb0b5  ldarg.0
0xb0b6  call     instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData Microsoft.Crm.CrmLive.Provisioning.SubscriptionRestoreActionBase::get_RestoreData()
0xb0bb  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData::get_InitialUserLiveId()
0xb0c0  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess::RetrieveSystemUserIdByEmail(valuetype [mscorlib]System.Guid organizationId, string email)
0xb0c5  stloc.3
0xb0c6  dup
0xb0c7  ldarg.0
0xb0c8  call     instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData Microsoft.Crm.CrmLive.Provisioning.SubscriptionRestoreActionBase::get_RestoreData()
0xb0cd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData::get_OrganizationId()
0xb0d2  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess::RetrieveSupportUserId(valuetype [mscorlib]System.Guid organizationId)
0xb0d7  stloc.s  4
0xb0d9  ldarg.0
0xb0da  call     instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData Microsoft.Crm.CrmLive.Provisioning.SubscriptionRestoreActionBase::get_RestoreData()
0xb0df  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData::get_OrganizationId()
0xb0e4  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess::RetrieveDelegatedAdminUserId(valuetype [mscorlib]System.Guid organizationId)
0xb0e9  stloc.s  5
0xb0eb  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparisonCollection::.ctor()
0xb0f0  stloc.s  6
0xb0f2  ldloc.s  6
0xb0f4  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison> [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparisonCollection::get_PropertyComparisonList()
0xb0f9  ldc.i4.5
0xb0fa  ldloc.1
0xb0fb  box      [mscorlib]System.Guid
0xb100  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Data.ConditionalOperator, object)
0xb105  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison>::Add(var<u1>)
0xb10a  ldloc.s  6
0xb10c  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison> [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparisonCollection::get_PropertyComparisonList()
0xb111  ldc.i4.5
0xb112  ldloc.2
0xb113  box      [mscorlib]System.Guid
0xb118  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Data.ConditionalOperator, object)
0xb11d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison>::Add(var<u1>)
0xb122  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0xb127  stloc.s  7
0xb129  ldloc.s  7
0xb12b  ldstr    aCrmuserid// "CrmUserId"
0xb130  ldloc.s  6
0xb132  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xb137  ldloc.s  7
0xb139  ldstr    aOrganizationid_0// "OrganizationId"
0xb13e  ldarg.0
0xb13f  call     instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData Microsoft.Crm.CrmLive.Provisioning.SubscriptionRestoreActionBase::get_RestoreData()
0xb144  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData::get_OrganizationId()
0xb149  box      [mscorlib]System.Guid
0xb14e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xb153  ldloc.0
0xb154  ldstr    aSystemuserorga// "SystemUserOrganizations"
0xb159  ldc.i4.1
0xb15a  newarr   [mscorlib]System.String
0xb15f  dup
0xb160  ldc.i4.0
0xb161  ldstr    aCrmuserid// "CrmUserId"
0xb166  stelem.ref
0xb167  ldc.i4.1
0xb168  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0xb16d  dup
0xb16e  ldc.i4.0
0xb16f  ldloc.s  7
0xb171  stelem.ref
0xb172  ldc.i4.s 0x2D
0xb174  ldstr    aDo// "Do"
0xb179  ldstr    aDDbsShDccm2110_12// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0xb17e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0xb183  dup
0xb184  callvirt instance int32 class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Count()
0xb189  ldc.i4.1
0xb18a  beq.s    loc_B197
0xb18c  ldstr    aDidNotFindTheE// "Did not find the expected number of non"...
0xb191  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0xb196  throw
0xb197  call     T0x2B000032
0xb19c  stloc.s  0xA
0xb19e  ldloca.s 0xA
0xb1a0  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Value()
0xb1a5  ldstr    aCrmuserid// "CrmUserId"
0xb1aa  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xb1af  unbox.any [mscorlib]System.Guid
0xb1b4  stloc.s  8
0xb1b6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0xb1bb  stloc.s  9
0xb1bd  ldloc.s  9
0xb1bf  ldstr    aCrmuserid// "CrmUserId"
0xb1c4  ldloc.3
0xb1c5  box      [mscorlib]System.Guid
0xb1ca  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xb1cf  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0xb1d4  stloc.s  7
0xb1d6  ldloc.s  7
0xb1d8  ldstr    aOrganizationid_0// "OrganizationId"
0xb1dd  ldarg.0
0xb1de  call     instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData Microsoft.Crm.CrmLive.Provisioning.SubscriptionRestoreActionBase::get_RestoreData()
0xb1e3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData::get_OrganizationId()
0xb1e8  box      [mscorlib]System.Guid
0xb1ed  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xb1f2  ldloc.s  7
0xb1f4  ldstr    aCrmuserid// "CrmUserId"
0xb1f9  ldloc.s  8
0xb1fb  box      [mscorlib]System.Guid
0xb200  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xb205  ldloc.0
0xb206  ldstr    aSystemuserorga// "SystemUserOrganizations"
0xb20b  ldloc.s  9
0xb20d  ldc.i4.1
0xb20e  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0xb213  dup
0xb214  ldc.i4.0
0xb215  ldloc.s  7
0xb217  stelem.ref
0xb218  ldc.i4.s 0x3C
0xb21a  ldstr    aDo// "Do"
0xb21f  ldstr    aDDbsShDccm2110_12// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0xb224  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0xb229  pop
0xb22a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0xb22f  stloc.s  9
0xb231  ldloc.s  9
0xb233  ldstr    aCrmuserid// "CrmUserId"
0xb238  ldloc.s  4
0xb23a  box      [mscorlib]System.Guid
0xb23f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xb244  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0xb249  stloc.s  7
0xb24b  ldloc.s  7
0xb24d  ldstr    aOrganizationid_0// "OrganizationId"
0xb252  ldarg.0
0xb253  call     instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData Microsoft.Crm.CrmLive.Provisioning.SubscriptionRestoreActionBase::get_RestoreData()
0xb258  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData::get_OrganizationId()
0xb25d  box      [mscorlib]System.Guid
0xb262  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xb267  ldloc.s  7
0xb269  ldstr    aCrmuserid// "CrmUserId"
0xb26e  ldloc.1
0xb26f  box      [mscorlib]System.Guid
0xb274  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xb279  ldloc.0
0xb27a  ldstr    aSystemuserorga// "SystemUserOrganizations"
0xb27f  ldloc.s  9
0xb281  ldc.i4.1
0xb282  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0xb287  dup
0xb288  ldc.i4.0
0xb289  ldloc.s  7
0xb28b  stelem.ref
0xb28c  ldc.i4.s 0x45
0xb28e  ldstr    aDo// "Do"
0xb293  ldstr    aDDbsShDccm2110_12// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0xb298  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0xb29d  pop
0xb29e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0xb2a3  stloc.s  9
0xb2a5  ldloc.s  9
0xb2a7  ldstr    aCrmuserid// "CrmUserId"
0xb2ac  ldloc.s  5
0xb2ae  box      [mscorlib]System.Guid
0xb2b3  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xb2b8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0xb2bd  stloc.s  7
0xb2bf  ldloc.s  7
0xb2c1  ldstr    aOrganizationid_0// "OrganizationId"
0xb2c6  ldarg.0
0xb2c7  call     instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData Microsoft.Crm.CrmLive.Provisioning.SubscriptionRestoreActionBase::get_RestoreData()
0xb2cc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData::get_OrganizationId()
0xb2d1  box      [mscorlib]System.Guid
0xb2d6  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xb2db  ldloc.s  7
0xb2dd  ldstr    aCrmuserid// "CrmUserId"
0xb2e2  ldloc.2
0xb2e3  box      [mscorlib]System.Guid
0xb2e8  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xb2ed  ldloc.0
0xb2ee  ldstr    aSystemuserorga// "SystemUserOrganizations"
0xb2f3  ldloc.s  9
0xb2f5  ldc.i4.1
0xb2f6  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0xb2fb  dup
0xb2fc  ldc.i4.0
0xb2fd  ldloc.s  7
0xb2ff  stelem.ref
0xb300  ldc.i4.s 0x4E
0xb302  ldstr    aDo// "Do"
0xb307  ldstr    aDDbsShDccm2110_12// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0xb30c  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0xb311  pop
0xb312  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0xb317  stloc.s  9
0xb319  ldloc.s  9
0xb31b  ldstr    aSupportusercrm// "SupportUserCrmUserId"
0xb320  ldloc.s  4
0xb322  box      [mscorlib]System.Guid
0xb327  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xb32c  ldloc.s  9
0xb32e  ldstr    aDelegatedadmin// "DelegatedAdminCrmUserId"
0xb333  ldloc.s  5
0xb335  box      [mscorlib]System.Guid
0xb33a  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xb33f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0xb344  stloc.s  7
0xb346  ldloc.s  7
0xb348  ldstr    aId// "Id"
0xb34d  ldarg.0
0xb34e  call     instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData Microsoft.Crm.CrmLive.Provisioning.SubscriptionRestoreActionBase::get_RestoreData()
0xb353  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData::get_OrganizationId()
0xb358  box      [mscorlib]System.Guid
0xb35d  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xb362  ldloc.0
0xb363  ldstr    aOrganization// "Organization"
0xb368  ldloc.s  9
0xb36a  ldc.i4.1
0xb36b  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0xb370  dup
0xb371  ldc.i4.0
0xb372  ldloc.s  7
0xb374  stelem.ref
0xb375  ldc.i4.s 0x57
0xb377  ldstr    aDo// "Do"
0xb37c  ldstr    aDDbsShDccm2110_12// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0xb381  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0xb386  pop
0xb387  leave.s  loc_B393
0xb389  ldloc.0
0xb38a  brfalse.s loc_B392
0xb38c  ldloc.0
0xb38d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb392  endfinally
0xb393  ldarg.0
0xb394  call     instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData Microsoft.Crm.CrmLive.Provisioning.SubscriptionRestoreActionBase::get_RestoreData()
0xb399  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.SubscriptionRestoreData::get_OrganizationId()
0xb39e  call     void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.LivePlatformSharedUtility::RecalculateOrganizationMaxStorage(valuetype [mscorlib]System.Guid)
0xb3a3  ret
```
