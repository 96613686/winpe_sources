# DpiAddDevice

- ea: `0x14029e9b0`
- end: `0x1402a0c6f`
- name: `DpiAddDevice`
- size: `8895`
- prototype: `__int64 __fastcall(PVOID ClientIdentificationAddress, PDEVICE_OBJECT DeviceObject)`
- caller_count: `0`
- callee_count: `35`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x14001b890`
- `0x1400406a8`
- `0x1400406ec`
- `0x140047870`
- `0x14005edac`
- `0x14008138c`
- `0x14008cfac`
- `0x1400a00d8`
- `0x1400a0100`
- `0x1400a01e0`
- `0x1400a0540`
- `0x140192114`
- `0x140197644`
- `0x140209564`
- `0x140209660`
- `0x1402098a0`
- `0x14029e9b0`
- `0x1402a3580`
- `0x1402a85f4`
- `0x1402ab508`
- `0x1402b1794`
- `0x1402b1be4`
- `0x1402b2014`
- `0x1402b23e4`
- `0x1402b2878`
- `0x1402ba574`
- `0x1402bbecc`
- `0x1402bc6f4`
- `0x1402bcfb0`
- `0x1402bd214`
- `0x1402bd824`
- `0x140365a0c`
- `0x1403cf9a0`
- `0x1403e6940`
- `0x1403f629c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14029ee08`
- `ntoskrnl!ExFreePoolWithTag` at `0x14029ef6c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14029ef93`
- `ntoskrnl!ExFreePoolWithTag` at `0x14029f09e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14029f0e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a013d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a020b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14029ee08`
- `ntoskrnl!ExFreePoolWithTag` at `0x14029ef6c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14029ef93`
- `ntoskrnl!ExFreePoolWithTag` at `0x14029f09e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14029f0e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a013d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a020b`
- `ntoskrnl!ExAllocatePool2` at `0x14029f9b0`
- `ntoskrnl!ExAllocatePool2` at `0x1402a0514`
- `ntoskrnl!ExAllocatePool2` at `0x1402a05da`
- `ntoskrnl!ExAllocatePool2` at `0x1402a064a`
- `ntoskrnl!ExAllocatePool2` at `0x14029f9b0`
- `ntoskrnl!ExAllocatePool2` at `0x1402a0514`
- `ntoskrnl!ExAllocatePool2` at `0x1402a05da`
- `ntoskrnl!ExAllocatePool2` at `0x1402a064a`
- `ntoskrnl!KeInitializeSpinLock` at `0x1402a02a1`
- `ntoskrnl!KeInitializeSpinLock` at `0x1402a0627`
- `ntoskrnl!KeInitializeSpinLock` at `0x1402a0697`
- `ntoskrnl!KeInitializeSpinLock` at `0x1402a02a1`
- `ntoskrnl!KeInitializeSpinLock` at `0x1402a0627`
- `ntoskrnl!KeInitializeSpinLock` at `0x1402a0697`
- `ntoskrnl!KeInitializeEvent` at `0x1402a0376`
- `ntoskrnl!KeInitializeEvent` at `0x1402a038e`
- `ntoskrnl!KeInitializeEvent` at `0x1402a03a6`
- `ntoskrnl!KeInitializeEvent` at `0x1402a03dc`
- `ntoskrnl!KeInitializeEvent` at `0x1402a0376`
- `ntoskrnl!KeInitializeEvent` at `0x1402a038e`
- `ntoskrnl!KeInitializeEvent` at `0x1402a03a6`
- `ntoskrnl!KeInitializeEvent` at `0x1402a03dc`
- `ntoskrnl!KeInitializeDpc` at `0x1402a030a`
- `ntoskrnl!KeInitializeDpc` at `0x1402a030a`
- `ntoskrnl!ExDeleteResourceLite` at `0x14029f0c9`
- `ntoskrnl!ExDeleteResourceLite` at `0x14029f0c9`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14029eec3`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14029eec3`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14029f06f`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14029f082`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14029f06f`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14029f082`
- `ntoskrnl!ExInitializeResourceLite` at `0x1402a056c`
- `ntoskrnl!ExInitializeResourceLite` at `0x1402a056c`
- `ntoskrnl!ObfDereferenceObject` at `0x14029f8b8`
- `ntoskrnl!ObfDereferenceObject` at `0x14029fe4b`
- `ntoskrnl!ObfDereferenceObject` at `0x14029f8b8`
- `ntoskrnl!ObfDereferenceObject` at `0x14029fe4b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14029f522`
- `ntoskrnl!RtlInitUnicodeString` at `0x14029f522`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14029ecaa`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14029ecd4`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14029ecee`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14029ed12`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14029ecaa`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14029ecd4`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14029ecee`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14029ed12`
- `ntoskrnl!RtlCompareMemory` at `0x14029edbd`
- `ntoskrnl!RtlCompareMemory` at `0x14029f90d`
- `ntoskrnl!RtlCompareMemory` at `0x14029fbcd`
- `ntoskrnl!RtlCompareMemory` at `0x14029fe94`
- `ntoskrnl!RtlCompareMemory` at `0x14029ff14`
- `ntoskrnl!RtlCompareMemory` at `0x14029edbd`
- `ntoskrnl!RtlCompareMemory` at `0x14029f90d`
- `ntoskrnl!RtlCompareMemory` at `0x14029fbcd`
- `ntoskrnl!RtlCompareMemory` at `0x14029fe94`
- `ntoskrnl!RtlCompareMemory` at `0x14029ff14`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x14029f89b`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x14029fe29`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x14029f89b`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x14029fe29`
- `ntoskrnl!IoDeleteDevice` at `0x14029f119`
- `ntoskrnl!IoDeleteDevice` at `0x14029f119`
- `ntoskrnl!IoCreateDevice` at `0x14029f338`
- `ntoskrnl!IoCreateDevice` at `0x14029f338`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402a0475`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402a09cc`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402a0475`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402a09cc`
- `ntoskrnl!RtlGetProductInfo` at `0x1402a0872`
- `ntoskrnl!RtlGetProductInfo` at `0x1402a0872`
- `ntoskrnl!KeReleaseMutex` at `0x1402a06d5`
- `ntoskrnl!KeReleaseMutex` at `0x1402a0a16`
- `ntoskrnl!KeReleaseMutex` at `0x1402a0ab4`
- `ntoskrnl!KeReleaseMutex` at `0x1402a06d5`
- `ntoskrnl!KeReleaseMutex` at `0x1402a0a16`
- `ntoskrnl!KeReleaseMutex` at `0x1402a0ab4`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x14029ec08`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x14029ec08`
- `ntoskrnl!RtlFindUnicodeSubstring` at `0x14029ec62`
- `ntoskrnl!RtlFindUnicodeSubstring` at `0x14029ed3e`
- `ntoskrnl!RtlFindUnicodeSubstring` at `0x14029ec62`
- `ntoskrnl!RtlFindUnicodeSubstring` at `0x14029ed3e`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x14029f3e1`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x14029f3e1`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x14029f401`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x14029f401`
- `ntoskrnl!IoGetDevicePropertyData` at `0x14029f4fa`
- `ntoskrnl!IoGetDevicePropertyData` at `0x14029f4fa`
- `ntoskrnl!IoGetDeviceProperty` at `0x14029f710`
- `ntoskrnl!IoGetDeviceProperty` at `0x14029f764`
- `ntoskrnl!IoGetDeviceProperty` at `0x14029f7c7`
- `ntoskrnl!IoGetDeviceProperty` at `0x14029f710`
- `ntoskrnl!IoGetDeviceProperty` at `0x14029f764`
- `ntoskrnl!IoGetDeviceProperty` at `0x14029f7c7`
- `ntoskrnl!KeInitializeMutex` at `0x1402a031f`
- `ntoskrnl!KeInitializeMutex` at `0x1402a0334`
- `ntoskrnl!KeInitializeMutex` at `0x1402a05ae`
- `ntoskrnl!KeInitializeMutex` at `0x1402a031f`
- `ntoskrnl!KeInitializeMutex` at `0x1402a0334`
- `ntoskrnl!KeInitializeMutex` at `0x1402a05ae`
- `ntoskrnl!RtlGetVersion` at `0x1402a0834`
- `ntoskrnl!RtlGetVersion` at `0x1402a0834`
- `ntoskrnl!ExGetFirmwareType` at `0x1402a088e`
- `ntoskrnl!ExGetFirmwareType` at `0x1402a088e`
- `ntoskrnl!IoDetachDevice` at `0x14029f108`
- `ntoskrnl!IoDetachDevice` at `0x14029f108`
- `watchdog!WdLogSingleEntry2` at `0x14029f1ad`
- `watchdog!WdLogSingleEntry2` at `0x14029f24f`
- `watchdog!WdLogSingleEntry2` at `0x14029f294`
- `watchdog!WdLogSingleEntry2` at `0x1402a074e`
- `watchdog!WdLogSingleEntry2` at `0x1402a079f`
- `watchdog!WdLogSingleEntry2` at `0x14029f1ad`
- `watchdog!WdLogSingleEntry2` at `0x14029f24f`
- `watchdog!WdLogSingleEntry2` at `0x14029f294`
- `watchdog!WdLogSingleEntry2` at `0x1402a074e`
- `watchdog!WdLogSingleEntry2` at `0x1402a079f`
- `watchdog!WdLogSingleEntry3` at `0x1402a0a73`
- `watchdog!WdLogSingleEntry3` at `0x1402a0a73`
- `watchdog!WdLogSingleEntry1` at `0x14029ed85`
- `watchdog!WdLogSingleEntry1` at `0x14029ede8`
- `watchdog!WdLogSingleEntry1` at `0x14029eede`
- `watchdog!WdLogSingleEntry1` at `0x14029ef11`
- `watchdog!WdLogSingleEntry1` at `0x14029f168`
- `watchdog!WdLogSingleEntry1` at `0x14029f1f1`
- `watchdog!WdLogSingleEntry1` at `0x14029f2c9`
- `watchdog!WdLogSingleEntry1` at `0x14029f353`
- `watchdog!WdLogSingleEntry1` at `0x14029f427`
- `watchdog!WdLogSingleEntry1` at `0x14029f62d`
- `watchdog!WdLogSingleEntry1` at `0x14029f728`
- `watchdog!WdLogSingleEntry1` at `0x14029f78b`
- `watchdog!WdLogSingleEntry1` at `0x14029f7ea`
- `watchdog!WdLogSingleEntry1` at `0x14029f82e`
- `watchdog!WdLogSingleEntry1` at `0x14029f867`
- `watchdog!WdLogSingleEntry1` at `0x14029f92b`
- `watchdog!WdLogSingleEntry1` at `0x14029f986`
- `watchdog!WdLogSingleEntry1` at `0x14029f9d7`
- `watchdog!WdLogSingleEntry1` at `0x14029fae2`
- `watchdog!WdLogSingleEntry1` at `0x14029fb49`
- `watchdog!WdLogSingleEntry1` at `0x14029fba2`
- `watchdog!WdLogSingleEntry1` at `0x14029fbfe`
- `watchdog!WdLogSingleEntry1` at `0x14029fc28`
- `watchdog!WdLogSingleEntry1` at `0x14029fcba`
- `watchdog!WdLogSingleEntry1` at `0x14029fd55`
- `watchdog!WdLogSingleEntry1` at `0x14029fdf2`
- `watchdog!WdLogSingleEntry1` at `0x14029fe67`
- `watchdog!WdLogSingleEntry1` at `0x14029feae`
- `watchdog!WdLogSingleEntry1` at `0x14029ff95`
- `watchdog!WdLogSingleEntry1` at `0x1402a0220`
- `watchdog!WdLogSingleEntry1` at `0x1402a0241`
- `watchdog!WdLogSingleEntry1` at `0x1402a027f`
- `watchdog!WdLogSingleEntry1` at `0x1402a0418`
- `watchdog!WdLogSingleEntry1` at `0x1402a04af`
- `watchdog!WdLogSingleEntry1` at `0x1402a0538`
- `watchdog!WdLogSingleEntry1` at `0x1402a0585`
- `watchdog!WdLogSingleEntry1` at `0x1402a05fe`
- `watchdog!WdLogSingleEntry1` at `0x1402a066e`
- `watchdog!WdLogSingleEntry1` at `0x1402a0903`
- `watchdog!WdLogSingleEntry1` at `0x14029ed85`
- `watchdog!WdLogSingleEntry1` at `0x14029ede8`
- `watchdog!WdLogSingleEntry1` at `0x14029eede`
- `watchdog!WdLogSingleEntry1` at `0x14029ef11`
- `watchdog!WdLogSingleEntry1` at `0x14029f168`
- `watchdog!WdLogSingleEntry1` at `0x14029f1f1`
- `watchdog!WdLogSingleEntry1` at `0x14029f2c9`
- `watchdog!WdLogSingleEntry1` at `0x14029f353`
- `watchdog!WdLogSingleEntry1` at `0x14029f427`
- `watchdog!WdLogSingleEntry1` at `0x14029f62d`
- `watchdog!WdLogSingleEntry1` at `0x14029f728`
- `watchdog!WdLogSingleEntry1` at `0x14029f78b`
- `watchdog!WdLogSingleEntry1` at `0x14029f7ea`
- `watchdog!WdLogSingleEntry1` at `0x14029f82e`
- `watchdog!WdLogSingleEntry1` at `0x14029f867`
- `watchdog!WdLogSingleEntry1` at `0x14029f92b`
- `watchdog!WdLogSingleEntry1` at `0x14029f986`
- `watchdog!WdLogSingleEntry1` at `0x14029f9d7`
- `watchdog!WdLogSingleEntry1` at `0x14029fae2`
- `watchdog!WdLogSingleEntry1` at `0x14029fb49`
- `watchdog!WdLogSingleEntry1` at `0x14029fba2`
- `watchdog!WdLogSingleEntry1` at `0x14029fbfe`
- `watchdog!WdLogSingleEntry1` at `0x14029fc28`
- `watchdog!WdLogSingleEntry1` at `0x14029fcba`
- `watchdog!WdLogSingleEntry1` at `0x14029fd55`
- `watchdog!WdLogSingleEntry1` at `0x14029fdf2`
- `watchdog!WdLogSingleEntry1` at `0x14029fe67`

## string_xrefs

- `0x14029eb7b`: `\Driver\VirtualComputeAccelerator`
- `0x14029f489`: `ComputeAccelerator`
- `0x1402a0935`: `Adapter AddDevice has completed with status %1`

## pseudocode

```c
__int64 __fastcall DpiAddDevice(
        struct _DRIVER_OBJECT *ClientIdentificationAddress,
        PDEVICE_OBJECT DeviceObject,
        int a3)
{
  struct _DEVICE_OBJECT *v3; // rsi
  char *DeviceExtension; // rbx
  char *v6; // r14
  _DWORD *DriverObjectExtension; // rax
  __int64 v8; // r8
  _DWORD *v9; // r13
  const UNICODE_STRING *p_DriverName; // r15
  wchar_t *Buffer; // rdi
  char v12; // di
  __int64 v13; // r8
  wchar_t *v14; // rdi
  NTSTATUS DeviceRegistryPaths; // esi
  char v16; // al
  void *v17; // rdi
  __int64 v18; // rdx
  char v19; // r15
  _DWORD *v20; // rcx
  _DWORD *v21; // rcx
  void (__fastcall *v22)(_QWORD); // rax
  void (__fastcall *v23)(_QWORD); // rax
  void (__fastcall *v24)(_QWORD); // rax
  void (__fastcall *v25)(_QWORD); // rax
  void *v26; // rcx
  struct _ERESOURCE *v27; // rcx
  _DWORD *v28; // rcx
  struct _DEVICE_OBJECT *v29; // rcx
  char v30; // r15
  ULONG v31; // edi
  __int64 v32; // rdx
  struct _DEVICE_OBJECT *v33; // rdi
  PDEVICE_OBJECT v34; // rax
  struct _DEVICE_OBJECT *v35; // rcx
  bool v36; // al
  struct _DEVICE_OBJECT *v37; // rcx
  int v38; // eax
  int v39; // ecx
  struct _DEVICE_OBJECT *v40; // rsi
  _DWORD *v41; // rdi
  GUID *v42; // rdi
  char v43; // al
  struct _DEVICE_OBJECT *AttachedDeviceReference; // rdi
  struct _DEVICE_OBJECT *v45; // rsi
  __int64 Pool2; // rax
  unsigned __int16 *v47; // rcx
  int v48; // edx
  int v49; // edi
  bool v50; // al
  __int64 v51; // rdi
  int v52; // eax
  char v53; // cl
  bool v54; // zf
  struct _DEVICE_OBJECT *v55; // rdi
  int v56; // edi
  char v57; // al
  _WORD *v58; // r9
  unsigned int v59; // r8d
  __int16 v60; // dx
  _WORD *v61; // rdi
  _WORD *i; // rax
  __int16 v63; // cx
  __int16 *v64; // rdx
  wchar_t *j; // rax
  _DWORD *v66; // rdx
  unsigned __int64 v67; // r8
  char **v68; // rcx
  __int64 v69; // rax
  __int64 v70; // rax
  __int64 v71; // rax
  char *v72; // rdi
  __int64 v73; // rdx
  bool v74; // cl
  int v75; // edi
  _QWORD *v76; // rdx
  PVOID *v77; // rax
  __int64 DiagnosticInfoArgs; // rax
  __int64 v79; // rdi
  unsigned int v80; // ebx
  struct _DEVICE_OBJECT *v81; // r14
  unsigned int v82; // eax
  int v83; // ecx
  int v84; // r8d
  int Exclusive; // [rsp+28h] [rbp-D8h]
  char v87; // [rsp+50h] [rbp-B0h]
  char v88; // [rsp+51h] [rbp-AFh]
  char v89; // [rsp+52h] [rbp-AEh]
  char v90; // [rsp+53h] [rbp-ADh]
  char v91; // [rsp+54h] [rbp-ACh]
  char v92; // [rsp+55h] [rbp-ABh]
  char v93; // [rsp+56h] [rbp-AAh]
  char v94; // [rsp+57h] [rbp-A9h]
  char v95; // [rsp+57h] [rbp-A9h]
  PDEVICE_OBJECT DeviceObjecta; // [rsp+58h] [rbp-A8h] BYREF
  char v97; // [rsp+60h] [rbp-A0h]
  int v98; // [rsp+64h] [rbp-9Ch]
  char v99; // [rsp+68h] [rbp-98h]
  char v100; // [rsp+69h] [rbp-97h]
  char v101; // [rsp+6Ah] [rbp-96h]
  char v102; // [rsp+6Bh] [rbp-95h]
  char v103; // [rsp+6Ch] [rbp-94h]
  char v104[3]; // [rsp+6Dh] [rbp-93h] BYREF
  int v105; // [rsp+70h] [rbp-90h]
  ULONG ResultLength; // [rsp+74h] [rbp-8Ch] BYREF
  PDEVICE_OBJECT TargetDevice; // [rsp+78h] [rbp-88h]
  void *Source1; // [rsp+80h] [rbp-80h] BYREF
  __int64 v109; // [rsp+88h] [rbp-78h] BYREF
  ULONG Type; // [rsp+90h] [rbp-70h] BYREF
  PDRIVER_OBJECT DriverObject; // [rsp+98h] [rbp-68h]
  __int64 v112; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v113[15]; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v114[2]; // [rsp+120h] [rbp+20h] BYREF
  UNICODE_STRING String1; // [rsp+130h] [rbp+30h] BYREF
  UNICODE_STRING v116; // [rsp+140h] [rbp+40h] BYREF
  UNICODE_STRING v117; // [rsp+150h] [rbp+50h] BYREF
  UNICODE_STRING v118; // [rsp+160h] [rbp+60h] BYREF
  _QWORD v119[2]; // [rsp+170h] [rbp+70h] BYREF
  __int64 v120; // [rsp+180h] [rbp+80h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+188h] [rbp+88h] BYREF
  __int64 v122; // [rsp+198h] [rbp+98h]
  __int64 v123; // [rsp+1A0h] [rbp+A0h] BYREF
  int v124; // [rsp+1A8h] [rbp+A8h]
  _OWORD v125[4]; // [rsp+1B0h] [rbp+B0h] BYREF
  _DWORD VersionInformation[72]; // [rsp+1F0h] [rbp+F0h] BYREF
  wchar_t Str1[20]; // [rsp+310h] [rbp+210h] BYREF
  _OWORD v128[2]; // [rsp+338h] [rbp+238h] BYREF
  wchar_t v129; // [rsp+358h] [rbp+258h]
  _OWORD v130[2]; // [rsp+360h] [rbp+260h] BYREF
  _OWORD v131[2]; // [rsp+380h] [rbp+280h] BYREF
  __int64 v132; // [rsp+3A0h] [rbp+2A0h]
  __int128 v133; // [rsp+3A8h] [rbp+2A8h] BYREF
  _OWORD v134[2]; // [rsp+3B8h] [rbp+2B8h]
  __int128 v135; // [rsp+3D8h] [rbp+2D8h] BYREF
  _OWORD v136[2]; // [rsp+3E8h] [rbp+2E8h]
  _OWORD v137[4]; // [rsp+410h] [rbp+310h] BYREF
  int v138; // [rsp+450h] [rbp+350h]
  WCHAR Data[20]; // [rsp+460h] [rbp+360h] BYREF

  v3 = DeviceObject;
  v123 = 0;
  v130[0] = *(_OWORD *)L"\\Driver\\VGPU";
  v124 = 0;
  v90 = 0;
  DeviceExtension = 0;
  v104[0] = 0;
  v6 = 0;
  v128[0] = *(_OWORD *)L"\\Driver\\WddmWarp";
  TargetDevice = DeviceObject;
  v118.Buffer = (wchar_t *)v130;
  v131[0] = *(_OWORD *)L"\\Driver\\BasicRender";
  v129 = aDriverWddmwarp[16];
  *(_OWORD *)((char *)v130 + 10) = *(_OWORD *)L"er\\VGPU";
  String1.Buffer = (wchar_t *)v128;
  v114[1] = v131;
  v132 = *(_QWORD *)L"der";
  v119[1] = &v133;
  v128[1] = *(_OWORD *)L"WddmWarp";
  v116.Buffer = (wchar_t *)&v135;
  v133 = *(_OWORD *)L"\\Driver\\BasicDisplay";
  v138 = *(_DWORD *)L"r";
  DriverObject = ClientIdentificationAddress;
  v131[1] = *(_OWORD *)L"BasicRender";
  v109 = 0;
  v93 = 0;
  DeviceObjecta = 0;
  v134[0] = *(_OWORD *)L"BasicDisplay";
  ResultLength = 0;
  v88 = 1;
  *(_OWORD *)((char *)v134 + 10) = *(_OWORD *)L"Display";
  LOBYTE(v98) = 0;
  v91 = 0;
  v136[0] = *(_OWORD *)L"VirtualRender";
  v87 = 0;
  v135 = *(_OWORD *)L"\\Driver\\VirtualRender";
  v92 = 0;
  v105 = 3;
  v137[1] = *(_OWORD *)L"VirtualComputeAccelerator";
  *(_OWORD *)((char *)v136 + 12) = *(_OWORD *)L"lRender";
  *(_QWORD *)&v118.Length = 1703960;
  v137[0] = *(_OWORD *)L"\\Driver\\VirtualComputeAccelerator";
  v137[2] = *(_OWORD *)L"omputeAccelerator";
  *(_QWORD *)&String1.Length = 2228256;
  v114[0] = 2621478;
  v119[0] = 2752552;
  *(_QWORD *)&v116.Length = 2883626;
  v137[3] = *(_OWORD *)L"celerator";
  *(_QWORD *)&v117.Length = 4456514;
  v117.Buffer = (wchar_t *)v137;
  if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
    McTemplateK0ppq_EtwWriteTransfer(
      (_DWORD)ClientIdentificationAddress,
      (unsigned int)EventEnterDpiAddDevice,
      a3,
      (_DWORD)ClientIdentificationAddress,
      (char)DeviceObject,
      0);
  v120 = MEMORY[0xFFFFF78000000320];
  DriverObjectExtension = IoGetDriverObjectExtension(ClientIdentificationAddress, ClientIdentificationAddress);
  v9 = DriverObjectExtension;
  if ( !DriverObjectExtension || DriverObjectExtension[4] != 1953656900 || DriverObjectExtension[5] != 1 )
  {
    DeviceRegistryPaths = -1073741811;
    WdLogSingleEntry3(0, 275, 21, -1073741811);
    v19 = v98;
    v16 = 0;
    WdLogGlobalForLineNumber = 330;
    goto LABEL_299;
  }
  v101 = 0;
  v103 = 0;
  LOBYTE(v8) = 1;
  v97 = 0;
  v100 = 0;
  v94 = 0;
  p_DriverName = &ClientIdentificationAddress->DriverName;
  Buffer = ClientIdentificationAddress->DriverName.Buffer;
  if ( (wchar_t *)RtlFindUnicodeSubstring(p_DriverName, v114, v8) == Buffer )
  {
    v12 = 1;
    v89 = 1;
    v102 = 1;
    v99 = 1;
LABEL_72:
    if ( byte_14015F450 && !v12 )
    {
      WdLogSingleEntry1(3);
      WdLogGlobalForLineNumber = 476;
      DeviceRegistryPaths = -1073741637;
      goto LABEL_35;
    }
    DeviceRegistryPaths = DpiDxgkDdiAddDevice(v9, v3, &v109);
    if ( DeviceRegistryPaths < 0 )
    {
      WdLogSingleEntry2(2, *((_QWORD *)v9 + 18));
      WdLogGlobalForLineNumber = 502;
LABEL_77:
      v16 = 0;
      goto LABEL_298;
    }
    v93 = 1;
    if ( v109 )
    {
      v32 = *((_QWORD *)v9 + 77);
      v31 = 6520;
      *(_DWORD *)&DestinationString.Length = 2;
      v105 = 0;
      if ( v32 )
      {
        if ( v89 )
        {
          DeviceRegistryPaths = -1073741637;
          WdLogSingleEntry2(2, v32);
          WdLogGlobalForLineNumber = 565;
          goto LABEL_35;
        }
        DeviceRegistryPaths = DpiDxgkDdiLinkDevice(v9, TargetDevice, v109, &v123);
        if ( DeviceRegistryPaths < 0 )
        {
          WdLogSingleEntry2(2, *((_QWORD *)v9 + 77));
          WdLogGlobalForLineNumber = 579;
          goto LABEL_77;
        }
        if ( HIDWORD(v123) > 0x100 )
        {
          DeviceRegistryPaths = -1073741756;
          WdLogSingleEntry1(2);
          WdLogGlobalForLineNumber = 595;
          goto LABEL_35;
        }
        if ( HIDWORD(v123) && !(_BYTE)v124 )
        {
          v31 = 2848;
          *(_DWORD *)&DestinationString.Length = 3;
          v105 = 1;
        }
      }
    }
    else
    {
      v105 = 2;
      if ( v12 )
      {
        DeviceRegistryPaths = -1073741637;
        WdLogSingleEntry1(2);
        WdLogGlobalForLineNumber = 532;
        goto LABEL_35;
      }
      v31 = 496;
      *(_DWORD *)&DestinationString.Length = 4;
    }
    DeviceRegistryPaths = IoCreateDevice(DriverObject, v31, 0, 0x23u, v97 == 0 ? 0x100 : 0, 0, &DeviceObjecta);
    if ( DeviceRegistryPaths < 0 )
    {
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 635;
      goto LABEL_19;
    }
    v105 |= (unsigned int)DeviceObjecta & 0xFFFF00;
    DeviceExtension = (char *)DeviceObjecta->DeviceExtension;
    *((_DWORD *)DeviceExtension + 5) = *(_DWORD *)&DestinationString.Length;
    *((_DWORD *)DeviceExtension + 4) = 1953656900;
    *((_QWORD *)DeviceExtension + 3) = DeviceObjecta;
    *((_QWORD *)DeviceExtension + 4) = DeviceObjecta;
    *((_QWORD *)DeviceExtension + 5) = v9;
    *((_QWORD *)DeviceExtension + 6) = v109;
    DeviceExtension[480] = v89;
    DeviceExtension[56] = 1;
    DeviceExtension[481] = v94;
    IoInitializeRemoveLockEx((PIO_REMOVE_LOCK)DeviceExtension + 2, 0x74727044u, 1u, 0, 0x20u);
    v33 = TargetDevice;
    *((_QWORD *)DeviceExtension + 19) = TargetDevice;
    v34 = IoAttachDeviceToDeviceStack(DeviceObjecta, v33);
    *((_QWORD *)DeviceExtension + 20) = v34;
    if ( !v34 )
    {
      DeviceRegistryPaths = -1073741810;
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 677;
      goto LABEL_35;
    }
    v95 = 0;
    *((_DWORD *)DeviceExtension + 71) = 1;
    *((_DWORD *)DeviceExtension + 70) = 1;
    *((_QWORD *)DeviceExtension + 38) = DpiFdoHandleRemoveDevice;
    if ( !DeviceExtension
      || *((_DWORD *)DeviceExtension + 4) != 1953656900
      || (unsigned int)(*((_DWORD *)DeviceExtension + 5) - 2) > 1 )
    {
      goto LABEL_237;
    }
    v35 = (struct _DEVICE_OBJECT *)*((_QWORD *)DeviceExtension + 19);
    LODWORD(Source1) = 0;
    wcscpy(Str1, L"ComputeAccelertor");
    v6 = DeviceExtension;
    Type = 0;
    if ( IoGetDevicePropertyData(v35, &DEVPKEY_Device_Class, 0, 0, 0x28u, Data, (PULONG)&Source1, &Type) >= 0 )
    {
      DestinationString = 0;
      RtlInitUnicodeString(&DestinationString, Data);
      if ( DestinationString.Length >= 0x13u && !wcsncmp_0(Str1, DestinationString.Buffer, 0x12u) )
        DeviceExtension[2722] = 1;
    }
    DeviceExtension[2717] = v99;
    DeviceExtension[1153] = v101;
    DeviceExtension[1154] = v102;
    DeviceExtension[1158] = v97;
    DeviceExtension[2718] = v103;
    DeviceExtension[2719] = v100;
    *((_DWORD *)DeviceExtension + 688) = 1;
    *((_DWORD *)DeviceExtension + 686) = 0;
    *((_QWORD *)DeviceExtension + 36) = DpiFdoHandleStartDevice;
    *((_QWORD *)DeviceExtension + 59) = &DpiFdoHandleSurpriseRemoval;
    *((_QWORD *)DeviceExtension + 49) = &DpiFdoHandleFilterResources;
    if ( !byte_14015EDD1 && !DeviceExtension[480] )
      *((_QWORD *)DeviceExtension + 40) = &DpiFdoHandleStopDevice;
    *(_QWORD *)(DeviceExtension + 500) = v123;
    *((_DWORD *)DeviceExtension + 127) = v124;
    DeviceRegistryPaths = DpiGetDeviceRegistryPaths(DeviceObjecta, v33, v9);
    if ( DeviceRegistryPaths < 0 )
    {
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 765;
      goto LABEL_284;
    }
    *(_DWORD *)&DestinationString.Length = 0;
    v36 = (int)DpiReadPnpRegistryValue(DeviceObjecta, L"SoftGPUAdapter", &DestinationString, 4, 2) >= 0
       && *(_DWORD *)&DestinationString.Length;
    v37 = (struct _DEVICE_OBJECT *)*((_QWORD *)DeviceExtension + 20);
    DeviceExtension[2716] = v36;
    if ( (int)DpiQueryBusInterface(v37, (__int64)(DeviceExtension + 856)) >= 0 )
    {
      if ( *((_QWORD *)v9 + 29) )
      {
        v38 = DpiAcpiRegisterAcpiCallbacks(DeviceObjecta);
        v39 = (unsigned __int8)v98;
        if ( v38 >= 0 )
          v39 = 1;
        v98 = v39;
      }
      DeviceExtension[1156] = 1;
    }
    v40 = TargetDevice;
    if ( IoGetDeviceProperty(TargetDevice, DevicePropertyBusNumber, 4u, DeviceExtension + 1144, &ResultLength) < 0 )
    {
      WdLogSingleEntry1(3);
      WdLogGlobalForLineNumber = 851;
      *((_DWORD *)DeviceExtension + 286) = -1;
    }
    v41 = DeviceExtension + 1148;
    if ( IoGetDeviceProperty(v40, DevicePropertyAddress, 4u, DeviceExtension + 1148, &ResultLength) < 0 || *v41 == -1 )
    {
      if ( !DeviceExtension[2716] )
      {
        WdLogSingleEntry1(3);
        WdLogGlobalForLineNumber = 879;
      }
      *v41 = -1;
    }
    v42 = (GUID *)(DeviceExtension + 544);
    DeviceRegistryPaths = IoGetDeviceProperty(
                            v40,
                            DevicePropertyBusTypeGuid,
                            0x10u,
                            DeviceExtension + 544,
                            &ResultLength);
    if ( DeviceRegistryPaths < 0 || ResultLength < 0x10 )
    {
      WdLogSingleEntry1(4);
      WdLogGlobalForLineNumber = 899;
      *v42 = GUID_BUS_TYPE_INVALID;
    }
    if ( v89 )
    {
      v43 = 0;
    }
    else
    {
      DeviceRegistryPaths = DpiFdoDetectPostDevice(DeviceObjecta, v104);
      if ( DeviceRegistryPaths < 0 )
      {
        WdLogSingleEntry1(2);
        WdLogGlobalForLineNumber = 922;
        goto LABEL_284;
      }
      v43 = v104[0];
      v90 = v104[0];
    }
    if ( v43 )
    {
      WdLogSingleEntry1(4);
      WdLogGlobalForLineNumber = 937;
      DeviceExtension[1152] = 1;
      byte_14015F1E8 = 1;
      if ( byte_14015EDD1 == 1 )
      {
        AttachedDeviceReference = IoGetAttachedDeviceReference(TargetDevice);
        DpiSetDeviceUsageType(AttachedDeviceReference);
        ObfDereferenceObject(AttachedDeviceReference);
        v42 = (GUID *)(DeviceExtension + 544);
      }
    }
    if ( DeviceExtension[1158] )
    {
      *((_DWORD *)DeviceExtension + 281) = 5140;
      *((_QWORD *)DeviceExtension + 142) = 0;
      *((_DWORD *)DeviceExtension + 280) = 0;
      *((_QWORD *)DeviceExtension + 141) = 139;
      goto LABEL_222;
    }
    if ( RtlCompareMemory(v42, &GUID_BUS_TYPE_PCI, 0x10u) != 16 )
    {
      if ( RtlCompareMemory(v42, &GUID_BUS_TYPE_ACPI, 0x10u) == 16 )
      {
        DestinationString = 0;
        v122 = 0;
        WdLogSingleEntry1(4);
        WdLogGlobalForLineNumber = 1181;
        if ( !DeviceExtension[1156] )
        {
          DeviceRegistryPaths = -1073741637;
          WdLogSingleEntry1(2);
          WdLogGlobalForLineNumber = 1189;
          goto LABEL_284;
        }
        *((_DWORD *)DeviceExtension + 280) = 2;
        BYTE1(DestinationString.Buffer) = 0;
        WORD1(DestinationString.Buffer) = 0;
        strcpy((char *)&DestinationString, "AeiC_HID");
        HIDWORD(DestinationString.Buffer) = 0;
        memset(Str1, 0, 36);
        if ( (int)DpEvalAcpiMethod((int)DeviceObjecta, Str1, 0x24u) >= 0 )
        {
          *(_QWORD *)(DeviceExtension + 1124) = *(_QWORD *)&Str1[8];
        }
        else
        {
          WdLogSingleEntry1(2);
          WdLogGlobalForLineNumber = 1225;
        }
        strcpy((char *)&DestinationString, "AeiC_SUB");
        BYTE1(DestinationString.Buffer) = 0;
        WORD1(DestinationString.Buffer) = 0;
        HIDWORD(DestinationString.Buffer) = 0;
        memset(Str1, 0, 36);
        if ( (int)DpEvalAcpiMethod((int)DeviceObjecta, Str1, 0x24u) >= 0 )
        {
          *(_QWORD *)(DeviceExtension + 1132) = *(_QWORD *)&Str1[8];
        }
        else
        {
          WdLogSingleEntry1(4);
          WdLogGlobalForLineNumber = 1259;
        }
        strcpy((char *)&DestinationString, "AeiC_HRV");
        BYTE1(DestinationString.Buffer) = 0;
        WORD1(DestinationString.Buffer) = 0;
        HIDWORD(DestinationString.Buffer) = 0;
        memset(Str1, 0, 36);
        DeviceRegistryPaths = DpEvalAcpiMethod((int)DeviceObjecta, Str1, 0x24u);
        if ( DeviceRegistryPaths >= 0 )
        {
          *((_DWORD *)DeviceExtension + 285) = Str1[8];
        }
        else
        {
          WdLogSingleEntry1(4);
          WdLogGlobalForLineNumber = 1293;
          DeviceRegistryPaths = 0;
        }
        if ( v90 )
        {
          v55 = IoGetAttachedDeviceReference(TargetDevice);
          DeviceRegistryPaths = DpiSetDeviceUsageType(v55);
          ObfDereferenceObject(v55);
          if ( DeviceRegistryPaths < 0 )
          {
            WdLogSingleEntry1(2);
            WdLogGlobalForLineNumber = 1321;
            DeviceRegistryPaths = 0;
          }
        }
      }
      else if ( RtlCompareMemory(v42, &GUID_BUS_VMBUS, 0x10u) == 16 )
      {
        WdLogSingleEntry1(4);
        WdLogGlobalForLineNumber = 1340;
        if ( DeviceExtension[2718] )
        {
          *((_DWORD *)DeviceExtension + 281) = 5140;
          *((_QWORD *)DeviceExtension + 141) = 705;
          *((_DWORD *)DeviceExtension + 284) = 0;
          *((_DWORD *)DeviceExtension + 285) = 1;
        }
        *((_DWORD *)DeviceExtension + 280) = 4;
      }
      else
      {
        RtlCompareMemory(v42, &GUID_BUS_TYPE_DISPLAY, 0x10u);
        v56 = 0;
        if ( DeviceExtension[480] )
        {
          *((_DWORD *)DeviceExtension + 280) = 3;
          *((_DWORD *)DeviceExtension + 281) = 5140;
          if ( DeviceExtension[1153] )
          {
            *((_DWORD *)DeviceExtension + 282) = 141;
          }
          else if ( DeviceExtension[2717] )
          {
            *((_DWORD *)DeviceExtension + 282) = 140;
          }
        }
        else
        {
          v57 = DeviceExtension[2719];
          if ( !v57 && !g_OSTestSigningEnabled )
          {
            DeviceRegistryPaths = -1073741637;
            WdLogSingleEntry1(2);
            WdLogGlobalForLineNumber = 1599;
            goto LABEL_284;
          }
          *((_DWORD *)DeviceExtension + 280) = 3;
          if ( v57 )
          {
            *((_DWORD *)DeviceExtension + 281) = 5140;
            *((_DWORD *)DeviceExtension + 282) = 53248;
            *(_QWORD *)(DeviceExtension + 1132) = 4098;
            *((_DWORD *)DeviceExtension + 285) = 0;
          }
          else
          {
            *(_QWORD *)&DestinationString.Length = 0;
            DeviceRegistryPaths = DpiGetDevicePropertyString(
                                    TargetDevice,
                                    DevicePropertyCompatibleIDs,
                                    (__int64)&ResultLength);
            if ( DeviceRegistryPaths >= 0 && (v58 = *(_WORD **)&DestinationString.Length) != 0 )
            {
              if ( DeviceExtension[2716] )
              {
                *((_DWORD *)DeviceExtension + 281) = 5140;
                v113[1] = L"SoftGPU_Full_D3D12";
                v59 = 0;
                v112 = 135;
                v113[4] = L"SoftGPU_Full_D3D9L";
                v113[7] = L"SoftGPU_Rod";
                v113[10] = L"SoftGPU_Dod";
                v113[13] = L"SoftGPU_MCDM";
                v113[0] = 0;
                v113[2] = 128;
                v113[3] = 0;
                v113[5] = 136;
                v113[6] = 0;
                v113[8] = 137;
                v113[9] = 0;
                v113[11] = 0x123400000086LL;
                v113[12] = 0x9ABC00005678LL;
                while ( v59 < 5 )
                {
                  v60 = *v58;
                  v61 = v58;
                  for ( i = (_WORD *)v113[3 * (int)v59 + 1]; v60 && *i && v60 == *i; ++i )
                    v60 = *++v61;
                  if ( !*i )
                  {
                    *((_DWORD *)DeviceExtension + 282) = v113[3 * (int)v59 - 1];
                    *((_DWORD *)DeviceExtension + 284) = *((_DWORD *)&v112 + 6 * (int)v59 + 1);
                    *((_DWORD *)DeviceExtension + 283) = v113[3 * (int)v59];
                    *((_DWORD *)DeviceExtension + 285) = HIDWORD(v113[3 * (int)v59]);
                    break;
                  }
                  ++v59;
                }
              }
              else
              {
                *(_DWORD *)&DestinationString.Length = 5140;
                *(_DWORD *)(&DestinationString.MaximumLength + 1) = 256;
                DestinationString.Buffer = L"MCDMTestDevice";
                LODWORD(v122) = 2721;
                while ( !v56 )
                {
                  v63 = *v58;
                  v64 = v58;
                  for ( j = DestinationString.Buffer; *v64; v63 = *v64 )
                  {
                    if ( !*j )
                      break;
                    if ( v63 != *j )
                      break;
                    ++v64;
                    ++j;
                  }
                  if ( !*j )
                  {
                    *((_DWORD *)DeviceExtension + 281) = *(_DWORD *)&DestinationString.Length;
                    *((_DWORD *)DeviceExtension + 282) = *(_DWORD *)(&DestinationString.MaximumLength + 1);
                    DeviceExtension[(int)v122] = 1;
                    break;
                  }
                  v56 = 1;
                }
                if ( !*((_DWORD *)DeviceExtension + 282) )
                {
                  ExFreePoolWithTag(v58, 0);
                  DeviceRegistryPaths = -1073741637;
                  WdLogSingleEntry1(2);
                  WdLogGlobalForLineNumber = 1573;
                  goto LABEL_284;
                }
              }
              ExFreePoolWithTag(v58, 0);
            }
            else
            {
              WdLogSingleEntry1(2);
              WdLogGlobalForLineNumber = 1585;
            }
          }
        }
      }
      goto LABEL_222;
    }
    WdLogSingleEntry1(4);
    v45 = TargetDevice;
    WdLogGlobalForLineNumber = 992;
    DpiQueryBusInterface(TargetDevice, (__int64)(DeviceExtension + 560));
    if ( !*((_QWORD *)DeviceExtension + 77) )
    {
      DeviceRegistryPaths = -1073741127;
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 1017;
      goto LABEL_284;
    }
    Pool2 = ExAllocatePool2(256, 256, 1953656900);
    *((_QWORD *)DeviceExtension + 139) = Pool2;
    if ( !Pool2 )
    {
      DeviceRegistryPaths = -1073741801;
      WdLogSingleEntry1(6);
      WdLogGlobalForLineNumber = 1037;
      goto LABEL_284;
    }
    (*((void (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD, int))DeviceExtension + 77))(
      *((_QWORD *)DeviceExtension + 71),
      0,
      Pool2,
      0,
      256);
    v47 = (unsigned __int16 *)*((_QWORD *)DeviceExtension + 139);
    *((_DWORD *)DeviceExtension + 280) = 1;
    v48 = *v47;
    *((_DWORD *)DeviceExtension + 281) = v48;
    v49 = v47[1];
    *((_DWORD *)DeviceExtension + 282) = v49;
    *((_DWORD *)DeviceExtension + 285) = *((unsigned __int8 *)v47 + 8);
    if ( (v47[7] & 0x7F) == 0 )
    {
      *((_DWORD *)DeviceExtension + 283) = v47[22];
      *((_DWORD *)DeviceExtension + 284) = v47[23];
    }
    v50 = v48 == 22611 && v49 == 4097;
    DeviceExtension[2720] = v50;
    DpiQueryBusInterface(v45, (__int64)(DeviceExtension + 624));
    DpiQueryBusInterface(*((PDEVICE_OBJECT *)DeviceExtension + 20), (__int64)(DeviceExtension + 672));
    if ( (int)DpiGetAgpStatus(DeviceObjecta) >= 0 && !*((_QWORD *)DeviceExtension + 85) )
    {
      WdLogSingleEntry1(3);
      WdLogGlobalForLineNumber = 1105;
    }
    v51 = *((_QWORD *)DeviceObjecta->DeviceExtension + 139);
    v52 = DpiFdoDetectVgaDeviceInCapabilities();
    if ( v52 < 0 )
    {
      DeviceRegistryPaths = v52;
LABEL_165:
      if ( v90 )
      {
        WdLogSingleEntry1(3);
        WdLogGlobalForLineNumber = 1161;
      }
      goto LABEL_222;
    }
    v53 = *(_BYTE *)(v51 + 11);
    if ( v53 )
    {
      if ( v53 != 3 )
      {
LABEL_163:
        DeviceRegistryPaths = -1073741823;
        goto LABEL_165;
      }
      v54 = *(_BYTE *)(v51 + 10) == 0;
    }
    else
    {
      v54 = *(_BYTE *)(v51 + 10) == 1;
    }
    if ( v54 )
    {
      DeviceRegistryPaths = v52;
      if ( !v90 )
      {
        if ( byte_14015F1E8 )
        {
LABEL_222:
          if ( DeviceExtension[2716] && DeviceExtension[2717] )
          {
            DeviceRegistryPaths = -1073741811;
            WdLogSingleEntry1(2);
            WdLogGlobalForLineNumber = 1612;
            goto LABEL_284;
          }
          KeInitializeSpinLock((PKSPIN_LOCK)DeviceExtension + 184);
          v66 = DeviceExtension + 1336;
          *((_WORD *)DeviceExtension + 660) = 64;
          if ( (((_BYTE)DeviceExtension + 56) & 4) != 0 )
          {
            *v66 = 1;
            v67 = 6;
            v66 = DeviceExtension + 1340;
          }
          else
          {
            v67 = 7;
          }
          memset64(v66, 0x100000001uLL, v67 >> 1);
          if ( (v67 & 1) != 0 )
            v66[v67 - 1] = 1;
          KeInitializeDpc((PRKDPC)DeviceExtension + 22, DpiFdoDpcForIsr, DeviceObjecta);
          KeInitializeMutex((PRKMUTEX)(DeviceExtension + 2544), 0);
          KeInitializeMutex((PRKMUTEX)(DeviceExtension + 2624), 0);
          *((_QWORD *)DeviceExtension + 317) = DeviceExtension + 2528;
          *((_QWORD *)DeviceExtension + 316) = DeviceExtension + 2528;
          *((_QWORD *)DeviceExtension + 327) = DeviceExtension + 2608;
          *((_QWORD *)DeviceExtension + 326) = DeviceExtension + 2608;
          *((_QWORD *)DeviceExtension + 342) = DeviceExtension + 2728;
          *((_QWORD *)DeviceExtension + 341) = DeviceExtension + 2728;
          KeInitializeEvent((PRKEVENT)(DeviceExtension + 1240), NotificationEvent, 1u);
          KeInitializeEvent((PRKEVENT)(DeviceExtension + 1264), NotificationEvent, 1u);
          KeInitializeEvent((PRKEVENT)(DeviceExtension + 1288), NotificationEvent, 0);
          *((_QWORD *)DeviceExtension + 153) = 0;
          *((_DWORD *)DeviceExtension + 292) = 1;
          *((_QWORD *)DeviceExtension + 147) = 0;
          *((_DWORD *)DeviceExtension + 296) = 0;
          KeInitializeEvent((PRKEVENT)(DeviceExtension + 1192), SynchronizationEvent, 0);
          v54 = *((_DWORD *)DeviceExtension + 4) == 1953656900;
          *((_DWORD *)DeviceExtension + 687) = 69640;
          if ( v54 )
          {
            if ( *((_DWORD *)DeviceExtension + 5) == 2 )
            {
              DeviceRegistryPaths = DpiFdoInitializeFdo(DeviceObjecta);
              if ( DeviceRegistryPaths < 0 )
              {
                WdLogSingleEntry1(2);
                WdLogGlobalForLineNumber = 1672;
                goto LABEL_284;
              }
              v91 = 1;
            }
            else if ( *((_DWORD *)DeviceExtension + 5) == 3 )
            {
              DeviceRegistryPaths = 0;
              *((_QWORD *)DeviceObjecta->DeviceExtension + 43) = &DpiLdaHandleQueryDeviceRelations;
            }
          }
LABEL_237:
          DeviceExtension[57] = v97;
          KeWaitForSingleObject(v9 + 18, Executive, 0, 0, 0);
          v87 = 1;
          if ( v6 )
          {
            if ( *((_DWORD *)v6 + 126) )
            {
              DeviceRegistryPaths = DpiLdaLinkDeviceToChain(DeviceObjecta);
              if ( DeviceRegistryPaths < 0 )
              {
                WdLogSingleEntry1(2);
                WdLogGlobalForLineNumber = 1727;
                goto LABEL_284;
              }
            }
          }
          v68 = (char **)*((_QWORD *)v9 + 8);
          if ( *v68 != (char *)(v9 + 14) )
            goto LABEL_295;
          *(_QWORD *)DeviceExtension = v9 + 14;
          *((_QWORD *)DeviceExtension + 1) = v68;
          *v68 = DeviceExtension;
          *((_QWORD *)v9 + 8) = DeviceExtension;
          ++v9[32];
          v95 = 1;
          if ( !*((_QWORD *)DeviceExtension + 21) )
          {
            v69 = ExAllocatePool2(64, 112, 1953656900);
            *((_QWORD *)DeviceExtension + 21) = v69;
            if ( !v69 )
            {
              DeviceRegistryPaths = -1073741801;
              WdLogSingleEntry1(6);
              WdLogGlobalForLineNumber = 1762;
              goto LABEL_283;
            }
            *(_DWORD *)(v69 + 104) = 1;
            *(_BYTE *)(*((_QWORD *)DeviceExtension + 21) + 108LL) = 0;
            DeviceRegistryPaths = ExInitializeResourceLite(*((PERESOURCE *)DeviceExtension + 21));
            if ( DeviceRegistryPaths < 0 )
            {
              WdLogSingleEntry1(2);
              WdLogGlobalForLineNumber = 1776;
              goto LABEL_283;
            }
            v92 = 1;
          }
          KeInitializeMutex((PRKMUTEX)(DeviceExtension + 176), 0);
          if ( !v6 )
            goto LABEL_257;
          if ( !*((_QWORD *)v6 + 185) )
          {
            v70 = ExAllocatePool2(64, 16, 1953656900);
            *((_QWORD *)v6 + 185) = v70;
            if ( !v70 )
            {
              DeviceRegistryPaths = -1073741801;
              WdLogSingleEntry1(6);
              WdLogGlobalForLineNumber = 1804;
              goto LABEL_284;
            }
            *(_DWORD *)(v70 + 8) = 1;
            KeInitializeSpinLock(*((PKSPIN_LOCK *)v6 + 185));
          }
          if ( *((_QWORD *)v6 + 186) )
          {
LABEL_257:
            v72 = DeviceExtension;
            if ( !v6 )
              goto LABEL_259;
          }
          else
          {
            v71 = ExAllocatePool2(64, 16, 1953656900);
            *((_QWORD *)v6 + 186) = v71;
            if ( !v71 )
            {
              DeviceRegistryPaths = -1073741801;
              WdLogSingleEntry1(6);
              WdLogGlobalForLineNumber = 1826;
              goto LABEL_284;
            }
            *(_DWORD *)(v71 + 8) = 1;
            KeInitializeSpinLock(*((PKSPIN_LOCK *)v6 + 186));
            v72 = DeviceExtension;
          }
          *((_DWORD *)v6 + 374) = 0;
          memset(v6 + 1504, 0, 0x400u);
LABEL_259:
          KeReleaseMutex((PRKMUTEX)(v9 + 18), 0);
          v87 = 0;
          *((_QWORD *)v72 + 16) = DpiFdoDispatchPnp;
          if ( v6 )
            *((_QWORD *)v6 + 17) = DpiFdoDispatchPower;
          if ( v90 )
          {
            *(_BYTE *)(*((_QWORD *)v6 + 21) + 108LL) = 1;
            AcquireMiniportListMutex();
            if ( qword_14015F080 )
            {
              if ( v6[1152] )
              {
                qword_14015F080 = (__int64)DeviceObjecta;
                WdLogSingleEntry2(2, DeviceObjecta);
                WdLogGlobalForLineNumber = 1884;
              }
            }
            else
            {
              qword_14015F080 = (__int64)DeviceObjecta;
            }
            v73 = *((_QWORD *)v6 + 6);
            Source1 = 0;
            DeviceRegistryPaths = DpiDxgkDdiExchangePreStartInfo(v9, v73, &Source1);
            ReleaseMiniportListMutex();
            if ( DeviceRegistryPaths < 0 )
            {
              WdLogSingleEntry2(2, *((_QWORD *)v9 + 143));
              WdLogGlobalForLineNumber = 1908;
              goto LABEL_283;
            }
            if ( *((_DWORD *)v6 + 4) == 1953656900 && *((_DWORD *)v6 + 5) == 2 )
            {
              v74 = (BYTE4(Source1) & 2) != 0;
              v6[2845] = BYTE4(Source1) & 1;
              v6[2846] = v74;
            }
          }
          if ( v89 && v101 )
          {
            if ( (qword_14015F078 = (__int64)DeviceObjecta,
                  memset(&VersionInformation[1], 0, 0x118u),
                  VersionInformation[0] = 284,
                  RtlGetVersion((PRTL_OSVERSIONINFOW)VersionInformation) >= 0)
              && (*(_DWORD *)&DestinationString.Length = 0,
                  RtlGetProductInfo(
                    VersionInformation[1],
                    VersionInformation[2],
                    LOWORD(VersionInformation[69]),
                    HIWORD(VersionInformation[69]),
                    (PULONG)&DestinationString.Length))
              && *(_DWORD *)&DestinationString.Length == 187
              || (unsigned int)ExGetFirmwareType() == 2
              || byte_14015EDD3 )
            {
              *(_WORD *)(v6 + 2845) = 257;
            }
          }
          if ( DeviceExtension[57] )
          {
            DeviceObjecta->Flags |= *(_DWORD *)(*((_QWORD *)DeviceExtension + 20) + 48LL) & 0x2014;
          }
          else
          {
            DeviceObjecta->Flags |= 4u;
            DeviceObjecta->Flags |= 0x2000u;
          }
          DeviceObjecta->Flags &= ~0x4000u;
          DeviceObjecta->Flags &= ~0x80u;
          WdLogSingleEntry1(4);
          WdLogGlobalForLineNumber = 2004;
LABEL_283:
          if ( !v6 )
          {
LABEL_287:
            if ( DeviceRegistryPaths >= 0 )
              goto LABEL_312;
            v75 = v105;
            v19 = v98;
            if ( v95 != 1 )
            {
              v16 = v87;
              goto LABEL_298;
            }
            KeWaitForSingleObject(v9 + 18, Executive, 0, 0, 0);
            v76 = *(_QWORD **)DeviceExtension;
            if ( *(char **)(*(_QWORD *)DeviceExtension + 8LL) == DeviceExtension )
            {
              v77 = (PVOID *)*((_QWORD *)DeviceExtension + 1);
              if ( *v77 == DeviceExtension )
              {
                *v77 = v76;
                v76[1] = v77;
                --v9[32];
                if ( v6 && *((_DWORD *)v6 + 126) )
                  DpiLdaUnLinkDeviceFromChain(DeviceObjecta);
                KeReleaseMutex((PRKMUTEX)(v9 + 18), 0);
                v16 = v87;
                v105 = v75;
                goto LABEL_299;
              }
            }
LABEL_295:
            __fastfail(3u);
          }
LABEL_284:
          if ( *((_DWORD *)v6 + 4) == 1953656900 && *((_DWORD *)v6 + 5) == 2 )
            DxgkLogInternalTriageEvent(
              *((_QWORD *)v6 + 504),
              131077,
              -1,
              (unsigned int)L"Adapter AddDevice has completed with status %1",
              DeviceRegistryPaths,
              0,
              0,
              0,
              0);
          goto LABEL_287;
        }
        WdLogSingleEntry1(3);
        WdLogGlobalForLineNumber = 1131;
        v90 = 1;
        byte_14015F1E9 = 1;
      }
      if ( byte_14015EDD6 )
        DeviceExtension[1155] = 1;
      goto LABEL_222;
    }
    goto LABEL_163;
  }
  v89 = 0;
  v102 = 0;
  v12 = 0;
  if ( !RtlCompareUnicodeString(&String1, p_DriverName, 1u) )
  {
    v99 = 1;
    goto LABEL_72;
  }
  v99 = 0;
  if ( !RtlCompareUnicodeString(&v116, p_DriverName, 1u) || !RtlCompareUnicodeString(&v117, p_DriverName, 1u) )
  {
    v94 = 1;
    goto LABEL_72;
  }
  if ( !RtlCompareUnicodeString(&v118, p_DriverName, 1u) )
  {
    v103 = 1;
    goto LABEL_72;
  }
  LOBYTE(v13) = 1;
  v14 = DriverObject->DriverName.Buffer;
  if ( (wchar_t *)RtlFindUnicodeSubstring(p_DriverName, v119, v13) != v14 )
  {
    *(_DWORD *)&DestinationString.Length = 0;
    if ( (unsigned int)DxgkGetDeviceFamily(&DestinationString) != 5
      || (v100 = 1, ((*(_DWORD *)&DestinationString.Length - 192) & 0xFFFFFFFD) != 0) )
    {
      v100 = 0;
    }
    v97 = *((_BYTE *)v9 + 134);
    *(_DWORD *)&DestinationString.Length = 0;
    v112 = 0;
    memset(v113, 0, 0x68u);
    v18 = *((_QWORD *)v9 + 6);
    v113[1] = L"Start";
    LODWORD(v113[0]) = 292;
    v113[2] = &DestinationString;
    LODWORD(v113[3]) = 67108868;
    LODWORD(v113[5]) = 4;
    DeviceRegistryPaths = RtlQueryRegistryValuesEx(0, v18, &v112, 0, 0);
    if ( DeviceRegistryPaths < 0 )
    {
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 455;
      goto LABEL_19;
    }
    if ( *(_DWORD *)&DestinationString.Length != 3 )
    {
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 466;
      DeviceRegistryPaths = -1073741637;
LABEL_35:
      v19 = v98;
      goto LABEL_36;
    }
    v12 = 0;
LABEL_71:
    v3 = TargetDevice;
    goto LABEL_72;
  }
  Source1 = 0;
  DeviceRegistryPaths = DpiGetDevicePropertyString(v3, DevicePropertyHardwareID, (__int64)&ResultLength);
  if ( DeviceRegistryPaths >= 0 )
  {
    v17 = Source1;
    if ( ResultLength >= 0x24 && RtlCompareMemory(Source1, L"ROOT\\BasicDisplay", 0x24u) == 36 )
    {
      v89 = 1;
      if ( byte_14015EDD2 )
      {
        v88 = 0;
        DeviceRegistryPaths = -1073741637;
        WdLogSingleEntry1(4);
        WdLogGlobalForLineNumber = 408;
      }
    }
    if ( v17 )
      ExFreePoolWithTag(v17, 0);
    if ( DeviceRegistryPaths < 0 )
      goto LABEL_35;
    v12 = v89;
    v101 = 1;
    goto LABEL_71;
  }
  WdLogSingleEntry1(2);
  WdLogGlobalForLineNumber = 383;
LABEL_19:
  v16 = 0;
LABEL_298:
  v19 = v98;
LABEL_299:
  if ( v16 == 1 )
    KeReleaseMutex((PRKMUTEX)(v9 + 18), 0);
LABEL_36:
  if ( DeviceObjecta )
  {
    if ( v91 == 1 )
      DpiFdoResetFdo();
    if ( v6 )
    {
      v20 = (_DWORD *)*((_QWORD *)v6 + 185);
      if ( v20 && v20[2] == 1 )
      {
        ExFreePoolWithTag(v20, 0);
        *((_QWORD *)v6 + 185) = 0;
      }
      v21 = (_DWORD *)*((_QWORD *)v6 + 186);
      if ( v21 && v21[2] == 1 )
      {
        ExFreePoolWithTag(v21, 0);
        *((_QWORD *)v6 + 186) = 0;
      }
      if ( v19 == 1 )
        DpiAcpiUnregisterAcpiCallbacks(DeviceObjecta);
      v22 = (void (__fastcall *)(_QWORD))*((_QWORD *)v6 + 73);
      if ( v22 )
      {
        v22(*((_QWORD *)v6 + 71));
        memset(v6 + 560, 0, 0x40u);
      }
      v23 = (void (__fastcall *)(_QWORD))*((_QWORD *)v6 + 81);
      if ( v23 )
      {
        v23(*((_QWORD *)v6 + 79));
        *((_OWORD *)v6 + 39) = 0;
        *((_OWORD *)v6 + 40) = 0;
        *((_OWORD *)v6 + 41) = 0;
      }
      v24 = (void (__fastcall *)(_QWORD))*((_QWORD *)v6 + 87);
      if ( v24 )
      {
        v24(*((_QWORD *)v6 + 85));
        memset(v6 + 672, 0, 0xB8u);
      }
      v25 = (void (__fastcall *)(_QWORD))*((_QWORD *)v6 + 110);
      if ( v25 )
      {
        v25(*((_QWORD *)v6 + 108));
        memset(v6 + 856, 0, 0x58u);
      }
      RtlFreeUnicodeString((PUNICODE_STRING)v6 + 32);
      RtlFreeUnicodeString((PUNICODE_STRING)v6 + 33);
      v26 = (void *)*((_QWORD *)v6 + 139);
      if ( v26 )
      {
        ExFreePoolWithTag(v26, 0);
        *((_QWORD *)v6 + 139) = 0;
      }
    }
    if ( DeviceExtension )
    {
      v27 = (struct _ERESOURCE *)*((_QWORD *)DeviceExtension + 21);
      if ( v27 )
      {
        if ( v92 == 1 )
          ExDeleteResourceLite(v27);
        v28 = (_DWORD *)*((_QWORD *)DeviceExtension + 21);
        if ( v28[26] == 1 && v28 )
        {
          ExFreePoolWithTag(v28, 0);
          *((_QWORD *)DeviceExtension + 21) = 0;
        }
      }
      v29 = (struct _DEVICE_OBJECT *)*((_QWORD *)DeviceExtension + 20);
      if ( v29 )
        IoDetachDevice(v29);
    }
    IoDeleteDevice(DeviceObjecta);
    DeviceObjecta = 0;
  }
  if ( v93 == 1 )
  {
    DpiDxgkDdiRemoveDevice(v9, v109);
    v30 = v88;
  }
  else
  {
    v30 = v88;
    if ( !v88 )
      goto LABEL_312;
    if ( !*((_QWORD *)v9 + 168) )
      goto LABEL_310;
    DiagnosticInfoArgs = DxgAllocateDiagnosticInfoArgs(1);
    v79 = DiagnosticInfoArgs;
    if ( !DiagnosticInfoArgs )
      goto LABEL_310;
    v80 = *(_DWORD *)(DiagnosticInfoArgs + 216);
    v81 = TargetDevice;
    *(_QWORD *)DiagnosticInfoArgs = v109;
    if ( (*((int (__fastcall **)(struct _DEVICE_OBJECT *, __int64))v9 + 168))(v81, DiagnosticInfoArgs) >= 0 )
    {
      if ( *(_DWORD *)(v79 + 220) > v80 )
        *(_DWORD *)(v79 + 220) = 0;
      DxgCreateLiveDumpWithDriverBlob(
        v81,
        0x1B0u,
        *(int *)(v79 + 8),
        DeviceRegistryPaths,
        0,
        0,
        (struct _DXGKARG_COLLECTDIAGNOSTICINFO *)v79);
      v30 = 0;
    }
    DxgFreeDiagnosticInfoArgs((struct _DXGKARG_COLLECTDIAGNOSTICINFO *)v79);
  }
  if ( !v30 )
    goto LABEL_312;
LABEL_310:
  if ( DeviceRegistryPaths != -1071774664 )
  {
    LOBYTE(Exclusive) = 0;
    DxgCreateLiveDumpWithWdLogs(403, 2049, DeviceRegistryPaths, 0, 0, Exclusive);
  }
LABEL_312:
  memset(v125, 0, sizeof(v125));
  v82 = DxgkDiagCalcDuration1us(&v120);
  v125[0] = 0x4000000006uLL;
  *(_QWORD *)((char *)&v125[3] + 4) = __PAIR64__(v82, v105);
  memset(&v125[1], 0, 28);
  LODWORD(v125[3]) = 34;
  HIDWORD(v125[3]) = DeviceRegistryPaths;
  DxgkWriteDiagEntry((struct _DXGK_DIAG_HEADER *)v125, 0x100000000uLL);
  if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
    McTemplateK0ppq_EtwWriteTransfer(
      v83,
      (unsigned int)EventExitDpiAddDevice,
      v84,
      (_DWORD)DriverObject,
      (char)TargetDevice,
      DeviceRegistryPaths);
  return (unsigned int)DeviceRegistryPaths;
}

