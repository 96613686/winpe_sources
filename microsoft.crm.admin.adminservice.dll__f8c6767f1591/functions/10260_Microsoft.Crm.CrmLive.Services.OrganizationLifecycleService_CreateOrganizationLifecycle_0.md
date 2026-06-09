# Microsoft.Crm.CrmLive.Services.OrganizationLifecycleService::CreateOrganizationLifecycle_0

- ea: `0x10260`
- end: `0x105de`
- name: `Microsoft.Crm.CrmLive.Services.OrganizationLifecycleService::CreateOrganizationLifecycle_0`
- size: `894`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x10250`

## callees

- `0xfcb0`
- `0xfcd0`
- `0xfcf0`
- `0xfd10`
- `0xfd90`
- `0xfdb0`
- `0xfdf0`
- `0x101e0`
- `0x101f0`
- `0x10260`
- `0x114c0`

## string_xrefs

- `0x10577`: `CreatedOn`
- `0x104a6`: `ConfigurationStatusCode`
- `0x103af`: `D:\a\1\s\src\CrmLive\Admin\OrganizationLifecycle\OrganizationLifecycleService.cs`
- `0x1050a`: `D:\a\1\s\src\CrmLive\Admin\OrganizationLifecycle\OrganizationLifecycleService.cs`
- `0x10552`: `D:\a\1\s\src\CrmLive\Admin\OrganizationLifecycle\OrganizationLifecycleService.cs`
- `0x1059d`: `D:\a\1\s\src\CrmLive\Admin\OrganizationLifecycle\OrganizationLifecycleService.cs`
- `0x10316`: `Org already created for this id: {0}. StackTrace: {1}`
- `0x103aa`: `CreateOrganizationLifecycle`
- `0x10505`: `CreateOrganizationLifecycle`
- `0x1054d`: `CreateOrganizationLifecycle`
- `0x10598`: `CreateOrganizationLifecycle`

## pseudocode

```c

