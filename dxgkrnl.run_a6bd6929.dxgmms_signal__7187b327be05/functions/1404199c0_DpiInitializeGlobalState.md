# DpiInitializeGlobalState

- ea: `0x1404199c0`
- end: `0x14041ab41`
- name: `DpiInitializeGlobalState`
- size: `4481`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140419008`

## callees

- `0x14002e2e0`
- `0x14005caec`
- `0x140087908`
- `0x1400a0bd0`
- `0x1400a0cb0`
- `0x1400a1000`
- `0x14024a810`
- `0x1402be30c`
- `0x1402bfb5c`
- `0x14030f37c`
- `0x1404199c0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14041a45c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14041aabb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14041aaf4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14041a45c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14041aabb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14041aaf4`
- `ntoskrnl!IoFreeWorkItem` at `0x14041aa89`
- `ntoskrnl!IoFreeWorkItem` at `0x14041aa89`
- `ntoskrnl!ExAllocatePool2` at `0x14041a478`
- `ntoskrnl!ExAllocatePool2` at `0x14041a546`
- `ntoskrnl!ExAllocatePool2` at `0x14041a478`
- `ntoskrnl!ExAllocatePool2` at `0x14041a546`
- `ntoskrnl!KeInitializeSpinLock` at `0x14041a6f6`
- `ntoskrnl!KeInitializeSpinLock` at `0x14041a6f6`
- `ntoskrnl!KeInitializeEvent` at `0x14041a4f4`
- `ntoskrnl!KeInitializeEvent` at `0x14041a84f`
- `ntoskrnl!KeInitializeEvent` at `0x14041a867`
- `ntoskrnl!KeInitializeEvent` at `0x14041a4f4`
- `ntoskrnl!KeInitializeEvent` at `0x14041a84f`
- `ntoskrnl!KeInitializeEvent` at `0x14041a867`
- `ntoskrnl!KeInitializeDpc` at `0x14041a5dc`
- `ntoskrnl!KeInitializeDpc` at `0x14041a5dc`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140419cad`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140419e21`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140419fb1`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14041a128`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140419cad`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140419e21`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140419fb1`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14041a128`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14041ab0f`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14041ab0f`
- `ntoskrnl!ZwClose` at `0x14041a1e7`
- `ntoskrnl!ZwClose` at `0x14041a30f`
- `ntoskrnl!ZwClose` at `0x14041a395`
- `ntoskrnl!ZwClose` at `0x14041a1e7`
- `ntoskrnl!ZwClose` at `0x14041a30f`
- `ntoskrnl!ZwClose` at `0x14041a395`
- `ntoskrnl!RtlInitUnicodeString` at `0x14041a168`
- `ntoskrnl!RtlInitUnicodeString` at `0x14041a227`
- `ntoskrnl!RtlInitUnicodeString` at `0x14041a2c9`
- `ntoskrnl!RtlInitUnicodeString` at `0x14041a353`
- `ntoskrnl!RtlInitUnicodeString` at `0x14041a168`
- `ntoskrnl!RtlInitUnicodeString` at `0x14041a227`
- `ntoskrnl!RtlInitUnicodeString` at `0x14041a2c9`
- `ntoskrnl!RtlInitUnicodeString` at `0x14041a353`
- `ntoskrnl!ZwOpenKey` at `0x14041a27b`
- `ntoskrnl!ZwOpenKey` at `0x14041a27b`
- `ntoskrnl!KeInitializeTimerEx` at `0x14041a5bf`
- `ntoskrnl!KeInitializeTimerEx` at `0x14041a5bf`
- `ntoskrnl!ZwQueryLicenseValue` at `0x140419a72`
- `ntoskrnl!ZwQueryLicenseValue` at `0x140419ae8`
- `ntoskrnl!ZwQueryLicenseValue` at `0x140419a72`
- `ntoskrnl!ZwQueryLicenseValue` at `0x140419ae8`
- `ntoskrnl!IoAllocateWorkItem` at `0x14041a5ef`
- `ntoskrnl!IoAllocateWorkItem` at `0x14041a5ef`
- `ntoskrnl!ZwCreateKey` at `0x14041a1d2`
- `ntoskrnl!ZwCreateKey` at `0x14041a1d2`
- `ntoskrnl!ZwSetValueKey` at `0x14041a2f7`
- `ntoskrnl!ZwSetValueKey` at `0x14041a381`
- `ntoskrnl!ZwSetValueKey` at `0x14041a2f7`
- `ntoskrnl!ZwSetValueKey` at `0x14041a381`
- `ntoskrnl!KeInitializeMutex` at `0x14041a4bf`
- `ntoskrnl!KeInitializeMutex` at `0x14041a58d`
- `ntoskrnl!KeInitializeMutex` at `0x14041a672`
- `ntoskrnl!KeInitializeMutex` at `0x14041a883`
- `ntoskrnl!KeInitializeMutex` at `0x14041a9d7`
- `ntoskrnl!KeInitializeMutex` at `0x14041a4bf`
- `ntoskrnl!KeInitializeMutex` at `0x14041a58d`
- `ntoskrnl!KeInitializeMutex` at `0x14041a672`
- `ntoskrnl!KeInitializeMutex` at `0x14041a883`
- `ntoskrnl!KeInitializeMutex` at `0x14041a9d7`
- `ntoskrnl!RtlCheckRegistryKey` at `0x140419b25`
- `ntoskrnl!RtlCheckRegistryKey` at `0x140419b25`
- `ntoskrnl!ExIsSoftBoot` at `0x140419b60`
- `ntoskrnl!ExIsSoftBoot` at `0x140419b60`
- `ntoskrnl!MmGetPhysicalMemoryRanges` at `0x14041a3d4`
- `ntoskrnl!MmGetPhysicalMemoryRanges` at `0x14041a3d4`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14041a52c`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14041a656`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14041a52c`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14041a656`
- `ntoskrnl!HalDispatchTable` at `0x14041a6a5`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x14041a764`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x14041a764`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14041aaa1`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14041aada`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14041aaa1`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14041aada`
- `watchdog!WdLogSingleEntry0` at `0x14041a975`
- `watchdog!WdLogSingleEntry0` at `0x14041a975`
- `watchdog!DMgrIsSetupRunning` at `0x140419b42`
- `watchdog!DMgrIsSetupRunning` at `0x140419b42`
- `watchdog!WdLogSingleEntry1` at `0x140419a8c`
- `watchdog!WdLogSingleEntry1` at `0x140419afe`
- `watchdog!WdLogSingleEntry1` at `0x140419e5d`
- `watchdog!WdLogSingleEntry1` at `0x14041a202`
- `watchdog!WdLogSingleEntry1` at `0x14041a294`
- `watchdog!WdLogSingleEntry1` at `0x14041a321`
- `watchdog!WdLogSingleEntry1` at `0x14041a3ab`
- `watchdog!WdLogSingleEntry1` at `0x14041a3f5`
- `watchdog!WdLogSingleEntry1` at `0x14041a49f`
- `watchdog!WdLogSingleEntry1` at `0x14041a56d`
- `watchdog!WdLogSingleEntry1` at `0x14041a616`
- `watchdog!WdLogSingleEntry1` at `0x14041a77d`
- `watchdog!WdLogSingleEntry1` at `0x14041a7e8`
- `watchdog!WdLogSingleEntry1` at `0x14041a9aa`
- `watchdog!WdLogSingleEntry1` at `0x14041aa64`
- `watchdog!WdLogSingleEntry1` at `0x140419a8c`
- `watchdog!WdLogSingleEntry1` at `0x140419afe`
- `watchdog!WdLogSingleEntry1` at `0x140419e5d`
- `watchdog!WdLogSingleEntry1` at `0x14041a202`
- `watchdog!WdLogSingleEntry1` at `0x14041a294`
- `watchdog!WdLogSingleEntry1` at `0x14041a321`
- `watchdog!WdLogSingleEntry1` at `0x14041a3ab`
- `watchdog!WdLogSingleEntry1` at `0x14041a3f5`
- `watchdog!WdLogSingleEntry1` at `0x14041a49f`
- `watchdog!WdLogSingleEntry1` at `0x14041a56d`
- `watchdog!WdLogSingleEntry1` at `0x14041a616`
- `watchdog!WdLogSingleEntry1` at `0x14041a77d`
- `watchdog!WdLogSingleEntry1` at `0x14041a7e8`
- `watchdog!WdLogSingleEntry1` at `0x14041a9aa`
- `watchdog!WdLogSingleEntry1` at `0x14041aa64`

## string_xrefs

- `0x14041a218`: `\Registry\Machine\System\CurrentControlSet\Control\GraphicsDrivers`
- `0x14041a79f`: `\Registry\Machine\System\CurrentControlSet\Control\GraphicsDrivers`
- `0x14041a159`: `\Registry\Machine\System\CurrentControlSet\Control\Video\`

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
  if ( (int)ZwQueryLicenseValue(v28, &v21, &dword_1401634C0, 4, &v20) < 0 )
  {
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 4103;
    dword_1401634C0 = 3;
  }
  v29[0] = 2490404;
  v29[1] = L"Kernel-ProductInfo";
  if ( (int)ZwQueryLicenseValue(v29, &v21, &dword_1401634C4, 4, &v20) < 0 )
  {
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 4119;
    dword_1401634C4 = 0;
  }
  if ( RtlCheckRegistryKey(2u, (PWSTR)L"GraphicsDrivers\\DisableUSWC") >= 0 )
    byte_140162E50 = 1;
  g_bDMgrIsSetupRunning = DMgrIsSetupRunning();
  if ( g_bDMgrIsSetupRunning == 1 )
    byte_140162E51 = 1;
  if ( (unsigned __int8)ExIsSoftBoot() )
    DpiKsrRestore();
  dword_140163324 = 7236;
  v16 = 0;
  v17 = 500000;
  v32 = 0;
  v34 = L"MiracastDefaultRtspPort";
  v33 = 288;
  v35 = &dword_140163324;
  v37 = &dword_140163324;
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
  if ( (v1 < 0 || !dword_140163324) && (dword_140163324 = 7236, v1 < 0) || (byte_140162E57 = 1, !v16) )
    byte_140162E57 = 0;
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
    byte_140162E59 = 0;
    byte_1401634D0 = 0;
    byte_140162E54 = 0;
  }
  else
  {
    byte_140162E59 = v17 != 0;
    byte_1401634D0 = v16 != 0;
    byte_140162E54 = v18 != 0;
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
    dword_140162E78 = v18;
    goto LABEL_23;
  }
  dword_140162E78 = 0;
  if ( v3 >= 0 )
  {
LABEL_23:
    byte_140162E7C = 0;
    byte_140162E7D = v17 != 0;
    if ( !v16 )
      goto LABEL_25;
  }
  byte_140162E7C = 1;
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
      byte_140162E52 = 1;
    byte_140162E53 = v16 == 1;
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
    if ( qword_1401630D0 )
      IoFreeWorkItem(qword_1401630D0);
    if ( v6 == 1 )
      ExDeleteNPagedLookasideList(&stru_140162F40);
    if ( qword_1401630F0 )
    {
      ExFreePoolWithTag(qword_1401630F0, 0);
      qword_1401630F0 = 0;
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
  word_140162EA0 = 0;
  qword_140162E90 = (__int64)&qword_140162E88;
  qword_140162E88 = (__int64)&qword_140162E88;
  KeInitializeEvent(&stru_140162EA8, NotificationEvent, 0);
  byte_140162EA2 = 0;
  ExInitializeNPagedLookasideList(&Lookaside, 0, 0, 0x200u, 0x58u, 0x74727044u, 0);
  v0 = 1;
  v11 = (struct _KMUTANT *)ExAllocatePool2(64, 56, 1953656900);
  qword_1401630F0 = v11;
  if ( !v11 )
  {
    v5 = -1073741801;
    WdLogSingleEntry1(6);
    WdLogGlobalForLineNumber = 4542;
    goto LABEL_74;
  }
  KeInitializeMutex(v11, 0);
  dword_1401630D8 = 0;
  qword_1401630E8 = (__int64)&qword_1401630E0;
  qword_1401630E0 = (__int64)&qword_1401630E0;
  KeInitializeTimerEx(&stru_140163050, SynchronizationTimer);
  KeInitializeDpc(&stru_140163090, DpiPdoPollingDpc, 0);
  qword_1401630D0 = IoAllocateWorkItem(g_pDriverObject);
  if ( !qword_1401630D0 )
  {
    v5 = -1073741801;
    WdLogSingleEntry1(6);
    WdLogGlobalForLineNumber = 4560;
    goto LABEL_74;
  }
  ExInitializeNPagedLookasideList(&stru_140162F40, 0, 0, 0x200u, 0x30u, 0x74727044u, 0);
  byte_1401632A0 = 0;
  KeInitializeMutex(&stru_1401632A8, 0);
  v24 = 2;
  qword_1401632E8 = (__int64)&qword_1401632E0;
  qword_1401632E0 = (__int64)&qword_1401632E0;
  v27 = 4;
  if ( ((int (__fastcall *)(__int64, __int64, int *, int *))HalDispatchTable->HalQuerySystemInformation)(
         9,
         4,
         &v24,
         &v27) < 0
    || (byte_140162E56 = 1, v24 == 2) )
  {
    byte_140162E56 = 0;
  }
  byte_140162E55 = 0;
  dword_140163254 = -1;
  KeInitializeSpinLock(&SpinLock);
  qword_140163308 = (__int64)&qword_140163300;
  qword_140163300 = (__int64)&qword_140163300;
  dword_140163320 = 0;
  qword_140163318 = (__int64)&qword_140163310;
  qword_140163310 = (__int64)&qword_140163310;
  v5 = IoRegisterPlugPlayNotification(
         EventCategoryDeviceInterfaceChange,
         1u,
         &GUID_DEVINTERFACE_UMDF_MIRACAST_DIVICE_ARRIVAL,
         (PDRIVER_OBJECT)g_pDriverObject,
         DpiMiracastInterfaceChange,
         0,
         &qword_1401632F0);
  if ( v5 < 0 )
  {
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 4635;
    qword_1401632F0 = 0;
LABEL_73:
    v6 = 1;
    goto LABEL_74;
  }
  *(_QWORD *)&SourceString.Length = 8781956;
  SourceString.Buffer = (wchar_t *)L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\GraphicsDrivers";
  v5 = DxgkCreateFeatureDatabase(&SourceString, 0, 1, 0, &qword_1401634D8);
  if ( v5 < 0 )
  {
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 4650;
    goto LABEL_73;
  }
  IoWorkItem = 0;
  qword_140163028 = (__int64)&qword_140163020;
  qword_140163020 = (__int64)&qword_140163020;
  dword_140163030 = 0;
  qword_140163018 = 0;
  dword_140162FE0 = 1;
  qword_140162FE8 = 0;
  dword_140162FF0 = 0;
  KeInitializeEvent(&stru_140162FF8, SynchronizationEvent, 0);
  KeInitializeEvent(&Event, NotificationEvent, 1u);
  byte_140163418 = 0;
  KeInitializeMutex(&stru_140163420, 0);
  qword_140163460 = (__int64)&qword_140163458;
  qword_140163458 = &qword_140163458;
  DpiIndirectDisplayInitialStartTracker();
  byte_140162E5C = 0;
  qword_1401633E8 = 1;
  dword_14016329C = 0;
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
  qword_1401634C8 = v13;
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
0x1404199c0  push    rbx
0x1404199c2  push    rsi
0x1404199c3  push    rdi
0x1404199c4  push    r12
0x1404199c6  push    r13
0x1404199c8  push    r14
0x1404199ca  push    r15
0x1404199cc  sub     rsp, 200h
0x1404199d3  mov     rax, cs:__security_cookie
0x1404199da  xor     rax, rsp
0x1404199dd  mov     [rsp+238h+var_48], rax
0x1404199e5  xor     r14d, r14d
0x1404199e8  mov     [rsp+238h+var_190], 3C003Ah
0x1404199f4  xorps   xmm1, xmm1
0x1404199f7  mov     [rsp+238h+KeyHandle], r14
0x1404199fc  xorps   xmm0, xmm0
0x1404199ff  mov     [rsp+238h+Data], r14d
0x140419a04  lea     rax, aKernelOnecoreD; "Kernel-OneCore-DeviceFamilyID"
0x140419a0b  mov     [rsp+238h+var_1C4], r14d
0x140419a10  mov     [rsp+238h+var_188], rax
0x140419a18  lea     r13d, [r14+4]
0x140419a1c  lea     rax, [rsp+238h+var_1D0]
0x140419a21  mov     [rsp+238h+var_1CC], r14d
0x140419a26  mov     r9d, r13d
0x140419a29  mov     [rsp+238h+var_1D0], r14d
0x140419a2e  lea     r8, dword_1401634C0
0x140419a35  mov     [rsp+238h+Class], rax
0x140419a3a  lea     rdx, [rsp+238h+var_1CC]
0x140419a3f  mov     sil, r14b
0x140419a42  lea     rcx, [rsp+238h+var_190]
0x140419a4a  movups  xmmword ptr [rsp+238h+UnicodeString.Length], xmm0
0x140419a52  movups  xmmword ptr [rsp+238h+ObjectAttributes.Length], xmm1
0x140419a5a  movups  xmmword ptr [rsp+238h+ObjectAttributes.ObjectName], xmm1
0x140419a62  movups  xmmword ptr [rsp+238h+ObjectAttributes.SecurityDescriptor], xmm1
0x140419a6a  movups  xmmword ptr [rsp+238h+DestinationString.Length], xmm0
0x140419a72  call    cs:__imp_ZwQueryLicenseValue
0x140419a79  nop     dword ptr [rax+rax+00h]
0x140419a7e  lea     r12d, [r14+2]
0x140419a82  test    eax, eax
0x140419a84  jns     short loc_140419AAC
0x140419a86  movsxd  rdx, eax
0x140419a89  mov     ecx, r12d
0x140419a8c  call    cs:__imp_WdLogSingleEntry1
0x140419a93  nop     dword ptr [rax+rax+00h]
0x140419a98  mov     cs:WdLogGlobalForLineNumber, 1007h
0x140419aa2  mov     cs:dword_1401634C0, 3
0x140419aac  lea     rax, aKernelProducti; "Kernel-ProductInfo"
0x140419ab3  mov     [rsp+238h+var_180], 260024h
0x140419abf  mov     [rsp+238h+var_178], rax
0x140419ac7  lea     r8, dword_1401634C4
0x140419ace  lea     rax, [rsp+238h+var_1D0]
0x140419ad3  mov     r9d, r13d
0x140419ad6  lea     rdx, [rsp+238h+var_1CC]
0x140419adb  mov     [rsp+238h+Class], rax
0x140419ae0  lea     rcx, [rsp+238h+var_180]
0x140419ae8  call    cs:__imp_ZwQueryLicenseValue
0x140419aef  nop     dword ptr [rax+rax+00h]
0x140419af4  test    eax, eax
0x140419af6  jns     short loc_140419B1B
0x140419af8  movsxd  rdx, eax
0x140419afb  mov     ecx, r12d
0x140419afe  call    cs:__imp_WdLogSingleEntry1
0x140419b05  nop     dword ptr [rax+rax+00h]
0x140419b0a  mov     cs:WdLogGlobalForLineNumber, 1017h
0x140419b14  mov     cs:dword_1401634C4, r14d
0x140419b1b  lea     rdx, aGraphicsdriver; "GraphicsDrivers\\DisableUSWC"
0x140419b22  mov     ecx, r12d; RelativeTo
0x140419b25  call    cs:__imp_RtlCheckRegistryKey
0x140419b2c  nop     dword ptr [rax+rax+00h]
0x140419b31  mov     r15d, 1
0x140419b37  test    eax, eax
0x140419b39  js      short loc_140419B42
0x140419b3b  mov     cs:byte_140162E50, r15b
0x140419b42  call    cs:__imp_DMgrIsSetupRunning
0x140419b49  nop     dword ptr [rax+rax+00h]
0x140419b4e  mov     cs:?g_bDMgrIsSetupRunning@@3EA, al; uchar g_bDMgrIsSetupRunning
0x140419b54  cmp     al, r15b
0x140419b57  jnz     short loc_140419B60
0x140419b59  mov     cs:byte_140162E51, r15b
0x140419b60  call    cs:__imp_ExIsSoftBoot
0x140419b67  nop     dword ptr [rax+rax+00h]
0x140419b6c  test    al, al
0x140419b6e  jz      short loc_140419B75
0x140419b70  call    DpiKsrRestore
0x140419b75  mov     ebx, 120h
0x140419b7a  mov     cs:dword_140163324, 1C44h
0x140419b84  mov     edi, 4000004h
0x140419b89  mov     [rsp+238h+var_1E8], r14d
0x140419b8e  xorps   xmm0, xmm0
0x140419b91  mov     [rsp+238h+var_1E4], 7A120h
0x140419b99  lea     rax, aMiracastdefaul; "MiracastDefaultRtspPort"
0x140419ba0  mov     [rsp+238h+var_128], r14
0x140419ba8  mov     [rsp+238h+var_118], rax
0x140419bb0  lea     r8, [rsp+238h+var_128]
0x140419bb8  lea     rax, dword_140163324
0x140419bbf  mov     [rsp+238h+var_120], ebx
0x140419bc6  mov     [rsp+238h+var_110], rax
0x140419bce  lea     rdx, Path; "GraphicsDrivers"
0x140419bd5  mov     [rsp+238h+var_100], rax
0x140419bdd  xor     r9d, r9d
0x140419be0  lea     rax, aPlatformsuppor; "PlatformSupportMiracast"
0x140419be7  mov     [rsp+238h+var_108], edi
0x140419bee  mov     [rsp+238h+var_E0], rax
0x140419bf6  mov     ecx, r12d
0x140419bf9  lea     rax, [rsp+238h+var_1E8]
0x140419bfe  mov     [rsp+238h+var_F8], r13d
0x140419c06  mov     [rsp+238h+var_D8], rax
0x140419c0e  lea     rax, [rsp+238h+var_1E8]
0x140419c13  mov     [rsp+238h+var_C8], rax
0x140419c1b  lea     rax, aSuspendadapter; "SuspendAdapterTimerPeriod"
0x140419c22  mov     [rsp+238h+var_A8], rax
0x140419c2a  lea     rax, [rsp+238h+var_1E4]
0x140419c2f  mov     [rsp+238h+var_A0], rax
0x140419c37  lea     rax, [rsp+238h+var_1E4]
0x140419c3c  mov     [rsp+238h+var_90], rax
0x140419c44  mov     [rsp+238h+var_F0], r14
0x140419c4c  mov     [rsp+238h+var_E8], ebx
0x140419c53  mov     [rsp+238h+var_D0], edi
0x140419c5a  mov     [rsp+238h+var_C0], r13d
0x140419c62  mov     [rsp+238h+var_B8], r14
0x140419c6a  mov     [rsp+238h+var_B0], ebx
0x140419c71  mov     [rsp+238h+var_98], edi
0x140419c78  mov     [rsp+238h+var_88], r13d
0x140419c80  mov     [rsp+238h+var_80], r14
0x140419c88  mov     [rsp+238h+var_78], r14d
0x140419c90  mov     [rsp+238h+var_70], r14
0x140419c98  movups  [rsp+238h+var_68], xmm0
0x140419ca0  mov     [rsp+238h+Class], r14
0x140419ca5  movups  [rsp+238h+var_58], xmm0
0x140419cad  call    cs:__imp_RtlQueryRegistryValuesEx
0x140419cb4  nop     dword ptr [rax+rax+00h]
0x140419cb9  test    eax, eax
0x140419cbb  js      short loc_140419CC6
0x140419cbd  cmp     cs:dword_140163324, r14d
0x140419cc4  jnz     short loc_140419CD4
0x140419cc6  mov     cs:dword_140163324, 1C44h
0x140419cd0  test    eax, eax
0x140419cd2  js      short loc_140419CE2
0x140419cd4  mov     cs:byte_140162E57, r15b
0x140419cdb  cmp     [rsp+238h+var_1E8], r14d
0x140419ce0  jnz     short loc_140419CE9
0x140419ce2  mov     cs:byte_140162E57, r14b
0x140419ce9  mov     eax, [rsp+238h+var_1E4]
0x140419ced  lea     r8, [rsp+238h+var_128]
0x140419cf5  neg     eax
0x140419cf7  mov     [rsp+238h+var_1E4], r14d
0x140419cfc  cdqe
0x140419cfe  lea     rdx, Path; "GraphicsDrivers"
0x140419d05  mov     qword ptr cs:DueTime, rax
0x140419d0c  xorps   xmm0, xmm0
0x140419d0f  lea     rax, aSupportmultipl; "SupportMultipleIntegratedDisplays"
0x140419d16  mov     [rsp+238h+var_1E8], r14d
0x140419d1b  mov     [rsp+238h+var_118], rax
0x140419d23  xor     r9d, r9d
0x140419d26  lea     rax, [rsp+238h+var_1E4]
0x140419d2b  mov     [rsp+238h+var_1E0], r14d
0x140419d30  mov     [rsp+238h+var_110], rax
0x140419d38  mov     ecx, r12d
0x140419d3b  lea     rax, [rsp+238h+var_1E4]
0x140419d40  mov     [rsp+238h+var_128], r14
0x140419d48  mov     [rsp+238h+var_100], rax
0x140419d50  lea     rax, aForcebddfallba; "ForceBddFallbackOnly"
0x140419d57  mov     [rsp+238h+var_E0], rax
0x140419d5f  lea     rax, [rsp+238h+var_1E8]
0x140419d64  mov     [rsp+238h+var_D8], rax
0x140419d6c  lea     rax, [rsp+238h+var_1E8]
0x140419d71  mov     [rsp+238h+var_C8], rax
0x140419d79  lea     rax, aDisablebgfxrel; "DisableBgfxRelay"
0x140419d80  mov     [rsp+238h+var_A8], rax
0x140419d88  lea     rax, [rsp+238h+var_1E0]
0x140419d8d  mov     [rsp+238h+var_A0], rax
0x140419d95  lea     rax, [rsp+238h+var_1E0]
0x140419d9a  mov     [rsp+238h+var_90], rax
0x140419da2  mov     [rsp+238h+var_120], ebx
0x140419da9  mov     [rsp+238h+var_108], edi
0x140419db0  mov     [rsp+238h+var_F8], r13d
0x140419db8  mov     [rsp+238h+var_F0], r14
0x140419dc0  mov     [rsp+238h+var_E8], ebx
0x140419dc7  mov     [rsp+238h+var_D0], edi
0x140419dce  mov     [rsp+238h+var_C0], r13d
0x140419dd6  mov     [rsp+238h+var_B8], r14
0x140419dde  mov     [rsp+238h+var_B0], ebx
0x140419de5  mov     [rsp+238h+var_98], edi
0x140419dec  mov     [rsp+238h+var_88], r13d
0x140419df4  mov     [rsp+238h+var_80], r14
0x140419dfc  mov     [rsp+238h+var_78], r14d
0x140419e04  mov     [rsp+238h+var_70], r14
0x140419e0c  movups  [rsp+238h+var_68], xmm0
0x140419e14  mov     [rsp+238h+Class], r14
0x140419e19  movups  [rsp+238h+var_58], xmm0
0x140419e21  call    cs:__imp_RtlQueryRegistryValuesEx
0x140419e28  nop     dword ptr [rax+rax+00h]
0x140419e2d  test    eax, eax
0x140419e2f  js      short loc_140419E57
0x140419e31  cmp     [rsp+238h+var_1E4], r14d
0x140419e36  setnz   cs:byte_140162E59
0x140419e3d  cmp     [rsp+238h+var_1E8], r14d
0x140419e42  setnz   cs:byte_1401634D0
0x140419e49  cmp     [rsp+238h+var_1E0], r14d
0x140419e4e  setnz   cs:byte_140162E54
0x140419e55  jmp     short loc_140419E88
0x140419e57  movsxd  rdx, eax
0x140419e5a  mov     ecx, r12d
0x140419e5d  call    cs:__imp_WdLogSingleEntry1
0x140419e64  nop     dword ptr [rax+rax+00h]
0x140419e69  mov     cs:WdLogGlobalForLineNumber, 108Fh
0x140419e73  mov     cs:byte_140162E59, r14b
0x140419e7a  mov     cs:byte_1401634D0, r14b
0x140419e81  mov     cs:byte_140162E54, r14b
0x140419e88  xorps   xmm0, xmm0
0x140419e8b  mov     [rsp+238h+var_1E0], r14d
0x140419e90  lea     rax, aHwschmode; "HwSchMode"
0x140419e97  mov     [rsp+238h+var_1E8], r15d
0x140419e9c  mov     [rsp+238h+var_118], rax
0x140419ea4  lea     r8, [rsp+238h+var_128]
0x140419eac  lea     rax, [rsp+238h+var_1E0]
0x140419eb1  mov     [rsp+238h+var_1E4], r14d
0x140419eb6  mov     [rsp+238h+var_110], rax
0x140419ebe  lea     rdx, Path; "GraphicsDrivers"
0x140419ec5  lea     rax, [rsp+238h+var_1E0]
0x140419eca  mov     [rsp+238h+var_128], r14
0x140419ed2  mov     [rsp+238h+var_100], rax
0x140419eda  xor     r9d, r9d
0x140419edd  lea     rax, aHwschoverrideb; "HwSchOverrideBlockList"
0x140419ee4  mov     [rsp+238h+var_120], ebx
0x140419eeb  mov     [rsp+238h+var_E0], rax
0x140419ef3  mov     ecx, r12d
0x140419ef6  lea     rax, [rsp+238h+var_1E8]
0x140419efb  mov     [rsp+238h+var_108], edi
0x140419f02  mov     [rsp+238h+var_D8], rax
0x140419f0a  lea     rax, [rsp+238h+var_1E8]
0x140419f0f  mov     [rsp+238h+var_C8], rax
0x140419f17  lea     rax, aHwschtreatexpe; "HwSchTreatExperimentalAsStable"
0x140419f1e  mov     [rsp+238h+var_A8], rax
0x140419f26  lea     rax, [rsp+238h+var_1E4]
0x140419f2b  mov     [rsp+238h+var_A0], rax
0x140419f33  lea     rax, [rsp+238h+var_1E4]
0x140419f38  mov     [rsp+238h+var_90], rax
0x140419f40  mov     [rsp+238h+var_F8], r13d
0x140419f48  mov     [rsp+238h+var_F0], r14
0x140419f50  mov     [rsp+238h+var_E8], ebx
0x140419f57  mov     [rsp+238h+var_D0], edi
0x140419f5e  mov     [rsp+238h+var_C0], r13d
0x140419f66  mov     [rsp+238h+var_B8], r14
0x140419f6e  mov     [rsp+238h+var_B0], ebx
0x140419f75  mov     [rsp+238h+var_98], edi
0x140419f7c  mov     [rsp+238h+var_88], r13d
0x140419f84  mov     [rsp+238h+var_80], r14
0x140419f8c  mov     [rsp+238h+var_78], r14d
0x140419f94  mov     [rsp+238h+var_70], r14
0x140419f9c  movups  [rsp+238h+var_68], xmm0
0x140419fa4  mov     [rsp+238h+Class], r14
0x140419fa9  movups  [rsp+238h+var_58], xmm0
0x140419fb1  call    cs:__imp_RtlQueryRegistryValuesEx
0x140419fb8  nop     dword ptr [rax+rax+00h]
0x140419fbd  test    eax, eax
0x140419fbf  js      short loc_140419FD2
0x140419fc1  mov     ecx, [rsp+238h+var_1E0]
0x140419fc5  cmp     ecx, 3
0x140419fc8  jnb     short loc_140419FD2
0x140419fca  mov     cs:dword_140162E78, ecx
0x140419fd0  jmp     short loc_140419FDD
0x140419fd2  mov     cs:dword_140162E78, r14d
0x140419fd9  test    eax, eax
0x140419fdb  js      short loc_140419FF7
0x140419fdd  cmp     [rsp+238h+var_1E4], r14d
0x140419fe2  mov     cs:byte_140162E7C, r14b
0x140419fe9  setnz   cs:byte_140162E7D
0x140419ff0  cmp     [rsp+238h+var_1E8], r14d
0x140419ff5  jz      short loc_140419FFE
0x140419ff7  mov     cs:byte_140162E7C, r15b
0x140419ffe  or      eax, 0FFFFFFFFh
0x14041a001  mov     [rsp+238h+var_1E8], r14d
0x14041a006  mov     [rsp+238h+var_1E0], eax
0x14041a00a  lea     r8, [rsp+238h+var_128]
0x14041a012  mov     [rsp+238h+var_1E4], eax
0x14041a016  lea     rdx, aGraphicsdriver_5; "GraphicsDrivers\\BasicDisplay"
0x14041a01d  xorps   xmm0, xmm0
0x14041a020  mov     [rsp+238h+var_128], r14
0x14041a028  lea     rax, aEnablebasicdis; "EnableBasicDisplayFallback"
0x14041a02f  mov     [rsp+238h+var_120], ebx
0x14041a036  mov     [rsp+238h+var_118], rax
0x14041a03e  xor     r9d, r9d
0x14041a041  lea     rax, [rsp+238h+var_1E0]
0x14041a046  mov     [rsp+238h+var_108], edi
0x14041a04d  mov     [rsp+238h+var_110], rax
0x14041a055  mov     ecx, r12d
0x14041a058  lea     rax, [rsp+238h+var_1E0]
0x14041a05d  mov     [rsp+238h+var_F8], r13d
0x14041a065  mov     [rsp+238h+var_100], rax
0x14041a06d  lea     rax, aDisablebasicdi; "DisableBasicDisplayFallback"
0x14041a074  mov     [rsp+238h+var_E0], rax
0x14041a07c  lea     rax, [rsp+238h+var_1E4]
0x14041a081  mov     [rsp+238h+var_D8], rax
0x14041a089  lea     rax, [rsp+238h+var_1E4]
0x14041a08e  mov     [rsp+238h+var_C8], rax
0x14041a096  lea     rax, aForcepreserveb; "ForcePreserveBootDisplay"
0x14041a09d  mov     [rsp+238h+var_A8], rax
0x14041a0a5  lea     rax, [rsp+238h+var_1E8]
0x14041a0aa  mov     [rsp+238h+var_A0], rax
  ... truncated ...
```
