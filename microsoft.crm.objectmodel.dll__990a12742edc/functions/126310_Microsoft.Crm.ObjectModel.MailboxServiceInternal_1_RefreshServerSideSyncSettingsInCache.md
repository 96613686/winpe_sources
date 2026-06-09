# Microsoft.Crm.ObjectModel.MailboxServiceInternal`1::RefreshServerSideSyncSettingsInCache

- ea: `0x126310`
- end: `0x1265ab`
- name: `Microsoft.Crm.ObjectModel.MailboxServiceInternal`1::RefreshServerSideSyncSettingsInCache`
- size: `667`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x126310`

## string_xrefs

- `0x12631e`: `incomingemaildeliverymethod`
- `0x12638d`: `incomingemaildeliverymethod`
- `0x12639a`: `incomingemaildeliverymethod`
- `0x1263aa`: `incomingemaildeliverymethod`
- `0x1263bc`: `incomingemaildeliverymethod`
- `0x12648b`: `enabledforincomingemail`
- `0x126498`: `enabledforincomingemail`
- `0x1264a8`: `enabledforincomingemail`
- `0x1264ba`: `enabledforincomingemail`
- `0x126338`: `testemailconfigurationscheduled`
- `0x12640b`: `testemailconfigurationscheduled`
- `0x126418`: `testemailconfigurationscheduled`
- `0x126428`: `testemailconfigurationscheduled`
- `0x12643a`: `testemailconfigurationscheduled`
- `0x126558`: `Server Side Sync Settings change event`
- `0x126579`: `Server Side Sync Settings change event`
- `0x12659a`: `Server Side Sync Settings change event`

## pseudocode

```c

```

## disassembly

