# Microsoft.Crm.RegControl::.cctor

- ea: `0x34520`
- end: `0x346ac`
- name: `Microsoft.Crm.RegControl::.cctor`
- size: `396`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## string_xrefs

- `0x3462c`: `CrmMergeBaseAndExtensionTableTool.exe`
- `0x34634`: `CrmMergeBaseAndExtensionTableTool.vshost.exe`
- `0x3464c`: `MetadataXmlValidatorForURs.exe`
- `0x34655`: `MetadataXmlValidatorForURs.vshost.exe`
- `0x3453e`: `CRM_Server_InstallDir`
- `0x34548`: `CRM_SrsDataConnector_InstallDir`
- `0x34552`: `InstallPath`
- `0x34582`: `Bin\CRMErrors.dll`
- `0x345d0`: `Bin\CRMErrors.dll`
- `0x3458a`: `Bin\CRMCore.dll`
- `0x345b5`: `Bin\CRMCore.dll`
- `0x345d8`: `Bin\CRMCore.dll`
- `0x34592`: `Bin\CRMWatson.dll`
- `0x345bd`: `Bin\CRMWatson.dll`
- `0x345e8`: `Bin\CRMWatson.dll`
- `0x3459a`: `Bin\sqmapi.dll`
- `0x345f0`: `Bin\sqmapi.dll`
- `0x345a2`: `Bin\osafehtm.dll`
- `0x345f8`: `Bin\osafehtm.dll`
- `0x345e0`: `Bin\CrmOfflineSync.dll`
- `0x3463c`: `MetadataXmlValidator.EXE`
- `0x34644`: `metadataxmlvalidator.vshost.exe`

## pseudocode

```c

```

## disassembly