```

## disassembly

```asm
0x14029e9b0  mov     [rsp-8+arg_10], rbx
0x14029e9b5  push    rbp
0x14029e9b6  push    rsi
0x14029e9b7  push    rdi
0x14029e9b8  push    r12
0x14029e9ba  push    r13
0x14029e9bc  push    r14
0x14029e9be  push    r15
0x14029e9c0  lea     rbp, [rsp-390h]
0x14029e9c8  sub     rsp, 490h
0x14029e9cf  mov     rax, cs:__security_cookie
0x14029e9d6  xor     rax, rsp
0x14029e9d9  mov     [rbp+3C0h+var_38], rax
0x14029e9e0  movups  xmm0, xmmword ptr cs:aDriverVgpu; "\\Driver\\VGPU"
0x14029e9e7  xor     eax, eax
0x14029e9e9  xor     r15d, r15d
0x14029e9ec  cmp     cs:bTracingEnabled, r15b
0x14029e9f3  mov     rsi, rdx
0x14029e9f6  movups  xmm1, xmmword ptr cs:aDriverVgpu+0Ah; "er\\VGPU"
0x14029e9fd  mov     [rbp+3C0h+var_320], rax
0x14029ea04  mov     rdi, rcx
0x14029ea07  movups  xmmword ptr [rbp+3C0h+var_160], xmm0
0x14029ea0e  mov     [rbp+3C0h+var_318], eax
0x14029ea14  lea     r12d, [r15+1]
0x14029ea18  movups  xmm0, xmmword ptr cs:aDriverWddmwarp; "\\Driver\\WddmWarp"
0x14029ea1f  mov     [rsp+4C0h+var_46D], al
0x14029ea23  mov     ebx, r15d
0x14029ea26  mov     [rsp+4C0h+var_453], al
0x14029ea2a  mov     r14d, r15d
0x14029ea2d  movups  [rbp+3C0h+var_188], xmm0
0x14029ea34  lea     rax, [rbp+3C0h+var_160]
0x14029ea3b  mov     [rsp+4C0h+TargetDevice], rdx
0x14029ea40  movups  xmm0, xmmword ptr cs:aDriverBasicren; "\\Driver\\BasicRender"
0x14029ea47  mov     [rbp+3C0h+var_360.Buffer], rax
0x14029ea4b  movzx   eax, word ptr cs:aDriverWddmwarp+20h; ""
0x14029ea52  movups  [rbp+3C0h+var_140], xmm0
0x14029ea59  mov     [rbp+3C0h+var_168], ax
0x14029ea60  lea     rax, [rbp+3C0h+var_188]
0x14029ea67  movsd   xmm0, qword ptr cs:aDriverBasicren+20h; "der"
0x14029ea6f  movups  xmmword ptr [rbp+3C0h+var_160+0Ah], xmm1
0x14029ea76  mov     [rbp+3C0h+String1.Buffer], rax
0x14029ea7a  lea     rax, [rbp+3C0h+var_140]
0x14029ea81  movups  xmm1, xmmword ptr cs:aDriverWddmwarp+10h; "WddmWarp"
0x14029ea88  mov     [rbp+3C0h+var_398], rax
0x14029ea8c  lea     rax, [rbp+3C0h+var_118]
0x14029ea93  movsd   [rbp+3C0h+var_120], xmm0
0x14029ea9b  movups  xmm0, xmmword ptr cs:aDriverBasicdis; "\\Driver\\BasicDisplay"
0x14029eaa2  mov     [rbp+3C0h+var_348], rax
0x14029eaa6  lea     rax, [rbp+3C0h+var_E8]
0x14029eaad  movups  [rbp+3C0h+var_178], xmm1
0x14029eab4  mov     [rbp+3C0h+var_380.Buffer], rax
0x14029eab8  movups  xmm1, xmmword ptr cs:aDriverBasicren+10h; "BasicRender"
0x14029eabf  mov     eax, dword ptr cs:aDriverVirtualc+40h; "r"
0x14029eac5  movups  [rbp+3C0h+var_118], xmm0
0x14029eacc  mov     [rbp+3C0h+var_70], eax
0x14029ead2  lea     rax, [rbp+3C0h+var_B0]
0x14029ead9  movups  xmm0, xmmword ptr cs:aDriverBasicdis+1Ah; "Display"
0x14029eae0  mov     [rbp+3C0h+DriverObject], rcx
0x14029eae4  movups  [rbp+3C0h+var_130], xmm1
0x14029eaeb  mov     [rbp+3C0h+var_438], r15
0x14029eaef  movups  xmm1, xmmword ptr cs:aDriverBasicdis+10h; "BasicDisplay"
0x14029eaf6  mov     [rsp+4C0h+var_46A], r15b
0x14029eafb  mov     [rsp+4C0h+DeviceObject], r15
0x14029eb00  movups  xmmword ptr [rbp+3C0h+var_108], xmm1
0x14029eb07  mov     [rsp+4C0h+ResultLength], r15d
0x14029eb0c  movups  xmm1, xmmword ptr cs:aDriverVirtualr+10h; "VirtualRender"
0x14029eb13  mov     [rsp+4C0h+var_46F], r12b
0x14029eb18  movups  xmmword ptr [rbp+3C0h+var_108+0Ah], xmm0
0x14029eb1f  mov     byte ptr [rsp+4C0h+var_45C], r15b
0x14029eb24  movups  xmm0, xmmword ptr cs:aDriverVirtualr; "\\Driver\\VirtualRender"
0x14029eb2b  mov     [rsp+4C0h+var_46C], r15b
0x14029eb30  movups  xmmword ptr [rbp+3C0h+var_D8], xmm1
0x14029eb37  mov     [rsp+4C0h+var_470], r15b
0x14029eb3c  movaps  xmm1, xmmword ptr cs:aDriverVirtualc+10h; "VirtualComputeAccelerator"
0x14029eb43  movups  [rbp+3C0h+var_E8], xmm0
0x14029eb4a  mov     [rsp+4C0h+var_46B], r15b
0x14029eb4f  movups  xmm0, xmmword ptr cs:aDriverVirtualr+1Ch; "lRender"
0x14029eb56  mov     [rsp+4C0h+var_450], 3
0x14029eb5e  movaps  [rbp+3C0h+var_A0], xmm1
0x14029eb65  movaps  xmm1, xmmword ptr cs:aDriverVirtualc+30h; "celerator"
0x14029eb6c  movups  xmmword ptr [rbp+3C0h+var_D8+0Ch], xmm0
0x14029eb73  mov     qword ptr [rbp+3C0h+var_360.Length], 1A0018h
0x14029eb7b  movaps  xmm0, xmmword ptr cs:aDriverVirtualc; "\\Driver\\VirtualComputeAccelerator"
0x14029eb82  movaps  [rbp+3C0h+var_B0], xmm0
0x14029eb89  movaps  xmm0, xmmword ptr cs:aDriverVirtualc+20h; "omputeAccelerator"
0x14029eb90  movaps  [rbp+3C0h+var_90], xmm0
0x14029eb97  mov     qword ptr [rbp+3C0h+String1.Length], 220020h
0x14029eb9f  mov     [rbp+3C0h+var_3A0], 280026h
0x14029eba7  mov     [rbp+3C0h+var_350], 2A0028h
0x14029ebaf  mov     qword ptr [rbp+3C0h+var_380.Length], 2C002Ah
0x14029ebb7  movaps  [rbp+3C0h+var_80], xmm1
0x14029ebbe  mov     qword ptr [rbp+3C0h+var_370.Length], 440042h
0x14029ebc6  mov     [rbp+3C0h+var_370.Buffer], rax
0x14029ebca  jz      short loc_14029EBEE
0x14029ebcc  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+1, r12b
0x14029ebd3  jz      short loc_14029EBEE
0x14029ebd5  mov     dword ptr [rsp+4C0h+Exclusive], r15d
0x14029ebda  mov     r9, rcx
0x14029ebdd  mov     qword ptr [rsp+4C0h+DeviceCharacteristics], rdx
0x14029ebe2  lea     rdx, EventEnterDpiAddDevice
0x14029ebe9  call    McTemplateK0ppq_EtwWriteTransfer
0x14029ebee  mov     rax, 0FFFFF78000000320h
0x14029ebf8  mov     rdx, rdi; ClientIdentificationAddress
0x14029ebfb  mov     rcx, rdi; DriverObject
0x14029ebfe  mov     rax, [rax]
0x14029ec01  mov     [rbp+3C0h+var_340], rax
0x14029ec08  call    cs:__imp_IoGetDriverObjectExtension
0x14029ec0f  nop     dword ptr [rax+rax+00h]
0x14029ec14  mov     r13, rax
0x14029ec17  test    rax, rax
0x14029ec1a  jz      loc_1402A0A5E
0x14029ec20  cmp     dword ptr [rax+10h], 74727044h
0x14029ec27  jnz     loc_1402A0A5E
0x14029ec2d  cmp     [rax+14h], r12d
0x14029ec31  jnz     loc_1402A0A5E
0x14029ec37  mov     [rsp+4C0h+var_456], r15b
0x14029ec3c  lea     rdx, [rbp+3C0h+var_3A0]
0x14029ec40  mov     [rsp+4C0h+var_454], r15b
0x14029ec45  mov     r8b, r12b
0x14029ec48  mov     [rsp+4C0h+var_460], r15b
0x14029ec4d  mov     [rsp+4C0h+var_457], r15b
0x14029ec52  mov     [rsp+4C0h+var_469], r15b
0x14029ec57  lea     r15, [rdi+38h]
0x14029ec5b  mov     rdi, [r15+8]
0x14029ec5f  mov     rcx, r15
0x14029ec62  call    cs:__imp_RtlFindUnicodeSubstring
0x14029ec69  nop     dword ptr [rax+rax+00h]
0x14029ec6e  mov     r12, 0FFFFFFFFC00000BBh
0x14029ec75  cmp     rax, rdi
0x14029ec78  jnz     short loc_14029EC93
0x14029ec7a  mov     eax, 1
0x14029ec7f  mov     dil, al
0x14029ec82  mov     [rsp+4C0h+var_46E], al
0x14029ec86  mov     [rsp+4C0h+var_455], al
0x14029ec8a  mov     [rsp+4C0h+var_458], al
0x14029ec8e  jmp     loc_14029F153
0x14029ec93  xor     eax, eax
0x14029ec95  lea     rcx, [rbp+3C0h+String1]; String1
0x14029ec99  mov     r8b, 1; CaseInSensitive
0x14029ec9c  mov     [rsp+4C0h+var_46E], al
0x14029eca0  mov     rdx, r15; String2
0x14029eca3  mov     [rsp+4C0h+var_455], al
0x14029eca7  mov     dil, al
0x14029ecaa  call    cs:__imp_RtlCompareUnicodeString
0x14029ecb1  nop     dword ptr [rax+rax+00h]
0x14029ecb6  xor     ecx, ecx
0x14029ecb8  test    eax, eax
0x14029ecba  jnz     short loc_14029ECC6
0x14029ecbc  mov     [rsp+4C0h+var_458], 1
0x14029ecc1  jmp     loc_14029F153
0x14029ecc6  mov     [rsp+4C0h+var_458], cl
0x14029ecca  mov     r8b, 1; CaseInSensitive
0x14029eccd  lea     rcx, [rbp+3C0h+var_380]; String1
0x14029ecd1  mov     rdx, r15; String2
0x14029ecd4  call    cs:__imp_RtlCompareUnicodeString
0x14029ecdb  nop     dword ptr [rax+rax+00h]
0x14029ece0  test    eax, eax
0x14029ece2  jz      short loc_14029ECFE
0x14029ece4  mov     r8b, 1; CaseInSensitive
0x14029ece7  lea     rcx, [rbp+3C0h+var_370]; String1
0x14029eceb  mov     rdx, r15; String2
0x14029ecee  call    cs:__imp_RtlCompareUnicodeString
0x14029ecf5  nop     dword ptr [rax+rax+00h]
0x14029ecfa  test    eax, eax
0x14029ecfc  jnz     short loc_14029ED08
0x14029ecfe  mov     [rsp+4C0h+var_469], 1
0x14029ed03  jmp     loc_14029F153
0x14029ed08  mov     r8b, 1; CaseInSensitive
0x14029ed0b  lea     rcx, [rbp+3C0h+var_360]; String1
0x14029ed0f  mov     rdx, r15; String2
0x14029ed12  call    cs:__imp_RtlCompareUnicodeString
0x14029ed19  nop     dword ptr [rax+rax+00h]
0x14029ed1e  test    eax, eax
0x14029ed20  jnz     short loc_14029ED2C
0x14029ed22  mov     [rsp+4C0h+var_454], 1
0x14029ed27  jmp     loc_14029F153
0x14029ed2c  mov     rdi, [rbp+3C0h+DriverObject]
0x14029ed30  lea     rdx, [rbp+3C0h+var_350]
0x14029ed34  mov     r8b, 1
0x14029ed37  mov     rcx, r15
0x14029ed3a  mov     rdi, [rdi+40h]
0x14029ed3e  call    cs:__imp_RtlFindUnicodeSubstring
0x14029ed45  nop     dword ptr [rax+rax+00h]
0x14029ed4a  cmp     rax, rdi
0x14029ed4d  jnz     loc_14029EE2D
0x14029ed53  xor     edi, edi
0x14029ed55  lea     rax, [rsp+4C0h+ResultLength]
0x14029ed5a  lea     r9, [rbp+3C0h+Source1]
0x14029ed5e  mov     [rbp+3C0h+Source1], rdi
0x14029ed62  mov     r8d, 100h
0x14029ed68  mov     qword ptr [rsp+4C0h+DeviceCharacteristics], rax; __int64
0x14029ed6d  mov     rcx, rsi; DeviceObject
0x14029ed70  lea     edx, [rdi+1]; DeviceProperty
0x14029ed73  call    DpiGetDevicePropertyString
0x14029ed78  movsxd  rsi, eax
0x14029ed7b  test    eax, eax
0x14029ed7d  jns     short loc_14029EDA2
0x14029ed7f  mov     rdx, rsi
0x14029ed82  lea     ecx, [rdi+2]
0x14029ed85  call    cs:__imp_WdLogSingleEntry1
0x14029ed8c  nop     dword ptr [rax+rax+00h]
0x14029ed91  mov     cs:WdLogGlobalForLineNumber, 17Fh
0x14029ed9b  mov     al, bl
0x14029ed9d  jmp     loc_1402A0A9A
0x14029eda2  cmp     [rsp+4C0h+ResultLength], 24h ; '$'
0x14029eda7  mov     rdi, [rbp+3C0h+Source1]
0x14029edab  jb      short loc_14029EDFE
0x14029edad  mov     r8d, 24h ; '$'; Length
0x14029edb3  lea     rdx, aRootBasicdispl; "ROOT\\BasicDisplay"
0x14029edba  mov     rcx, rdi; Source1
0x14029edbd  call    cs:__imp_RtlCompareMemory
0x14029edc4  nop     dword ptr [rax+rax+00h]
0x14029edc9  cmp     rax, 24h ; '$'
0x14029edcd  jnz     short loc_14029EDFE
0x14029edcf  cmp     cs:byte_14015EDD2, bl
0x14029edd5  mov     [rsp+4C0h+var_46E], 1
0x14029edda  jz      short loc_14029EDFE
0x14029eddc  mov     [rsp+4C0h+var_46F], bl
0x14029ede0  mov     esi, r12d
0x14029ede3  xor     edx, edx
0x14029ede5  lea     ecx, [rax-20h]
0x14029ede8  call    cs:__imp_WdLogSingleEntry1
0x14029edef  nop     dword ptr [rax+rax+00h]
0x14029edf4  mov     cs:WdLogGlobalForLineNumber, 198h
0x14029edfe  test    rdi, rdi
0x14029ee01  jz      short loc_14029EE14
0x14029ee03  xor     edx, edx; Tag
0x14029ee05  mov     rcx, rdi; P
0x14029ee08  call    cs:__imp_ExFreePoolWithTag
0x14029ee0f  nop     dword ptr [rax+rax+00h]
0x14029ee14  xor     edi, edi
0x14029ee16  test    esi, esi
0x14029ee18  js      loc_14029EF2A
0x14029ee1e  mov     dil, [rsp+4C0h+var_46E]
0x14029ee23  mov     [rsp+4C0h+var_456], 1
0x14029ee28  jmp     loc_14029F14E
0x14029ee2d  xor     edi, edi
0x14029ee2f  lea     rcx, [rbp+3C0h+DestinationString]
0x14029ee36  mov     dword ptr [rbp+3C0h+DestinationString.Length], edi
0x14029ee3c  call    DxgkGetDeviceFamily
0x14029ee41  cmp     eax, 5
0x14029ee44  jnz     short loc_14029EE5D
0x14029ee46  mov     eax, dword ptr [rbp+3C0h+DestinationString.Length]
0x14029ee4c  add     eax, 0FFFFFF40h
0x14029ee51  mov     [rsp+4C0h+var_457], 1
0x14029ee56  test    eax, 0FFFFFFFDh
0x14029ee5b  jz      short loc_14029EE62
0x14029ee5d  mov     [rsp+4C0h+var_457], dil
0x14029ee62  mov     al, [r13+86h]
0x14029ee69  lea     rcx, [rbp+3C0h+var_418]; void *
0x14029ee6d  xor     edx, edx; Val
0x14029ee6f  mov     [rsp+4C0h+var_460], al
0x14029ee73  mov     dword ptr [rbp+3C0h+DestinationString.Length], edi
0x14029ee79  mov     [rbp+3C0h+var_420], rdi
0x14029ee7d  lea     r8d, [rdx+68h]; Size
0x14029ee81  call    memset
0x14029ee86  mov     rdx, [r13+30h]
0x14029ee8a  lea     rax, aStart; "Start"
0x14029ee91  mov     [rbp+3C0h+var_410], rax
0x14029ee95  lea     r8, [rbp+3C0h+var_420]
0x14029ee99  lea     rax, [rbp+3C0h+DestinationString]
0x14029eea0  mov     dword ptr [rbp+3C0h+var_418], 124h
0x14029eea7  xor     r9d, r9d
0x14029eeaa  mov     [rbp+3C0h+var_408], rax
0x14029eeae  xor     ecx, ecx
0x14029eeb0  mov     dword ptr [rbp+3C0h+var_400], 4000004h
0x14029eeb7  mov     dword ptr [rbp+3C0h+var_3F0], 4
0x14029eebe  mov     qword ptr [rsp+4C0h+DeviceCharacteristics], rdi
0x14029eec3  call    cs:__imp_RtlQueryRegistryValuesEx
0x14029eeca  nop     dword ptr [rax+rax+00h]
0x14029eecf  movsxd  rsi, eax
0x14029eed2  test    eax, eax
0x14029eed4  jns     short loc_14029EEF9
0x14029eed6  mov     rdx, rsi
0x14029eed9  mov     ecx, 2
0x14029eede  call    cs:__imp_WdLogSingleEntry1
0x14029eee5  nop     dword ptr [rax+rax+00h]
0x14029eeea  mov     cs:WdLogGlobalForLineNumber, 1C7h
0x14029eef4  jmp     loc_14029ED9B
0x14029eef9  cmp     dword ptr [rbp+3C0h+DestinationString.Length], 3
0x14029ef00  jz      loc_14029F14B
0x14029ef06  mov     edx, dword ptr [rbp+3C0h+DestinationString.Length]
0x14029ef0c  mov     ecx, 2
0x14029ef11  call    cs:__imp_WdLogSingleEntry1
0x14029ef18  nop     dword ptr [rax+rax+00h]
0x14029ef1d  mov     cs:WdLogGlobalForLineNumber, 1D2h
0x14029ef27  mov     rsi, r12
0x14029ef2a  mov     r15d, [rsp+4C0h+var_45C]
0x14029ef2f  mov     r12d, 1
0x14029ef35  mov     rcx, [rsp+4C0h+DeviceObject]
0x14029ef3a  test    rcx, rcx
0x14029ef3d  jz      loc_14029F12A
0x14029ef43  cmp     [rsp+4C0h+var_46C], r12b
0x14029ef48  jnz     short loc_14029EF4F
0x14029ef4a  call    DpiFdoResetFdo
0x14029ef4f  test    r14, r14
0x14029ef52  jz      loc_14029F0B1
0x14029ef58  mov     rcx, [r14+5C8h]; P
0x14029ef5f  test    rcx, rcx
0x14029ef62  jz      short loc_14029EF7F
  ... truncated ...
```
