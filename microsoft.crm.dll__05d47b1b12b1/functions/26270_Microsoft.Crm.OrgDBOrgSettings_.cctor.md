# Microsoft.Crm.OrgDBOrgSettings::.cctor

- ea: `0x26270`
- end: `0x2715e`
- name: `Microsoft.Crm.OrgDBOrgSettings::.cctor`
- size: `3822`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x26220`
- `0x26240`
- `0x26250`
- `0x26270`

## string_xrefs

- `0x262cb`: `AutoCreateContactOnPromote`
- `0x2634a`: `LookupNameMatchesDuringImport`
- `0x264b6`: `RecordCountLimitToSwitchToCteSecuritySql`
- `0x26543`: `IdsCountForUsingGuidStringForSecurity`
- `0x26591`: `IdsCountBeforeUsingJoinsForSecurity`
- `0x266cb`: `UsePlainTextForEmailTemplateBody`
- `0x266dc`: `DisableIECompatMode`
- `0x267d3`: `EnableReLinkingToExistingCRMRecord`
- `0x268a9`: `DisableImplicitSharingOfCommunicationActivities`
- `0x269ec`: `SecuritySettingForEmail`
- `0x26a19`: `GrantSharedAccessForMergeToSubordinateOwner`
- `0x26acf`: `ListComponentInstalled`
- `0x26b56`: `CreateSPFoldersUsingNameandGuid`
- `0x26bb0`: `GrantFullAccessForMergeToMasterOwner`
- `0x26c37`: `MakeSocialPanePhoneCallCompleted`
- `0x26ceb`: `DisableClientUpdateNotification`
- `0x26d1c`: `MinRowCountForFKIndexCreateInReferencingEntity`
- `0x26d4a`: `MinRowCountForFKIndexCreateInReferencedEntity`
- `0x26fe9`: `FullTextSpecialCharactersToRemoveFromSearchToken`
- `0x27016`: `UseDeletePrivilegeInsteadOfAppendToForChildEntityDelete`
- `0x27070`: `SecurityQueryHint`
- `0x270ca`: `UseOrganizationServiceForMultiEntityQuickFind`
- `0x27124`: `officeShellServiceTimeout`
- `0x27151`: `DistinctPhysicalAndLogicalDeletesForExchangeSync`

## pseudocode

```c

