# DpiInitializeGlobalState

- ea: `0x1404129c0`
- end: `0x140413b41`
- name: `DpiInitializeGlobalState`
- size: `4481`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140412008`

## callees

- `0x14002e110`
- `0x14005c75c`
- `0x140086f38`
- `0x1400a0100`
- `0x1400a01e0`
- `0x1400a0540`
- `0x140247230`
- `0x1402b78bc`
- `0x1402b910c`
- `0x14030860c`
- `0x1404129c0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14041345c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140413abb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140413af4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14041345c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140413abb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140413af4`
- `ntoskrnl!IoFreeWorkItem` at `0x140413a89`
- `ntoskrnl!IoFreeWorkItem` at `0x140413a89`
- `ntoskrnl!ExAllocatePool2` at `0x140413478`
- `ntoskrnl!ExAllocatePool2` at `0x140413546`
- `ntoskrnl!ExAllocatePool2` at `0x140413478`
- `ntoskrnl!ExAllocatePool2` at `0x140413546`
- `ntoskrnl!KeInitializeSpinLock` at `0x1404136f6`
- `ntoskrnl!KeInitializeSpinLock` at `0x1404136f6`
- `ntoskrnl!KeInitializeEvent` at `0x1404134f4`
- `ntoskrnl!KeInitializeEvent` at `0x14041384f`
- `ntoskrnl!KeInitializeEvent` at `0x140413867`
- `ntoskrnl!KeInitializeEvent` at `0x1404134f4`
- `ntoskrnl!KeInitializeEvent` at `0x14041384f`
- `ntoskrnl!KeInitializeEvent` at `0x140413867`
- `ntoskrnl!KeInitializeDpc` at `0x1404135dc`
- `ntoskrnl!KeInitializeDpc` at `0x1404135dc`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140412cad`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140412e21`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140412fb1`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140413128`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140412cad`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140412e21`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140412fb1`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140413128`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140413b0f`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140413b0f`
- `ntoskrnl!ZwClose` at `0x1404131e7`
- `ntoskrnl!ZwClose` at `0x14041330f`
- `ntoskrnl!ZwClose` at `0x140413395`
- `ntoskrnl!ZwClose` at `0x1404131e7`
- `ntoskrnl!ZwClose` at `0x14041330f`
- `ntoskrnl!ZwClose` at `0x140413395`
- `ntoskrnl!RtlInitUnicodeString` at `0x140413168`
- `ntoskrnl!RtlInitUnicodeString` at `0x140413227`
- `ntoskrnl!RtlInitUnicodeString` at `0x1404132c9`
- `ntoskrnl!RtlInitUnicodeString` at `0x140413353`
- `ntoskrnl!RtlInitUnicodeString` at `0x140413168`
- `ntoskrnl!RtlInitUnicodeString` at `0x140413227`
- `ntoskrnl!RtlInitUnicodeString` at `0x1404132c9`
- `ntoskrnl!RtlInitUnicodeString` at `0x140413353`
- `ntoskrnl!ZwOpenKey` at `0x14041327b`
- `ntoskrnl!ZwOpenKey` at `0x14041327b`
- `ntoskrnl!KeInitializeTimerEx` at `0x1404135bf`
- `ntoskrnl!KeInitializeTimerEx` at `0x1404135bf`
- `ntoskrnl!ZwQueryLicenseValue` at `0x140412a72`
- `ntoskrnl!ZwQueryLicenseValue` at `0x140412ae8`
- `ntoskrnl!ZwQueryLicenseValue` at `0x140412a72`
- `ntoskrnl!ZwQueryLicenseValue` at `0x140412ae8`
- `ntoskrnl!IoAllocateWorkItem` at `0x1404135ef`
- `ntoskrnl!IoAllocateWorkItem` at `0x1404135ef`
- `ntoskrnl!ZwCreateKey` at `0x1404131d2`
- `ntoskrnl!ZwCreateKey` at `0x1404131d2`
- `ntoskrnl!ZwSetValueKey` at `0x1404132f7`
- `ntoskrnl!ZwSetValueKey` at `0x140413381`
- `ntoskrnl!ZwSetValueKey` at `0x1404132f7`
- `ntoskrnl!ZwSetValueKey` at `0x140413381`
- `ntoskrnl!KeInitializeMutex` at `0x1404134bf`
- `ntoskrnl!KeInitializeMutex` at `0x14041358d`
- `ntoskrnl!KeInitializeMutex` at `0x140413672`
- `ntoskrnl!KeInitializeMutex` at `0x140413883`
- `ntoskrnl!KeInitializeMutex` at `0x1404139d7`
- `ntoskrnl!KeInitializeMutex` at `0x1404134bf`
- `ntoskrnl!KeInitializeMutex` at `0x14041358d`
- `ntoskrnl!KeInitializeMutex` at `0x140413672`
- `ntoskrnl!KeInitializeMutex` at `0x140413883`
- `ntoskrnl!KeInitializeMutex` at `0x1404139d7`
- `ntoskrnl!RtlCheckRegistryKey` at `0x140412b25`
- `ntoskrnl!RtlCheckRegistryKey` at `0x140412b25`
- `ntoskrnl!ExIsSoftBoot` at `0x140412b60`
- `ntoskrnl!ExIsSoftBoot` at `0x140412b60`
- `ntoskrnl!MmGetPhysicalMemoryRanges` at `0x1404133d4`
- `ntoskrnl!MmGetPhysicalMemoryRanges` at `0x1404133d4`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14041352c`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140413656`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14041352c`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140413656`
- `ntoskrnl!HalDispatchTable` at `0x1404136a5`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x140413764`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x140413764`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140413aa1`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140413ada`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140413aa1`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140413ada`
- `watchdog!WdLogSingleEntry0` at `0x140413975`
- `watchdog!WdLogSingleEntry0` at `0x140413975`
- `watchdog!DMgrIsSetupRunning` at `0x140412b42`
- `watchdog!DMgrIsSetupRunning` at `0x140412b42`
- `watchdog!WdLogSingleEntry1` at `0x140412a8c`
- `watchdog!WdLogSingleEntry1` at `0x140412afe`
- `watchdog!WdLogSingleEntry1` at `0x140412e5d`
- `watchdog!WdLogSingleEntry1` at `0x140413202`
- `watchdog!WdLogSingleEntry1` at `0x140413294`
- `watchdog!WdLogSingleEntry1` at `0x140413321`
- `watchdog!WdLogSingleEntry1` at `0x1404133ab`
- `watchdog!WdLogSingleEntry1` at `0x1404133f5`
- `watchdog!WdLogSingleEntry1` at `0x14041349f`
- `watchdog!WdLogSingleEntry1` at `0x14041356d`
- `watchdog!WdLogSingleEntry1` at `0x140413616`
- `watchdog!WdLogSingleEntry1` at `0x14041377d`
- `watchdog!WdLogSingleEntry1` at `0x1404137e8`
- `watchdog!WdLogSingleEntry1` at `0x1404139aa`
- `watchdog!WdLogSingleEntry1` at `0x140413a64`
- `watchdog!WdLogSingleEntry1` at `0x140412a8c`
- `watchdog!WdLogSingleEntry1` at `0x140412afe`
- `watchdog!WdLogSingleEntry1` at `0x140412e5d`
- `watchdog!WdLogSingleEntry1` at `0x140413202`
- `watchdog!WdLogSingleEntry1` at `0x140413294`
- `watchdog!WdLogSingleEntry1` at `0x140413321`
- `watchdog!WdLogSingleEntry1` at `0x1404133ab`
- `watchdog!WdLogSingleEntry1` at `0x1404133f5`
- `watchdog!WdLogSingleEntry1` at `0x14041349f`
- `watchdog!WdLogSingleEntry1` at `0x14041356d`
- `watchdog!WdLogSingleEntry1` at `0x140413616`
- `watchdog!WdLogSingleEntry1` at `0x14041377d`
- `watchdog!WdLogSingleEntry1` at `0x1404137e8`
- `watchdog!WdLogSingleEntry1` at `0x1404139aa`
- `watchdog!WdLogSingleEntry1` at `0x140413a64`

## string_xrefs

- `0x140413218`: `\Registry\Machine\System\CurrentControlSet\Control\GraphicsDrivers`
- `0x14041379f`: `\Registry\Machine\System\CurrentControlSet\Control\GraphicsDrivers`
- `0x140413159`: `\Registry\Machine\System\CurrentControlSet\Control\Video\`

## pseudocode

```c
__int64 DpiInitializeGlobalState()
{
  char v0; // si
  int v1; // eax
  int v2; // eax
  int v3; // eax
  NTSTATUS v4; // eax
  NTSTATUS v5; // ebx
  char v6; // di
  PPHYSICAL_MEMORY_RANGE PhysicalMemoryRanges; // rax
  int v8; // r9d
  PHYSICAL_ADDRESS BaseAddress; // rcx
  struct _KMUTANT *Pool2; // rax
  struct _KMUTANT *v11; // rax
  __int64 v12; // rax
  DISPLAY_MUX_MGR *v13; // rbx
  int NtObjectType; // eax
  int v16; // [rsp+50h] [rbp-1E8h] BYREF
  int v17; // [rsp+54h] [rbp-1E4h] BYREF
  unsigned int v18; // [rsp+58h] [rbp-1E0h] BYREF
  void *KeyHandle; // [rsp+60h] [rbp-1D8h] BYREF
  int v20; // [rsp+68h] [rbp-1D0h] BYREF
  int v21; // [rsp+6Ch] [rbp-1CCh] BYREF
  int Data; // [rsp+70h] [rbp-1C8h] BYREF
  int v23; // [rsp+74h] [rbp-1C4h] BYREF
  int v24; // [rsp+78h] [rbp-1C0h] BYREF
  UNICODE_STRING SourceString; // [rsp+80h] [rbp-1B8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-1A8h] BYREF
  int v27; // [rsp+A0h] [rbp-198h] BYREF
  _QWORD v28[2]; // [rsp+A8h] [rbp-190h] BYREF
  _QWORD v29[2]; // [rsp+B8h] [rbp-180h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C8h] [rbp-170h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+F8h] [rbp-140h] BYREF
  __int64 v32; // [rsp+110h] [rbp-128h] BYREF
  int v33; // [rsp+118h] [rbp-120h]
  const wchar_t *v34; // [rsp+120h] [rbp-118h]
  int *v35; // [rsp+128h] [rbp-110h]
  int v36; // [rsp+130h] [rbp-108h]
  int *v37; // [rsp+138h] [rbp-100h]
  int v38; // [rsp+140h] [rbp-F8h]
  __int64 v39; // [rsp+148h] [rbp-F0h]
  int v40; // [rsp+150h] [rbp-E8h]
  const wchar_t *v41; // [rsp+158h] [rbp-E0h]
  int *v42; // [rsp+160h] [rbp-D8h]
  int v43; // [rsp+168h] [rbp-D0h]
  int *v44; // [rsp+170h] [rbp-C8h]
  int v45; // [rsp+178h] [rbp-C0h]
  __int64 v46; // [rsp+180h] [rbp-B8h]
  int v47; // [rsp+188h] [rbp-B0h]
  const wchar_t *v48; // [rsp+190h] [rbp-A8h]
  int *v49; // [rsp+198h] [rbp-A0h]
  int v50; // [rsp+1A0h] [rbp-98h]
  int *v51; // [rsp+1A8h] [rbp-90h]
  int v52; // [rsp+1B0h] [rbp-88h]
  __int64 v53; // [rsp+1B8h] [rbp-80h]
  int v54; // [rsp+1C0h] [rbp-78h]
  __int64 v55; // [rsp+1C8h] [rbp-70h]
  __int128 v56; // [rsp+1D0h] [rbp-68h]
  __int128 v57; // [rsp+1E0h] [rbp-58h]

  v28[0] = 3932218;
  KeyHandle = 0;
  Data = 0;
  v23 = 0;
  v28[1] = L"Kernel-OneCore-DeviceFamilyID";
  v21 = 0;
  v20 = 0;
  v0 = 0;
  UnicodeString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  if ( (int)ZwQueryLicenseValue(v28, &v21, &dword_14015F440, 4, &v20) < 0 )
  {
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 4103;
    dword_14015F440 = 3;
  }
  v29[0] = 2490404;
  v29[1] = L"Kernel-ProductInfo";
  if ( (int)ZwQueryLicenseValue(v29, &v21, &dword_14015F444, 4, &v20) < 0 )
  {
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 4119;
    dword_14015F444 = 0;
  }
  if ( RtlCheckRegistryKey(2u, (PWSTR)L"GraphicsDrivers\\DisableUSWC") >= 0 )
    byte_14015EDD0 = 1;
  g_bDMgrIsSetupRunning = DMgrIsSetupRunning();
  if ( g_bDMgrIsSetupRunning == 1 )
    byte_14015EDD1 = 1;
  if ( (unsigned __int8)ExIsSoftBoot() )
    DpiKsrRestore();
  dword_14015F2A4 = 7236;
  v16 = 0;
  v17 = 500000;
  v32 = 0;
  v34 = L"MiracastDefaultRtspPort";
  v33 = 288;
  v35 = &dword_14015F2A4;
  v37 = &dword_14015F2A4;
  v36 = 67108868;
  v41 = L"PlatformSupportMiracast";
  v38 = 4;
  v42 = &v16;
  v44 = &v16;
  v48 = L"SuspendAdapterTimerPeriod";
  v49 = &v17;
  v51 = &v17;
  v39 = 0;
  v40 = 288;
  v43 = 67108868;
  v45 = 4;
  v46 = 0;
  v47 = 288;
  v50 = 67108868;
  v52 = 4;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  v1 = RtlQueryRegistryValuesEx(2, L"GraphicsDrivers", &v32, 0, 0);
  if ( (v1 < 0 || !dword_14015F2A4) && (dword_14015F2A4 = 7236, v1 < 0) || (byte_14015EDD7 = 1, !v16) )
    byte_14015EDD7 = 0;
  v2 = -v17;
  v17 = 0;
  DueTime.QuadPart = v2;
  v16 = 0;
  v34 = L"SupportMultipleIntegratedDisplays";
  v18 = 0;
  v35 = &v17;
  v32 = 0;
  v37 = &v17;
  v41 = L"ForceBddFallbackOnly";
  v42 = &v16;
  v44 = &v16;
  v48 = L"DisableBgfxRelay";
  v49 = (int *)&v18;
  v51 = (int *)&v18;
  v33 = 288;
  v36 = 67108868;
  v38 = 4;
  v39 = 0;
  v40 = 288;
  v43 = 67108868;
  v45 = 4;
  v46 = 0;
  v47 = 288;
  v50 = 67108868;
  v52 = 4;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  if ( (int)RtlQueryRegistryValuesEx(2, L"GraphicsDrivers", &v32, 0, 0) < 0 )
  {
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 4239;
    byte_14015EDD9 = 0;
    byte_14015F450 = 0;
    byte_14015EDD4 = 0;
  }
  else
  {
    byte_14015EDD9 = v17 != 0;
    byte_14015F450 = v16 != 0;
    byte_14015EDD4 = v18 != 0;
  }
  v18 = 0;
  v16 = 1;
  v34 = L"HwSchMode";
  v17 = 0;
  v35 = (int *)&v18;
  v32 = 0;
  v37 = (int *)&v18;
  v33 = 288;
  v41 = L"HwSchOverrideBlockList";
  v36 = 67108868;
  v42 = &v16;
  v44 = &v16;
  v48 = L"HwSchTreatExperimentalAsStable";
  v49 = &v17;
  v51 = &v17;
  v38 = 4;
  v39 = 0;
  v40 = 288;
  v43 = 67108868;
  v45 = 4;
  v46 = 0;
  v47 = 288;
  v50 = 67108868;
  v52 = 4;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  v3 = RtlQueryRegistryValuesEx(2, L"GraphicsDrivers", &v32, 0, 0);
  if ( v3 >= 0 && v18 < 3 )
  {
    dword_14015EDF8 = v18;
    goto LABEL_23;
  }
  dword_14015EDF8 = 0;
  if ( v3 >= 0 )
  {
LABEL_23:
    byte_14015EDFC = 0;
    byte_14015EDFD = v17 != 0;
    if ( !v16 )
      goto LABEL_25;
  }
  byte_14015EDFC = 1;
LABEL_25:
  v16 = 0;
  v18 = -1;
  v17 = -1;
  v32 = 0;
  v33 = 288;
  v34 = L"EnableBasicDisplayFallback";
  v36 = 67108868;
  v35 = (int *)&v18;
  v38 = 4;
  v37 = (int *)&v18;
  v41 = L"DisableBasicDisplayFallback";
  v42 = &v17;
  v44 = &v17;
  v48 = L"ForcePreserveBootDisplay";
  v49 = &v16;
  v51 = &v16;
  v39 = 0;
  v40 = 288;
  v43 = 67108868;
  v45 = 4;
  v46 = 0;
  v47 = 288;
  v50 = 67108868;
  v52 = 4;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  if ( (int)RtlQueryRegistryValuesEx(2, L"GraphicsDrivers\\BasicDisplay", &v32, 0, 0) >= 0 )
  {
    if ( v18 != 1 && v17 == 1 )
      byte_14015EDD2 = 1;
    byte_14015EDD3 = v16 == 1;
  }
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Video\\");
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v4 = ZwCreateKey(&KeyHandle, 0xCu, &ObjectAttributes, 0, 0, 0, 0);
  if ( v4 < 0 )
  {
    if ( v4 != -1073741771 )
    {
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 4359;
    }
  }
  else
  {
    ZwClose(KeyHandle);
  }
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\GraphicsDrivers");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v5 = ZwOpenKey(&KeyHandle, 0x40000000u, &ObjectAttributes);
  if ( v5 < 0 )
  {
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 4384;
LABEL_36:
    v6 = 0;
LABEL_74:
    if ( qword_14015F050 )
      IoFreeWorkItem(qword_14015F050);
    if ( v6 == 1 )
      ExDeleteNPagedLookasideList(&stru_14015EEC0);
    if ( qword_14015F070 )
    {
      ExFreePoolWithTag(qword_14015F070, 0);
      qword_14015F070 = 0;
    }
    if ( v0 == 1 )
      ExDeleteNPagedLookasideList(&Lookaside);
    if ( Mutex )
    {
      ExFreePoolWithTag(Mutex, 0);
      Mutex = 0;
    }
    goto LABEL_84;
  }
  Data = 69640;
  RtlInitUnicodeString(&DestinationString, L"DxgKrnlVersion");
  v5 = ZwSetValueKey(KeyHandle, &DestinationString, 0, 4u, &Data, 4u);
  if ( v5 < 0 )
  {
    ZwClose(KeyHandle);
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 4406;
    goto LABEL_36;
  }
  v23 = 20499;
  RtlInitUnicodeString(&DestinationString, L"MinDxgKrnlVersion");
  v5 = ZwSetValueKey(KeyHandle, &DestinationString, 0, 4u, &v23, 4u);
  ZwClose(KeyHandle);
  if ( v5 < 0 )
  {
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 4428;
    goto LABEL_36;
  }
  v6 = 0;
  DpGlobals = 0;
  PhysicalMemoryRanges = MmGetPhysicalMemoryRanges();
  if ( !PhysicalMemoryRanges )
  {
    v5 = -1073741670;
    WdLogSingleEntry1(6);
    WdLogGlobalForLineNumber = 4452;
    goto LABEL_74;
  }
  v8 = 0;
  if ( PhysicalMemoryRanges->NumberOfBytes.QuadPart )
  {
    do
    {
      DpGlobals += PhysicalMemoryRanges[v8].NumberOfBytes.QuadPart;
      BaseAddress = PhysicalMemoryRanges[v8].BaseAddress;
      if ( BaseAddress.QuadPart + PhysicalMemoryRanges[v8].NumberOfBytes.QuadPart > *(&DpGlobals + 1) )
        *(&DpGlobals + 1) = BaseAddress.QuadPart + PhysicalMemoryRanges[v8].NumberOfBytes.QuadPart;
      ++v8;
    }
    while ( PhysicalMemoryRanges[v8].NumberOfBytes.QuadPart );
  }
  ExFreePoolWithTag(PhysicalMemoryRanges, 0);
  Pool2 = (struct _KMUTANT *)ExAllocatePool2(64, 56, 1953656900);
  Mutex = Pool2;
  if ( !Pool2 )
  {
    v5 = -1073741801;
    WdLogSingleEntry1(6);
    WdLogGlobalForLineNumber = 4496;
    goto LABEL_74;
  }
  KeInitializeMutex(Pool2, 0);
  word_14015EE20 = 0;
  qword_14015EE10 = (__int64)&qword_14015EE08;
  qword_14015EE08 = (__int64)&qword_14015EE08;
  KeInitializeEvent(&stru_14015EE28, NotificationEvent, 0);
  byte_14015EE22 = 0;
  ExInitializeNPagedLookasideList(&Lookaside, 0, 0, 0x200u, 0x58u, 0x74727044u, 0);
  v0 = 1;
  v11 = (struct _KMUTANT *)ExAllocatePool2(64, 56, 1953656900);
  qword_14015F070 = v11;
  if ( !v11 )
  {
    v5 = -1073741801;
    WdLogSingleEntry1(6);
    WdLogGlobalForLineNumber = 4542;
    goto LABEL_74;
  }
  KeInitializeMutex(v11, 0);
  dword_14015F058 = 0;
  qword_14015F068 = (__int64)&qword_14015F060;
  qword_14015F060 = (__int64)&qword_14015F060;
  KeInitializeTimerEx(&stru_14015EFD0, SynchronizationTimer);
  KeInitializeDpc(&stru_14015F010, DpiPdoPollingDpc, 0);
  qword_14015F050 = IoAllocateWorkItem(g_pDriverObject);
  if ( !qword_14015F050 )
  {
    v5 = -1073741801;
    WdLogSingleEntry1(6);
    WdLogGlobalForLineNumber = 4560;
    goto LABEL_74;
  }
  ExInitializeNPagedLookasideList(&stru_14015EEC0, 0, 0, 0x200u, 0x30u, 0x74727044u, 0);
  byte_14015F220 = 0;
  KeInitializeMutex(&stru_14015F228, 0);
  v24 = 2;
  qword_14015F268 = (__int64)&qword_14015F260;
  qword_14015F260 = (__int64)&qword_14015F260;
  v27 = 4;
  if ( ((int (__fastcall *)(__int64, __int64, int *, int *))HalDispatchTable->HalQuerySystemInformation)(
         9,
         4,
         &v24,
         &v27) < 0
    || (byte_14015EDD6 = 1, v24 == 2) )
  {
    byte_14015EDD6 = 0;
  }
  byte_14015EDD5 = 0;
  dword_14015F1D4 = -1;
  KeInitializeSpinLock(&SpinLock);
  qword_14015F288 = (__int64)&qword_14015F280;
  qword_14015F280 = (__int64)&qword_14015F280;
  dword_14015F2A0 = 0;
  qword_14015F298 = (__int64)&qword_14015F290;
  qword_14015F290 = (__int64)&qword_14015F290;
  v5 = IoRegisterPlugPlayNotification(
         EventCategoryDeviceInterfaceChange,
         1u,
         &GUID_DEVINTERFACE_UMDF_MIRACAST_DIVICE_ARRIVAL,
         (PDRIVER_OBJECT)g_pDriverObject,
         DpiMiracastInterfaceChange,
         0,
         &qword_14015F270);
  if ( v5 < 0 )
  {
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 4635;
    qword_14015F270 = 0;
LABEL_73:
    v6 = 1;
    goto LABEL_74;
  }
  *(_QWORD *)&SourceString.Length = 8781956;
  SourceString.Buffer = (wchar_t *)L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\GraphicsDrivers";
  v5 = DxgkCreateFeatureDatabase(&SourceString, 0, 1, 0, &qword_14015F458);
  if ( v5 < 0 )
  {
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 4650;
    goto LABEL_73;
  }
  IoWorkItem = 0;
  qword_14015EFA8 = (__int64)&qword_14015EFA0;
  qword_14015EFA0 = (__int64)&qword_14015EFA0;
  dword_14015EFB0 = 0;
  qword_14015EF98 = 0;
  dword_14015EF60 = 1;
  qword_14015EF68 = 0;
  dword_14015EF70 = 0;
  KeInitializeEvent(&stru_14015EF78, SynchronizationEvent, 0);
  KeInitializeEvent(&Event, NotificationEvent, 1u);
  byte_14015F398 = 0;
  KeInitializeMutex(&stru_14015F3A0, 0);
  qword_14015F3E0 = (__int64)&qword_14015F3D8;
  qword_14015F3D8 = &qword_14015F3D8;
  DpiIndirectDisplayInitialStartTracker();
  byte_14015EDDC = 0;
  qword_14015F368 = 1;
  dword_14015F21C = 0;
  v12 = operator new(360, 1265072196, 256);
  v13 = (DISPLAY_MUX_MGR *)v12;
  if ( v12 )
  {
    *(_BYTE *)v12 = 0;
    *(_DWORD *)(v12 + 4) = 1;
    *(_BYTE *)(v12 + 8) = 0;
    *(_DWORD *)(v12 + 12) = 1;
    *(_QWORD *)(v12 + 24) = 0;
    *(_QWORD *)(v12 + 32) = 0;
    *(_QWORD *)(v12 + 40) = 0;
    *(_DWORD *)(v12 + 48) = 0;
    *(_DWORD *)(v12 + 52) = -1;
    *(_DWORD *)(v12 + 56) = 1;
    *(_QWORD *)(v12 + 64) = 0;
    *(_QWORD *)(v12 + 72) = 0;
    *(_DWORD *)(v12 + 80) = 0;
    *(_BYTE *)(v12 + 84) = 0;
    *(_QWORD *)(v12 + 88) = 0;
    *(_QWORD *)(v12 + 96) = 0;
    *(_QWORD *)(v12 + 104) = 0;
    *(_BYTE *)(v12 + 112) = 0;
    *(_OWORD *)(v12 + 116) = 0;
    *(_DWORD *)(v12 + 132) = 0;
    *(_QWORD *)(v12 + 136) = 0;
    *(_DWORD *)(v12 + 144) = 0;
    *(_BYTE *)(v12 + 148) = 0;
    memset((void *)(v12 + 149), 0, 0xD1u);
  }
  else
  {
    v13 = 0;
  }
  qword_14015F448 = v13;
  if ( !v13 )
  {
    v6 = 1;
    WdLogSingleEntry0(2);
    WdLogGlobalForLineNumber = 4692;
    v5 = -1073741801;
    goto LABEL_74;
  }
  v5 = DISPLAY_MUX_MGR::Init(v13);
  if ( v5 < 0 )
  {
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 4699;
    goto LABEL_73;
  }
  if ( (unsigned int)Feature_ForceConnectionDetectionOnDcToAc__private_IsEnabledDeviceUsageNoInline() )
    KeInitializeMutex(&Object, 0);
  NtObjectType = 0;
  if ( !g_pDpDisplayMuxSwitchNtObject )
  {
    *(_DWORD *)&SourceString.Length = 0x20000;
    *(_DWORD *)(&SourceString.MaximumLength + 1) = 0x20000;
    SourceString.Buffer = (wchar_t *)0x1F000000020000LL;
    NtObjectType = DxgkCreateNtObjectType(
                     L"DxgkDisplayMuxSwitch",
                     0,
                     (__int64)DpiDisplayMuxObjectDelete,
                     0,
                     (__int64)&g_pDpDisplayMuxSwitchNtObject,
                     0);
  }
  v5 = NtObjectType;
  if ( NtObjectType < 0 )
  {
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 4715;
    goto LABEL_73;
  }
LABEL_84:
  RtlFreeUnicodeString(&UnicodeString);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1404129c0  push    rbx
0x1404129c2  push    rsi
0x1404129c3  push    rdi
0x1404129c4  push    r12
0x1404129c6  push    r13
0x1404129c8  push    r14
0x1404129ca  push    r15
0x1404129cc  sub     rsp, 200h
0x1404129d3  mov     rax, cs:__security_cookie
0x1404129da  xor     rax, rsp
0x1404129dd  mov     [rsp+238h+var_48], rax
0x1404129e5  xor     r14d, r14d
0x1404129e8  mov     [rsp+238h+var_190], 3C003Ah
0x1404129f4  xorps   xmm1, xmm1
0x1404129f7  mov     [rsp+238h+KeyHandle], r14
0x1404129fc  xorps   xmm0, xmm0
0x1404129ff  mov     [rsp+238h+Data], r14d
0x140412a04  lea     rax, aKernelOnecoreD; "Kernel-OneCore-DeviceFamilyID"
0x140412a0b  mov     [rsp+238h+var_1C4], r14d
0x140412a10  mov     [rsp+238h+var_188], rax
0x140412a18  lea     r13d, [r14+4]
0x140412a1c  lea     rax, [rsp+238h+var_1D0]
0x140412a21  mov     [rsp+238h+var_1CC], r14d
0x140412a26  mov     r9d, r13d
0x140412a29  mov     [rsp+238h+var_1D0], r14d
0x140412a2e  lea     r8, dword_14015F440
0x140412a35  mov     [rsp+238h+Class], rax
0x140412a3a  lea     rdx, [rsp+238h+var_1CC]
0x140412a3f  mov     sil, r14b
0x140412a42  lea     rcx, [rsp+238h+var_190]
0x140412a4a  movups  xmmword ptr [rsp+238h+UnicodeString.Length], xmm0
0x140412a52  movups  xmmword ptr [rsp+238h+ObjectAttributes.Length], xmm1
0x140412a5a  movups  xmmword ptr [rsp+238h+ObjectAttributes.ObjectName], xmm1
0x140412a62  movups  xmmword ptr [rsp+238h+ObjectAttributes.SecurityDescriptor], xmm1
0x140412a6a  movups  xmmword ptr [rsp+238h+DestinationString.Length], xmm0
0x140412a72  call    cs:__imp_ZwQueryLicenseValue
0x140412a79  nop     dword ptr [rax+rax+00h]
0x140412a7e  lea     r12d, [r14+2]
0x140412a82  test    eax, eax
0x140412a84  jns     short loc_140412AAC
0x140412a86  movsxd  rdx, eax
0x140412a89  mov     ecx, r12d
0x140412a8c  call    cs:__imp_WdLogSingleEntry1
0x140412a93  nop     dword ptr [rax+rax+00h]
0x140412a98  mov     cs:WdLogGlobalForLineNumber, 1007h
0x140412aa2  mov     cs:dword_14015F440, 3
0x140412aac  lea     rax, aKernelProducti; "Kernel-ProductInfo"
0x140412ab3  mov     [rsp+238h+var_180], 260024h
0x140412abf  mov     [rsp+238h+var_178], rax
0x140412ac7  lea     r8, dword_14015F444
0x140412ace  lea     rax, [rsp+238h+var_1D0]
0x140412ad3  mov     r9d, r13d
0x140412ad6  lea     rdx, [rsp+238h+var_1CC]
0x140412adb  mov     [rsp+238h+Class], rax
0x140412ae0  lea     rcx, [rsp+238h+var_180]
0x140412ae8  call    cs:__imp_ZwQueryLicenseValue
0x140412aef  nop     dword ptr [rax+rax+00h]
0x140412af4  test    eax, eax
0x140412af6  jns     short loc_140412B1B
0x140412af8  movsxd  rdx, eax
0x140412afb  mov     ecx, r12d
0x140412afe  call    cs:__imp_WdLogSingleEntry1
0x140412b05  nop     dword ptr [rax+rax+00h]
0x140412b0a  mov     cs:WdLogGlobalForLineNumber, 1017h
0x140412b14  mov     cs:dword_14015F444, r14d
0x140412b1b  lea     rdx, aGraphicsdriver; "GraphicsDrivers\\DisableUSWC"
0x140412b22  mov     ecx, r12d; RelativeTo
0x140412b25  call    cs:__imp_RtlCheckRegistryKey
0x140412b2c  nop     dword ptr [rax+rax+00h]
0x140412b31  mov     r15d, 1
0x140412b37  test    eax, eax
0x140412b39  js      short loc_140412B42
0x140412b3b  mov     cs:byte_14015EDD0, r15b
0x140412b42  call    cs:__imp_DMgrIsSetupRunning
0x140412b49  nop     dword ptr [rax+rax+00h]
0x140412b4e  mov     cs:?g_bDMgrIsSetupRunning@@3EA, al; uchar g_bDMgrIsSetupRunning
0x140412b54  cmp     al, r15b
0x140412b57  jnz     short loc_140412B60
0x140412b59  mov     cs:byte_14015EDD1, r15b
0x140412b60  call    cs:__imp_ExIsSoftBoot
0x140412b67  nop     dword ptr [rax+rax+00h]
0x140412b6c  test    al, al
0x140412b6e  jz      short loc_140412B75
0x140412b70  call    DpiKsrRestore
0x140412b75  mov     ebx, 120h
0x140412b7a  mov     cs:dword_14015F2A4, 1C44h
0x140412b84  mov     edi, 4000004h
0x140412b89  mov     [rsp+238h+var_1E8], r14d
0x140412b8e  xorps   xmm0, xmm0
0x140412b91  mov     [rsp+238h+var_1E4], 7A120h
0x140412b99  lea     rax, aMiracastdefaul; "MiracastDefaultRtspPort"
0x140412ba0  mov     [rsp+238h+var_128], r14
0x140412ba8  mov     [rsp+238h+var_118], rax
0x140412bb0  lea     r8, [rsp+238h+var_128]
0x140412bb8  lea     rax, dword_14015F2A4
0x140412bbf  mov     [rsp+238h+var_120], ebx
0x140412bc6  mov     [rsp+238h+var_110], rax
0x140412bce  lea     rdx, Path; "GraphicsDrivers"
0x140412bd5  mov     [rsp+238h+var_100], rax
0x140412bdd  xor     r9d, r9d
0x140412be0  lea     rax, aPlatformsuppor; "PlatformSupportMiracast"
0x140412be7  mov     [rsp+238h+var_108], edi
0x140412bee  mov     [rsp+238h+var_E0], rax
0x140412bf6  mov     ecx, r12d
0x140412bf9  lea     rax, [rsp+238h+var_1E8]
0x140412bfe  mov     [rsp+238h+var_F8], r13d
0x140412c06  mov     [rsp+238h+var_D8], rax
0x140412c0e  lea     rax, [rsp+238h+var_1E8]
0x140412c13  mov     [rsp+238h+var_C8], rax
0x140412c1b  lea     rax, aSuspendadapter; "SuspendAdapterTimerPeriod"
0x140412c22  mov     [rsp+238h+var_A8], rax
0x140412c2a  lea     rax, [rsp+238h+var_1E4]
0x140412c2f  mov     [rsp+238h+var_A0], rax
0x140412c37  lea     rax, [rsp+238h+var_1E4]
0x140412c3c  mov     [rsp+238h+var_90], rax
0x140412c44  mov     [rsp+238h+var_F0], r14
0x140412c4c  mov     [rsp+238h+var_E8], ebx
0x140412c53  mov     [rsp+238h+var_D0], edi
0x140412c5a  mov     [rsp+238h+var_C0], r13d
0x140412c62  mov     [rsp+238h+var_B8], r14
0x140412c6a  mov     [rsp+238h+var_B0], ebx
0x140412c71  mov     [rsp+238h+var_98], edi
0x140412c78  mov     [rsp+238h+var_88], r13d
0x140412c80  mov     [rsp+238h+var_80], r14
0x140412c88  mov     [rsp+238h+var_78], r14d
0x140412c90  mov     [rsp+238h+var_70], r14
0x140412c98  movups  [rsp+238h+var_68], xmm0
0x140412ca0  mov     [rsp+238h+Class], r14
0x140412ca5  movups  [rsp+238h+var_58], xmm0
0x140412cad  call    cs:__imp_RtlQueryRegistryValuesEx
0x140412cb4  nop     dword ptr [rax+rax+00h]
0x140412cb9  test    eax, eax
0x140412cbb  js      short loc_140412CC6
0x140412cbd  cmp     cs:dword_14015F2A4, r14d
0x140412cc4  jnz     short loc_140412CD4
0x140412cc6  mov     cs:dword_14015F2A4, 1C44h
0x140412cd0  test    eax, eax
0x140412cd2  js      short loc_140412CE2
0x140412cd4  mov     cs:byte_14015EDD7, r15b
0x140412cdb  cmp     [rsp+238h+var_1E8], r14d
0x140412ce0  jnz     short loc_140412CE9
0x140412ce2  mov     cs:byte_14015EDD7, r14b
0x140412ce9  mov     eax, [rsp+238h+var_1E4]
0x140412ced  lea     r8, [rsp+238h+var_128]
0x140412cf5  neg     eax
0x140412cf7  mov     [rsp+238h+var_1E4], r14d
0x140412cfc  cdqe
0x140412cfe  lea     rdx, Path; "GraphicsDrivers"
0x140412d05  mov     qword ptr cs:DueTime, rax
0x140412d0c  xorps   xmm0, xmm0
0x140412d0f  lea     rax, aSupportmultipl; "SupportMultipleIntegratedDisplays"
0x140412d16  mov     [rsp+238h+var_1E8], r14d
0x140412d1b  mov     [rsp+238h+var_118], rax
0x140412d23  xor     r9d, r9d
0x140412d26  lea     rax, [rsp+238h+var_1E4]
0x140412d2b  mov     [rsp+238h+var_1E0], r14d
0x140412d30  mov     [rsp+238h+var_110], rax
0x140412d38  mov     ecx, r12d
0x140412d3b  lea     rax, [rsp+238h+var_1E4]
0x140412d40  mov     [rsp+238h+var_128], r14
0x140412d48  mov     [rsp+238h+var_100], rax
0x140412d50  lea     rax, aForcebddfallba; "ForceBddFallbackOnly"
0x140412d57  mov     [rsp+238h+var_E0], rax
0x140412d5f  lea     rax, [rsp+238h+var_1E8]
0x140412d64  mov     [rsp+238h+var_D8], rax
0x140412d6c  lea     rax, [rsp+238h+var_1E8]
0x140412d71  mov     [rsp+238h+var_C8], rax
0x140412d79  lea     rax, aDisablebgfxrel; "DisableBgfxRelay"
0x140412d80  mov     [rsp+238h+var_A8], rax
0x140412d88  lea     rax, [rsp+238h+var_1E0]
0x140412d8d  mov     [rsp+238h+var_A0], rax
0x140412d95  lea     rax, [rsp+238h+var_1E0]
0x140412d9a  mov     [rsp+238h+var_90], rax
0x140412da2  mov     [rsp+238h+var_120], ebx
0x140412da9  mov     [rsp+238h+var_108], edi
0x140412db0  mov     [rsp+238h+var_F8], r13d
0x140412db8  mov     [rsp+238h+var_F0], r14
0x140412dc0  mov     [rsp+238h+var_E8], ebx
0x140412dc7  mov     [rsp+238h+var_D0], edi
0x140412dce  mov     [rsp+238h+var_C0], r13d
0x140412dd6  mov     [rsp+238h+var_B8], r14
0x140412dde  mov     [rsp+238h+var_B0], ebx
0x140412de5  mov     [rsp+238h+var_98], edi
0x140412dec  mov     [rsp+238h+var_88], r13d
0x140412df4  mov     [rsp+238h+var_80], r14
0x140412dfc  mov     [rsp+238h+var_78], r14d
0x140412e04  mov     [rsp+238h+var_70], r14
0x140412e0c  movups  [rsp+238h+var_68], xmm0
0x140412e14  mov     [rsp+238h+Class], r14
0x140412e19  movups  [rsp+238h+var_58], xmm0
0x140412e21  call    cs:__imp_RtlQueryRegistryValuesEx
0x140412e28  nop     dword ptr [rax+rax+00h]
0x140412e2d  test    eax, eax
0x140412e2f  js      short loc_140412E57
0x140412e31  cmp     [rsp+238h+var_1E4], r14d
0x140412e36  setnz   cs:byte_14015EDD9
0x140412e3d  cmp     [rsp+238h+var_1E8], r14d
0x140412e42  setnz   cs:byte_14015F450
0x140412e49  cmp     [rsp+238h+var_1E0], r14d
0x140412e4e  setnz   cs:byte_14015EDD4
0x140412e55  jmp     short loc_140412E88
0x140412e57  movsxd  rdx, eax
0x140412e5a  mov     ecx, r12d
0x140412e5d  call    cs:__imp_WdLogSingleEntry1
0x140412e64  nop     dword ptr [rax+rax+00h]
0x140412e69  mov     cs:WdLogGlobalForLineNumber, 108Fh
0x140412e73  mov     cs:byte_14015EDD9, r14b
0x140412e7a  mov     cs:byte_14015F450, r14b
0x140412e81  mov     cs:byte_14015EDD4, r14b
0x140412e88  xorps   xmm0, xmm0
0x140412e8b  mov     [rsp+238h+var_1E0], r14d
0x140412e90  lea     rax, aHwschmode; "HwSchMode"
0x140412e97  mov     [rsp+238h+var_1E8], r15d
0x140412e9c  mov     [rsp+238h+var_118], rax
0x140412ea4  lea     r8, [rsp+238h+var_128]
0x140412eac  lea     rax, [rsp+238h+var_1E0]
0x140412eb1  mov     [rsp+238h+var_1E4], r14d
0x140412eb6  mov     [rsp+238h+var_110], rax
0x140412ebe  lea     rdx, Path; "GraphicsDrivers"
0x140412ec5  lea     rax, [rsp+238h+var_1E0]
0x140412eca  mov     [rsp+238h+var_128], r14
0x140412ed2  mov     [rsp+238h+var_100], rax
0x140412eda  xor     r9d, r9d
0x140412edd  lea     rax, aHwschoverrideb; "HwSchOverrideBlockList"
0x140412ee4  mov     [rsp+238h+var_120], ebx
0x140412eeb  mov     [rsp+238h+var_E0], rax
0x140412ef3  mov     ecx, r12d
0x140412ef6  lea     rax, [rsp+238h+var_1E8]
0x140412efb  mov     [rsp+238h+var_108], edi
0x140412f02  mov     [rsp+238h+var_D8], rax
0x140412f0a  lea     rax, [rsp+238h+var_1E8]
0x140412f0f  mov     [rsp+238h+var_C8], rax
0x140412f17  lea     rax, aHwschtreatexpe; "HwSchTreatExperimentalAsStable"
0x140412f1e  mov     [rsp+238h+var_A8], rax
0x140412f26  lea     rax, [rsp+238h+var_1E4]
0x140412f2b  mov     [rsp+238h+var_A0], rax
0x140412f33  lea     rax, [rsp+238h+var_1E4]
0x140412f38  mov     [rsp+238h+var_90], rax
0x140412f40  mov     [rsp+238h+var_F8], r13d
0x140412f48  mov     [rsp+238h+var_F0], r14
0x140412f50  mov     [rsp+238h+var_E8], ebx
0x140412f57  mov     [rsp+238h+var_D0], edi
0x140412f5e  mov     [rsp+238h+var_C0], r13d
0x140412f66  mov     [rsp+238h+var_B8], r14
0x140412f6e  mov     [rsp+238h+var_B0], ebx
0x140412f75  mov     [rsp+238h+var_98], edi
0x140412f7c  mov     [rsp+238h+var_88], r13d
0x140412f84  mov     [rsp+238h+var_80], r14
0x140412f8c  mov     [rsp+238h+var_78], r14d
0x140412f94  mov     [rsp+238h+var_70], r14
0x140412f9c  movups  [rsp+238h+var_68], xmm0
0x140412fa4  mov     [rsp+238h+Class], r14
0x140412fa9  movups  [rsp+238h+var_58], xmm0
0x140412fb1  call    cs:__imp_RtlQueryRegistryValuesEx
0x140412fb8  nop     dword ptr [rax+rax+00h]
0x140412fbd  test    eax, eax
0x140412fbf  js      short loc_140412FD2
0x140412fc1  mov     ecx, [rsp+238h+var_1E0]
0x140412fc5  cmp     ecx, 3
0x140412fc8  jnb     short loc_140412FD2
0x140412fca  mov     cs:dword_14015EDF8, ecx
0x140412fd0  jmp     short loc_140412FDD
0x140412fd2  mov     cs:dword_14015EDF8, r14d
0x140412fd9  test    eax, eax
0x140412fdb  js      short loc_140412FF7
0x140412fdd  cmp     [rsp+238h+var_1E4], r14d
0x140412fe2  mov     cs:byte_14015EDFC, r14b
0x140412fe9  setnz   cs:byte_14015EDFD
0x140412ff0  cmp     [rsp+238h+var_1E8], r14d
0x140412ff5  jz      short loc_140412FFE
0x140412ff7  mov     cs:byte_14015EDFC, r15b
0x140412ffe  or      eax, 0FFFFFFFFh
0x140413001  mov     [rsp+238h+var_1E8], r14d
0x140413006  mov     [rsp+238h+var_1E0], eax
0x14041300a  lea     r8, [rsp+238h+var_128]
0x140413012  mov     [rsp+238h+var_1E4], eax
0x140413016  lea     rdx, aGraphicsdriver_5; "GraphicsDrivers\\BasicDisplay"
0x14041301d  xorps   xmm0, xmm0
0x140413020  mov     [rsp+238h+var_128], r14
0x140413028  lea     rax, aEnablebasicdis; "EnableBasicDisplayFallback"
0x14041302f  mov     [rsp+238h+var_120], ebx
0x140413036  mov     [rsp+238h+var_118], rax
0x14041303e  xor     r9d, r9d
0x140413041  lea     rax, [rsp+238h+var_1E0]
0x140413046  mov     [rsp+238h+var_108], edi
0x14041304d  mov     [rsp+238h+var_110], rax
0x140413055  mov     ecx, r12d
0x140413058  lea     rax, [rsp+238h+var_1E0]
0x14041305d  mov     [rsp+238h+var_F8], r13d
0x140413065  mov     [rsp+238h+var_100], rax
0x14041306d  lea     rax, aDisablebasicdi; "DisableBasicDisplayFallback"
0x140413074  mov     [rsp+238h+var_E0], rax
0x14041307c  lea     rax, [rsp+238h+var_1E4]
0x140413081  mov     [rsp+238h+var_D8], rax
0x140413089  lea     rax, [rsp+238h+var_1E4]
0x14041308e  mov     [rsp+238h+var_C8], rax
0x140413096  lea     rax, aForcepreserveb; "ForcePreserveBootDisplay"
0x14041309d  mov     [rsp+238h+var_A8], rax
0x1404130a5  lea     rax, [rsp+238h+var_1E8]
0x1404130aa  mov     [rsp+238h+var_A0], rax
  ... truncated ...
```