```asm
0x126310  ldarg.1
0x126311  ldstr    aActdeliverymet// "actdeliverymethod"
0x126316  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x12631b  brfalse.s loc_126347
0x12631d  ldarg.1
0x12631e  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0x126323  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x126328  brfalse.s loc_126347
0x12632a  ldarg.1
0x12632b  ldstr    aOutgoingemaild// "outgoingemaildeliverymethod"
0x126330  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x126335  brfalse.s loc_126347
0x126337  ldarg.1
0x126338  ldstr    aTestemailconfi// "testemailconfigurationscheduled"
0x12633d  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x126342  ldc.i4.0
0x126343  ceq
0x126345  br.s     loc_126348
0x126347  ldc.i4.1
0x126348  stloc.0
0x126349  ldloc.0
0x12634a  brtrue.s loc_12634D
0x12634c  ret
0x12634d  ldarg.1
0x12634e  ldstr    aActdeliverymet// "actdeliverymethod"
0x126353  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x126358  brfalse.s loc_12637C
0x12635a  ldarg.2
0x12635b  ldstr    aActdeliverymet// "actdeliverymethod"
0x126360  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x126365  brfalse.s loc_12636A
0x126367  ldc.i4.0
0x126368  br.s     loc_12638C
0x12636a  ldarg.2
0x12636b  ldstr    aActdeliverymet// "actdeliverymethod"
0x126370  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x126375  unbox.any [mscorlib]System.Int32
0x12637a  br.s     loc_12638C
0x12637c  ldarg.1
0x12637d  ldstr    aActdeliverymet// "actdeliverymethod"
0x126382  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x126387  unbox.any [mscorlib]System.Int32
0x12638c  ldarg.1
0x12638d  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0x126392  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x126397  brfalse.s loc_1263BB
0x126399  ldarg.2
0x12639a  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0x12639f  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x1263a4  brfalse.s loc_1263A9
0x1263a6  ldc.i4.0
0x1263a7  br.s     loc_1263CB
0x1263a9  ldarg.2
0x1263aa  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0x1263af  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1263b4  unbox.any [mscorlib]System.Int32
0x1263b9  br.s     loc_1263CB
0x1263bb  ldarg.1
0x1263bc  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0x1263c1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1263c6  unbox.any [mscorlib]System.Int32
0x1263cb  ldarg.1
0x1263cc  ldstr    aOutgoingemaild// "outgoingemaildeliverymethod"
0x1263d1  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x1263d6  brfalse.s loc_1263FA
0x1263d8  ldarg.2
0x1263d9  ldstr    aOutgoingemaild// "outgoingemaildeliverymethod"
0x1263de  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x1263e3  brfalse.s loc_1263E8
0x1263e5  ldc.i4.0
0x1263e6  br.s     loc_12640A
0x1263e8  ldarg.2
0x1263e9  ldstr    aOutgoingemaild// "outgoingemaildeliverymethod"
0x1263ee  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1263f3  unbox.any [mscorlib]System.Int32
0x1263f8  br.s     loc_12640A
0x1263fa  ldarg.1
0x1263fb  ldstr    aOutgoingemaild// "outgoingemaildeliverymethod"
0x126400  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x126405  unbox.any [mscorlib]System.Int32
0x12640a  ldarg.1
0x12640b  ldstr    aTestemailconfi// "testemailconfigurationscheduled"
0x126410  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x126415  brfalse.s loc_126439
0x126417  ldarg.2
0x126418  ldstr    aTestemailconfi// "testemailconfigurationscheduled"
0x12641d  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x126422  brfalse.s loc_126427
0x126424  ldc.i4.0
0x126425  br.s     loc_126449
0x126427  ldarg.2
0x126428  ldstr    aTestemailconfi// "testemailconfigurationscheduled"
0x12642d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x126432  unbox.any [mscorlib]System.Boolean
0x126437  br.s     loc_126449
0x126439  ldarg.1
0x12643a  ldstr    aTestemailconfi// "testemailconfigurationscheduled"
0x12643f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x126444  unbox.any [mscorlib]System.Boolean
0x126449  stloc.1
0x12644a  ldarg.1
0x12644b  ldstr    aEnabledforact// "enabledforact"
0x126450  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x126455  brfalse.s loc_126479
0x126457  ldarg.2
0x126458  ldstr    aEnabledforact// "enabledforact"
0x12645d  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x126462  brfalse.s loc_126467
0x126464  ldc.i4.1
0x126465  br.s     loc_126489
0x126467  ldarg.2
0x126468  ldstr    aEnabledforact// "enabledforact"
0x12646d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x126472  unbox.any [mscorlib]System.Boolean
0x126477  br.s     loc_126489
0x126479  ldarg.1
0x12647a  ldstr    aEnabledforact// "enabledforact"
0x12647f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x126484  unbox.any [mscorlib]System.Boolean
0x126489  stloc.2
0x12648a  ldarg.1
0x12648b  ldstr    aEnabledforinco// "enabledforincomingemail"
0x126490  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x126495  brfalse.s loc_1264B9
0x126497  ldarg.2
0x126498  ldstr    aEnabledforinco// "enabledforincomingemail"
0x12649d  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x1264a2  brfalse.s loc_1264A7
0x1264a4  ldc.i4.1
0x1264a5  br.s     loc_1264C9
0x1264a7  ldarg.2
0x1264a8  ldstr    aEnabledforinco// "enabledforincomingemail"
0x1264ad  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1264b2  unbox.any [mscorlib]System.Boolean
0x1264b7  br.s     loc_1264C9
0x1264b9  ldarg.1
0x1264ba  ldstr    aEnabledforinco// "enabledforincomingemail"
0x1264bf  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1264c4  unbox.any [mscorlib]System.Boolean
0x1264c9  stloc.3
0x1264ca  ldarg.1
0x1264cb  ldstr    aEnabledforoutg// "enabledforoutgoingemail"
0x1264d0  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x1264d5  brfalse.s loc_1264F9
0x1264d7  ldarg.2
0x1264d8  ldstr    aEnabledforoutg// "enabledforoutgoingemail"
0x1264dd  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x1264e2  brfalse.s loc_1264E7
0x1264e4  ldc.i4.1
0x1264e5  br.s     loc_126509
0x1264e7  ldarg.2
0x1264e8  ldstr    aEnabledforoutg// "enabledforoutgoingemail"
0x1264ed  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1264f2  unbox.any [mscorlib]System.Boolean
0x1264f7  br.s     loc_126509
0x1264f9  ldarg.1
0x1264fa  ldstr    aEnabledforoutg// "enabledforoutgoingemail"
0x1264ff  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x126504  unbox.any [mscorlib]System.Boolean
0x126509  stloc.s  4
0x12650b  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x126510  ldarg.3
0x126511  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x126516  ldarg.3
0x126517  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x12651c  stloc.s  5
0x12651e  ldc.i4.2
0x12651f  ceq
0x126521  stloc.s  6
0x126523  ldc.i4.2
0x126524  ceq
0x126526  stloc.s  7
0x126528  ldc.i4.1
0x126529  ceq
0x12652b  stloc.s  8
0x12652d  ldloc.s  5
0x12652f  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.EmailConnectionChannelType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_EmailConnectionChannel()
0x126534  brfalse.s loc_126544
0x126536  ldloc.s  5
0x126538  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.EmailConnectionChannelType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_EmailConnectionChannel()
0x12653d  ldc.i4.1
0x12653e  ceq
0x126540  ldloc.1
0x126541  and
0x126542  br.s     loc_126545
0x126544  ldc.i4.1
0x126545  stloc.s  9
0x126547  ldloc.0
0x126548  ldloc.s  9
0x12654a  and
0x12654b  ldloc.s  6
0x12654d  and
0x12654e  brfalse.s loc_126569
0x126550  ldloc.1
0x126551  ldloc.s  4
0x126553  or
0x126554  brfalse.s loc_126569
0x126556  ldc.i4.s 0x59
0x126558  ldstr    aServerSideSync_0// "Server Side Sync Settings change event"
0x12655d  ldarg.3
0x12655e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x126563  call     void [Microsoft.Crm.Core]Microsoft.Crm.NotificationManager::FireEvent(valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType, string, valuetype [mscorlib]System.Guid)
0x126568  ret
0x126569  ldloc.0
0x12656a  ldloc.s  9
0x12656c  and
0x12656d  ldloc.s  7
0x12656f  and
0x126570  brfalse.s loc_12658A
0x126572  ldloc.1
0x126573  ldloc.3
0x126574  or
0x126575  brfalse.s loc_12658A
0x126577  ldc.i4.s 0x59
0x126579  ldstr    aServerSideSync_0// "Server Side Sync Settings change event"
0x12657e  ldarg.3
0x12657f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x126584  call     void [Microsoft.Crm.Core]Microsoft.Crm.NotificationManager::FireEvent(valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType, string, valuetype [mscorlib]System.Guid)
0x126589  ret
0x12658a  ldloc.0
0x12658b  ldloc.s  9
0x12658d  and
0x12658e  ldloc.s  8
0x126590  and
0x126591  brfalse.s loc_1265AA
0x126593  ldloc.1
0x126594  ldloc.2
0x126595  or
0x126596  brfalse.s loc_1265AA
0x126598  ldc.i4.s 0x59
0x12659a  ldstr    aServerSideSync_0// "Server Side Sync Settings change event"
0x12659f  ldarg.3
0x1265a0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1265a5  call     void [Microsoft.Crm.Core]Microsoft.Crm.NotificationManager::FireEvent(valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType, string, valuetype [mscorlib]System.Guid)
0x1265aa  ret
```
