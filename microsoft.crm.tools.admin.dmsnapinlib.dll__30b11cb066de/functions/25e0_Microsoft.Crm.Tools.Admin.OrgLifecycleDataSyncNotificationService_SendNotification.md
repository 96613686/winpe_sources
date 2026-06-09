# Microsoft.Crm.Tools.Admin.OrgLifecycleDataSyncNotificationService::SendNotification

- ea: `0x25e0`
- end: `0x27ae`
- name: `Microsoft.Crm.Tools.Admin.OrgLifecycleDataSyncNotificationService::SendNotification`
- size: `462`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x167b0`
- `0x17070`

## callees

- `0x24e0`
- `0x2500`
- `0x2520`
- `0x2540`
- `0x2560`
- `0x2580`
- `0x25e0`
- `0x27b0`
- `0x84e0`
- `0x8670`
- `0x86e0`
- `0x8a30`
- `0x91d0`
- `0x9320`

## string_xrefs

- `0x2657`: `InstallDbVersion`

## pseudocode

```c

```

## disassembly

```asm
0x25e0  ldarg.1
0x25e1  brfalse.s loc_2602
0x25e3  ldarg.1
0x25e4  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrgLifecycleDataSyncNotification::get_OrganizationId()
0x25e9  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x25ee  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x25f3  brtrue.s loc_2602
0x25f5  ldarg.1
0x25f6  ldfld    string Microsoft.Crm.Tools.Admin.OrgLifecycleDataSyncNotification::Name
0x25fb  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x2600  brfalse.s loc_2603
0x2602  ret
0x2603  nop
0x2604  newobj   instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::.ctor()
0x2609  stloc.0
0x260a  ldloc.0
0x260b  ldarg.1
0x260c  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrgLifecycleDataSyncNotification::get_OrganizationId()
0x2611  ldc.i4.0
0x2612  call     void Microsoft.Crm.Tools.Admin.OrganizationInfo::RetrieveOrganizationParameters(class Microsoft.Crm.Tools.Admin.OrganizationInfo organizationInfo, valuetype [mscorlib]System.Guid organizationId, bool throwIfOrgDatabasePropertiesAreUnavailable)
0x2617  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x261c  dup
0x261d  ldstr    aBeforedbversio// "BeforeDbVersion"
0x2622  ldarg.1
0x2623  callvirt instance class [mscorlib]System.Version Microsoft.Crm.Tools.Admin.OrgLifecycleDataSyncNotification::get_BeforeDbVersion()
0x2628  dup
0x2629  brtrue.s loc_262F
0x262b  pop
0x262c  ldnull
0x262d  br.s     loc_2634
0x262f  callvirt instance string [mscorlib]System.Object::ToString()
0x2634  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2639  dup
0x263a  ldstr    aAfterdbversion// "AfterDbVersion"
0x263f  ldarg.1
0x2640  callvirt instance class [mscorlib]System.Version Microsoft.Crm.Tools.Admin.OrgLifecycleDataSyncNotification::get_AfterDbVersion()
0x2645  dup
0x2646  brtrue.s loc_264C
0x2648  pop
0x2649  ldnull
0x264a  br.s     loc_2651
0x264c  callvirt instance string [mscorlib]System.Object::ToString()
0x2651  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2656  dup
0x2657  ldstr    aInstalldbversi// "InstallDbVersion"
0x265c  ldarg.1
0x265d  callvirt instance class [mscorlib]System.Version Microsoft.Crm.Tools.Admin.OrgLifecycleDataSyncNotification::get_InstallDbVersion()
0x2662  dup
0x2663  brtrue.s loc_2669
0x2665  pop
0x2666  ldnull
0x2667  br.s     loc_266E
0x2669  callvirt instance string [mscorlib]System.Object::ToString()
0x266e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2673  dup
0x2674  ldstr    aOrganizationid// "OrganizationId"
0x2679  ldarg.1
0x267a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrgLifecycleDataSyncNotification::get_OrganizationId()
0x267f  box      [mscorlib]System.Guid
0x2684  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2689  dup
0x268a  ldstr    aTimetakeninsec// "TimeTakenInSeconds"
0x268f  ldarg.1
0x2690  callvirt instance int64 Microsoft.Crm.Tools.Admin.OrgLifecycleDataSyncNotification::get_TimeTakenInSeconds()
0x2695  box      [mscorlib]System.Int64
0x269a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x269f  dup
0x26a0  ldstr    aHasfailed// "HasFailed"
0x26a5  ldarg.1
0x26a6  callvirt instance bool Microsoft.Crm.Tools.Admin.OrgLifecycleDataSyncNotification::get_HasFailed()
0x26ab  box      [mscorlib]System.Boolean
0x26b0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x26b5  stloc.1
0x26b6  ldloc.0
0x26b7  brfalse.s loc_2717
0x26b9  ldloc.1
0x26ba  ldstr    aOrganizationun// "OrganizationUniqueName"
0x26bf  ldloc.0
0x26c0  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationUniqueName()
0x26c5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x26ca  ldloc.1
0x26cb  ldstr    aOrganizationfr// "OrganizationFriendlyName"
0x26d0  ldloc.0
0x26d1  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationFriendlyName()
0x26d6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x26db  ldloc.1
0x26dc  ldstr    aOrganizationty// "OrganizationType"
0x26e1  ldloc.0
0x26e2  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationType()
0x26e7  stloc.3
0x26e8  ldloca.s 3
0x26ea  constrained. [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType
0x26f0  callvirt instance string [mscorlib]System.Object::ToString()
0x26f5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x26fa  ldloc.1
0x26fb  ldstr    aExistingdataba// "ExistingDatabaseVersion"
0x2700  ldloc.0
0x2701  callvirt instance class [mscorlib]System.Version Microsoft.Crm.Tools.Admin.OrganizationInfo::get_ExistingDatabaseVersion()
0x2706  dup
0x2707  brtrue.s loc_270D
0x2709  pop
0x270a  ldnull
0x270b  br.s     loc_2712
0x270d  callvirt instance string [mscorlib]System.Object::ToString()
0x2712  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2717  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x271c  dup
0x271d  ldstr    aOrganizationid// "OrganizationId"
0x2722  ldarg.1
0x2723  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrgLifecycleDataSyncNotification::get_OrganizationId()
0x2728  box      [mscorlib]System.Guid
0x272d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2732  dup
0x2733  ldstr    aMessagename// "MessageName"
0x2738  ldstr    aLifecyclechang// "LifecycleChange"
0x273d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2742  dup
0x2743  ldstr    aMessageid// "MessageId"
0x2748  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x274d  stloc.s  4
0x274f  ldloca.s 4
0x2751  constrained. [mscorlib]System.Guid
0x2757  callvirt instance string [mscorlib]System.Object::ToString()
0x275c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2761  dup
0x2762  ldstr    aLifecyclechang// "LifecycleChange"
0x2767  ldarg.1
0x2768  ldfld    string Microsoft.Crm.Tools.Admin.OrgLifecycleDataSyncNotification::Name
0x276d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2772  dup
0x2773  ldstr    aLifecycleevent// "LifecycleEventProperties"
0x2778  ldloc.1
0x2779  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x277e  stloc.2
0x277f  ldarg.1
0x2780  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrgLifecycleDataSyncNotification::get_OrganizationId()
0x2785  call     bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.DataSyncNotificationHelper::IsOrgSubscribedToEventHub(valuetype [mscorlib]System.Guid)
0x278a  brfalse.s loc_279E
0x278c  ldloc.2
0x278d  ldarg.1
0x278e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrgLifecycleDataSyncNotification::get_OrganizationId()
0x2793  ldstr    aLifecycle// "lifecycle"
0x2798  ldnull
0x2799  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.DataSyncNotificationHelper::SendEventHubMessage(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x279e  leave.s  loc_27AD
0x27a0  stloc.s  5
0x27a2  ldarg.0
0x27a3  ldarg.1
0x27a4  ldloc.s  5
0x27a6  call     instance void Microsoft.Crm.Tools.Admin.OrgLifecycleDataSyncNotificationService::LogErrorEvent(class Microsoft.Crm.Tools.Admin.OrgLifecycleDataSyncNotification notification, class [mscorlib]System.Exception e)
0x27ab  leave.s  loc_27AD
0x27ad  ret
```