```

## disassembly

```asm
0x26270  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.OrgSettingData> Microsoft.Crm.OrgDBOrgSettings::settings
0x26275  brtrue   loc_2715D
0x2627a  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.OrgSettingData>::.ctor()
0x2627f  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.OrgSettingData> Microsoft.Crm.OrgDBOrgSettings::settings
0x26284  newobj   instance void Microsoft.Crm.OrgSettingData::.ctor()
0x26289  stloc.0
0x2628a  ldloc.0
0x2628b  ldc.i4.1
0x2628c  callvirt instance void Microsoft.Crm.OrgSettingData::set_SettingType(valuetype Microsoft.Crm.OrgDBOrgSettingType value)
0x26291  ldloc.0
0x26292  ldc.i4.0
0x26293  box      [mscorlib]System.Boolean
0x26298  callvirt instance void Microsoft.Crm.OrgSettingData::set_DefaultValue(object value)
0x2629d  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.OrgSettingData> Microsoft.Crm.OrgDBOrgSettings::settings
0x262a2  ldstr    aDisablesmartma// "DisableSmartMatching"
0x262a7  ldloc.0
0x262a8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.OrgSettingData>::Add(var<u1>, !!T0)
0x262ad  newobj   instance void Microsoft.Crm.OrgSettingData::.ctor()
0x262b2  stloc.1
0x262b3  ldloc.1
0x262b4  ldc.i4.1
0x262b5  callvirt instance void Microsoft.Crm.OrgSettingData::set_SettingType(valuetype Microsoft.Crm.OrgDBOrgSettingType value)
0x262ba  ldloc.1
0x262bb  ldc.i4.1
0x262bc  box      [mscorlib]System.Boolean
0x262c1  callvirt instance void Microsoft.Crm.OrgSettingData::set_DefaultValue(object value)
0x262c6  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.OrgSettingData> Microsoft.Crm.OrgDBOrgSettings::settings
0x262cb  ldstr    aAutocreatecont// "AutoCreateContactOnPromote"
0x262d0  ldloc.1
0x262d1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.OrgSettingData>::Add(var<u1>, !!T0)
0x262d6  newobj   instance void Microsoft.Crm.OrgSettingData::.ctor()
0x262db  stloc.2
0x262dc  ldloc.2
0x262dd  ldc.i4.0
0x262de  callvirt instance void Microsoft.Crm.OrgSettingData::set_SettingType(valuetype Microsoft.Crm.OrgDBOrgSettingType value)
0x262e3  ldloc.2
0x262e4  ldc.i4.s 0xA
0x262e6  box      [mscorlib]System.Int32
0x262eb  callvirt instance void Microsoft.Crm.OrgSettingData::set_DefaultValue(object value)
0x262f0  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.OrgSettingData> Microsoft.Crm.OrgDBOrgSettings::settings
0x262f5  ldstr    aBackgroundsend// "BackgroundSendBatchSize"
0x262fa  ldloc.2
0x262fb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.OrgSettingData>::Add(var<u1>, !!T0)
0x26300  newobj   instance void Microsoft.Crm.OrgSettingData::.ctor()
0x26305  stloc.3
0x26306  ldloc.3
0x26307  ldc.i4.1
0x26308  callvirt instance void Microsoft.Crm.OrgSettingData::set_SettingType(valuetype Microsoft.Crm.OrgDBOrgSettingType value)
0x2630d  ldloc.3
0x2630e  ldc.i4.0
0x2630f  box      [mscorlib]System.Boolean
0x26314  callvirt instance void Microsoft.Crm.OrgSettingData::set_DefaultValue(object value)
0x26319  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.OrgSettingData> Microsoft.Crm.OrgDBOrgSettings::settings
0x2631e  ldstr    aDisableinactiv// "DisableInactiveRecordFilterForMailMerge"
0x26323  ldloc.3
0x26324  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.OrgSettingData>::Add(var<u1>, !!T0)
0x26329  newobj   instance void Microsoft.Crm.OrgSettingData::.ctor()
0x2632e  stloc.s  4
0x26330  ldloc.s  4
0x26332  ldc.i4.1
0x26333  callvirt instance void Microsoft.Crm.OrgSettingData::set_SettingType(valuetype Microsoft.Crm.OrgDBOrgSettingType value)
0x26338  ldloc.s  4
0x2633a  ldc.i4.0
0x2633b  box      [mscorlib]System.Boolean
0x26340  callvirt instance void Microsoft.Crm.OrgSettingData::set_DefaultValue(object value)
0x26345  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.OrgSettingData> Microsoft.Crm.OrgDBOrgSettings::settings
0x2634a  ldstr    aLookupnamematc// "LookupNameMatchesDuringImport"
0x2634f  ldloc.s  4
0x26351  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.OrgSettingData>::Add(var<u1>, !!T0)
0x26356  newobj   instance void Microsoft.Crm.OrgSettingData::.ctor()
0x2635b  stloc.s  5
0x2635d  ldloc.s  5
0x2635f  ldc.i4.1
0x26360  callvirt instance void Microsoft.Crm.OrgSettingData::set_SettingType(valuetype Microsoft.Crm.OrgDBOrgSettingType value)
0x26365  ldloc.s  5
0x26367  ldc.i4.0
0x26368  box      [mscorlib]System.Boolean
0x2636d  callvirt instance void Microsoft.Crm.OrgSettingData::set_DefaultValue(object value)
0x26372  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.OrgSettingData> Microsoft.Crm.OrgDBOrgSettings::settings
0x26377  ldstr    aTraceexchanges// "TraceExchangeSyncData"
0x2637c  ldloc.s  5
0x2637e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.OrgSettingData>::Add(var<u1>, !!T0)
0x26383  newobj   instance void Microsoft.Crm.OrgSettingData::.ctor()
0x26388  stloc.s  6
0x2638a  ldloc.s  6
0x2638c  ldc.i4.0
0x2638d  callvirt instance void Microsoft.Crm.OrgSettingData::set_SettingType(valuetype Microsoft.Crm.OrgDBOrgSettingType value)
0x26392  ldloc.s  6
0x26394  ldc.i4.1
0x26395  box      [mscorlib]System.Int32
0x2639a  callvirt instance void Microsoft.Crm.OrgSettingData::set_DefaultValue(object value)
0x2639f  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.OrgSettingData> Microsoft.Crm.OrgDBOrgSettings::settings
0x263a4  ldstr    aEnableretrieve// "EnableRetrieveMultipleOptimization"
0x263a9  ldloc.s  6
0x263ab  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.OrgSettingData>::Add(var<u1>, !!T0)
0x263b0  newobj   instance void Microsoft.Crm.OrgSettingData::.ctor()
0x263b5  stloc.s  7
0x263b7  ldloc.s  7
0x263b9  ldc.i4.1
0x263ba  callvirt instance void Microsoft.Crm.OrgSettingData::set_SettingType(valuetype Microsoft.Crm.OrgDBOrgSettingType value)
0x263bf  ldloc.s  7
0x263c1  ldc.i4.1
0x263c2  box      [mscorlib]System.Boolean
0x263c7  callvirt instance void Microsoft.Crm.OrgSettingData::set_DefaultValue(object value)
0x263cc  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.OrgSettingData> Microsoft.Crm.OrgDBOrgSettings::settings
0x263d1  ldstr    aDonotignoreint// "DoNotIgnoreInternalEmailToQueues"
0x263d6  ldloc.s  7
0x263d8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.OrgSettingData>::Add(var<u1>, !!T0)
0x263dd  newobj   instance void Microsoft.Crm.OrgSettingData::.ctor()
0x263e2  stloc.s  8
0x263e4  ldloc.s  8
0x263e6  ldc.i4.1
0x263e7  callvirt instance void Microsoft.Crm.OrgSettingData::set_SettingType(valuetype Microsoft.Crm.OrgDBOrgSettingType value)
0x263ec  ldloc.s  8
0x263ee  ldc.i4.0
0x263ef  box      [mscorlib]System.Boolean
0x263f4  callvirt instance void Microsoft.Crm.OrgSettingData::set_DefaultValue(object value)
0x263f9  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.OrgSettingData> Microsoft.Crm.OrgDBOrgSettings::settings
0x263fe  ldstr    aSkipgettingrec// "SkipGettingRecordCountForPaging"
0x26403  ldloc.s  8
0x26405  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.OrgSettingData>::Add(var<u1>, !!T0)
0x2640a  newobj   instance void Microsoft.Crm.OrgSettingData::.ctor()
0x2640f  stloc.s  9
0x26411  ldloc.s  9
0x26413  ldc.i4.0
0x26414  callvirt instance void Microsoft.Crm.OrgSettingData::set_SettingType(valuetype Microsoft.Crm.OrgDBOrgSettingType value)
0x26419  ldloc.s  9
0x2641b  ldc.i4.0
0x2641c  box      [mscorlib]System.Int32
0x26421  callvirt instance void Microsoft.Crm.OrgSettingData::set_DefaultValue(object value)
0x26426  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.OrgSettingData> Microsoft.Crm.OrgDBOrgSettings::settings
0x2642b  ldstr    aVerboseerrorso// "VerboseErrorsOnPromoteToCRM"
0x26430  ldloc.s  9
0x26432  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.OrgSettingData>::Add(var<u1>, !!T0)
0x26437  newobj   instance void Microsoft.Crm.OrgSettingData::.ctor()
0x2643c  stloc.s  0xA
0x2643e  ldloc.s  0xA
0x26440  ldc.i4.1
0x26441  callvirt instance void Microsoft.Crm.OrgSettingData::set_SettingType(valuetype Microsoft.Crm.OrgDBOrgSettingType value)
0x26446  ldloc.s  0xA
0x26448  ldc.i4.0
0x26449  box      [mscorlib]System.Boolean
0x2644e  callvirt instance void Microsoft.Crm.OrgSettingData::set_DefaultValue(object value)
0x26453  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.OrgSettingData> Microsoft.Crm.OrgDBOrgSettings::settings
0x26458  ldstr    aSkipsuffixonkb// "SkipSuffixOnKBArticles"
0x2645d  ldloc.s  0xA
0x2645f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.OrgSettingData>::Add(var<u1>, !!T0)
0x26464  newobj   instance void Microsoft.Crm.OrgSettingData::.ctor()
0x26469  stloc.s  0xB
0x2646b  ldloc.s  0xB
0x2646d  ldc.i4.0
0x2646e  callvirt instance void Microsoft.Crm.OrgSettingData::set_SettingType(valuetype Microsoft.Crm.OrgDBOrgSettingType value)
0x26473  ldloc.s  0xB
0x26475  ldc.i4.1
0x26476  box      [mscorlib]System.Int32
0x2647b  callvirt instance void Microsoft.Crm.OrgSettingData::set_DefaultValue(object value)
0x26480  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.OrgSettingData> Microsoft.Crm.OrgDBOrgSettings::settings
0x26485  ldstr    aEnablequickfin// "EnableQuickFindOptimization"
0x2648a  ldloc.s  0xB
0x2648c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.OrgSettingData>::Add(var<u1>, !!T0)
0x26491  newobj   instance void Microsoft.Crm.OrgSettingData::.ctor()
0x26496  stloc.s  0xC
0x26498  ldloc.s  0xC
0x2649a  ldc.i4.0
0x2649b  callvirt instance void Microsoft.Crm.OrgSettingData::set_SettingType(valuetype Microsoft.Crm.OrgDBOrgSettingType value)
0x264a0  ldloc.s  0xC
0x264a2  ldc.i4   0x124F8
0x264a7  box      [mscorlib]System.Int32
0x264ac  callvirt instance void Microsoft.Crm.OrgSettingData::set_DefaultValue(object value)
0x264b1  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.OrgSettingData> Microsoft.Crm.OrgDBOrgSettings::settings
0x264b6  ldstr    aRecordcountlim// "RecordCountLimitToSwitchToCteSecuritySq"...
0x264bb  ldloc.s  0xC
0x264bd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.OrgSettingData>::Add(var<u1>, !!T0)
0x264c2  newobj   instance void Microsoft.Crm.OrgSettingData::.ctor()
0x264c7  stloc.s  0xD
0x264c9  ldloc.s  0xD
0x264cb  ldc.i4.0
0x264cc  callvirt instance void Microsoft.Crm.OrgSettingData::set_SettingType(valuetype Microsoft.Crm.OrgDBOrgSettingType value)
0x264d1  ldloc.s  0xD
0x264d3  ldc.i4.s 0x50
0x264d5  box      [mscorlib]System.Int32
0x264da  callvirt instance void Microsoft.Crm.OrgSettingData::set_DefaultValue(object value)
0x264df  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.OrgSettingData> Microsoft.Crm.OrgDBOrgSettings::settings
0x264e4  ldstr    aMaximumchildus// "MaximumChildUsersCountLimitBeforeUsingJ"...
0x264e9  ldloc.s  0xD
0x264eb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.OrgSettingData>::Add(var<u1>, !!T0)
0x264f0  newobj   instance void Microsoft.Crm.OrgSettingData::.ctor()
0x264f5  stloc.s  0xE
0x264f7  ldloc.s  0xE
0x264f9  ldc.i4.0
0x264fa  callvirt instance void Microsoft.Crm.OrgSettingData::set_SettingType(valuetype Microsoft.Crm.OrgDBOrgSettingType value)
0x264ff  ldloc.s  0xE
0x26501  ldc.i4   0x3E8
0x26506  box      [mscorlib]System.Int32
0x2650b  callvirt instance void Microsoft.Crm.OrgSettingData::set_DefaultValue(object value)
0x26510  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.OrgSettingData> Microsoft.Crm.OrgDBOrgSettings::settings
0x26515  ldstr    aRetrievemultip// "RetrieveMultipleSharingCountThreshold"
0x2651a  ldloc.s  0xE
0x2651c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.OrgSettingData>::Add(var<u1>, !!T0)
0x26521  newobj   instance void Microsoft.Crm.OrgSettingData::.ctor()
0x26526  stloc.s  0xF
0x26528  ldloc.s  0xF
0x2652a  ldc.i4.0
0x2652b  callvirt instance void Microsoft.Crm.OrgSettingData::set_SettingType(valuetype Microsoft.Crm.OrgDBOrgSettingType value)
0x26530  ldloc.s  0xF
0x26532  ldc.i4.s 0x1E
0x26534  box      [mscorlib]System.Int32
0x26539  callvirt instance void Microsoft.Crm.OrgSettingData::set_DefaultValue(object value)
0x2653e  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.OrgSettingData> Microsoft.Crm.OrgDBOrgSettings::settings
0x26543  ldstr    aIdscountforusi// "IdsCountForUsingGuidStringForSecurity"
0x26548  ldloc.s  0xF
0x2654a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.OrgSettingData>::Add(var<u1>, !!T0)
0x2654f  newobj   instance void Microsoft.Crm.OrgSettingData::.ctor()
0x26554  stloc.s  0x10
0x26556  ldloc.s  0x10
0x26558  ldc.i4.0
0x26559  callvirt instance void Microsoft.Crm.OrgSettingData::set_SettingType(valuetype Microsoft.Crm.OrgDBOrgSettingType value)
0x2655e  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x26563  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::GetSku()
0x26568  ldc.i4.2
0x26569  bne.un.s loc_2657B
0x2656b  ldloc.s  0x10
0x2656d  ldc.i4.s 0x1F
0x2656f  box      [mscorlib]System.Int32
0x26574  callvirt instance void Microsoft.Crm.OrgSettingData::set_DefaultValue(object value)
0x26579  br.s     loc_2658C
0x2657b  ldloc.s  0x10
0x2657d  ldc.i4   0x3E8
0x26582  box      [mscorlib]System.Int32
0x26587  callvirt instance void Microsoft.Crm.OrgSettingData::set_DefaultValue(object value)
0x2658c  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.OrgSettingData> Microsoft.Crm.OrgDBOrgSettings::settings
0x26591  ldstr    aIdscountbefore// "IdsCountBeforeUsingJoinsForSecurity"
0x26596  ldloc.s  0x10
0x26598  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.OrgSettingData>::Add(var<u1>, !!T0)
0x2659d  newobj   instance void Microsoft.Crm.OrgSettingData::.ctor()
0x265a2  stloc.s  0x11
0x265a4  ldloc.s  0x11
0x265a6  ldc.i4.0
0x265a7  callvirt instance void Microsoft.Crm.OrgSettingData::set_SettingType(valuetype Microsoft.Crm.OrgDBOrgSettingType value)
0x265ac  ldloc.s  0x11
0x265ae  ldc.i4.s 0xA
0x265b0  box      [mscorlib]System.Int32
0x265b5  callvirt instance void Microsoft.Crm.OrgSettingData::set_DefaultValue(object value)
0x265ba  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.OrgSettingData> Microsoft.Crm.OrgDBOrgSettings::settings
0x265bf  ldstr    aSharinglimitfo// "SharingLimitForPOASnapshotTable"
0x265c4  ldloc.s  0x11
0x265c6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.OrgSettingData>::Add(var<u1>, !!T0)
0x265cb  newobj   instance void Microsoft.Crm.OrgSettingData::.ctor()
0x265d0  stloc.s  0x12
0x265d2  ldloc.s  0x12
0x265d4  ldc.i4.2
0x265d5  callvirt instance void Microsoft.Crm.OrgSettingData::set_SettingType(valuetype Microsoft.Crm.OrgDBOrgSettingType value)
0x265da  ldloc.s  0x12
0x265dc  ldsfld   string [mscorlib]System.String::Empty
0x265e1  callvirt instance void Microsoft.Crm.OrgSettingData::set_DefaultValue(object value)
0x265e6  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.OrgSettingData> Microsoft.Crm.OrgDBOrgSettings::settings
0x265eb  ldstr    aJumpbaralphabe// "JumpBarAlphabetOverride"
0x265f0  ldloc.s  0x12
0x265f2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.OrgSettingData>::Add(var<u1>, !!T0)
0x265f7  newobj   instance void Microsoft.Crm.OrgSettingData::.ctor()
0x265fc  stloc.s  0x13
0x265fe  ldloc.s  0x13
0x26600  ldc.i4.2
0x26601  callvirt instance void Microsoft.Crm.OrgSettingData::set_SettingType(valuetype Microsoft.Crm.OrgDBOrgSettingType value)
0x26606  ldloc.s  0x13
0x26608  ldsfld   string [mscorlib]System.String::Empty
0x2660d  callvirt instance void Microsoft.Crm.OrgSettingData::set_DefaultValue(object value)
0x26612  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.OrgSettingData> Microsoft.Crm.OrgDBOrgSettings::settings
0x26617  ldstr    aJumpbarnumberi// "JumpBarNumberIndicatorOverride"
0x2661c  ldloc.s  0x13
0x2661e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.OrgSettingData>::Add(var<u1>, !!T0)
0x26623  newobj   instance void Microsoft.Crm.OrgSettingData::.ctor()
0x26628  stloc.s  0x14
0x2662a  ldloc.s  0x14
0x2662c  ldc.i4.1
0x2662d  callvirt instance void Microsoft.Crm.OrgSettingData::set_SettingType(valuetype Microsoft.Crm.OrgDBOrgSettingType value)
0x26632  ldloc.s  0x14
0x26634  ldc.i4.0
0x26635  box      [mscorlib]System.Boolean
0x2663a  callvirt instance void Microsoft.Crm.OrgSettingData::set_DefaultValue(object value)
0x2663f  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.OrgSettingData> Microsoft.Crm.OrgDBOrgSettings::settings
0x26644  ldstr    aClientueipdisa// "ClientUEIPDisabled"
0x26649  ldloc.s  0x14
0x2664b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.OrgSettingData>::Add(var<u1>, !!T0)
0x26650  newobj   instance void Microsoft.Crm.OrgSettingData::.ctor()
0x26655  stloc.s  0x15
0x26657  ldloc.s  0x15
0x26659  ldc.i4.1
0x2665a  callvirt instance void Microsoft.Crm.OrgSettingData::set_SettingType(valuetype Microsoft.Crm.OrgDBOrgSettingType value)
0x2665f  ldloc.s  0x15
0x26661  ldc.i4.0
0x26662  box      [mscorlib]System.Boolean
0x26667  callvirt instance void Microsoft.Crm.OrgSettingData::set_DefaultValue(object value)
0x2666c  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.OrgSettingData> Microsoft.Crm.OrgDBOrgSettings::settings
0x26671  ldstr    aOverridev5send// "OverrideV5SenderConflictResolution"
0x26676  ldloc.s  0x15
0x26678  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.OrgSettingData>::Add(var<u1>, !!T0)
0x2667d  newobj   instance void Microsoft.Crm.OrgSettingData::.ctor()
0x26682  stloc.s  0x16
0x26684  ldloc.s  0x16
  ... truncated ...
```
