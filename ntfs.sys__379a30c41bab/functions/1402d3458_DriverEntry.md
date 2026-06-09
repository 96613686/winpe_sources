# DriverEntry

- ea: `0x1402d3458`
- end: `0x1402d5020`
- name: `DriverEntry`
- size: `7112`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `33`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1402d33f0`

## callees

- `0x14000549c`
- `0x140007ea0`
- `0x14002f300`
- `0x14003b220`
- `0x14003b8bc`
- `0x14003e960`
- `0x140040428`
- `0x1400404e0`
- `0x140041688`
- `0x140041858`
- `0x140041900`
- `0x14004c8f0`
- `0x14004c948`
- `0x14004cabc`
- `0x14004cb04`
- `0x140059088`
- `0x1400592c0`
- `0x140059740`
- `0x1400dfc38`
- `0x1400dfca8`
- `0x1400e0080`
- `0x1400fe924`
- `0x140114460`
- `0x14025258c`
- `0x1402525f8`
- `0x140290cfc`
- `0x1402937cc`
- `0x1402d20f0`
- `0x1402d21b0`
- `0x1402d3458`
- `0x1402d50bc`
- `0x1402d51a0`
- `0x1402d52d0`

## import_xrefs

- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x1402d35bc`
- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x1402d35bc`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1402d3afb`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1402d3afb`
- `ntoskrnl!KeBugCheckEx` at `0x1402d4d3f`
- `ntoskrnl!KeBugCheckEx` at `0x1402d4d3f`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x1402d39e5`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x1402d39e5`
- `ntoskrnl!RtlInitAnsiString` at `0x1402d3506`
- `ntoskrnl!RtlInitAnsiString` at `0x1402d3506`
- `ntoskrnl!FsRtlQueryMaximumVirtualDiskNestingLevel` at `0x1402d35dc`
- `ntoskrnl!FsRtlQueryMaximumVirtualDiskNestingLevel` at `0x1402d35dc`
- `ntoskrnl!ExInitializeResourceLite` at `0x1402d4c30`
- `ntoskrnl!ExInitializeResourceLite` at `0x1402d4c30`
- `ntoskrnl!IoCreateDevice` at `0x1402d3a33`
- `ntoskrnl!IoCreateDevice` at `0x1402d3a33`
- `ntoskrnl!EtwRegister` at `0x1402d4b50`
- `ntoskrnl!EtwRegister` at `0x1402d4bce`
- `ntoskrnl!EtwRegister` at `0x1402d4b50`
- `ntoskrnl!EtwRegister` at `0x1402d4bce`
- `ntoskrnl!RtlGetVersion` at `0x1402d34d7`
- `ntoskrnl!RtlGetVersion` at `0x1402d34d7`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1402d358c`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1402d358c`
- `ntoskrnl!KeInitializeGuardedMutex` at `0x1402d362d`
- `ntoskrnl!KeInitializeGuardedMutex` at `0x1402d4cb6`
- `ntoskrnl!KeInitializeGuardedMutex` at `0x1402d4f15`
- `ntoskrnl!KeInitializeGuardedMutex` at `0x1402d4f44`
- `ntoskrnl!KeInitializeGuardedMutex` at `0x1402d362d`
- `ntoskrnl!KeInitializeGuardedMutex` at `0x1402d4cb6`
- `ntoskrnl!KeInitializeGuardedMutex` at `0x1402d4f15`
- `ntoskrnl!KeInitializeGuardedMutex` at `0x1402d4f44`
- `ntoskrnl!MmLockPagableDataSection` at `0x1402d3748`
- `ntoskrnl!MmLockPagableDataSection` at `0x1402d3748`
- `ntoskrnl!TmCurrentTransaction` at `0x1402d3768`
- `ntoskrnl!TmCurrentTransaction` at `0x1402d3768`
- `ntoskrnl!KeAllocateCalloutStackEx` at `0x1402d3873`
- `ntoskrnl!KeAllocateCalloutStackEx` at `0x1402d3898`
- `ntoskrnl!KeAllocateCalloutStackEx` at `0x1402d38bd`
- `ntoskrnl!KeAllocateCalloutStackEx` at `0x1402d38e2`
- `ntoskrnl!KeAllocateCalloutStackEx` at `0x1402d3907`
- `ntoskrnl!KeAllocateCalloutStackEx` at `0x1402d3873`
- `ntoskrnl!KeAllocateCalloutStackEx` at `0x1402d3898`
- `ntoskrnl!KeAllocateCalloutStackEx` at `0x1402d38bd`
- `ntoskrnl!KeAllocateCalloutStackEx` at `0x1402d38e2`
- `ntoskrnl!KeAllocateCalloutStackEx` at `0x1402d3907`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1402d3a68`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1402d3a68`
- `ntoskrnl!ExIsSoftBoot` at `0x1402d3b07`
- `ntoskrnl!ExIsSoftBoot` at `0x1402d3b07`
- `ntoskrnl!FsRtlMdlReadCompleteDev` at `0x1402d3cf0`
- `ntoskrnl!FsRtlMdlWriteCompleteDev` at `0x1402d3d0c`
- `ntoskrnl!FsRtlRegisterFileSystemFilterCallbacks` at `0x1402d48b5`
- `ntoskrnl!FsRtlRegisterFileSystemFilterCallbacks` at `0x1402d48b5`
- `ntoskrnl!InitializeSListHead` at `0x1402d4ce5`
- `ntoskrnl!InitializeSListHead` at `0x1402d4ce5`
- `ntoskrnl!KeInitializeTimer` at `0x1402d4de8`
- `ntoskrnl!KeInitializeTimer` at `0x1402d4de8`
- `ntoskrnl!KeInitializeDpc` at `0x1402d4e0c`
- `ntoskrnl!KeInitializeDpc` at `0x1402d4e0c`
- `ntoskrnl!ExAllocateTimer` at `0x1402d4e4e`
- `ntoskrnl!ExAllocateTimer` at `0x1402d4e4e`
- `ntoskrnl!KeInitializeSemaphore` at `0x1402d4ef4`
- `ntoskrnl!KeInitializeSemaphore` at `0x1402d4ef4`
- `ntoskrnl!IoRegisterFileSystem` at `0x1402d4fa3`
- `ntoskrnl!IoRegisterFileSystem` at `0x1402d4fa3`
- `ntoskrnl!IoRegisterDriverReinitialization` at `0x1402d4fc7`
- `ntoskrnl!IoRegisterDriverReinitialization` at `0x1402d4fc7`
- `ntoskrnl!PsIsDiskCountersEnabled` at `0x1402d4fe8`
- `ntoskrnl!PsIsDiskCountersEnabled` at `0x1402d4fe8`
- `ntoskrnl!PoRegisterCoalescingCallback` at `0x1402d500d`
- `ntoskrnl!PoRegisterCoalescingCallback` at `0x1402d500d`
- `ntoskrnl!SeDeassignSecurity` at `0x1402d492d`
- `ntoskrnl!SeDeassignSecurity` at `0x1402d492d`
- `ntoskrnl!KeFreeCalloutStack` at `0x1402d49ba`
- `ntoskrnl!KeFreeCalloutStack` at `0x1402d49d9`
- `ntoskrnl!KeFreeCalloutStack` at `0x1402d49f8`
- `ntoskrnl!KeFreeCalloutStack` at `0x1402d4a17`
- `ntoskrnl!KeFreeCalloutStack` at `0x1402d4a36`
- `ntoskrnl!KeFreeCalloutStack` at `0x1402d49ba`
- `ntoskrnl!KeFreeCalloutStack` at `0x1402d49d9`
- `ntoskrnl!KeFreeCalloutStack` at `0x1402d49f8`
- `ntoskrnl!KeFreeCalloutStack` at `0x1402d4a17`
- `ntoskrnl!KeFreeCalloutStack` at `0x1402d4a36`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402d368c`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402d3a05`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402d3a54`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402d368c`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402d3a05`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402d3a54`
- `ntoskrnl!KeInitializeEvent` at `0x1402d4ca3`
- `ntoskrnl!KeInitializeEvent` at `0x1402d4ca3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402d495f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402d4a9f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402d4ac0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402d4adf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402d495f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402d4a9f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402d4ac0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402d4adf`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402d3794`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402d3ab3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402d4d57`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402d3794`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402d3ab3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402d4d57`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1402d483a`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1402d4870`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1402d483a`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1402d4870`
- `HAL!KeQueryPerformanceCounter` at `0x1402d47f3`
- `HAL!KeQueryPerformanceCounter` at `0x1402d47f3`

## string_xrefs

- `0x1402d3d99`: `\Registry\Machine\System\CurrentControlSet\Control\MiniNT`
- `0x1402d3dcc`: `\Registry\Machine\System\CurrentControlSet\Control\UpdateOS`
- `0x1402d3e5b`: `NtfsAllowExtendedCharacter8dot3Rename`
- `0x1402d4026`: `NtfsDisableCompression`
- `0x1402d43a3`: `AllowOverAllocateOnVirtualMount`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  int v2; // r12d
  __int64 CachedFeatureEnabledState; // rax
  __int64 v6; // rax
  ULONG MaximumVirtualDiskNestingLevel; // eax
  void *v8; // rsi
  int v9; // edi
  PVOID PoolWithTag; // rax
  int CalloutStack; // ebx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // rdx
  int v21; // esi
  int v22; // r15d
  __int64 v23; // rcx
  int v24; // eax
  int v25; // ebx
  unsigned int v26; // edx
  int v27; // eax
  int v28; // r13d
  int v29; // ebx
  unsigned int v30; // edi
  int v31; // eax
  int ValueKeyWithFallBack; // eax
  unsigned int v34; // eax
  __int64 v35; // rcx
  __int64 v36; // rdx
  NTSTATUS v37; // eax
  __int64 v38; // rcx
  SIZE_T v39; // rdx
  PVOID v40; // rax
  __int64 (__fastcall *v41)(_QWORD); // rcx
  LONG v42; // edx
  __int64 v43; // rdx
  _BYTE v44[4]; // [rsp+40h] [rbp-C0h] BYREF
  int v45; // [rsp+44h] [rbp-BCh] BYREF
  __int128 v46; // [rsp+48h] [rbp-B8h] BYREF
  struct _STRING DestinationString; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING v48; // [rsp+70h] [rbp-90h] BYREF
  __int128 v49; // [rsp+80h] [rbp-80h] BYREF
  ULONG CompressFragmentWorkSpaceSize[4]; // [rsp+90h] [rbp-70h] BYREF
  struct _STRING Parameter; // [rsp+A0h] [rbp-60h] BYREF
  PCWSTR SourceString[2]; // [rsp+B0h] [rbp-50h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+C0h] [rbp-40h] BYREF
  ULONG CompressBufferWorkSpaceSize; // [rsp+C8h] [rbp-38h] BYREF
  struct _DRIVER_OBJECT *FilterDriverObject; // [rsp+D0h] [rbp-30h]
  struct _UNICODE_STRING DeviceName; // [rsp+D8h] [rbp-28h] BYREF
  struct _UNICODE_STRING SymbolicLinkName; // [rsp+E8h] [rbp-18h] BYREF
  _FS_FILTER_CALLBACKS Callbacks; // [rsp+100h] [rbp+0h] BYREF
  char v59; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int64 retaddr; // [rsp+268h] [rbp+168h]

  v2 = 0;
  FilterDriverObject = DriverObject;
  DeviceObject = 0;
  v44[0] = 0;
  CompressBufferWorkSpaceSize = 0;
  CompressFragmentWorkSpaceSize[0] = 0;
  DeviceName = 0;
  OSVersionInfo.dwOSVersionInfoSize = 284;
  SymbolicLinkName = 0;
  v48 = 0;
  v49 = 0;
  v46 = 0;
  *(_OWORD *)SourceString = 0;
  RtlGetVersion(&OSVersionInfo);
  DestinationString = 0;
  if ( !_InterlockedExchangeAdd(&g_AssertsOperational, 0) )
  {
    RtlInitAnsiString(&DestinationString, "ntfs.sys");
    Parameter = DestinationString;
    InitializeTelemetryAssertsKMWorkerInternal(&Parameter);
  }
  if ( (unsigned int)Feature_SFS_CD_BugFixes_2410__private_IsEnabledDeviceUsageNoInline() )
  {
    CachedFeatureEnabledState = wil_details_FeatureStateCache_GetCachedFeatureEnabledState(
                                  &Feature_SFS_CD_BugFixes_2410__private_featureState,
                                  Feature_SFS_CD_BugFixes_2410__private_descriptor);
    wil_details_FeatureReporting_ReportUsageToService(
      Feature_SFS_CD_BugFixes_2410__private_descriptor,
      CachedFeatureEnabledState,
      1);
  }
  if ( (unsigned int)Feature_SFS_CD_BugFixes_2511__private_IsEnabledDeviceUsageNoInline() )
  {
    v6 = wil_details_FeatureStateCache_GetCachedFeatureEnabledState(
           &Feature_SFS_CD_BugFixes_2511__private_featureState,
           Feature_SFS_CD_BugFixes_2511__private_descriptor);
    wil_details_FeatureReporting_ReportUsageToService(Feature_SFS_CD_BugFixes_2511__private_descriptor, v6, 1);
  }
  NtfsNumberProcessors = KeQueryActiveProcessorCountEx(0xFFFFu);
  NtfsLastAccess = 36000000000LL;
  RtlGetCompressionWorkSpaceSize(2u, &CompressBufferWorkSpaceSize, CompressFragmentWorkSpaceSize);
  memset(&NtfsData, 0, 0x968u);
  MaximumVirtualDiskNestingLevel = FsRtlQueryMaximumVirtualDiskNestingLevel();
  NtfsReserveStackStorage = 0;
  NtfsMaxNestingLevel = MaximumVirtualDiskNestingLevel;
  NtfsReserveStackPnp = 0;
  NtfsReserveStackCleanup = 0;
  NtfsReserveStackLogFileFull = 0;
  NtfsReserveStackTxfFlush = 0;
  NtfsReserveStacksRead = 0;
  NtfsReserveStacksWrite = 0;
  NtfsReserveStacksFlush = 0;
  KeInitializeGuardedMutex(&stru_140095940);
  NtfsInitializeReservedHeader(&qword_1400958B8, 288);
  NtfsInitializeReservedHeader(qword_1400959D8, 152);
  v45 = 156;
  *(_QWORD *)&DestinationString.Length = &v59;
  *(_OWORD *)SourceString = *(_OWORD *)L"fh";
  NtfsInitializeCompatibilityModeKeyPath();
  RtlInitUnicodeString(&v48, &NtfsCompatibilityModeKeyPath);
  PoolType = PagedPool;
  *((_QWORD *)&v46 + 1) = L"NtfsForceNonPagedPoolAllocation";
  dword_140095AE4 = PagedPoolCacheAligned;
  LODWORD(v46) = 4194366;
  v49 = *(_OWORD *)L"z|";
  if ( (int)NtfsQueryValueKey(SourceString, &v46, &v45, &DestinationString, v44) < 0
    && (int)NtfsQueryValueKeyWithFallBack(
              (unsigned int)&v48,
              (unsigned int)&v49,
              (unsigned int)&v46,
              (unsigned int)&v45,
              (__int64)&DestinationString,
              (__int64)v44) < 0 )
  {
    v8 = *(void **)&DestinationString.Length;
  }
  else
  {
    v8 = *(void **)&DestinationString.Length;
    if ( *(_DWORD *)(*(unsigned int *)(*(_QWORD *)&DestinationString.Length + 8LL) + *(_QWORD *)&DestinationString.Length) == 1 )
    {
      PoolType = 512;
      dword_140095AE4 = 516;
      MmLockPagableDataSection(NtfsCommonCreate);
    }
  }
  wil_InitializeFeatureStaging();
  *(_QWORD *)&Parameter.Length = 0;
  v9 = 0x1000000;
  if ( (unsigned int)TmCurrentTransaction(&Parameter) != -1073741637 )
    v9 = 0;
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)512, 0x1000u, 0x4A66744Eu);
  VirtualAddress = PoolWithTag;
  if ( !PoolWithTag )
  {
    CalloutStack = -1073741670;
    if ( !NtfsStatusDebugFlags )
    {
LABEL_152:
      if ( SecurityDescriptor )
        SeDeassignSecurity(&SecurityDescriptor);
      NtfsDeleteReservedHeader(&qword_1400958B8);
      NtfsDeleteReservedHeader(qword_1400959D8);
      if ( VirtualAddress )
      {
        ExFreePoolWithTag(VirtualAddress, 0);
        VirtualAddress = 0;
      }
      NtfsDeleteReservedBuffer(&qword_140095978);
      NtfsDeleteReservedBuffer(&qword_140095990);
      NtfsDeleteReservedBuffer(&qword_1400959A8);
      NtfsDeleteReservedBuffer(&qword_1400959C0);
      NtfsDeleteReservedBuffer(qword_140095A58);
      if ( NtfsReserveStackStorage )
      {
        KeFreeCalloutStack();
        NtfsReserveStackStorage = 0;
      }
      if ( NtfsReserveStackPnp )
      {
        KeFreeCalloutStack();
        NtfsReserveStackPnp = 0;
      }
      if ( NtfsReserveStackCleanup )
      {
        KeFreeCalloutStack();
        NtfsReserveStackCleanup = 0;
      }
      if ( NtfsReserveStackLogFileFull )
      {
        KeFreeCalloutStack();
        NtfsReserveStackLogFileFull = 0;
      }
      if ( NtfsReserveStackTxfFlush )
      {
        KeFreeCalloutStack();
        NtfsReserveStackTxfFlush = 0;
      }
      if ( NtfsReserveStacksRead )
      {
        NtfsFreeReservedStacks(NtfsReserveStacksRead);
        NtfsReserveStacksRead = 0;
      }
      if ( NtfsReserveStacksWrite )
      {
        NtfsFreeReservedStacks(NtfsReserveStacksWrite);
        NtfsReserveStacksWrite = 0;
      }
      if ( NtfsReserveStacksFlush )
      {
        NtfsFreeReservedStacks(NtfsReserveStacksFlush);
        NtfsReserveStacksFlush = 0;
      }
      if ( NtfsRegistryPath.Buffer )
      {
        ExFreePoolWithTag(NtfsRegistryPath.Buffer, 0);
        NtfsRegistryPath.Buffer = 0;
      }
      if ( qword_140095548 )
      {
        ExFreePoolWithTag(qword_140095548, 0);
        qword_140095548 = 0;
      }
      if ( v44[0] )
        ExFreePoolWithTag(v8, 0);
      UninitializeTelemetryAssertsKM();
      return CalloutStack;
    }
    v12 = 1704859;
LABEL_17:
    NtfsStatusTraceAndDebugInternal(0, 3221225626LL, v12);
    goto LABEL_152;
  }
  memset(PoolWithTag, 0, 0x1000u);
  CalloutStack = NtfsInitializeReservedBuffer(qword_140095A58, 0x10000);
  if ( CalloutStack < 0 )
    goto LABEL_152;
  CalloutStack = NtfsInitializeReservedBuffer(&qword_140095978, 0x10000);
  if ( CalloutStack < 0 )
    goto LABEL_152;
  CalloutStack = NtfsInitializeReservedBuffer(&qword_140095990, 69632);
  if ( CalloutStack < 0 )
    goto LABEL_152;
  CalloutStack = NtfsInitializeReservedBuffer(&qword_1400959A8, CompressFragmentWorkSpaceSize[0]);
  if ( CalloutStack < 0 )
    goto LABEL_152;
  CalloutStack = NtfsInitializeReservedBuffer(&qword_1400959C0, 0x10000);
  if ( CalloutStack < 0 )
    goto LABEL_152;
  LOBYTE(v13) = 4;
  CalloutStack = KeAllocateCalloutStackEx(0, v13, 0, &NtfsReserveStackStorage);
  if ( CalloutStack < 0 )
    goto LABEL_152;
  LOBYTE(v14) = 1;
  CalloutStack = KeAllocateCalloutStackEx(0, v14, 0, &NtfsReserveStackPnp);
  if ( CalloutStack < 0 )
    goto LABEL_152;
  LOBYTE(v15) = 1;
  CalloutStack = KeAllocateCalloutStackEx(0, v15, 0, &NtfsReserveStackCleanup);
  if ( CalloutStack < 0 )
    goto LABEL_152;
  LOBYTE(v16) = 1;
  CalloutStack = KeAllocateCalloutStackEx(0, v16, 0, &NtfsReserveStackLogFileFull);
  if ( CalloutStack < 0 )
    goto LABEL_152;
  LOBYTE(v17) = 1;
  CalloutStack = KeAllocateCalloutStackEx(0, v17, 0, &NtfsReserveStackTxfFlush);
  if ( CalloutStack < 0 )
    goto LABEL_152;
  LOBYTE(v18) = 2;
  NtfsReserveStacksRead = (PVOID)NtfsAllocateReservedStacks(10, v18);
  if ( !NtfsReserveStacksRead )
  {
    CalloutStack = -1073741670;
    if ( !NtfsStatusDebugFlags )
      goto LABEL_152;
    v12 = 1704990;
    goto LABEL_17;
  }
  LOBYTE(v19) = 2;
  NtfsReserveStacksWrite = (PVOID)NtfsAllocateReservedStacks(10, v19);
  if ( !NtfsReserveStacksWrite )
  {
    CalloutStack = -1073741670;
    if ( !NtfsStatusDebugFlags )
      goto LABEL_152;
    v12 = 1704996;
    goto LABEL_17;
  }
  LOBYTE(v20) = 1;
  NtfsReserveStacksFlush = (PVOID)NtfsAllocateReservedStacks(1, v20);
  if ( !NtfsReserveStacksFlush )
  {
    CalloutStack = -1073741670;
    if ( !NtfsStatusDebugFlags )
      goto LABEL_152;
    v12 = 1705002;
    goto LABEL_17;
  }
  Parameter = (struct _STRING)retaddr;
  KeExpandKernelStackAndCalloutEx(NtfsMeasureExpandedStackCalloutDepthCallout, &Parameter, 0x6000u, 0, 0);
  NtfsFramesToSkipOnSwappedStack = (int)Parameter.Buffer;
  RtlInitUnicodeString(&DeviceName, L"\\Ntfs");
  CalloutStack = IoCreateDevice(DriverObject, 0, &DeviceName, 8u, 0, 0, &DeviceObject);
  if ( CalloutStack < 0 )
    goto LABEL_152;
  RtlInitUnicodeString(&SymbolicLinkName, L"\\DosDevices\\Ntfs");
  CalloutStack = IoCreateSymbolicLink(&SymbolicLinkName, &DeviceName);
  if ( CalloutStack < 0 )
    goto LABEL_152;
  DeviceObject->Flags |= 0x8000000u;
  NtfsRegistryPath.MaximumLength = RegistryPath->Length + 2;
  NtfsRegistryPath.Length = RegistryPath->Length;
  NtfsRegistryPath.Buffer = (PWSTR)ExAllocatePoolWithTag(
                                     (POOL_TYPE)(PoolType | 0x10),
                                     NtfsRegistryPath.MaximumLength,
                                     0x4A66744Eu);
  if ( !NtfsRegistryPath.Buffer )
  {
    CalloutStack = -1073741670;
    if ( !NtfsStatusDebugFlags )
      goto LABEL_152;
    v12 = 1705079;
    goto LABEL_17;
  }
  v21 = 0;
  *(_DWORD *)&Parameter.Length = 0;
  v22 = 0;
  RtlCopyUnicodeString(&NtfsRegistryPath, RegistryPath);
  if ( (unsigned __int8)ExIsSoftBoot() )
    dword_140095BE8 |= 1u;
  DriverObject->MajorFunction[5] = (PDRIVER_DISPATCH)&NtfsFsdDispatchWait;
  DriverObject->MajorFunction[26] = (PDRIVER_DISPATCH)&NtfsFsdDispatchWait;
  DriverObject->MajorFunction[25] = (PDRIVER_DISPATCH)&NtfsFsdDispatchWait;
  DriverObject->MajorFunction[8] = (PDRIVER_DISPATCH)&NtfsFsdDispatchWait;
  DriverObject->MajorFunction[7] = (PDRIVER_DISPATCH)&NtfsFsdDispatchWait;
  DriverObject->MajorFunction[11] = (PDRIVER_DISPATCH)&NtfsFsdDispatch;
  DriverObject->MajorFunction[10] = (PDRIVER_DISPATCH)&NtfsFsdDispatch;
  DriverObject->MajorFunction[21] = (PDRIVER_DISPATCH)&NtfsFsdDispatch;
  DriverObject->MajorFunction[20] = (PDRIVER_DISPATCH)&NtfsFsdDispatch;
  DriverObject->MajorFunction[17] = (PDRIVER_DISPATCH)&NtfsFsdLockControl;
  DriverObject->MajorFunction[12] = (PDRIVER_DISPATCH)&NtfsFsdDirectoryControl;
  DriverObject->MajorFunction[6] = (PDRIVER_DISPATCH)&NtfsFsdSetInformation;
  DriverObject->MajorFunction[0] = (PDRIVER_DISPATCH)&NtfsFsdCreate;
  DriverObject->MajorFunction[2] = (PDRIVER_DISPATCH)&NtfsFsdClose;
  DriverObject->MajorFunction[3] = (PDRIVER_DISPATCH)&NtfsFsdRead;
  DriverObject->MajorFunction[4] = (PDRIVER_DISPATCH)&NtfsFsdWrite;
  DriverObject->MajorFunction[9] = (PDRIVER_DISPATCH)&NtfsFsdFlushBuffers;
  DriverObject->MajorFunction[13] = (PDRIVER_DISPATCH)NtfsFsdFileSystemControl;
  DriverObject->MajorFunction[18] = (PDRIVER_DISPATCH)&NtfsFsdCleanup;
  DriverObject->MajorFunction[16] = (PDRIVER_DISPATCH)&NtfsFsdShutdown;
  DriverObject->MajorFunction[27] = (PDRIVER_DISPATCH)NtfsFsdPnp;
  DriverObject->MajorFunction[14] = (PDRIVER_DISPATCH)&NtfsFsdDeviceControl;
  DriverObject->FastIoDispatch = (PFAST_IO_DISPATCH)&NtfsFastIoDispatch;
  qword_140094DC8 = (__int64)NtfsFastIoCheckIfPossible;
  qword_140094DD0 = (__int64)NtfsCopyReadA;
  qword_140094DD8 = (__int64)NtfsCopyWriteA;
  qword_140094DE0 = (__int64)NtfsFastQueryBasicInfo;
  qword_140094DE8 = (__int64)NtfsFastQueryStdInfo;
  qword_140094DF0 = (__int64)NtfsFastLock;
  qword_140094DF8 = (__int64)NtfsFastUnlockSingle;
  qword_140094E00 = (__int64)NtfsFastUnlockAll;
  qword_140094E08 = (__int64)NtfsFastUnlockAllByKey;
  qword_140094E30 = (__int64)NtfsFastQueryNetworkOpenInfo;
  qword_140094E20 = (__int64)NtfsReleaseForCreateSection;
  qword_140094E38 = (__int64)NtfsAcquireFileForModWrite;
  qword_140094E88 = (__int64)NtfsReleaseFileForModWrite;
  qword_140094E40 = (__int64)NtfsMdlReadA;
  qword_140094E48 = (__int64)FsRtlMdlReadCompleteDev;
  qword_140094E50 = (__int64)NtfsPrepareMdlWriteA;
  qword_140094E58 = (__int64)FsRtlMdlWriteCompleteDev;
  qword_140094E80 = (__int64)NtfsNetworkOpenCreate;
  qword_140094E90 = (__int64)NtfsAcquireFileForCcFlush;
  NtfsFastIoDispatch = 240;
  qword_140094E10 = 0;
  qword_140094E28 = 0;
  qword_140094E18 = 0;
  qword_140094E98 = (__int64)NtfsReleaseFileForCcFlush;
  qword_140094EA0 = (__int64)&NtfsIssueBypassIo;
  qword_140094EA8 = (__int64)&NtfsBypassIoVolumeAttachNotification;
  McGenEventRegisterContext_EtwRegister_0();
  if ( (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 1) != 0 )
    McTemplateU0_EtwWriteTransfer(v23, ntfsinit_c1233);
  *(_DWORD *)&v48.Length = 7602290;
  v48.Buffer = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\MiniNT";
  if ( (int)NtfsQueryValueKey(&v48, 0, 0, 0, 0) >= 0 )
    v9 |= 0x4000u;
  *(_DWORD *)&v48.Length = 7864438;
  v48.Buffer = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\UpdateOS";
  v24 = NtfsQueryValueKey(&v48, 0, 0, 0, 0);
  LODWORD(v46) = 4980810;
  v25 = v9 | 0x8000000;
  *((_QWORD *)&v46 + 1) = L"NtfsAllowExtendedCharacterIn8dot3Name";
  if ( v24 < 0 )
    v25 = v9;
  if ( (int)NtfsQueryValueKeyWithFallBack(
              (unsigned int)&v48,
              (unsigned int)&v49,
              (unsigned int)&v46,
              (unsigned int)&v45,
              (__int64)&DestinationString,
              (__int64)v44) >= 0
    && *(_DWORD *)(*(unsigned int *)(*(_QWORD *)&DestinationString.Length + 8LL) + *(_QWORD *)&DestinationString.Length) == 1 )
  {
    v25 |= 0x20u;
  }
  LODWORD(v46) = 4980810;
  *((_QWORD *)&v46 + 1) = L"NtfsAllowExtendedCharacter8dot3Rename";
  if ( (int)NtfsQueryValueKeyWithFallBack(
              (unsigned int)&v48,
              (unsigned int)&v49,
              (unsigned int)&v46,
              (unsigned int)&v45,
              (__int64)&DestinationString,
              (__int64)v44) >= 0
    && *(_DWORD *)(*(unsigned int *)(*(_QWORD *)&DestinationString.Length + 8LL) + *(_QWORD *)&DestinationString.Length) == 1 )
  {
    v25 |= 0x800u;
  }
  LODWORD(v46) = 3145774;
  *((_QWORD *)&v46 + 1) = L"NtfsDisableVolsnapHints";
  if ( (int)NtfsQueryValueKeyWithFallBack(
              (unsigned int)&v48,
              (unsigned int)&v49,
              (unsigned int)&v46,
              (unsigned int)&v45,
              (__int64)&DestinationString,
              (__int64)v44) >= 0
    && *(_DWORD *)(*(unsigned int *)(*(_QWORD *)&DestinationString.Length + 8LL) + *(_QWORD *)&DestinationString.Length) == 1 )
  {
    v25 |= 0x8000u;
  }
  NtfsMftZoneMultiplier = 1;
  *((_QWORD *)&v46 + 1) = L"NtfsMftZoneReservation";
  LODWORD(v46) = 3014700;
  if ( (int)NtfsQueryValueKeyWithFallBack(
              (unsigned int)&v48,
              (unsigned int)&v49,
              (unsigned int)&v46,
              (unsigned int)&v45,
              (__int64)&DestinationString,
              (__int64)v44) >= 0 )
  {
    v26 = *(_DWORD *)(*(unsigned int *)(*(_QWORD *)&DestinationString.Length + 8LL)
                    + *(_QWORD *)&DestinationString.Length);
    if ( v26 )
    {
      v27 = 100;
      if ( v26 < 0x64 )
        v27 = *(_DWORD *)(*(unsigned int *)(*(_QWORD *)&DestinationString.Length + 8LL)
                        + *(_QWORD *)&DestinationString.Length);
      NtfsMftZoneMultiplier = v27;
    }
  }
  LODWORD(v46) = 2097182;
  *((_QWORD *)&v46 + 1) = L"NtfsMemoryUsage";
  v28 = 1;
  if ( (int)NtfsQueryValueKeyWithFallBack(
              (unsigned int)&v48,
              (unsigned int)&v49,
              (unsigned int)&v46,
              (unsigned int)&v45,
              (__int64)&DestinationString,
              (__int64)v44) >= 0
    && (unsigned int)(*(_DWORD *)(*(unsigned int *)(*(_QWORD *)&DestinationString.Length + 8LL)
                                + *(_QWORD *)&DestinationString.Length)
                    - 1) <= 1 )
  {
    v28 = *(_DWORD *)(*(unsigned int *)(*(_QWORD *)&DestinationString.Length + 8LL)
                    + *(_QWORD *)&DestinationString.Length);
  }
  LODWORD(v46) = 2621478;
  *((_QWORD *)&v46 + 1) = L"NtfsQuotaNotifyRate";
  if ( (int)NtfsQueryValueKeyWithFallBack(
              (unsigned int)&v48,
              (unsigned int)&v49,
              (unsigned int)&v46,
              (unsigned int)&v45,
              (__int64)&DestinationString,
              (__int64)v44) >= 0 )
    NtfsMaxQuotaNotifyRate = 10000000LL
                           * *(unsigned int *)(*(unsigned int *)(*(_QWORD *)&DestinationString.Length + 8LL)
                                             + *(_QWORD *)&DestinationString.Length);
  LODWORD(v46) = 3014700;
  *((_QWORD *)&v46 + 1) = L"NtfsDisableCompression";
  if ( ((int)NtfsQueryValueKey(SourceString, &v46, &v45, &DestinationString, v44) >= 0
     || (int)NtfsQueryValueKeyWithFallBack(
               (unsigned int)&v48,
               (unsigned int)&v49,
               (unsigned int)&v46,
               (unsigned int)&v45,
               (__int64)&DestinationString,
               (__int64)v44) >= 0)
    && *(_DWORD *)(*(unsigned int *)(*(_QWORD *)&DestinationString.Length + 8LL) + *(_QWORD *)&DestinationString.Length) == 1 )
  {
    v25 |= 0x400u;
  }
  LODWORD(v46) = 4849736;
  *((_QWORD *)&v46 + 1) = L"NtfsEncryptPagingFileForGuardedHosts";
  if ( (int)NtfsQueryValueKeyWithFallBack(
              (unsigned int)&v48,
              (unsigned int)&v49,
              (unsigned int)&v46,
              (unsigned int)&v45,
              (__int64)&DestinationString,
              (__int64)v44) >= 0
    && *(_DWORD *)(*(unsigned int *)(*(_QWORD *)&DestinationString.Length + 8LL) + *(_QWORD *)&DestinationString.Length) == 1 )
  {
    v25 |= 0x2080u;
  }
  if ( (v25 & 0x80u) == 0 )
  {
    LODWORD(v46) = 2883626;
    *((_QWORD *)&v46 + 1) = L"NtfsDisableEncryption";
    if ( (int)NtfsQueryValueKey(SourceString, &v46, &v45, &DestinationString, v44) < 0
      && (int)NtfsQueryValueKeyWithFallBack(
                (unsigned int)&v48,
                (unsigned int)&v49,
                (unsigned int)&v46,
                (unsigned int)&v45,
                (__int64)&DestinationString,
                (__int64)v44) < 0
      || !*(_DWORD *)(*(unsigned int *)(*(_QWORD *)&DestinationString.Length + 8LL)
                    + *(_QWORD *)&DestinationString.Length) )
    {
      v25 |= 0x80u;
    }
    if ( (v25 & 0x80u) != 0 )
    {
      LODWORD(v46) = 2883626;
      *((_QWORD *)&v46 + 1) = L"NtfsEncryptPagingFile";
      if ( ((int)NtfsQueryValueKey(SourceString, &v46, &v45, &DestinationString, v44) >= 0
         || (int)NtfsQueryValueKeyWithFallBack(
                   (unsigned int)&v48,
                   (unsigned int)&v49,
                   (unsigned int)&v46,
                   (unsigned int)&v45,
                   (__int64)&DestinationString,
                   (__int64)v44) >= 0)
        && *(_DWORD *)(*(unsigned int *)(*(_QWORD *)&DestinationString.Length + 8LL)
                     + *(_QWORD *)&DestinationString.Length) == 1 )
      {
        v25 |= 0x2000u;
      }
    }
  }
  LODWORD(v46) = 2883626;
  *((_QWORD *)&v46 + 1) = L"NtfsBugcheckOnCorrupt";
  if ( (int)NtfsQueryValueKeyWithFallBack(
              (unsigned int)&v48,
              (unsigned int)&v49,
              (unsigned int)&v46,
              (unsigned int)&v45,
              (__int64)&DestinationString,
              (__int64)v44) >= 0
    && *(_DWORD *)(*(unsigned int *)(*(_QWORD *)&DestinationString.Length + 8LL) + *(_QWORD *)&DestinationString.Length) == 1 )
  {
    v25 |= 0x10000u;
  }
  LODWORD(v46) = 3407922;
  *((_QWORD *)&v46 + 1) = L"NtfsDisableDebugCodeFlags";
  if ( (int)NtfsQueryValueKeyWithFallBack(
              (unsigned int)&v48,
              (unsigned int)&v49,
              (unsigned int)&v46,
              (unsigned int)&v45,
              (__int64)&DestinationString,
              (__int64)v44) >= 0
    && *(_DWORD *)(*(unsigned int *)(*(_QWORD *)&DestinationString.Length + 8LL) + *(_QWORD *)&DestinationString.Length) )
  {
    v2 = *(_DWORD *)(*(unsigned int *)(*(_QWORD *)&DestinationString.Length + 8LL) + *(_QWORD *)&DestinationString.Length);
  }
  LODWORD(v46) = 3276848;
  *((_QWORD *)&v46 + 1) = L"NtfsEnableDebugCodeFlags";
  if ( (int)NtfsQueryValueKeyWithFallBack(
              (unsigned int)&v48,
              (unsigned int)&v49,
              (unsigned int)&v46,
              (unsigned int)&v45,
              (__int64)&DestinationString,
              (__int64)v44) >= 0 )
  {
    if ( *(_DWORD *)(*(unsigned int *)(*(_QWORD *)&DestinationString.Length + 8LL) + *(_QWORD *)&DestinationString.Length) )
      v21 = *(_DWORD *)(*(unsigned int *)(*(_QWORD *)&DestinationString.Length + 8LL)
                      + *(_QWORD *)&DestinationString.Length);
    *(_DWORD *)&Parameter.Length = v21;
  }
  LODWORD(v46) = 2883626;
  *((_QWORD *)&v46 + 1) = L"NtfsDisableLfsUpgrade";
  if ( (int)NtfsQueryValueKeyWithFallBack(
              (unsigned int)&v48,
              (unsigned int)&v49,
              (unsigned int)&v46,
              (unsigned int)&v45,
              (__int64)&DestinationString,
              (__int64)v44) >= 0
    && *(_DWORD *)(*(unsigned int *)(*(_QWORD *)&DestinationString.Length + 8LL) + *(_QWORD *)&DestinationString.Length) == 1 )
  {
    v25 |= 1u;
  }
  LODWORD(v46) = 3145774;
  *((_QWORD *)&v46 + 1) = L"NtfsDisableLfsDowngrade";
  if ( (int)NtfsQueryValueKeyWithFallBack(
              (unsigned int)&v48,
              (unsigned int)&v49,
              (unsigned int)&v46,
              (unsigned int)&v45,
              (__int64)&DestinationString,
              (__int64)v44) >= 0
    && *(_DWORD *)(*(unsigned int *)(*(_QWORD *)&DestinationString.Length + 8LL) + *(_QWORD *)&DestinationString.Length) == 1 )
  {
    v25 |= 2u;
  }
  LODWORD(v46) = 4194366;
  *((_QWORD *)&v46 + 1) = L"AllowOverAllocateOnVirtualMount";
  v29 = v25 | 0x40000;
  v30 = v29;
  if ( (int)NtfsQueryValueKey(SourceString, &v46, &v45, &DestinationString, v44) < 0 )
  {
    if ( (int)NtfsQueryValueKeyWithFallBack(
                (unsigned int)&v48,
                (unsigned int)&v49,
                (unsigned int)&v46,
                (unsigned int)&v45,
                (__int64)&DestinationString,
                (__int64)v44) >= 0
      && !*(_DWORD *)(*(unsigned int *)(*(_QWORD *)&DestinationString.Length + 8LL)
                    + *(_QWORD *)&DestinationString.Length) )
    {
      v30 = v29 & 0xFFFBFFFF;
    }
  }
  else
  {
    v30 = v29 & 0xFFFBFFFF;
    if ( *(_DWORD *)(*(unsigned int *)(*(_QWORD *)&DestinationString.Length + 8LL) + *(_QWORD *)&DestinationString.Length) )
      v30 = v29;
  }
  if ( NtfsEnforceWalThroughFua )
    v30 |= 0x200000u;
  LODWORD(v46) = 3932218;
  *((_QWORD *)&v46 + 1) = L"NtfsEnableCorruptLogPutRecord";
  if ( (int)NtfsQueryValueKeyWithFallBack(
              (unsigned int)&v48,
              (unsigned int)&v49,
              (unsigned int)&v46,
              (unsigned int)&v45,
              (__int64)&DestinationString,
              (__int64)v44) >= 0
    && *(_DWORD *)(*(unsigned int *)(*(_QWORD *)&DestinationString.Length + 8LL) + *(_QWORD *)&DestinationString.Length) == 1 )
  {
    v30 |= 0x400000u;
  }
  LODWORD(v46) = 4849736;
  *((_QWORD *)&v46 + 1) = L"NtfsEnableTxfDeprecatedFunctionality";
  if ( (int)NtfsQueryValueKey(SourceString, &v46, &v45, &DestinationString, v44) < 0 )
  {
    if ( (int)NtfsQueryValueKeyWithFallBack(
                (unsigned int)&v48,
                (unsigned int)&v49,
                (unsigned int)&v46,
                (unsigned int)&v45,
                (__int64)&DestinationString,
                (__int64)v44) >= 0
      && *(_DWORD *)(*(unsigned int *)(*(_QWORD *)&DestinationString.Length + 8LL) + *(_QWORD *)&DestinationString.Length) == 1 )
    {
      v30 |= 0x800000u;
    }
  }
  else
  {
    v31 = v30 | 0x800000;
    if ( *(_DWORD *)(*(unsigned int *)(*(_QWORD *)&DestinationString.Length + 8LL) + *(_QWORD *)&DestinationString.Length) != 1 )
      v31 = v30;
    v30 = v31;
  }
  LODWORD(v46) = 2490404;
  *((_QWORD *)&v46 + 1) = L"NtfsUsnMinuteTimer";
  dword_140095AAC = 5;
  if ( (int)NtfsQueryValueKey(SourceString, &v46, &v45, &DestinationString, v44) >= 0
    || (int)NtfsQueryValueKeyWithFallBack(
              (unsigned int)&v48,
              (unsigned int)&v49,
              (unsigned int)&v46,
              (unsigned int)&v45,
              (__int64)&DestinationString,
              (__int64)v44) >= 0 )
  {
    dword_140095AAC = *(_DWORD *)(*(unsigned int *)(*(_QWORD *)&DestinationString.Length + 8LL)
                                + *(_QWORD *)&DestinationString.Length);
  }
  if ( (unsigned int)(dword_140095AAC - 1) > 4 )
    dword_140095AAC = 5;
  LODWORD(v46) = 2621478;
  *((_QWORD *)&v46 + 1) = L"NtfsUsnTimeOutCount";
  dword_140095AA8 = 3;
  if ( (int)NtfsQueryValueKey(SourceString, &v46, &v45, &DestinationString, v44) >= 0
    || (int)NtfsQueryValueKeyWithFallBack(
              (unsigned int)&v48,
              (unsigned int)&v49,
              (unsigned int)&v46,
              (unsigned int)&v45,
              (__int64)&DestinationString,
              (__int64)v44) >= 0 )
  {
    dword_140095AA8 = *(_DWORD *)(*(unsigned int *)(*(_QWORD *)&DestinationString.Length + 8LL)
                                + *(_QWORD *)&DestinationString.Length);
  }
  if ( (unsigned int)(dword_140095AA8 - 1) > 2 )
    dword_140095AA8 = 3;
  LODWORD(v46) = 3014700;
  *((_QWORD *)&v46 + 1) = L"NtfsAllowUsnMinSize1Mb";
  if ( ((int)NtfsQueryValueKey(SourceString, &v46, &v45, &DestinationString, v44) >= 0
     || (int)NtfsQueryValueKeyWithFallBack(
               (unsigned int)&v48,
               (unsigned int)&v49,
               (unsigned int)&v46,
               (unsigned int)&v45,
               (__int64)&DestinationString,
               (__int64)v44) >= 0)
    && *(_DWORD *)(*(unsigned int *)(*(_QWORD *)&DestinationString.Length + 8LL) + *(_QWORD *)&DestinationString.Length) == 1 )
  {
    v30 |= 0x2000000u;
  }
  LODWORD(v46) = 3932218;
  *((_QWORD *)&v46 + 1) = L"NtfsAllowTpOnNonSpacesVolumes";
  if ( (int)NtfsQueryValueKeyWithFallBack(
              (unsigned int)&v48,
              (unsigned int)&v49,
              (unsigned int)&v46,
              (unsigned int)&v45,
              (__int64)&DestinationString,
              (__int64)v44) >= 0
    && *(_DWORD *)(*(unsigned int *)(*(_QWORD *)&DestinationString.Length + 8LL) + *(_QWORD *)&DestinationString.Length) == 1 )
  {
    v30 |= 0x40000000u;
  }
  LODWORD(v46) = 2752552;
  *((_QWORD *)&v46 + 1) = L"NtfsTpSmartTrimFlags";
  if ( (int)NtfsQueryValueKeyWithFallBack(
              (unsigned int)&v48,
              (unsigned int)&v49,
              (unsigned int)&v46,
              (unsigned int)&v45,
              (__int64)&DestinationString,
              (__int64)v44) >= 0
    && (*(_BYTE *)(*(unsigned int *)(*(_QWORD *)&DestinationString.Length + 8LL) + *(_QWORD *)&DestinationString.Length)
      & 1) != 0 )
  {
    v22 = 1;
  }
  LODWORD(v46) = 3407922;
  *((_QWORD *)&v46 + 1) = L"NtfsVcbEresourceBoostCpus";
  ValueKeyWithFallBack = NtfsQueryValueKeyWithFallBack(
                           (unsigned int)&v48,
                           (unsigned int)&v49,
                           (unsigned int)&v46,
                           (unsigned int)&v45,
                           (__int64)&DestinationString,
                           (__int64)v44);
  v8 = *(void **)&DestinationString.Length;
  if ( ValueKeyWithFallBack < 0 )
    dword_140095C80 = 64;
  else
    dword_140095C80 = *(_DWORD *)(*(unsigned int *)(*(_QWORD *)&DestinationString.Length + 8LL)
                                + *(_QWORD *)&DestinationString.Length);
  KeQueryPerformanceCounter(&NtfsPerformanceFrequency);
  NtfsInitializeNtfsData(FilterDriverObject, (__int64)DeviceObject, v28);
  ExInitializeNPagedLookasideList(&FsLibRangeLockIntLookasideList, 0, 0, 0x200u, 0x410u, 0x6E694C52u, 0x10u);
  ExInitializeNPagedLookasideList(&FsLibRangeLockLookasideList, 0, 0, 0x200u, 0x28u, 0x696C4C52u, 8u);
  FsLibInitializeDAX();
  memset(&Callbacks, 0, sizeof(Callbacks));
  Callbacks.PreAcquireForSectionSynchronization = (PFS_FILTER_CALLBACK)NtfsFilterCallbackAcquireForCreateSection;
  Callbacks.SizeOfFsFilterCallbacks = 120;
  Callbacks.PreQueryOpen = (PFS_FILTER_CALLBACK)NtfsFilterCallbackQueryOpen;
  CalloutStack = FsRtlRegisterFileSystemFilterCallbacks(FilterDriverObject, &Callbacks);
  if ( CalloutStack < 0 )
  {
    if ( NtfsStatusDebugFlags
      && (unsigned int)CalloutStack < 0xFFFFFFED
      && CalloutStack != -1073741802
      && (unsigned int)(CalloutStack + 2147483643) > 1
      && CalloutStack != -1073741807
      && CalloutStack != -1073741608 )
    {
      NtfsStatusTraceAndDebugInternal(0, (unsigned int)CalloutStack, 1706113);
    }
    goto LABEL_152;
  }
  dword_1400956BC |= v22;
  dword_1400958B0 |= v2;
  dword_1400956B8 |= v30 | 0x40;
  dword_1400958B4 |= *(_DWORD *)&Parameter.Length;
  v34 = EtwRegister(&NtfsSystemEventProvider, 0, 0, &qword_1400957E8);
  v36 = v34;
  if ( (v34 & 0x80000000) != 0 )
  {
    LOBYTE(v35) = NtfsStatusDebugFlags;
    if ( NtfsStatusDebugFlags
      && v34 < 0xFFFFFFED
      && v34 != -1073741802
      && v34 + 2147483643 > 1
      && v34 != -1073741807
      && v34 != -1073741608 )
    {
      NtfsStatusTraceAndDebugInternal(0, v34, 1706150);
    }
    qword_1400957E8 = 0;
  }
  McGenEventRegister_EtwRegister(v35, v36);
  v37 = EtwRegister(&NtfsUbpmEventProvider, 0, 0, &RegHandle);
  if ( v37 < 0 )
  {
    if ( NtfsStatusDebugFlags
      && (unsigned int)v37 < 0xFFFFFFED
      && v37 != -1073741802
      && (unsigned int)(v37 + 2147483643) > 1
      && v37 != -1073741807
      && v37 != -1073741608 )
    {
      NtfsStatusTraceAndDebugInternal(0, (unsigned int)v37, 1706163);
    }
    RegHandle = 0;
  }
  NtfsInitializeTelemetry();
  ExInitializeResourceLite(&NtfsDynamicRegistrySettingsResource);
  NtfsSetupWatchForRegistryChanges(&NtfsCompatibilityModeKeyPath);
  NtfsSetupWatchForRegistryChanges(SourceString[1]);
  NtfsSetupDeveloperModeDetection();
  NtfsUpdateDynamicRegistrySettings(0);
  if ( IoPerfRegistryConfig )
  {
    byte_140094822 = 1;
    byte_140094820 = 1;
  }
  else
  {
    NtfsInitializeIoPerf();
  }
  NtfsSendGlobalCorruptionActionEvent(v38);
  KeInitializeEvent(&NtfsEncryptionPendingEvent, NotificationEvent, 1u);
  KeInitializeGuardedMutex(&NtfsMcbMutex);
  NtfsMcbCleanupInProgress = 0;
  qword_140094F28 = (__int64)&NtfsMcbLruQueue;
  NtfsMcbLruQueue = &NtfsMcbLruQueue;
  InitializeSListHead(&NtfsUnchainedMcbQueue);
  v39 = 8LL * (unsigned int)dword_14009553C;
  NtfsMcbCurrentLevel = 0;
  NtfsMcbHighWaterMark = 16000 * v28;
  NtfsMcbLowWaterMark = 8000 * v28;
  if ( v39 > 0xFFFFFFFF )
    KeBugCheckEx(0x24u, 0xB8001A0917uLL, 0, 0, 0);
  v40 = ExAllocatePoolWithTag((POOL_TYPE)512, v39, 0x7266744Eu);
  qword_140095548 = v40;
  if ( !v40 )
  {
    CalloutStack = -1073741670;
    if ( !NtfsStatusDebugFlags )
      goto LABEL_152;
    v12 = 1706269;
    goto LABEL_17;
  }
  memset(v40, 0, 8LL * (unsigned int)dword_14009553C);
  if ( (dword_1400956B8 & 0x200000) != 0 )
    v41 = 0;
  else
    v41 = NtfsFlushDiskCache;
  LfsInitializeLogFileService(v41);
  stru_140095618.List.Flink = 0;
  stru_140095618.WorkerRoutine = (PWORKER_THREAD_ROUTINE)NtfsCheckpointAllVolumes;
  stru_140095618.Parameter = &stru_140095618;
  KeInitializeTimer(&Timer);
  dword_1400955F8 = 0;
  KeInitializeDpc(&Dpc, NtfsVolumeCheckpointDpc, 0);
  dword_140095638 = 1;
  stru_140095680.List.Flink = 0;
  stru_140095680.WorkerRoutine = (PWORKER_THREAD_ROUTINE)NtfsCheckUsnTimeOut;
  stru_140095680.Parameter = &stru_140095680;
  qword_140095660 = ExAllocateTimer(NtfsUsnTimeOutDpc, 0, 8);
  if ( !qword_140095660 )
  {
    CalloutStack = -1073741670;
    if ( !NtfsStatusDebugFlags )
      goto LABEL_152;
    v12 = 1706381;
    goto LABEL_17;
  }
  LODWORD(v46) = 2621478;
  *((_QWORD *)&v46 + 1) = L"NtfsGlobalPostLimit";
  if ( (int)NtfsQueryValueKeyWithFallBack(
              (unsigned int)&v48,
              (unsigned int)&v49,
              (unsigned int)&v46,
              (unsigned int)&v45,
              (__int64)&DestinationString,
              (__int64)v44) < 0
    || (v42 = *(_DWORD *)(*(unsigned int *)(*(_QWORD *)&DestinationString.Length + 8LL)
                        + *(_QWORD *)&DestinationString.Length),
        v42 < 4) )
  {
    v42 = 4;
  }
  else if ( v42 > 200 )
  {
    v42 = 200;
  }
  KeInitializeSemaphore(&NtfsGlobalPostThrottle, v42, v42);
  Source1 = 0;
  dword_1400956C0 = 0;
  KeInitializeGuardedMutex(&NtfsScavengerLock);
  NtfsScavengerRunning = 0;
  qword_140095008 = (__int64)&NtfsScavengerWorkList;
  NtfsScavengerWorkList = (__int64)&NtfsScavengerWorkList;
  KeInitializeGuardedMutex(&NtfsRepairEventCounterMutex);
  NtfsRepairBlockedEventCount = 0;
  NtfsRepairTotalEventCount = 0;
  NtfsRepairThreadCount = 0;
  memset(&NtfsRepairStatistics, 0, 0x7Cu);
  memset(NtfsRepairBlockedEventVerbCount, 0, sizeof(NtfsRepairBlockedEventVerbCount));
  NtfsRepairEventCounters = -1;
  dword_140094C48 = -1;
  TxfGlobalInitialize();
  IoRegisterFileSystem(DeviceObject);
  if ( (dword_1400956B8 & 0x80u) != 0 )
    IoRegisterDriverReinitialization(FilterDriverObject, NtfsLoadAddOns, 0);
  qword_140095A98 = 196608;
  dword_140095AA0 = 4;
  NtfsDiskAccountingEnabled = PsIsDiskCountersEnabled();
  LOBYTE(v43) = 1;
  PoRegisterCoalescingCallback(NtfsCoalescingCallback, v43, &qword_140095640, 0);
  return 0;
}

```