```asm
0x34520  ldstr    aSoftwareMicros_2// "SOFTWARE\\Microsoft\\MSCRM"
0x34525  stsfld   string Microsoft.Crm.RegControl::serverKey
0x3452a  ldstr    aSoftwareMicros_3// "SOFTWARE\\Microsoft\\MSCRMClient"
0x3452f  stsfld   string Microsoft.Crm.RegControl::clientKey
0x34534  ldstr    aSoftwareMicros_4// "SOFTWARE\\Microsoft\\MSCRMClient\\MSCRM"...
0x34539  stsfld   string Microsoft.Crm.RegControl::clientLMKey
0x3453e  ldstr    aCrmServerInsta// "CRM_Server_InstallDir"
0x34543  stsfld   string Microsoft.Crm.RegControl::serverKeyDir
0x34548  ldstr    aCrmSrsdataconn// "CRM_SrsDataConnector_InstallDir"
0x3454d  stsfld   string Microsoft.Crm.RegControl::reportDataExtensionKeyDir
0x34552  ldstr    aInstallpath// "InstallPath"
0x34557  stsfld   string Microsoft.Crm.RegControl::clientKeyDir
0x3455c  ldstr    aRcoffline// "RCOffline"
0x34561  stsfld   string Microsoft.Crm.RegControl::clientKeyOffline
0x34566  ldstr    aSmoffline// "SMOffline"
0x3456b  stsfld   string Microsoft.Crm.RegControl::clientKeyGoingOffline
0x34570  ldstr    aServer// "Server"
0x34575  stsfld   string Microsoft.Crm.RegControl::serverSubFolder
0x3457a  ldc.i4.5
0x3457b  newarr   [mscorlib]System.String
0x34580  dup
0x34581  ldc.i4.0
0x34582  ldstr    aBinCrmerrorsDl// "Bin\\CRMErrors.dll"
0x34587  stelem.ref
0x34588  dup
0x34589  ldc.i4.1
0x3458a  ldstr    aBinCrmcoreDll// "Bin\\CRMCore.dll"
0x3458f  stelem.ref
0x34590  dup
0x34591  ldc.i4.2
0x34592  ldstr    aBinCrmwatsonDl// "Bin\\CRMWatson.dll"
0x34597  stelem.ref
0x34598  dup
0x34599  ldc.i4.3
0x3459a  ldstr    aBinSqmapiDll// "Bin\\sqmapi.dll"
0x3459f  stelem.ref
0x345a0  dup
0x345a1  ldc.i4.4
0x345a2  ldstr    aBinOsafehtmDll// "Bin\\osafehtm.dll"
0x345a7  stelem.ref
0x345a8  stsfld   string[] Microsoft.Crm.RegControl::fatClientBinaries
0x345ad  ldc.i4.2
0x345ae  newarr   [mscorlib]System.String
0x345b3  dup
0x345b4  ldc.i4.0
0x345b5  ldstr    aBinCrmcoreDll// "Bin\\CRMCore.dll"
0x345ba  stelem.ref
0x345bb  dup
0x345bc  ldc.i4.1
0x345bd  ldstr    aBinCrmwatsonDl// "Bin\\CRMWatson.dll"
0x345c2  stelem.ref
0x345c3  stsfld   string[] Microsoft.Crm.RegControl::lightClientBinaries
0x345c8  ldc.i4.6
0x345c9  newarr   [mscorlib]System.String
0x345ce  dup
0x345cf  ldc.i4.0
0x345d0  ldstr    aBinCrmerrorsDl// "Bin\\CRMErrors.dll"
0x345d5  stelem.ref
0x345d6  dup
0x345d7  ldc.i4.1
0x345d8  ldstr    aBinCrmcoreDll// "Bin\\CRMCore.dll"
0x345dd  stelem.ref
0x345de  dup
0x345df  ldc.i4.2
0x345e0  ldstr    aBinCrmofflines// "Bin\\CrmOfflineSync.dll"
0x345e5  stelem.ref
0x345e6  dup
0x345e7  ldc.i4.3
0x345e8  ldstr    aBinCrmwatsonDl// "Bin\\CRMWatson.dll"
0x345ed  stelem.ref
0x345ee  dup
0x345ef  ldc.i4.4
0x345f0  ldstr    aBinSqmapiDll// "Bin\\sqmapi.dll"
0x345f5  stelem.ref
0x345f6  dup
0x345f7  ldc.i4.5
0x345f8  ldstr    aBinOsafehtmDll// "Bin\\osafehtm.dll"
0x345fd  stelem.ref
0x345fe  stsfld   string[] Microsoft.Crm.RegControl::serverBinaries
0x34603  ldc.i4.s 0xA
0x34605  newarr   [mscorlib]System.String
0x3460a  dup
0x3460b  ldc.i4.0
0x3460c  ldstr    aCrmdbtoolExe// "CrmDbTool.EXE"
0x34611  stelem.ref
0x34612  dup
0x34613  ldc.i4.1
0x34614  ldstr    aCrmdbtoolVshos// "crmdbtool.vshost.exe"
0x34619  stelem.ref
0x3461a  dup
0x3461b  ldc.i4.2
0x3461c  ldstr    aLive2onpremtoo// "Live2OnpremTool.exe"
0x34621  stelem.ref
0x34622  dup
0x34623  ldc.i4.3
0x34624  ldstr    aLive2onpremtoo_0// "live2onpremtool.vshost.exe"
0x34629  stelem.ref
0x3462a  dup
0x3462b  ldc.i4.4
0x3462c  ldstr    aCrmmergebasean// "CrmMergeBaseAndExtensionTableTool.exe"
0x34631  stelem.ref
0x34632  dup
0x34633  ldc.i4.5
0x34634  ldstr    aCrmmergebasean_0// "CrmMergeBaseAndExtensionTableTool.vshos"...
0x34639  stelem.ref
0x3463a  dup
0x3463b  ldc.i4.6
0x3463c  ldstr    aMetadataxmlval_1// "MetadataXmlValidator.EXE"
0x34641  stelem.ref
0x34642  dup
0x34643  ldc.i4.7
0x34644  ldstr    aMetadataxmlval_2// "metadataxmlvalidator.vshost.exe"
0x34649  stelem.ref
0x3464a  dup
0x3464b  ldc.i4.8
0x3464c  ldstr    aMetadataxmlval// "MetadataXmlValidatorForURs.exe"
0x34651  stelem.ref
0x34652  dup
0x34653  ldc.i4.s 9
0x34655  ldstr    aMetadataxmlval_0// "MetadataXmlValidatorForURs.vshost.exe"
0x3465a  stelem.ref
0x3465b  stsfld   string[] Microsoft.Crm.RegControl::internalToolHandle
0x34660  ldc.i4.0
0x34661  stsfld   bool Microsoft.Crm.RegControl::s_bLoadedBinaries
0x34666  ldnull
0x34667  stsfld   object Microsoft.Crm.RegControl::s_inClientContextCached
0x3466c  ldnull
0x3466d  stsfld   object Microsoft.Crm.RegControl::s_inCrmInternalToolContextCached
0x34672  ldnull
0x34673  stsfld   object Microsoft.Crm.RegControl::s_inConfigDbToolContextCached
0x34678  ldnull
0x34679  stsfld   object Microsoft.Crm.RegControl::s_inCrmEmailRouterContextCached
0x3467e  ldnull
0x3467f  stsfld   object Microsoft.Crm.RegControl::s_inServerContextCached
0x34684  ldnull
0x34685  stsfld   object Microsoft.Crm.RegControl::s_inServerSetupCached
0x3468a  ldsflda  valuetype [mscorlib]System.Nullable`1<bool> Microsoft.Crm.RegControl::isInHosterContextCached
0x3468f  initobj  valuetype [mscorlib]System.Nullable`1<bool>
0x34695  ldc.i4.0
0x34696  stsfld   int32 Microsoft.Crm.RegControl::s_roundRobinToken
0x3469b  ldc.i4.2
0x3469c  stsfld   int32 Microsoft.Crm.RegControl::maxConnectionsPerClient
0x346a1  newobj   instance void [mscorlib]System.Object::.ctor()
0x346a6  stsfld   object Microsoft.Crm.RegControl::s_syncRoot
0x346ab  ret
```