```

## disassembly

```asm
0x10260  ldarg.1
0x10261  ldstr    aOrganizationin// "organizationInfo"
0x10266  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1026b  ldarg.1
0x1026c  callvirt instance class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmLive.Puid Microsoft.Crm.CrmLive.Services.OrganizationInfo::get_InitialUserPuid()
0x10271  ldstr    aOrganizationin_0// "organizationInfo.InitialUserPuid"
0x10276  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1027b  ldarg.1
0x1027c  callvirt instance string Microsoft.Crm.CrmLive.Services.OrganizationInfo::get_InitialUserEmail()
0x10281  ldstr    aOrganizationin_1// "organizationInfo.InitialUserEmail"
0x10286  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1028b  ldarg.1
0x1028c  callvirt instance string Microsoft.Crm.CrmLive.Services.OrganizationInfo::get_InitialUserFirstName()
0x10291  ldstr    aOrganizationin_2// "organizationInfo.InitialUserFirstName"
0x10296  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1029b  ldarg.1
0x1029c  callvirt instance string Microsoft.Crm.CrmLive.Services.OrganizationInfo::get_InitialUserLastName()
0x102a1  ldstr    aOrganizationin_3// "organizationInfo.InitialUserLastName"
0x102a6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x102ab  ldarg.1
0x102ac  callvirt instance string Microsoft.Crm.CrmLive.Services.OrganizationInfo::get_InitialUserLiveId()
0x102b1  ldstr    aOrganizationin_4// "organizationInfo.InitialUserLiveId"
0x102b6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x102bb  ldarg.1
0x102bc  callvirt instance string Microsoft.Crm.CrmLive.Services.OrganizationInfo::get_OrganizationFriendlyName()
0x102c1  ldstr    aOrganizationin_5// "organizationInfo.OrganizationFriendlyNa"...
0x102c6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x102cb  ldarg.1
0x102cc  callvirt instance string Microsoft.Crm.CrmLive.Services.OrganizationInfo::get_OrganizationUniqueName()
0x102d1  ldstr    aOrganizationin_6// "organizationInfo.OrganizationUniqueName"
0x102d6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x102db  ldarg.2
0x102dc  ldstr    aOrgid// "orgId"
0x102e1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x102e6  ldstr    aOrganizationli_0// "OrganizationLifeCycle_"
0x102eb  ldarga.s 2
0x102ed  constrained. [mscorlib]System.Guid
0x102f3  callvirt instance string [mscorlib]System.Object::ToString()
0x102f8  call     string [mscorlib]System.String::Concat(string, string)
0x102fd  call     class [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.IConfigDBLock [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigDBLock::NewLock(string)
0x10302  stloc.0
0x10303  ldarg.s  4
0x10305  brtrue.s loc_10344
0x10307  ldarg.2
0x10308  ldarg.0
0x10309  call     instance class Microsoft.Crm.CrmLive.Services.CrmLiveContext Microsoft.Crm.CrmLive.Services.OrganizationLifecycleService::get_Context()
0x1030e  call     bool Microsoft.Crm.CrmLive.Services.OrganizationLifecycleService::DoesOrganizationExist(valuetype [mscorlib]System.Guid orgId, class Microsoft.Crm.CrmLive.Services.CrmLiveContext context)
0x10313  brfalse.s loc_10344
0x10315  ldnull
0x10316  ldstr    aOrgAlreadyCrea// "Org already created for this id: {0}. S"...
0x1031b  ldc.i4.2
0x1031c  newarr   [mscorlib]System.Object
0x10321  dup
0x10322  ldc.i4.0
0x10323  ldarga.s 2
0x10325  ldstr    aD// "D"
0x1032a  call     instance string [mscorlib]System.Guid::ToString(string)
0x1032f  stelem.ref
0x10330  dup
0x10331  ldc.i4.1
0x10332  call     string [mscorlib]System.Environment::get_StackTrace()
0x10337  stelem.ref
0x10338  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::Error(class [mscorlib]System.Exception, string, object[])
0x1033d  ldarg.2
0x1033e  stloc.1
0x1033f  leave    loc_105DC
0x10344  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x10349  stloc.2
0x1034a  ldloc.2
0x1034b  ldc.i4.2
0x1034c  ldc.i4   0x1000
0x10351  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ICrmTransaction [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::BeginTransaction(valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigScope, valuetype [System.Data]System.Data.IsolationLevel)
0x10356  stloc.3
0x10357  ldarg.s  4
0x10359  brfalse  loc_103E0
0x1035e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x10363  stloc.s  7
0x10365  ldloc.s  7
0x10367  ldstr    aCrmorganizatio// "CrmOrganizationId"
0x1036c  ldarg.2
0x1036d  box      [mscorlib]System.Guid
0x10372  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x10377  ldloc.s  7
0x10379  ldstr    aOrganizationun// "OrganizationUniqueName"
0x1037e  ldarg.1
0x1037f  callvirt instance string Microsoft.Crm.CrmLive.Services.OrganizationInfo::get_OrganizationUniqueName()
0x10384  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x10389  ldc.i4.s 0xB
0x1038b  ldloc.s  7
0x1038d  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.OrganizationLifecycleStatus Microsoft.Crm.CrmLive.Services.OrganizationLifecycleService::GetOrganizationLifecycleStatus(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag conditions)
0x10392  bne.un.s loc_103BC
0x10394  ldloc.2
0x10395  ldstr    aOrganizationli// "OrganizationLifecycle"
0x1039a  ldc.i4.1
0x1039b  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x103a0  dup
0x103a1  ldc.i4.0
0x103a2  ldloc.s  7
0x103a4  stelem.ref
0x103a5  ldc.i4   0x8E
0x103aa  ldstr    aCreateorganiza// "CreateOrganizationLifecycle"
0x103af  ldstr    aDA1SSrcCrmlive_21// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x103b4  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Delete(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x103b9  pop
0x103ba  br.s     loc_103E0
0x103bc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x103c1  ldstr    aOrganizationli_1// "OrganizationLifecycleStatus for orgId {"...
0x103c6  ldc.i4.1
0x103c7  newarr   [mscorlib]System.Object
0x103cc  dup
0x103cd  ldc.i4.0
0x103ce  ldarg.2
0x103cf  box      [mscorlib]System.Guid
0x103d4  stelem.ref
0x103d5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x103da  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0x103df  throw
0x103e0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x103e5  stloc.s  4
0x103e7  ldloc.s  4
0x103e9  ldstr    aCrmorganizatio// "CrmOrganizationId"
0x103ee  ldarg.2
0x103ef  box      [mscorlib]System.Guid
0x103f4  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x103f9  ldloc.s  4
0x103fb  ldstr    aInitialuserema// "InitialUserEmail"
0x10400  ldarg.1
0x10401  callvirt instance string Microsoft.Crm.CrmLive.Services.OrganizationInfo::get_InitialUserEmail()
0x10406  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1040b  ldloc.s  4
0x1040d  ldstr    aInitialuserfir// "InitialUserFirstName"
0x10412  ldarg.1
0x10413  callvirt instance string Microsoft.Crm.CrmLive.Services.OrganizationInfo::get_InitialUserFirstName()
0x10418  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1041d  ldloc.s  4
0x1041f  ldstr    aInitialuserlas// "InitialUserLastName"
0x10424  ldarg.1
0x10425  callvirt instance string Microsoft.Crm.CrmLive.Services.OrganizationInfo::get_InitialUserLastName()
0x1042a  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1042f  ldloc.s  4
0x10431  ldstr    aInitialuserpui// "InitialUserPuid"
0x10436  ldarg.1
0x10437  callvirt instance class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmLive.Puid Microsoft.Crm.CrmLive.Services.OrganizationInfo::get_InitialUserPuid()
0x1043c  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmLive.Puid::get_Text()
0x10441  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x10446  ldloc.s  4
0x10448  ldstr    aInitialuserliv// "InitialUserLiveId"
0x1044d  ldarg.1
0x1044e  callvirt instance string Microsoft.Crm.CrmLive.Services.OrganizationInfo::get_InitialUserLiveId()
0x10453  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x10458  ldloc.s  4
0x1045a  ldstr    aOrganizationfr// "OrganizationFriendlyName"
0x1045f  ldarg.1
0x10460  callvirt instance string Microsoft.Crm.CrmLive.Services.OrganizationInfo::get_OrganizationFriendlyName()
0x10465  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1046a  ldloc.s  4
0x1046c  ldstr    aOrganizationun// "OrganizationUniqueName"
0x10471  ldarg.1
0x10472  callvirt instance string Microsoft.Crm.CrmLive.Services.OrganizationInfo::get_OrganizationUniqueName()
0x10477  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1047c  ldloc.s  4
0x1047e  ldstr    aStatuscode// "StatusCode"
0x10483  ldarg.3
0x10484  box      [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.OrganizationLifecycleStatus
0x10489  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1048e  ldloc.s  4
0x10490  ldstr    aModifiedon// "ModifiedOn"
0x10495  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x1049a  box      [mscorlib]System.DateTime
0x1049f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x104a4  ldloc.s  4
0x104a6  ldstr    aConfigurations// "ConfigurationStatusCode"
0x104ab  ldc.i4.0
0x104ac  box      [Microsoft.Crm.Constants]Microsoft.Crm.CrmLive.OrganizationConfigurationStatus
0x104b1  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x104b6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x104bb  stloc.s  5
0x104bd  ldloc.s  5
0x104bf  ldstr    aOrganizationun// "OrganizationUniqueName"
0x104c4  ldarg.1
0x104c5  callvirt instance string Microsoft.Crm.CrmLive.Services.OrganizationInfo::get_OrganizationUniqueName()
0x104ca  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x104cf  ldloc.s  5
0x104d1  ldstr    aStatuscode// "StatusCode"
0x104d6  ldc.i4.0
0x104d7  box      [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.OrganizationLifecycleStatus
0x104dc  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x104e1  ldloc.2
0x104e2  ldstr    aOrganizationli// "OrganizationLifecycle"
0x104e7  ldc.i4.1
0x104e8  newarr   [mscorlib]System.String
0x104ed  dup
0x104ee  ldc.i4.0
0x104ef  ldstr    aId// "Id"
0x104f4  stelem.ref
0x104f5  ldc.i4.1
0x104f6  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x104fb  dup
0x104fc  ldc.i4.0
0x104fd  ldloc.s  5
0x104ff  stelem.ref
0x10500  ldc.i4   0xA9
0x10505  ldstr    aCreateorganiza// "CreateOrganizationLifecycle"
0x1050a  ldstr    aDA1SSrcCrmlive_21// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x1050f  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x10514  stloc.s  6
0x10516  ldloc.s  6
0x10518  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection::IsNullOrEmpty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection)
0x1051d  brtrue.s loc_1055F
0x1051f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x10524  stloc.s  8
0x10526  ldloc.s  8
0x10528  ldstr    aId// "Id"
0x1052d  ldloc.s  6
0x1052f  ldstr    aId// "Id"
0x10534  callvirt instance var<u1> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Item(void)
0x10539  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1053e  ldloc.2
0x1053f  ldstr    aOrganizationli// "OrganizationLifecycle"
0x10544  ldloc.s  4
0x10546  ldloc.s  8
0x10548  ldc.i4   0xAE
0x1054d  ldstr    aCreateorganiza// "CreateOrganizationLifecycle"
0x10552  ldstr    aDA1SSrcCrmlive_21// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x10557  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x1055c  pop
0x1055d  br.s     loc_105A8
0x1055f  ldloc.s  4
0x10561  ldstr    aId// "Id"
0x10566  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x1056b  box      [mscorlib]System.Guid
0x10570  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x10575  ldloc.s  4
0x10577  ldstr    aCreatedon// "CreatedOn"
0x1057c  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x10581  box      [mscorlib]System.DateTime
0x10586  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1058b  ldloc.2
0x1058c  ldstr    aOrganizationli// "OrganizationLifecycle"
0x10591  ldloc.s  4
0x10593  ldc.i4   0xB4
0x10598  ldstr    aCreateorganiza// "CreateOrganizationLifecycle"
0x1059d  ldstr    aDA1SSrcCrmlive_21// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x105a2  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x105a7  pop
0x105a8  ldloc.3
0x105a9  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ICrmTransaction::CommitTransaction()
0x105ae  leave.s  loc_105CE
0x105b0  pop
0x105b1  ldloc.3
0x105b2  ldc.i4.0
0x105b3  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ICrmTransaction::RollbackTransaction(bool)
0x105b8  rethrow
0x105ba  ldloc.3
0x105bb  brfalse.s loc_105C3
0x105bd  ldloc.3
0x105be  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x105c3  endfinally
0x105c4  ldloc.2
0x105c5  brfalse.s loc_105CD
0x105c7  ldloc.2
0x105c8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x105cd  endfinally
0x105ce  ldarg.2
0x105cf  stloc.1
0x105d0  leave.s  loc_105DC
0x105d2  ldloc.0
0x105d3  brfalse.s loc_105DB
0x105d5  ldloc.0
0x105d6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x105db  endfinally
0x105dc  ldloc.1
0x105dd  ret
```