## disassembly

```asm
0x1402d3458  mov     [rsp-8+arg_10], rbx
0x1402d345d  push    rbp
0x1402d345e  push    rsi
0x1402d345f  push    rdi
0x1402d3460  push    r12
0x1402d3462  push    r13
0x1402d3464  push    r14
0x1402d3466  push    r15
0x1402d3468  lea     rbp, [rsp-130h]
0x1402d3470  sub     rsp, 230h
0x1402d3477  mov     rax, cs:__security_cookie
0x1402d347e  xor     rax, rsp
0x1402d3481  mov     [rbp+160h+var_40], rax
0x1402d3488  xor     r12d, r12d
0x1402d348b  mov     [rbp+160h+FilterDriverObject], rcx
0x1402d348f  xorps   xmm0, xmm0
0x1402d3492  mov     [rbp+160h+var_1A0], r12
0x1402d3496  xorps   xmm1, xmm1
0x1402d3499  mov     [rsp+260h+var_220], r12b
0x1402d349e  mov     r13, rcx
0x1402d34a1  mov     [rbp+160h+CompressBufferWorkSpaceSize], r12d
0x1402d34a5  lea     rcx, OSVersionInfo; lpVersionInformation
0x1402d34ac  mov     [rbp+160h+CompressFragmentWorkSpaceSize], r12d
0x1402d34b0  movups  xmmword ptr [rbp+160h+DeviceName.Length], xmm0
0x1402d34b4  mov     r14, rdx
0x1402d34b7  mov     cs:OSVersionInfo.dwOSVersionInfoSize, 11Ch
0x1402d34c1  movups  xmmword ptr [rbp+160h+SymbolicLinkName.Length], xmm1
0x1402d34c5  movups  xmmword ptr [rsp+260h+var_1F0.Length], xmm0
0x1402d34ca  movups  [rbp+160h+var_1E0], xmm1
0x1402d34ce  movups  [rsp+260h+var_218], xmm0
0x1402d34d3  movups  xmmword ptr [rbp+160h+SourceString], xmm1
0x1402d34d7  call    cs:__imp_RtlGetVersion
0x1402d34de  nop     dword ptr [rax+rax+00h]
0x1402d34e3  xorps   xmm0, xmm0
0x1402d34e6  mov     eax, r12d
0x1402d34e9  movups  xmmword ptr [rsp+260h+DestinationString.Length], xmm0
0x1402d34ee  lock xadd cs:g_AssertsOperational, eax
0x1402d34f6  test    eax, eax
0x1402d34f8  jnz     short loc_1402D3525
0x1402d34fa  lea     rdx, aNtfsSys; "ntfs.sys"
0x1402d3501  lea     rcx, [rsp+260h+DestinationString]; DestinationString
0x1402d3506  call    cs:__imp_RtlInitAnsiString
0x1402d350d  nop     dword ptr [rax+rax+00h]
0x1402d3512  movaps  xmm0, xmmword ptr [rsp+260h+DestinationString.Length]
0x1402d3517  lea     rcx, [rbp+160h+Parameter]
0x1402d351b  movdqa  [rbp+160h+Parameter], xmm0
0x1402d3520  call    InitializeTelemetryAssertsKMWorkerInternal
0x1402d3525  call    Feature_SFS_CD_BugFixes_2410__private_IsEnabledDeviceUsageNoInline
0x1402d352a  mov     r15d, 1
0x1402d3530  test    eax, eax
0x1402d3532  jz      short loc_1402D3559
0x1402d3534  lea     rdx, Feature_SFS_CD_BugFixes_2410__private_descriptor
0x1402d353b  lea     rcx, Feature_SFS_CD_BugFixes_2410__private_featureState
0x1402d3542  call    wil_details_FeatureStateCache_GetCachedFeatureEnabledState
0x1402d3547  mov     r8d, r15d
0x1402d354a  lea     rcx, Feature_SFS_CD_BugFixes_2410__private_descriptor
0x1402d3551  mov     rdx, rax
0x1402d3554  call    wil_details_FeatureReporting_ReportUsageToService
0x1402d3559  call    Feature_SFS_CD_BugFixes_2511__private_IsEnabledDeviceUsageNoInline
0x1402d355e  test    eax, eax
0x1402d3560  jz      short loc_1402D3587
0x1402d3562  lea     rdx, Feature_SFS_CD_BugFixes_2511__private_descriptor
0x1402d3569  lea     rcx, Feature_SFS_CD_BugFixes_2511__private_featureState
0x1402d3570  call    wil_details_FeatureStateCache_GetCachedFeatureEnabledState
0x1402d3575  mov     r8d, r15d
0x1402d3578  lea     rcx, Feature_SFS_CD_BugFixes_2511__private_descriptor
0x1402d357f  mov     rdx, rax
0x1402d3582  call    wil_details_FeatureReporting_ReportUsageToService
0x1402d3587  mov     ecx, 0FFFFh; GroupNumber
0x1402d358c  call    cs:__imp_KeQueryActiveProcessorCountEx
0x1402d3593  nop     dword ptr [rax+rax+00h]
0x1402d3598  mov     cs:NtfsNumberProcessors, eax
0x1402d359e  mov     ecx, 2; CompressionFormatAndEngine
0x1402d35a3  mov     rax, 861C46800h
0x1402d35ad  lea     r8, [rbp+160h+CompressFragmentWorkSpaceSize]; CompressFragmentWorkSpaceSize
0x1402d35b1  lea     rdx, [rbp+160h+CompressBufferWorkSpaceSize]; CompressBufferWorkSpaceSize
0x1402d35b5  mov     cs:NtfsLastAccess, rax
0x1402d35bc  call    cs:__imp_RtlGetCompressionWorkSpaceSize
0x1402d35c3  nop     dword ptr [rax+rax+00h]
0x1402d35c8  xor     edx, edx; Val
0x1402d35ca  lea     rcx, NtfsData; void *
0x1402d35d1  mov     r8d, 968h; Size
0x1402d35d7  call    memset
0x1402d35dc  call    cs:__imp_FsRtlQueryMaximumVirtualDiskNestingLevel
0x1402d35e3  nop     dword ptr [rax+rax+00h]
0x1402d35e8  lea     rcx, stru_140095940; Mutex
0x1402d35ef  mov     cs:NtfsReserveStackStorage, r12
0x1402d35f6  mov     cs:NtfsMaxNestingLevel, eax
0x1402d35fc  mov     cs:NtfsReserveStackPnp, r12
0x1402d3603  mov     cs:NtfsReserveStackCleanup, r12
0x1402d360a  mov     cs:NtfsReserveStackLogFileFull, r12
0x1402d3611  mov     cs:NtfsReserveStackTxfFlush, r12
0x1402d3618  mov     cs:NtfsReserveStacksRead, r12
0x1402d361f  mov     cs:NtfsReserveStacksWrite, r12
0x1402d3626  mov     cs:NtfsReserveStacksFlush, r12
0x1402d362d  call    cs:__imp_KeInitializeGuardedMutex
0x1402d3634  nop     dword ptr [rax+rax+00h]
0x1402d3639  mov     edx, 120h
0x1402d363e  lea     rcx, qword_1400958B8
0x1402d3645  call    NtfsInitializeReservedHeader
0x1402d364a  mov     edx, 98h
0x1402d364f  lea     rcx, qword_1400959D8
0x1402d3656  call    NtfsInitializeReservedHeader
0x1402d365b  movups  xmm0, xmmword ptr cs:aFh; "fh"
0x1402d3662  lea     rax, [rbp+160h+var_E0]
0x1402d3669  mov     [rsp+260h+var_21C], 9Ch
0x1402d3671  mov     qword ptr [rsp+260h+DestinationString.Length], rax
0x1402d3676  movdqu  xmmword ptr [rbp+160h+SourceString], xmm0
0x1402d367b  call    NtfsInitializeCompatibilityModeKeyPath
0x1402d3680  lea     rdx, NtfsCompatibilityModeKeyPath; SourceString
0x1402d3687  lea     rcx, [rsp+260h+var_1F0]; DestinationString
0x1402d368c  call    cs:__imp_RtlInitUnicodeString
0x1402d3693  nop     dword ptr [rax+rax+00h]
0x1402d3698  movups  xmm0, xmmword ptr cs:aZ; "z|"
0x1402d369f  lea     rax, aNtfsforcenonpa; "NtfsForceNonPagedPoolAllocation"
0x1402d36a6  mov     cs:PoolType, r15d
0x1402d36ad  mov     qword ptr [rsp+260h+var_218+8], rax
0x1402d36b2  lea     r9, [rsp+260h+DestinationString]
0x1402d36b7  lea     rax, [rsp+260h+var_220]
0x1402d36bc  mov     cs:dword_140095AE4, 5
0x1402d36c6  lea     r8, [rsp+260h+var_21C]
0x1402d36cb  mov     [rsp+260h+Context], rax
0x1402d36d0  lea     rdx, [rsp+260h+var_218]
0x1402d36d5  mov     dword ptr [rsp+260h+var_218], 40003Eh
0x1402d36dd  lea     rcx, [rbp+160h+SourceString]
0x1402d36e1  movdqu  [rbp+160h+var_1E0], xmm0
0x1402d36e6  call    NtfsQueryValueKey
0x1402d36eb  test    eax, eax
0x1402d36ed  jns     short loc_1402D371F
0x1402d36ef  lea     rax, [rsp+260h+var_220]
0x1402d36f4  mov     qword ptr [rsp+260h+Exclusive], rax
0x1402d36f9  lea     r9, [rsp+260h+var_21C]
0x1402d36fe  lea     rax, [rsp+260h+DestinationString]
0x1402d3703  lea     r8, [rsp+260h+var_218]
0x1402d3708  mov     [rsp+260h+Context], rax
0x1402d370d  lea     rdx, [rbp+160h+var_1E0]
0x1402d3711  lea     rcx, [rsp+260h+var_1F0]
0x1402d3716  call    NtfsQueryValueKeyWithFallBack
0x1402d371b  test    eax, eax
0x1402d371d  js      short loc_1402D3756
0x1402d371f  mov     rsi, qword ptr [rsp+260h+DestinationString.Length]
0x1402d3724  mov     eax, [rsi+8]
0x1402d3727  cmp     [rax+rsi], r15d
0x1402d372b  jnz     short loc_1402D375B
0x1402d372d  lea     rcx, NtfsCommonCreate; AddressWithinSection
0x1402d3734  mov     cs:PoolType, 200h
0x1402d373e  mov     cs:dword_140095AE4, 204h
0x1402d3748  call    cs:__imp_MmLockPagableDataSection
0x1402d374f  nop     dword ptr [rax+rax+00h]
0x1402d3754  jmp     short loc_1402D375B
0x1402d3756  mov     rsi, qword ptr [rsp+260h+DestinationString.Length]
0x1402d375b  call    wil_InitializeFeatureStaging
0x1402d3760  lea     rcx, [rbp+160h+Parameter]
0x1402d3764  mov     qword ptr [rbp+160h+Parameter], r12
0x1402d3768  call    cs:__imp_TmCurrentTransaction
0x1402d376f  nop     dword ptr [rax+rax+00h]
0x1402d3774  mov     ebx, 1000h
0x1402d3779  mov     edi, 1000000h
0x1402d377e  cmp     eax, 0C00000BBh
0x1402d3783  mov     r8d, 4A66744Eh; Tag
0x1402d3789  mov     edx, ebx; NumberOfBytes
0x1402d378b  mov     ecx, 200h; PoolType
0x1402d3790  cmovnz  edi, r12d
0x1402d3794  call    cs:__imp_ExAllocatePoolWithTag
0x1402d379b  nop     dword ptr [rax+rax+00h]
0x1402d37a0  mov     cs:VirtualAddress, rax
0x1402d37a7  test    rax, rax
0x1402d37aa  jnz     short loc_1402D37D3
0x1402d37ac  mov     al, cs:NtfsStatusDebugFlags
0x1402d37b2  mov     ebx, 0C000009Ah
0x1402d37b7  test    al, al
0x1402d37b9  jz      loc_1402D491D
0x1402d37bf  mov     r8d, 1A039Bh
0x1402d37c5  mov     edx, ebx
0x1402d37c7  xor     ecx, ecx
0x1402d37c9  call    NtfsStatusTraceAndDebugInternal
0x1402d37ce  jmp     loc_1402D491D
0x1402d37d3  mov     r8, rbx; Size
0x1402d37d6  xor     edx, edx; Val
0x1402d37d8  mov     rcx, rax; void *
0x1402d37db  call    memset
0x1402d37e0  mov     edx, 10000h
0x1402d37e5  lea     rcx, qword_140095A58
0x1402d37ec  call    NtfsInitializeReservedBuffer
0x1402d37f1  mov     ebx, eax
0x1402d37f3  test    eax, eax
0x1402d37f5  js      loc_1402D491D
0x1402d37fb  mov     edx, 10000h
0x1402d3800  lea     rcx, qword_140095978
0x1402d3807  call    NtfsInitializeReservedBuffer
0x1402d380c  mov     ebx, eax
0x1402d380e  test    eax, eax
0x1402d3810  js      loc_1402D491D
0x1402d3816  mov     edx, 11000h
0x1402d381b  lea     rcx, qword_140095990
0x1402d3822  call    NtfsInitializeReservedBuffer
0x1402d3827  mov     ebx, eax
0x1402d3829  test    eax, eax
0x1402d382b  js      loc_1402D491D
0x1402d3831  mov     edx, [rbp+160h+CompressFragmentWorkSpaceSize]
0x1402d3834  lea     rcx, qword_1400959A8
0x1402d383b  call    NtfsInitializeReservedBuffer
0x1402d3840  mov     ebx, eax
0x1402d3842  test    eax, eax
0x1402d3844  js      loc_1402D491D
0x1402d384a  mov     edx, 10000h
0x1402d384f  lea     rcx, qword_1400959C0
0x1402d3856  call    NtfsInitializeReservedBuffer
0x1402d385b  mov     ebx, eax
0x1402d385d  test    eax, eax
0x1402d385f  js      loc_1402D491D
0x1402d3865  lea     r9, NtfsReserveStackStorage
0x1402d386c  xor     r8d, r8d
0x1402d386f  mov     dl, 4
0x1402d3871  xor     ecx, ecx
0x1402d3873  call    cs:__imp_KeAllocateCalloutStackEx
0x1402d387a  nop     dword ptr [rax+rax+00h]
0x1402d387f  mov     ebx, eax
0x1402d3881  test    eax, eax
0x1402d3883  js      loc_1402D491D
0x1402d3889  lea     r9, NtfsReserveStackPnp
0x1402d3890  xor     r8d, r8d
0x1402d3893  mov     dl, r15b
0x1402d3896  xor     ecx, ecx
0x1402d3898  call    cs:__imp_KeAllocateCalloutStackEx
0x1402d389f  nop     dword ptr [rax+rax+00h]
0x1402d38a4  mov     ebx, eax
0x1402d38a6  test    eax, eax
0x1402d38a8  js      loc_1402D491D
0x1402d38ae  lea     r9, NtfsReserveStackCleanup
0x1402d38b5  xor     r8d, r8d
0x1402d38b8  mov     dl, r15b
0x1402d38bb  xor     ecx, ecx
0x1402d38bd  call    cs:__imp_KeAllocateCalloutStackEx
0x1402d38c4  nop     dword ptr [rax+rax+00h]
0x1402d38c9  mov     ebx, eax
0x1402d38cb  test    eax, eax
0x1402d38cd  js      loc_1402D491D
0x1402d38d3  lea     r9, NtfsReserveStackLogFileFull
0x1402d38da  xor     r8d, r8d
0x1402d38dd  mov     dl, r15b
0x1402d38e0  xor     ecx, ecx
0x1402d38e2  call    cs:__imp_KeAllocateCalloutStackEx
0x1402d38e9  nop     dword ptr [rax+rax+00h]
0x1402d38ee  mov     ebx, eax
0x1402d38f0  test    eax, eax
0x1402d38f2  js      loc_1402D491D
0x1402d38f8  lea     r9, NtfsReserveStackTxfFlush
0x1402d38ff  xor     r8d, r8d
0x1402d3902  mov     dl, r15b
0x1402d3905  xor     ecx, ecx
0x1402d3907  call    cs:__imp_KeAllocateCalloutStackEx
0x1402d390e  nop     dword ptr [rax+rax+00h]
0x1402d3913  mov     ebx, eax
0x1402d3915  test    eax, eax
0x1402d3917  js      loc_1402D491D
0x1402d391d  mov     ebx, 0Ah
0x1402d3922  mov     dl, 2
0x1402d3924  mov     ecx, ebx
0x1402d3926  call    NtfsAllocateReservedStacks
0x1402d392b  mov     cs:NtfsReserveStacksRead, rax
0x1402d3932  test    rax, rax
0x1402d3935  jnz     short loc_1402D3955
0x1402d3937  mov     al, cs:NtfsStatusDebugFlags
0x1402d393d  mov     ebx, 0C000009Ah
0x1402d3942  test    al, al
0x1402d3944  jz      loc_1402D491D
0x1402d394a  mov     r8d, 1A041Eh
0x1402d3950  jmp     loc_1402D37C5
0x1402d3955  mov     dl, 2
0x1402d3957  mov     ecx, ebx
0x1402d3959  call    NtfsAllocateReservedStacks
0x1402d395e  mov     cs:NtfsReserveStacksWrite, rax
0x1402d3965  test    rax, rax
0x1402d3968  jnz     short loc_1402D3988
0x1402d396a  mov     al, cs:NtfsStatusDebugFlags
0x1402d3970  mov     ebx, 0C000009Ah
0x1402d3975  test    al, al
0x1402d3977  jz      loc_1402D491D
0x1402d397d  mov     r8d, 1A0424h
0x1402d3983  jmp     loc_1402D37C5
0x1402d3988  mov     dl, r15b
0x1402d398b  mov     ecx, r15d
0x1402d398e  call    NtfsAllocateReservedStacks
0x1402d3993  mov     cs:NtfsReserveStacksFlush, rax
0x1402d399a  test    rax, rax
0x1402d399d  jnz     short loc_1402D39BD
0x1402d399f  mov     al, cs:NtfsStatusDebugFlags
0x1402d39a5  mov     ebx, 0C000009Ah
0x1402d39aa  test    al, al
0x1402d39ac  jz      loc_1402D491D
0x1402d39b2  mov     r8d, 1A042Ah
0x1402d39b8  jmp     loc_1402D37C5
0x1402d39bd  mov     rax, [rbp+168h]
0x1402d39c4  lea     rdx, [rbp+160h+Parameter]; Parameter
0x1402d39c8  xor     r9d, r9d; Wait
0x1402d39cb  mov     qword ptr [rbp+160h+Parameter], rax
0x1402d39cf  mov     r8d, 6000h; Size
0x1402d39d5  mov     qword ptr [rbp+160h+Parameter+8], r12
0x1402d39d9  lea     rcx, NtfsMeasureExpandedStackCalloutDepthCallout; Callout
  ... truncated ...
```
