# DpiAddDevice

- ea: `0x1402a5360`
- end: `0x1402a761f`
- name: `DpiAddDevice`
- size: `8895`
- prototype: `__int64 __fastcall(struct _DRIVER_OBJECT *ClientIdentificationAddress, PDEVICE_OBJECT DeviceObject, int)`
- caller_count: `0`
- callee_count: `35`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x14001b9c0`
- `0x140040908`
- `0x14004094c`
- `0x140047a70`
- `0x14005f160`
- `0x140081d5c`
- `0x14008d9cc`
- `0x1400a0ba8`
- `0x1400a0bd0`
- `0x1400a0cb0`
- `0x1400a1000`
- `0x140196118`
- `0x14019b644`
- `0x14020bbb4`
- `0x14020bcb0`
- `0x14020bef0`
- `0x1402a5360`
- `0x1402a9f30`
- `0x1402aefa4`
- `0x1402b1eb8`
- `0x1402b8144`
- `0x1402b8594`
- `0x1402b89c4`
- `0x1402b8d94`
- `0x1402b9228`
- `0x1402c0fc4`
- `0x1402c291c`
- `0x1402c3144`
- `0x1402c3a00`
- `0x1402c3c64`
- `0x1402c4274`
- `0x140365a4c`
- `0x1403cfdc0`
- `0x1403e6c70`
- `0x1403f441c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1402a57b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a591c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a5943`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a5a4e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a5a99`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a6aed`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a6bbb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a57b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a591c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a5943`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a5a4e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a5a99`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a6aed`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a6bbb`
- `ntoskrnl!ExAllocatePool2` at `0x1402a6360`
- `ntoskrnl!ExAllocatePool2` at `0x1402a6ec4`
- `ntoskrnl!ExAllocatePool2` at `0x1402a6f8a`
- `ntoskrnl!ExAllocatePool2` at `0x1402a6ffa`
- `ntoskrnl!ExAllocatePool2` at `0x1402a6360`
- `ntoskrnl!ExAllocatePool2` at `0x1402a6ec4`
- `ntoskrnl!ExAllocatePool2` at `0x1402a6f8a`
- `ntoskrnl!ExAllocatePool2` at `0x1402a6ffa`
- `ntoskrnl!KeInitializeSpinLock` at `0x1402a6c51`
- `ntoskrnl!KeInitializeSpinLock` at `0x1402a6fd7`
- `ntoskrnl!KeInitializeSpinLock` at `0x1402a7047`
- `ntoskrnl!KeInitializeSpinLock` at `0x1402a6c51`
- `ntoskrnl!KeInitializeSpinLock` at `0x1402a6fd7`
- `ntoskrnl!KeInitializeSpinLock` at `0x1402a7047`
- `ntoskrnl!KeInitializeEvent` at `0x1402a6d26`
- `ntoskrnl!KeInitializeEvent` at `0x1402a6d3e`
- `ntoskrnl!KeInitializeEvent` at `0x1402a6d56`
- `ntoskrnl!KeInitializeEvent` at `0x1402a6d8c`
- `ntoskrnl!KeInitializeEvent` at `0x1402a6d26`
- `ntoskrnl!KeInitializeEvent` at `0x1402a6d3e`
- `ntoskrnl!KeInitializeEvent` at `0x1402a6d56`
- `ntoskrnl!KeInitializeEvent` at `0x1402a6d8c`
- `ntoskrnl!KeInitializeDpc` at `0x1402a6cba`
- `ntoskrnl!KeInitializeDpc` at `0x1402a6cba`
- `ntoskrnl!ExDeleteResourceLite` at `0x1402a5a79`
- `ntoskrnl!ExDeleteResourceLite` at `0x1402a5a79`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1402a5873`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1402a5873`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402a5a1f`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402a5a32`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402a5a1f`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402a5a32`
- `ntoskrnl!ExInitializeResourceLite` at `0x1402a6f1c`
- `ntoskrnl!ExInitializeResourceLite` at `0x1402a6f1c`
- `ntoskrnl!ObfDereferenceObject` at `0x1402a6268`
- `ntoskrnl!ObfDereferenceObject` at `0x1402a67fb`
- `ntoskrnl!ObfDereferenceObject` at `0x1402a6268`
- `ntoskrnl!ObfDereferenceObject` at `0x1402a67fb`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402a5ed2`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402a5ed2`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1402a565a`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1402a5684`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1402a569e`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1402a56c2`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1402a565a`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1402a5684`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1402a569e`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1402a56c2`
- `ntoskrnl!RtlCompareMemory` at `0x1402a576d`
- `ntoskrnl!RtlCompareMemory` at `0x1402a62bd`
- `ntoskrnl!RtlCompareMemory` at `0x1402a657d`
- `ntoskrnl!RtlCompareMemory` at `0x1402a6844`
- `ntoskrnl!RtlCompareMemory` at `0x1402a68c4`
- `ntoskrnl!RtlCompareMemory` at `0x1402a576d`
- `ntoskrnl!RtlCompareMemory` at `0x1402a62bd`
- `ntoskrnl!RtlCompareMemory` at `0x1402a657d`
- `ntoskrnl!RtlCompareMemory` at `0x1402a6844`
- `ntoskrnl!RtlCompareMemory` at `0x1402a68c4`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x1402a624b`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x1402a67d9`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x1402a624b`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x1402a67d9`
- `ntoskrnl!IoDeleteDevice` at `0x1402a5ac9`
- `ntoskrnl!IoDeleteDevice` at `0x1402a5ac9`
- `ntoskrnl!IoCreateDevice` at `0x1402a5ce8`
- `ntoskrnl!IoCreateDevice` at `0x1402a5ce8`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402a6e25`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402a737c`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402a6e25`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402a737c`
- `ntoskrnl!RtlGetProductInfo` at `0x1402a7222`
- `ntoskrnl!RtlGetProductInfo` at `0x1402a7222`
- `ntoskrnl!KeReleaseMutex` at `0x1402a7085`
- `ntoskrnl!KeReleaseMutex` at `0x1402a73c6`
- `ntoskrnl!KeReleaseMutex` at `0x1402a7464`
- `ntoskrnl!KeReleaseMutex` at `0x1402a7085`
- `ntoskrnl!KeReleaseMutex` at `0x1402a73c6`
- `ntoskrnl!KeReleaseMutex` at `0x1402a7464`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x1402a55b8`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x1402a55b8`
- `ntoskrnl!RtlFindUnicodeSubstring` at `0x1402a5612`
- `ntoskrnl!RtlFindUnicodeSubstring` at `0x1402a56ee`
- `ntoskrnl!RtlFindUnicodeSubstring` at `0x1402a5612`
- `ntoskrnl!RtlFindUnicodeSubstring` at `0x1402a56ee`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x1402a5d91`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x1402a5d91`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x1402a5db1`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x1402a5db1`
- `ntoskrnl!IoGetDevicePropertyData` at `0x1402a5eaa`
- `ntoskrnl!IoGetDevicePropertyData` at `0x1402a5eaa`
- `ntoskrnl!IoGetDeviceProperty` at `0x1402a60c0`
- `ntoskrnl!IoGetDeviceProperty` at `0x1402a6114`
- `ntoskrnl!IoGetDeviceProperty` at `0x1402a6177`
- `ntoskrnl!IoGetDeviceProperty` at `0x1402a60c0`
- `ntoskrnl!IoGetDeviceProperty` at `0x1402a6114`
- `ntoskrnl!IoGetDeviceProperty` at `0x1402a6177`
- `ntoskrnl!KeInitializeMutex` at `0x1402a6ccf`
- `ntoskrnl!KeInitializeMutex` at `0x1402a6ce4`
- `ntoskrnl!KeInitializeMutex` at `0x1402a6f5e`
- `ntoskrnl!KeInitializeMutex` at `0x1402a6ccf`
- `ntoskrnl!KeInitializeMutex` at `0x1402a6ce4`
- `ntoskrnl!KeInitializeMutex` at `0x1402a6f5e`
- `ntoskrnl!RtlGetVersion` at `0x1402a71e4`
- `ntoskrnl!RtlGetVersion` at `0x1402a71e4`
- `ntoskrnl!ExGetFirmwareType` at `0x1402a723e`
- `ntoskrnl!ExGetFirmwareType` at `0x1402a723e`
- `ntoskrnl!IoDetachDevice` at `0x1402a5ab8`
- `ntoskrnl!IoDetachDevice` at `0x1402a5ab8`
- `watchdog!WdLogSingleEntry2` at `0x1402a5b5d`
- `watchdog!WdLogSingleEntry2` at `0x1402a5bff`
- `watchdog!WdLogSingleEntry2` at `0x1402a5c44`
- `watchdog!WdLogSingleEntry2` at `0x1402a70fe`
- `watchdog!WdLogSingleEntry2` at `0x1402a714f`
- `watchdog!WdLogSingleEntry2` at `0x1402a5b5d`
- `watchdog!WdLogSingleEntry2` at `0x1402a5bff`
- `watchdog!WdLogSingleEntry2` at `0x1402a5c44`
- `watchdog!WdLogSingleEntry2` at `0x1402a70fe`
- `watchdog!WdLogSingleEntry2` at `0x1402a714f`
- `watchdog!WdLogSingleEntry3` at `0x1402a7423`
- `watchdog!WdLogSingleEntry3` at `0x1402a7423`
- `watchdog!WdLogSingleEntry1` at `0x1402a5735`
- `watchdog!WdLogSingleEntry1` at `0x1402a5798`
- `watchdog!WdLogSingleEntry1` at `0x1402a588e`
- `watchdog!WdLogSingleEntry1` at `0x1402a58c1`
- `watchdog!WdLogSingleEntry1` at `0x1402a5b18`
- `watchdog!WdLogSingleEntry1` at `0x1402a5ba1`
- `watchdog!WdLogSingleEntry1` at `0x1402a5c79`
- `watchdog!WdLogSingleEntry1` at `0x1402a5d03`
- `watchdog!WdLogSingleEntry1` at `0x1402a5dd7`
- `watchdog!WdLogSingleEntry1` at `0x1402a5fdd`
- `watchdog!WdLogSingleEntry1` at `0x1402a60d8`
- `watchdog!WdLogSingleEntry1` at `0x1402a613b`
- `watchdog!WdLogSingleEntry1` at `0x1402a619a`
- `watchdog!WdLogSingleEntry1` at `0x1402a61de`
- `watchdog!WdLogSingleEntry1` at `0x1402a6217`
- `watchdog!WdLogSingleEntry1` at `0x1402a62db`
- `watchdog!WdLogSingleEntry1` at `0x1402a6336`
- `watchdog!WdLogSingleEntry1` at `0x1402a6387`
- `watchdog!WdLogSingleEntry1` at `0x1402a6492`
- `watchdog!WdLogSingleEntry1` at `0x1402a64f9`
- `watchdog!WdLogSingleEntry1` at `0x1402a6552`
- `watchdog!WdLogSingleEntry1` at `0x1402a65ae`
- `watchdog!WdLogSingleEntry1` at `0x1402a65d8`
- `watchdog!WdLogSingleEntry1` at `0x1402a666a`
- `watchdog!WdLogSingleEntry1` at `0x1402a6705`
- `watchdog!WdLogSingleEntry1` at `0x1402a67a2`
- `watchdog!WdLogSingleEntry1` at `0x1402a6817`
- `watchdog!WdLogSingleEntry1` at `0x1402a685e`
- `watchdog!WdLogSingleEntry1` at `0x1402a6945`
- `watchdog!WdLogSingleEntry1` at `0x1402a6bd0`
- `watchdog!WdLogSingleEntry1` at `0x1402a6bf1`
- `watchdog!WdLogSingleEntry1` at `0x1402a6c2f`
- `watchdog!WdLogSingleEntry1` at `0x1402a6dc8`
- `watchdog!WdLogSingleEntry1` at `0x1402a6e5f`
- `watchdog!WdLogSingleEntry1` at `0x1402a6ee8`
- `watchdog!WdLogSingleEntry1` at `0x1402a6f35`
- `watchdog!WdLogSingleEntry1` at `0x1402a6fae`
- `watchdog!WdLogSingleEntry1` at `0x1402a701e`
- `watchdog!WdLogSingleEntry1` at `0x1402a72b3`
- `watchdog!WdLogSingleEntry1` at `0x1402a5735`
- `watchdog!WdLogSingleEntry1` at `0x1402a5798`
- `watchdog!WdLogSingleEntry1` at `0x1402a588e`
- `watchdog!WdLogSingleEntry1` at `0x1402a58c1`
- `watchdog!WdLogSingleEntry1` at `0x1402a5b18`
- `watchdog!WdLogSingleEntry1` at `0x1402a5ba1`
- `watchdog!WdLogSingleEntry1` at `0x1402a5c79`
- `watchdog!WdLogSingleEntry1` at `0x1402a5d03`
- `watchdog!WdLogSingleEntry1` at `0x1402a5dd7`
- `watchdog!WdLogSingleEntry1` at `0x1402a5fdd`
- `watchdog!WdLogSingleEntry1` at `0x1402a60d8`
- `watchdog!WdLogSingleEntry1` at `0x1402a613b`
- `watchdog!WdLogSingleEntry1` at `0x1402a619a`
- `watchdog!WdLogSingleEntry1` at `0x1402a61de`
- `watchdog!WdLogSingleEntry1` at `0x1402a6217`
- `watchdog!WdLogSingleEntry1` at `0x1402a62db`
- `watchdog!WdLogSingleEntry1` at `0x1402a6336`
- `watchdog!WdLogSingleEntry1` at `0x1402a6387`
- `watchdog!WdLogSingleEntry1` at `0x1402a6492`
- `watchdog!WdLogSingleEntry1` at `0x1402a64f9`
- `watchdog!WdLogSingleEntry1` at `0x1402a6552`
- `watchdog!WdLogSingleEntry1` at `0x1402a65ae`
- `watchdog!WdLogSingleEntry1` at `0x1402a65d8`
- `watchdog!WdLogSingleEntry1` at `0x1402a666a`
- `watchdog!WdLogSingleEntry1` at `0x1402a6705`
- `watchdog!WdLogSingleEntry1` at `0x1402a67a2`
- `watchdog!WdLogSingleEntry1` at `0x1402a6817`

## string_xrefs

- `0x1402a552b`: `\Driver\VirtualComputeAccelerator`
- `0x1402a5e39`: `ComputeAccelerator`
- `0x1402a72e5`: `Adapter AddDevice has completed with status %1`

## pseudocode

```c
__int64 __fastcall DpiAddDevice(
        struct _DRIVER_OBJECT *ClientIdentificationAddress,
        PDEVICE_OBJECT DeviceObject,
        int a3)
{
  struct _DEVICE_OBJECT *started; // rsi
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
  int v15; // eax
  char v16; // al
  void *v17; // rdi
  __int64 v18; // rdx
  int v19; // eax
  char v20; // r15
  _DWORD *v21; // rcx
  _DWORD *v22; // rcx
  void (__fastcall *v23)(_QWORD); // rax
  void (__fastcall *v24)(_QWORD); // rax
  void (__fastcall *v25)(_QWORD); // rax
  void (__fastcall *v26)(_QWORD); // rax
  void *v27; // rcx
  struct _ERESOURCE *v28; // rcx
  _DWORD *v29; // rcx
  struct _DEVICE_OBJECT *v30; // rcx
  char v31; // r15
  ULONG v32; // edi
  __int64 v33; // rdx
  int v34; // eax
  NTSTATUS v35; // eax
  struct _DEVICE_OBJECT *v36; // rdi
  PDEVICE_OBJECT v37; // rax
  struct _DEVICE_OBJECT *v38; // rcx
  int DeviceRegistryPaths; // eax
  bool v40; // al
  struct _DEVICE_OBJECT *v41; // rcx
  int v42; // eax
  int v43; // ecx
  NTSTATUS DeviceProperty; // eax
  _DWORD *v45; // rdi
  NTSTATUS v46; // eax
  GUID *v47; // rdi
  int v48; // eax
  char v49; // al
  struct _DEVICE_OBJECT *AttachedDeviceReference; // rdi
  struct _DEVICE_OBJECT *v51; // rsi
  __int64 Pool2; // rax
  unsigned __int16 *v53; // rcx
  int v54; // edx
  int v55; // edi
  bool v56; // al
  int AgpStatus; // eax
  __int64 v58; // rdi
  int v59; // eax
  char v60; // cl
  bool v61; // zf
  int v62; // eax
  struct _DEVICE_OBJECT *v63; // rdi
  int v64; // edi
  char v65; // al
  int DevicePropertyString; // eax
  _WORD *v67; // r9
  unsigned int v68; // r8d
  __int16 v69; // dx
  _WORD *v70; // rdi
  _WORD *i; // rax
  __int16 v72; // cx
  __int16 *v73; // rdx
  wchar_t *j; // rax
  _DWORD *v75; // rdx
  unsigned __int64 v76; // r8
  int v77; // eax
  int v78; // eax
  char **v79; // rcx
  __int64 v80; // rax
  NTSTATUS v81; // eax
  __int64 v82; // rax
  __int64 v83; // rax
  char *v84; // rdi
  __int64 v85; // rdx
  bool v86; // cl
  int v87; // edi
  _QWORD *v88; // rdx
  PVOID *v89; // rax
  __int64 DiagnosticInfoArgs; // rax
  __int64 v91; // rdi
  unsigned int v92; // ebx
  struct _DEVICE_OBJECT *v93; // r14
  unsigned int v94; // eax
  int v95; // ecx
  int v96; // r8d
  ULONG DeviceCharacteristics[2]; // [rsp+20h] [rbp-E0h]
  ULONG DeviceCharacteristicsa[2]; // [rsp+20h] [rbp-E0h]
  int Exclusive; // [rsp+28h] [rbp-D8h]
  char v101; // [rsp+50h] [rbp-B0h]
  char v102; // [rsp+51h] [rbp-AFh]
  char v103; // [rsp+52h] [rbp-AEh]
  char v104; // [rsp+53h] [rbp-ADh]
  char v105; // [rsp+54h] [rbp-ACh]
  char v106; // [rsp+55h] [rbp-ABh]
  char v107; // [rsp+56h] [rbp-AAh]
  char v108; // [rsp+57h] [rbp-A9h]
  char v109; // [rsp+57h] [rbp-A9h]
  PDEVICE_OBJECT DeviceObjecta; // [rsp+58h] [rbp-A8h] BYREF
  char v111; // [rsp+60h] [rbp-A0h]
  int v112; // [rsp+64h] [rbp-9Ch]
  char v113; // [rsp+68h] [rbp-98h]
  char v114; // [rsp+69h] [rbp-97h]
  char v115; // [rsp+6Ah] [rbp-96h]
  char v116; // [rsp+6Bh] [rbp-95h]
  char v117; // [rsp+6Ch] [rbp-94h]
  char v118[3]; // [rsp+6Dh] [rbp-93h] BYREF
  int v119; // [rsp+70h] [rbp-90h]
  ULONG ResultLength; // [rsp+74h] [rbp-8Ch] BYREF
  PDEVICE_OBJECT TargetDevice; // [rsp+78h] [rbp-88h]
  void *Source1; // [rsp+80h] [rbp-80h] BYREF
  __int64 v123; // [rsp+88h] [rbp-78h] BYREF
  ULONG Type; // [rsp+90h] [rbp-70h] BYREF
  PDRIVER_OBJECT DriverObject; // [rsp+98h] [rbp-68h]
  __int64 v126; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v127[15]; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v128[2]; // [rsp+120h] [rbp+20h] BYREF
  UNICODE_STRING String1; // [rsp+130h] [rbp+30h] BYREF
  UNICODE_STRING v130; // [rsp+140h] [rbp+40h] BYREF
  UNICODE_STRING v131; // [rsp+150h] [rbp+50h] BYREF
  UNICODE_STRING v132; // [rsp+160h] [rbp+60h] BYREF
  _QWORD v133[2]; // [rsp+170h] [rbp+70h] BYREF
  __int64 v134; // [rsp+180h] [rbp+80h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+188h] [rbp+88h] BYREF
  __int64 v136; // [rsp+198h] [rbp+98h]
  __int64 v137; // [rsp+1A0h] [rbp+A0h] BYREF
  int v138; // [rsp+1A8h] [rbp+A8h]
  _OWORD v139[4]; // [rsp+1B0h] [rbp+B0h] BYREF
  _DWORD VersionInformation[72]; // [rsp+1F0h] [rbp+F0h] BYREF
  wchar_t Str1[20]; // [rsp+310h] [rbp+210h] BYREF
  _OWORD v142[2]; // [rsp+338h] [rbp+238h] BYREF
  wchar_t v143; // [rsp+358h] [rbp+258h]
  _OWORD v144[2]; // [rsp+360h] [rbp+260h] BYREF
  _OWORD v145[2]; // [rsp+380h] [rbp+280h] BYREF
  __int64 v146; // [rsp+3A0h] [rbp+2A0h]
  __int128 v147; // [rsp+3A8h] [rbp+2A8h] BYREF
  _OWORD v148[2]; // [rsp+3B8h] [rbp+2B8h]
  __int128 v149; // [rsp+3D8h] [rbp+2D8h] BYREF
  _OWORD v150[2]; // [rsp+3E8h] [rbp+2E8h]
  _OWORD v151[4]; // [rsp+410h] [rbp+310h] BYREF
  int v152; // [rsp+450h] [rbp+350h]
  WCHAR Data[20]; // [rsp+460h] [rbp+360h] BYREF

  started = DeviceObject;
  v137 = 0;
  v144[0] = *(_OWORD *)L"\\Driver\\VGPU";
  v138 = 0;
  v104 = 0;
  DeviceExtension = 0;
  v118[0] = 0;
  v6 = 0;
  v142[0] = *(_OWORD *)L"\\Driver\\WddmWarp";
  TargetDevice = DeviceObject;
  v132.Buffer = (wchar_t *)v144;
  v145[0] = *(_OWORD *)L"\\Driver\\BasicRender";
  v143 = aDriverWddmwarp[16];
  *(_OWORD *)((char *)v144 + 10) = *(_OWORD *)L"er\\VGPU";
  String1.Buffer = (wchar_t *)v142;
  v128[1] = v145;
  v146 = *(_QWORD *)L"der";
  v133[1] = &v147;
  v142[1] = *(_OWORD *)L"WddmWarp";
  v130.Buffer = (wchar_t *)&v149;
  v147 = *(_OWORD *)L"\\Driver\\BasicDisplay";
  v152 = *(_DWORD *)L"r";
  DriverObject = ClientIdentificationAddress;
  v145[1] = *(_OWORD *)L"BasicRender";
  v123 = 0;
  v107 = 0;
  DeviceObjecta = 0;
  v148[0] = *(_OWORD *)L"BasicDisplay";
  ResultLength = 0;
  v102 = 1;
  *(_OWORD *)((char *)v148 + 10) = *(_OWORD *)L"Display";
  LOBYTE(v112) = 0;
  v105 = 0;
  v150[0] = *(_OWORD *)L"VirtualRender";
  v101 = 0;
  v149 = *(_OWORD *)L"\\Driver\\VirtualRender";
  v106 = 0;
  v119 = 3;
  v151[1] = *(_OWORD *)L"VirtualComputeAccelerator";
  *(_OWORD *)((char *)v150 + 12) = *(_OWORD *)L"lRender";
  *(_QWORD *)&v132.Length = 1703960;
  v151[0] = *(_OWORD *)L"\\Driver\\VirtualComputeAccelerator";
  v151[2] = *(_OWORD *)L"omputeAccelerator";
  *(_QWORD *)&String1.Length = 2228256;
  v128[0] = 2621478;
  v133[0] = 2752552;
  *(_QWORD *)&v130.Length = 2883626;
  v151[3] = *(_OWORD *)L"celerator";
  *(_QWORD *)&v131.Length = 4456514;
  v131.Buffer = (wchar_t *)v151;
  if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
    McTemplateK0ppq_EtwWriteTransfer(
      (_DWORD)ClientIdentificationAddress,
      (unsigned int)EventEnterDpiAddDevice,
      a3,
      (_DWORD)ClientIdentificationAddress,
      (char)DeviceObject,
      0);
  v134 = MEMORY[0xFFFFF78000000320];
  DriverObjectExtension = IoGetDriverObjectExtension(ClientIdentificationAddress, ClientIdentificationAddress);
  v9 = DriverObjectExtension;
  if ( !DriverObjectExtension || DriverObjectExtension[4] != 1953656900 || DriverObjectExtension[5] != 1 )
  {
    LODWORD(started) = -1073741811;
    WdLogSingleEntry3(0, 275, 21, -1073741811);
    v20 = v112;
    v16 = 0;
    WdLogGlobalForLineNumber = 330;
    goto LABEL_299;
  }
  v115 = 0;
  v117 = 0;
  LOBYTE(v8) = 1;
  v111 = 0;
  v114 = 0;
  v108 = 0;
  p_DriverName = &ClientIdentificationAddress->DriverName;
  Buffer = ClientIdentificationAddress->DriverName.Buffer;
  if ( (wchar_t *)RtlFindUnicodeSubstring(p_DriverName, v128, v8) == Buffer )
  {
    v12 = 1;
    v103 = 1;
    v116 = 1;
    v113 = 1;
LABEL_72:
    if ( byte_1401634D0 && !v12 )
    {
      WdLogSingleEntry1(3, p_DriverName);
      WdLogGlobalForLineNumber = 476;
      LODWORD(started) = -1073741637;
      goto LABEL_35;
    }
    started = (struct _DEVICE_OBJECT *)(int)DpiDxgkDdiAddDevice(v9, started, &v123);
    if ( (int)started < 0 )
    {
      WdLogSingleEntry2(2, *((_QWORD *)v9 + 18), started);
      WdLogGlobalForLineNumber = 502;
LABEL_77:
      v16 = 0;
      goto LABEL_298;
    }
    v107 = 1;
    if ( v123 )
    {
      v33 = *((_QWORD *)v9 + 77);
      v32 = 6520;
      *(_DWORD *)&DestinationString.Length = 2;
      v119 = 0;
      if ( v33 )
      {
        if ( v103 )
        {
          LODWORD(started) = -1073741637;
          WdLogSingleEntry2(2, v33, -1073741637);
          WdLogGlobalForLineNumber = 565;
          goto LABEL_35;
        }
        v34 = DpiDxgkDdiLinkDevice(v9, TargetDevice, v123, &v137, *(_QWORD *)DeviceCharacteristics);
        LODWORD(started) = v34;
        if ( v34 < 0 )
        {
          WdLogSingleEntry2(2, *((_QWORD *)v9 + 77), v34);
          WdLogGlobalForLineNumber = 579;
          goto LABEL_77;
        }
        if ( HIDWORD(v137) > 0x100 )
        {
          LODWORD(started) = -1073741756;
          WdLogSingleEntry1(2, -1073741756);
          WdLogGlobalForLineNumber = 595;
          goto LABEL_35;
        }
        if ( HIDWORD(v137) && !(_BYTE)v138 )
        {
          v32 = 2848;
          *(_DWORD *)&DestinationString.Length = 3;
          v119 = 1;
        }
      }
    }
    else
    {
      v119 = 2;
      if ( v12 )
      {
        LODWORD(started) = -1073741637;
        WdLogSingleEntry1(2, -1073741637);
        WdLogGlobalForLineNumber = 532;
        goto LABEL_35;
      }
      v32 = 496;
      *(_DWORD *)&DestinationString.Length = 4;
    }
    v35 = IoCreateDevice(DriverObject, v32, 0, 0x23u, v111 == 0 ? 0x100 : 0, 0, &DeviceObjecta);
    LODWORD(started) = v35;
    if ( v35 < 0 )
    {
      WdLogSingleEntry1(2, v35);
      WdLogGlobalForLineNumber = 635;
      goto LABEL_19;
    }
    v119 |= (unsigned int)DeviceObjecta & 0xFFFF00;
    DeviceExtension = (char *)DeviceObjecta->DeviceExtension;
    *((_DWORD *)DeviceExtension + 5) = *(_DWORD *)&DestinationString.Length;
    *((_DWORD *)DeviceExtension + 4) = 1953656900;
    *((_QWORD *)DeviceExtension + 3) = DeviceObjecta;
    *((_QWORD *)DeviceExtension + 4) = DeviceObjecta;
    *((_QWORD *)DeviceExtension + 5) = v9;
    *((_QWORD *)DeviceExtension + 6) = v123;
    DeviceExtension[480] = v103;
    DeviceExtension[56] = 1;
    DeviceExtension[481] = v108;
    IoInitializeRemoveLockEx((PIO_REMOVE_LOCK)DeviceExtension + 2, 0x74727044u, 1u, 0, 0x20u);
    v36 = TargetDevice;
    *((_QWORD *)DeviceExtension + 19) = TargetDevice;
    v37 = IoAttachDeviceToDeviceStack(DeviceObjecta, v36);
    *((_QWORD *)DeviceExtension + 20) = v37;
    if ( !v37 )
    {
      LODWORD(started) = -1073741810;
      WdLogSingleEntry1(2, -1073741810);
      WdLogGlobalForLineNumber = 677;
      goto LABEL_35;
    }
    v109 = 0;
    *((_DWORD *)DeviceExtension + 71) = 1;
    *((_DWORD *)DeviceExtension + 70) = 1;
    *((_QWORD *)DeviceExtension + 38) = DpiFdoHandleRemoveDevice;
    if ( !DeviceExtension
      || *((_DWORD *)DeviceExtension + 4) != 1953656900
      || (unsigned int)(*((_DWORD *)DeviceExtension + 5) - 2) > 1 )
    {
      goto LABEL_237;
    }
    v38 = (struct _DEVICE_OBJECT *)*((_QWORD *)DeviceExtension + 19);
    LODWORD(Source1) = 0;
    wcscpy(Str1, L"ComputeAccelertor");
    v6 = DeviceExtension;
    Type = 0;
    if ( IoGetDevicePropertyData(v38, &DEVPKEY_Device_Class, 0, 0, 0x28u, Data, (PULONG)&Source1, &Type) >= 0 )
    {
      DestinationString = 0;
      RtlInitUnicodeString(&DestinationString, Data);
      if ( DestinationString.Length >= 0x13u && !wcsncmp_0(Str1, DestinationString.Buffer, 0x12u) )
        DeviceExtension[2722] = 1;
    }
    DeviceExtension[2717] = v113;
    DeviceExtension[1153] = v115;
    DeviceExtension[1154] = v116;
    DeviceExtension[1158] = v111;
    DeviceExtension[2718] = v117;
    DeviceExtension[2719] = v114;
    *((_DWORD *)DeviceExtension + 688) = 1;
    *((_DWORD *)DeviceExtension + 686) = 0;
    *((_QWORD *)DeviceExtension + 36) = DpiFdoHandleStartDevice;
    *((_QWORD *)DeviceExtension + 59) = &DpiFdoHandleSurpriseRemoval;
    *((_QWORD *)DeviceExtension + 49) = &DpiFdoHandleFilterResources;
    if ( !byte_140162E51 && !DeviceExtension[480] )
      *((_QWORD *)DeviceExtension + 40) = &DpiFdoHandleStopDevice;
    *(_QWORD *)(DeviceExtension + 500) = v137;
    *((_DWORD *)DeviceExtension + 127) = v138;
    DeviceRegistryPaths = DpiGetDeviceRegistryPaths(DeviceObjecta, v36, v9);
    LODWORD(started) = DeviceRegistryPaths;
    if ( DeviceRegistryPaths < 0 )
    {
      WdLogSingleEntry1(2, DeviceRegistryPaths);
      WdLogGlobalForLineNumber = 765;
      goto LABEL_284;
    }
    *(_DWORD *)&DestinationString.Length = 0;
    DeviceCharacteristicsa[0] = 2;
    v40 = (int)DpiReadPnpRegistryValue(
                 DeviceObjecta,
                 L"SoftGPUAdapter",
                 &DestinationString,
                 4,
                 *(_QWORD *)DeviceCharacteristicsa) >= 0
       && *(_DWORD *)&DestinationString.Length;
    v41 = (struct _DEVICE_OBJECT *)*((_QWORD *)DeviceExtension + 20);
    DeviceExtension[2716] = v40;
    if ( (int)DpiQueryBusInterface(v41, (__int64)(DeviceExtension + 856)) >= 0 )
    {
      if ( *((_QWORD *)v9 + 29) )
      {
        v42 = DpiAcpiRegisterAcpiCallbacks(DeviceObjecta);
        v43 = (unsigned __int8)v112;
        if ( v42 >= 0 )
          v43 = 1;
        v112 = v43;
      }
      DeviceExtension[1156] = 1;
    }
    started = TargetDevice;
    DeviceProperty = IoGetDeviceProperty(
                       TargetDevice,
                       DevicePropertyBusNumber,
                       4u,
                       DeviceExtension + 1144,
                       &ResultLength);
    if ( DeviceProperty < 0 )
    {
      WdLogSingleEntry1(3, DeviceProperty);
      WdLogGlobalForLineNumber = 851;
      *((_DWORD *)DeviceExtension + 286) = -1;
    }
    v45 = DeviceExtension + 1148;
    v46 = IoGetDeviceProperty(started, DevicePropertyAddress, 4u, DeviceExtension + 1148, &ResultLength);
    if ( v46 < 0 || *v45 == -1 )
    {
      if ( !DeviceExtension[2716] )
      {
        WdLogSingleEntry1(3, v46);
        WdLogGlobalForLineNumber = 879;
      }
      *v45 = -1;
    }
    v47 = (GUID *)(DeviceExtension + 544);
    LODWORD(started) = IoGetDeviceProperty(
                         started,
                         DevicePropertyBusTypeGuid,
                         0x10u,
                         DeviceExtension + 544,
                         &ResultLength);
    if ( (int)started < 0 || ResultLength < 0x10 )
    {
      WdLogSingleEntry1(4, DeviceObjecta);
      WdLogGlobalForLineNumber = 899;
      *v47 = GUID_BUS_TYPE_INVALID;
    }
    if ( v103 )
    {
      v49 = 0;
    }
    else
    {
      v48 = DpiFdoDetectPostDevice(DeviceObjecta, v118);
      LODWORD(started) = v48;
      if ( v48 < 0 )
      {
        WdLogSingleEntry1(2, v48);
        WdLogGlobalForLineNumber = 922;
        goto LABEL_284;
      }
      v49 = v118[0];
      v104 = v118[0];
    }
    if ( v49 )
    {
      WdLogSingleEntry1(4, DeviceObjecta);
      WdLogGlobalForLineNumber = 937;
      DeviceExtension[1152] = 1;
      byte_140163268 = 1;
      if ( byte_140162E51 == 1 )
      {
        AttachedDeviceReference = IoGetAttachedDeviceReference(TargetDevice);
        DpiSetDeviceUsageType(AttachedDeviceReference);
        ObfDereferenceObject(AttachedDeviceReference);
        v47 = (GUID *)(DeviceExtension + 544);
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
    if ( RtlCompareMemory(v47, &GUID_BUS_TYPE_PCI, 0x10u) != 16 )
    {
      if ( RtlCompareMemory(v47, &GUID_BUS_TYPE_ACPI, 0x10u) == 16 )
      {
        DestinationString = 0;
        v136 = 0;
        WdLogSingleEntry1(4, DeviceObjecta);
        WdLogGlobalForLineNumber = 1181;
        if ( !DeviceExtension[1156] )
        {
          LODWORD(started) = -1073741637;
          WdLogSingleEntry1(2, -1073741637);
          WdLogGlobalForLineNumber = 1189;
          goto LABEL_284;
        }
        *((_DWORD *)DeviceExtension + 280) = 2;
        BYTE1(DestinationString.Buffer) = 0;
        WORD1(DestinationString.Buffer) = 0;
        strcpy((char *)&DestinationString, "AeiC_HID");
        HIDWORD(DestinationString.Buffer) = 0;
        memset(Str1, 0, 36);
        v62 = DpEvalAcpiMethod((int)DeviceObjecta, Str1, 0x24u);
        if ( v62 >= 0 )
        {
          *(_QWORD *)(DeviceExtension + 1124) = *(_QWORD *)&Str1[8];
        }
        else
        {
          WdLogSingleEntry1(2, v62);
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
          WdLogSingleEntry1(4, DpEvalAcpiMethod);
          WdLogGlobalForLineNumber = 1259;
        }
        strcpy((char *)&DestinationString, "AeiC_HRV");
        BYTE1(DestinationString.Buffer) = 0;
        WORD1(DestinationString.Buffer) = 0;
        HIDWORD(DestinationString.Buffer) = 0;
        memset(Str1, 0, 36);
        LODWORD(started) = DpEvalAcpiMethod((int)DeviceObjecta, Str1, 0x24u);
        if ( (int)started >= 0 )
        {
          *((_DWORD *)DeviceExtension + 285) = Str1[8];
        }
        else
        {
          WdLogSingleEntry1(4, DpEvalAcpiMethod);
          WdLogGlobalForLineNumber = 1293;
          LODWORD(started) = 0;
        }
        if ( v104 )
        {
          v63 = IoGetAttachedDeviceReference(TargetDevice);
          started = (struct _DEVICE_OBJECT *)(int)DpiSetDeviceUsageType(v63);
          ObfDereferenceObject(v63);
          if ( (int)started < 0 )
          {
            WdLogSingleEntry1(2, started);
            WdLogGlobalForLineNumber = 1321;
            LODWORD(started) = 0;
          }
        }
      }
      else if ( RtlCompareMemory(v47, &GUID_BUS_VMBUS, 0x10u) == 16 )
      {
        WdLogSingleEntry1(4, DeviceObjecta);
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
        RtlCompareMemory(v47, &GUID_BUS_TYPE_DISPLAY, 0x10u);
        v64 = 0;
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
          v65 = DeviceExtension[2719];
          if ( !v65 && !g_OSTestSigningEnabled )
          {
            LODWORD(started) = -1073741637;
            WdLogSingleEntry1(2, -1073741637);
            WdLogGlobalForLineNumber = 1599;
            goto LABEL_284;
          }
          *((_DWORD *)DeviceExtension + 280) = 3;
          if ( v65 )
          {
            *((_DWORD *)DeviceExtension + 281) = 5140;
            *((_DWORD *)DeviceExtension + 282) = 53248;
            *(_QWORD *)(DeviceExtension + 1132) = 4098;
            *((_DWORD *)DeviceExtension + 285) = 0;
          }
          else
          {
            *(_QWORD *)&DestinationString.Length = 0;
            DevicePropertyString = DpiGetDevicePropertyString(
                                     TargetDevice,
                                     DevicePropertyCompatibleIDs,
                                     (__int64)&ResultLength);
            LODWORD(started) = DevicePropertyString;
            if ( DevicePropertyString >= 0 && (v67 = *(_WORD **)&DestinationString.Length) != 0 )
            {
              if ( DeviceExtension[2716] )
              {
                *((_DWORD *)DeviceExtension + 281) = 5140;
                v127[1] = L"SoftGPU_Full_D3D12";
                v68 = 0;
                v126 = 135;
                v127[4] = L"SoftGPU_Full_D3D9L";
                v127[7] = L"SoftGPU_Rod";
                v127[10] = L"SoftGPU_Dod";
                v127[13] = L"SoftGPU_MCDM";
                v127[0] = 0;
                v127[2] = 128;
                v127[3] = 0;
                v127[5] = 136;
                v127[6] = 0;
                v127[8] = 137;
                v127[9] = 0;
                v127[11] = 0x123400000086LL;
                v127[12] = 0x9ABC00005678LL;
                while ( v68 < 5 )
                {
                  v69 = *v67;
                  v70 = v67;
                  for ( i = (_WORD *)v127[3 * (int)v68 + 1]; v69 && *i && v69 == *i; ++i )
                    v69 = *++v70;
                  if ( !*i )
                  {
                    *((_DWORD *)DeviceExtension + 282) = v127[3 * (int)v68 - 1];
                    *((_DWORD *)DeviceExtension + 284) = *((_DWORD *)&v126 + 6 * (int)v68 + 1);
                    *((_DWORD *)DeviceExtension + 283) = v127[3 * (int)v68];
                    *((_DWORD *)DeviceExtension + 285) = HIDWORD(v127[3 * (int)v68]);
                    break;
                  }
                  ++v68;
                }
              }
              else
              {
                *(_DWORD *)&DestinationString.Length = 5140;
                *(_DWORD *)(&DestinationString.MaximumLength + 1) = 256;
                DestinationString.Buffer = L"MCDMTestDevice";
                LODWORD(v136) = 2721;
                while ( !v64 )
                {
                  v72 = *v67;
                  v73 = v67;
                  for ( j = DestinationString.Buffer; *v73; v72 = *v73 )
                  {
                    if ( !*j )
                      break;
                    if ( v72 != *j )
                      break;
                    ++v73;
                    ++j;
                  }
                  if ( !*j )
                  {
                    *((_DWORD *)DeviceExtension + 281) = *(_DWORD *)&DestinationString.Length;
                    *((_DWORD *)DeviceExtension + 282) = *(_DWORD *)(&DestinationString.MaximumLength + 1);
                    DeviceExtension[(int)v136] = 1;
                    break;
                  }
                  v64 = 1;
                }
                if ( !*((_DWORD *)DeviceExtension + 282) )
                {
                  ExFreePoolWithTag(v67, 0);
                  LODWORD(started) = -1073741637;
                  WdLogSingleEntry1(2, -1073741637);
                  WdLogGlobalForLineNumber = 1573;
                  goto LABEL_284;
                }
              }
              ExFreePoolWithTag(v67, 0);
            }
            else
            {
              WdLogSingleEntry1(2, DevicePropertyString);
              WdLogGlobalForLineNumber = 1585;
            }
          }
        }
      }
      goto LABEL_222;
    }
    WdLogSingleEntry1(4, DeviceObjecta);
    v51 = TargetDevice;
    WdLogGlobalForLineNumber = 992;
    DpiQueryBusInterface(TargetDevice, (__int64)(DeviceExtension + 560));
    if ( !*((_QWORD *)DeviceExtension + 77) )
    {
      LODWORD(started) = -1073741127;
      WdLogSingleEntry1(2, -1073741127);
      WdLogGlobalForLineNumber = 1017;
      goto LABEL_284;
    }
    Pool2 = ExAllocatePool2(256, 256, 1953656900);
    *((_QWORD *)DeviceExtension + 139) = Pool2;
    if ( !Pool2 )
    {
      LODWORD(started) = -1073741801;
      WdLogSingleEntry1(6, -1073741801);
      WdLogGlobalForLineNumber = 1037;
      goto LABEL_284;
    }
    (*((void (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD, int))DeviceExtension + 77))(
      *((_QWORD *)DeviceExtension + 71),
      0,
      Pool2,
      0,
      256);
    v53 = (unsigned __int16 *)*((_QWORD *)DeviceExtension + 139);
    *((_DWORD *)DeviceExtension + 280) = 1;
    v54 = *v53;
    *((_DWORD *)DeviceExtension + 281) = v54;
    v55 = v53[1];
    *((_DWORD *)DeviceExtension + 282) = v55;
    *((_DWORD *)DeviceExtension + 285) = *((unsigned __int8 *)v53 + 8);
    if ( (v53[7] & 0x7F) == 0 )
    {
      *((_DWORD *)DeviceExtension + 283) = v53[22];
      *((_DWORD *)DeviceExtension + 284) = v53[23];
    }
    v56 = v54 == 22611 && v55 == 4097;
    DeviceExtension[2720] = v56;
    DpiQueryBusInterface(v51, (__int64)(DeviceExtension + 624));
    DpiQueryBusInterface(*((PDEVICE_OBJECT *)DeviceExtension + 20), (__int64)(DeviceExtension + 672));
    AgpStatus = DpiGetAgpStatus(DeviceObjecta);
    if ( AgpStatus >= 0 && !*((_QWORD *)DeviceExtension + 85) )
    {
      WdLogSingleEntry1(3, AgpStatus);
      WdLogGlobalForLineNumber = 1105;
    }
    v58 = *((_QWORD *)DeviceObjecta->DeviceExtension + 139);
    v59 = DpiFdoDetectVgaDeviceInCapabilities();
    if ( v59 < 0 )
    {
      LODWORD(started) = v59;
LABEL_165:
      if ( v104 )
      {
        WdLogSingleEntry1(3, DeviceObjecta);
        WdLogGlobalForLineNumber = 1161;
      }
      goto LABEL_222;
    }
    v60 = *(_BYTE *)(v58 + 11);
    if ( v60 )
    {
      if ( v60 != 3 )
      {
LABEL_163:
        LODWORD(started) = -1073741823;
        goto LABEL_165;
      }
      v61 = *(_BYTE *)(v58 + 10) == 0;
    }
    else
    {
      v61 = *(_BYTE *)(v58 + 10) == 1;
    }
    if ( v61 )
    {
      LODWORD(started) = v59;
      if ( !v104 )
      {
        if ( byte_140163268 )
        {
LABEL_222:
          if ( DeviceExtension[2716] && DeviceExtension[2717] )
          {
            LODWORD(started) = -1073741811;
            WdLogSingleEntry1(2, -1073741811);
            WdLogGlobalForLineNumber = 1612;
            goto LABEL_284;
          }
          KeInitializeSpinLock((PKSPIN_LOCK)DeviceExtension + 184);
          v75 = DeviceExtension + 1336;
          *((_WORD *)DeviceExtension + 660) = 64;
          if ( (((_BYTE)DeviceExtension + 56) & 4) != 0 )
          {
            *v75 = 1;
            v76 = 6;
            v75 = DeviceExtension + 1340;
          }
          else
          {
            v76 = 7;
          }
          memset64(v75, 0x100000001uLL, v76 >> 1);
          if ( (v76 & 1) != 0 )
            v75[v76 - 1] = 1;
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
          v61 = *((_DWORD *)DeviceExtension + 4) == 1953656900;
          *((_DWORD *)DeviceExtension + 687) = 69640;
          if ( v61 )
          {
            if ( *((_DWORD *)DeviceExtension + 5) == 2 )
            {
              v77 = DpiFdoInitializeFdo(DeviceObjecta);
              LODWORD(started) = v77;
              if ( v77 < 0 )
              {
                WdLogSingleEntry1(2, v77);
                WdLogGlobalForLineNumber = 1672;
                goto LABEL_284;
              }
              v105 = 1;
            }
            else if ( *((_DWORD *)DeviceExtension + 5) == 3 )
            {
              LODWORD(started) = 0;
              *((_QWORD *)DeviceObjecta->DeviceExtension + 43) = &DpiLdaHandleQueryDeviceRelations;
            }
          }
LABEL_237:
          DeviceExtension[57] = v111;
          KeWaitForSingleObject(v9 + 18, Executive, 0, 0, 0);
          v101 = 1;
          if ( v6 )
          {
            if ( *((_DWORD *)v6 + 126) )
            {
              v78 = DpiLdaLinkDeviceToChain(DeviceObjecta);
              LODWORD(started) = v78;
              if ( v78 < 0 )
              {
                WdLogSingleEntry1(2, v78);
                WdLogGlobalForLineNumber = 1727;
                goto LABEL_284;
              }
            }
          }
          v79 = (char **)*((_QWORD *)v9 + 8);
          if ( *v79 != (char *)(v9 + 14) )
            goto LABEL_295;
          *(_QWORD *)DeviceExtension = v9 + 14;
          *((_QWORD *)DeviceExtension + 1) = v79;
          *v79 = DeviceExtension;
          *((_QWORD *)v9 + 8) = DeviceExtension;
          ++v9[32];
          v109 = 1;
          if ( !*((_QWORD *)DeviceExtension + 21) )
          {
            v80 = ExAllocatePool2(64, 112, 1953656900);
            *((_QWORD *)DeviceExtension + 21) = v80;
            if ( !v80 )
            {
              LODWORD(started) = -1073741801;
              WdLogSingleEntry1(6, -1073741801);
              WdLogGlobalForLineNumber = 1762;
              goto LABEL_283;
            }
            *(_DWORD *)(v80 + 104) = 1;
            *(_BYTE *)(*((_QWORD *)DeviceExtension + 21) + 108LL) = 0;
            v81 = ExInitializeResourceLite(*((PERESOURCE *)DeviceExtension + 21));
            LODWORD(started) = v81;
            if ( v81 < 0 )
            {
              WdLogSingleEntry1(2, v81);
              WdLogGlobalForLineNumber = 1776;
              goto LABEL_283;
            }
            v106 = 1;
          }
          KeInitializeMutex((PRKMUTEX)(DeviceExtension + 176), 0);
          if ( !v6 )
            goto LABEL_257;
          if ( !*((_QWORD *)v6 + 185) )
          {
            v82 = ExAllocatePool2(64, 16, 1953656900);
            *((_QWORD *)v6 + 185) = v82;
            if ( !v82 )
            {
              LODWORD(started) = -1073741801;
              WdLogSingleEntry1(6, -1073741801);
              WdLogGlobalForLineNumber = 1804;
              goto LABEL_284;
            }
            *(_DWORD *)(v82 + 8) = 1;
            KeInitializeSpinLock(*((PKSPIN_LOCK *)v6 + 185));
          }
          if ( *((_QWORD *)v6 + 186) )
          {
LABEL_257:
            v84 = DeviceExtension;
            if ( !v6 )
              goto LABEL_259;
          }
          else
          {
            v83 = ExAllocatePool2(64, 16, 1953656900);
            *((_QWORD *)v6 + 186) = v83;
            if ( !v83 )
            {
              LODWORD(started) = -1073741801;
              WdLogSingleEntry1(6, -1073741801);
              WdLogGlobalForLineNumber = 1826;
              goto LABEL_284;
            }
            *(_DWORD *)(v83 + 8) = 1;
            KeInitializeSpinLock(*((PKSPIN_LOCK *)v6 + 186));
            v84 = DeviceExtension;
          }
          *((_DWORD *)v6 + 374) = 0;
          memset(v6 + 1504, 0, 0x400u);
LABEL_259:
          KeReleaseMutex((PRKMUTEX)(v9 + 18), 0);
          v101 = 0;
          *((_QWORD *)v84 + 16) = DpiFdoDispatchPnp;
          if ( v6 )
            *((_QWORD *)v6 + 17) = DpiFdoDispatchPower;
          if ( v104 )
          {
            *(_BYTE *)(*((_QWORD *)v6 + 21) + 108LL) = 1;
            AcquireMiniportListMutex();
            if ( qword_140163100 )
            {
              if ( v6[1152] )
              {
                qword_140163100 = (__int64)DeviceObjecta;
                WdLogSingleEntry2(2, DeviceObjecta, (int)started);
                WdLogGlobalForLineNumber = 1884;
              }
            }
            else
            {
              qword_140163100 = (__int64)DeviceObjecta;
            }
            v85 = *((_QWORD *)v6 + 6);
            Source1 = 0;
            started = (struct _DEVICE_OBJECT *)(int)DpiDxgkDdiExchangePreStartInfo(v9, v85, &Source1);
            ReleaseMiniportListMutex();
            if ( (int)started < 0 )
            {
              WdLogSingleEntry2(2, *((_QWORD *)v9 + 143), started);
              WdLogGlobalForLineNumber = 1908;
              goto LABEL_283;
            }
            if ( *((_DWORD *)v6 + 4) == 1953656900 && *((_DWORD *)v6 + 5) == 2 )
            {
              v86 = (BYTE4(Source1) & 2) != 0;
              v6[2845] = BYTE4(Source1) & 1;
              v6[2846] = v86;
            }
          }
          if ( v103 && v115 )
          {
            if ( (qword_1401630F8 = (__int64)DeviceObjecta,
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
              || byte_140162E53 )
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
          WdLogSingleEntry1(4, DeviceObjecta);
          WdLogGlobalForLineNumber = 2004;
LABEL_283:
          if ( !v6 )
          {
LABEL_287:
            if ( (int)started >= 0 )
              goto LABEL_312;
            v87 = v119;
            v20 = v112;
            if ( v109 != 1 )
            {
              v16 = v101;
              goto LABEL_298;
            }
            KeWaitForSingleObject(v9 + 18, Executive, 0, 0, 0);
            v88 = *(_QWORD **)DeviceExtension;
            if ( *(char **)(*(_QWORD *)DeviceExtension + 8LL) == DeviceExtension )
            {
              v89 = (PVOID *)*((_QWORD *)DeviceExtension + 1);
              if ( *v89 == DeviceExtension )
              {
                *v89 = v88;
                v88[1] = v89;
                --v9[32];
                if ( v6 && *((_DWORD *)v6 + 126) )
                  DpiLdaUnLinkDeviceFromChain(DeviceObjecta);
                KeReleaseMutex((PRKMUTEX)(v9 + 18), 0);
                v16 = v101;
                v119 = v87;
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
              (int)started,
              0,
              0,
              0,
              0);
          goto LABEL_287;
        }
        WdLogSingleEntry1(3, DeviceObjecta);
        WdLogGlobalForLineNumber = 1131;
        v104 = 1;
        byte_140163269 = 1;
      }
      if ( byte_140162E56 )
        DeviceExtension[1155] = 1;
      goto LABEL_222;
    }
    goto LABEL_163;
  }
  v103 = 0;
  v116 = 0;
  v12 = 0;
  if ( !RtlCompareUnicodeString(&String1, p_DriverName, 1u) )
  {
    v113 = 1;
    goto LABEL_72;
  }
  v113 = 0;
  if ( !RtlCompareUnicodeString(&v130, p_DriverName, 1u) || !RtlCompareUnicodeString(&v131, p_DriverName, 1u) )
  {
    v108 = 1;
    goto LABEL_72;
  }
  if ( !RtlCompareUnicodeString(&v132, p_DriverName, 1u) )
  {
    v117 = 1;
    goto LABEL_72;
  }
  LOBYTE(v13) = 1;
  v14 = DriverObject->DriverName.Buffer;
  if ( (wchar_t *)RtlFindUnicodeSubstring(p_DriverName, v133, v13) != v14 )
  {
    *(_DWORD *)&DestinationString.Length = 0;
    if ( (unsigned int)DxgkGetDeviceFamily(&DestinationString) != 5
      || (v114 = 1, ((*(_DWORD *)&DestinationString.Length - 192) & 0xFFFFFFFD) != 0) )
    {
      v114 = 0;
    }
    v111 = *((_BYTE *)v9 + 134);
    *(_DWORD *)&DestinationString.Length = 0;
    v126 = 0;
    memset(v127, 0, 0x68u);
    v18 = *((_QWORD *)v9 + 6);
    v127[1] = L"Start";
    LODWORD(v127[0]) = 292;
    v127[2] = &DestinationString;
    LODWORD(v127[3]) = 67108868;
    LODWORD(v127[5]) = 4;
    *(_QWORD *)DeviceCharacteristics = 0;
    v19 = RtlQueryRegistryValuesEx(0, v18, &v126);
    LODWORD(started) = v19;
    if ( v19 < 0 )
    {
      WdLogSingleEntry1(2, v19);
      WdLogGlobalForLineNumber = 455;
      goto LABEL_19;
    }
    if ( *(_DWORD *)&DestinationString.Length != 3 )
    {
      WdLogSingleEntry1(2, *(unsigned int *)&DestinationString.Length);
      WdLogGlobalForLineNumber = 466;
      LODWORD(started) = -1073741637;
LABEL_35:
      v20 = v112;
      goto LABEL_36;
    }
    v12 = 0;
LABEL_71:
    started = TargetDevice;
    goto LABEL_72;
  }
  Source1 = 0;
  v15 = DpiGetDevicePropertyString(started, DevicePropertyHardwareID, (__int64)&ResultLength);
  LODWORD(started) = v15;
  if ( v15 >= 0 )
  {
    v17 = Source1;
    if ( ResultLength >= 0x24 && RtlCompareMemory(Source1, L"ROOT\\BasicDisplay", 0x24u) == 36 )
    {
      v103 = 1;
      if ( byte_140162E52 )
      {
        v102 = 0;
        LODWORD(started) = -1073741637;
        WdLogSingleEntry1(4, 0);
        WdLogGlobalForLineNumber = 408;
      }
    }
    if ( v17 )
      ExFreePoolWithTag(v17, 0);
    if ( (int)started < 0 )
      goto LABEL_35;
    v12 = v103;
    v115 = 1;
    goto LABEL_71;
  }
  WdLogSingleEntry1(2, v15);
  WdLogGlobalForLineNumber = 383;
LABEL_19:
  v16 = 0;
LABEL_298:
  v20 = v112;
LABEL_299:
  if ( v16 == 1 )
    KeReleaseMutex((PRKMUTEX)(v9 + 18), 0);
LABEL_36:
  if ( DeviceObjecta )
  {
    if ( v105 == 1 )
      DpiFdoResetFdo();
    if ( v6 )
    {
      v21 = (_DWORD *)*((_QWORD *)v6 + 185);
      if ( v21 && v21[2] == 1 )
      {
        ExFreePoolWithTag(v21, 0);
        *((_QWORD *)v6 + 185) = 0;
      }
      v22 = (_DWORD *)*((_QWORD *)v6 + 186);
      if ( v22 && v22[2] == 1 )
      {
        ExFreePoolWithTag(v22, 0);
        *((_QWORD *)v6 + 186) = 0;
      }
      if ( v20 == 1 )
        DpiAcpiUnregisterAcpiCallbacks(DeviceObjecta);
      v23 = (void (__fastcall *)(_QWORD))*((_QWORD *)v6 + 73);
      if ( v23 )
      {
        v23(*((_QWORD *)v6 + 71));
        memset(v6 + 560, 0, 0x40u);
      }
      v24 = (void (__fastcall *)(_QWORD))*((_QWORD *)v6 + 81);
      if ( v24 )
      {
        v24(*((_QWORD *)v6 + 79));
        *((_OWORD *)v6 + 39) = 0;
        *((_OWORD *)v6 + 40) = 0;
        *((_OWORD *)v6 + 41) = 0;
      }
      v25 = (void (__fastcall *)(_QWORD))*((_QWORD *)v6 + 87);
      if ( v25 )
      {
        v25(*((_QWORD *)v6 + 85));
        memset(v6 + 672, 0, 0xB8u);
      }
      v26 = (void (__fastcall *)(_QWORD))*((_QWORD *)v6 + 110);
      if ( v26 )
      {
        v26(*((_QWORD *)v6 + 108));
        memset(v6 + 856, 0, 0x58u);
      }
      RtlFreeUnicodeString((PUNICODE_STRING)v6 + 32);
      RtlFreeUnicodeString((PUNICODE_STRING)v6 + 33);
      v27 = (void *)*((_QWORD *)v6 + 139);
      if ( v27 )
      {
        ExFreePoolWithTag(v27, 0);
        *((_QWORD *)v6 + 139) = 0;
      }
    }
    if ( DeviceExtension )
    {
      v28 = (struct _ERESOURCE *)*((_QWORD *)DeviceExtension + 21);
      if ( v28 )
      {
        if ( v106 == 1 )
          ExDeleteResourceLite(v28);
        v29 = (_DWORD *)*((_QWORD *)DeviceExtension + 21);
        if ( v29[26] == 1 && v29 )
        {
          ExFreePoolWithTag(v29, 0);
          *((_QWORD *)DeviceExtension + 21) = 0;
        }
      }
      v30 = (struct _DEVICE_OBJECT *)*((_QWORD *)DeviceExtension + 20);
      if ( v30 )
        IoDetachDevice(v30);
    }
    IoDeleteDevice(DeviceObjecta);
    DeviceObjecta = 0;
  }
  if ( v107 == 1 )
  {
    DpiDxgkDdiRemoveDevice(v9, v123);
    v31 = v102;
  }
  else
  {
    v31 = v102;
    if ( !v102 )
      goto LABEL_312;
    if ( !*((_QWORD *)v9 + 168) )
      goto LABEL_310;
    DiagnosticInfoArgs = DxgAllocateDiagnosticInfoArgs(1);
    v91 = DiagnosticInfoArgs;
    if ( !DiagnosticInfoArgs )
      goto LABEL_310;
    v92 = *(_DWORD *)(DiagnosticInfoArgs + 216);
    v93 = TargetDevice;
    *(_QWORD *)DiagnosticInfoArgs = v123;
    if ( (*((int (__fastcall **)(struct _DEVICE_OBJECT *, __int64))v9 + 168))(v93, DiagnosticInfoArgs) >= 0 )
    {
      if ( *(_DWORD *)(v91 + 220) > v92 )
        *(_DWORD *)(v91 + 220) = 0;
      DxgCreateLiveDumpWithDriverBlob(
        v93,
        0x1B0u,
        *(int *)(v91 + 8),
        (int)started,
        0,
        0,
        (struct _DXGKARG_COLLECTDIAGNOSTICINFO *)v91);
      v31 = 0;
    }
    DxgFreeDiagnosticInfoArgs((struct _DXGKARG_COLLECTDIAGNOSTICINFO *)v91);
  }
  if ( !v31 )
    goto LABEL_312;
LABEL_310:
  if ( (_DWORD)started != -1071774664 )
  {
    LOBYTE(Exclusive) = 0;
    DxgCreateLiveDumpWithWdLogs(403, 2049, (int)started, 0, 0, Exclusive);
  }
LABEL_312:
  memset(v139, 0, sizeof(v139));
  v94 = DxgkDiagCalcDuration1us(&v134);
  v139[0] = 0x4000000006uLL;
  *(_QWORD *)((char *)&v139[3] + 4) = __PAIR64__(v94, v119);
  memset(&v139[1], 0, 28);
  LODWORD(v139[3]) = 34;
  HIDWORD(v139[3]) = (_DWORD)started;
  DxgkWriteDiagEntry((struct _DXGK_DIAG_HEADER *)v139, 0x100000000uLL);
  if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
    McTemplateK0ppq_EtwWriteTransfer(
      v95,
      (unsigned int)EventExitDpiAddDevice,
      v96,
      (_DWORD)DriverObject,
      (char)TargetDevice,
      (char)started);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x1402a5360  mov     [rsp-8+arg_10], rbx
0x1402a5365  push    rbp
0x1402a5366  push    rsi
0x1402a5367  push    rdi
0x1402a5368  push    r12
0x1402a536a  push    r13
0x1402a536c  push    r14
0x1402a536e  push    r15
0x1402a5370  lea     rbp, [rsp-390h]
0x1402a5378  sub     rsp, 490h
0x1402a537f  mov     rax, cs:__security_cookie
0x1402a5386  xor     rax, rsp
0x1402a5389  mov     [rbp+3C0h+var_38], rax
0x1402a5390  movups  xmm0, xmmword ptr cs:aDriverVgpu; "\\Driver\\VGPU"
0x1402a5397  xor     eax, eax
0x1402a5399  xor     r15d, r15d
0x1402a539c  cmp     cs:bTracingEnabled, r15b
0x1402a53a3  mov     rsi, rdx
0x1402a53a6  movups  xmm1, xmmword ptr cs:aDriverVgpu+0Ah; "er\\VGPU"
0x1402a53ad  mov     [rbp+3C0h+var_320], rax
0x1402a53b4  mov     rdi, rcx
0x1402a53b7  movups  xmmword ptr [rbp+3C0h+var_160], xmm0
0x1402a53be  mov     [rbp+3C0h+var_318], eax
0x1402a53c4  lea     r12d, [r15+1]
0x1402a53c8  movups  xmm0, xmmword ptr cs:aDriverWddmwarp; "\\Driver\\WddmWarp"
0x1402a53cf  mov     [rsp+4C0h+var_46D], al
0x1402a53d3  mov     ebx, r15d
0x1402a53d6  mov     [rsp+4C0h+var_453], al
0x1402a53da  mov     r14d, r15d
0x1402a53dd  movups  [rbp+3C0h+var_188], xmm0
0x1402a53e4  lea     rax, [rbp+3C0h+var_160]
0x1402a53eb  mov     [rsp+4C0h+TargetDevice], rdx
0x1402a53f0  movups  xmm0, xmmword ptr cs:aDriverBasicren; "\\Driver\\BasicRender"
0x1402a53f7  mov     [rbp+3C0h+var_360.Buffer], rax
0x1402a53fb  movzx   eax, word ptr cs:aDriverWddmwarp+20h; ""
0x1402a5402  movups  [rbp+3C0h+var_140], xmm0
0x1402a5409  mov     [rbp+3C0h+var_168], ax
0x1402a5410  lea     rax, [rbp+3C0h+var_188]
0x1402a5417  movsd   xmm0, qword ptr cs:aDriverBasicren+20h; "der"
0x1402a541f  movups  xmmword ptr [rbp+3C0h+var_160+0Ah], xmm1
0x1402a5426  mov     [rbp+3C0h+String1.Buffer], rax
0x1402a542a  lea     rax, [rbp+3C0h+var_140]
0x1402a5431  movups  xmm1, xmmword ptr cs:aDriverWddmwarp+10h; "WddmWarp"
0x1402a5438  mov     [rbp+3C0h+var_398], rax
0x1402a543c  lea     rax, [rbp+3C0h+var_118]
0x1402a5443  movsd   [rbp+3C0h+var_120], xmm0
0x1402a544b  movups  xmm0, xmmword ptr cs:aDriverBasicdis; "\\Driver\\BasicDisplay"
0x1402a5452  mov     [rbp+3C0h+var_348], rax
0x1402a5456  lea     rax, [rbp+3C0h+var_E8]
0x1402a545d  movups  [rbp+3C0h+var_178], xmm1
0x1402a5464  mov     [rbp+3C0h+var_380.Buffer], rax
0x1402a5468  movups  xmm1, xmmword ptr cs:aDriverBasicren+10h; "BasicRender"
0x1402a546f  mov     eax, dword ptr cs:aDriverVirtualc+40h; "r"
0x1402a5475  movups  [rbp+3C0h+var_118], xmm0
0x1402a547c  mov     [rbp+3C0h+var_70], eax
0x1402a5482  lea     rax, [rbp+3C0h+var_B0]
0x1402a5489  movups  xmm0, xmmword ptr cs:aDriverBasicdis+1Ah; "Display"
0x1402a5490  mov     [rbp+3C0h+DriverObject], rcx
0x1402a5494  movups  [rbp+3C0h+var_130], xmm1
0x1402a549b  mov     [rbp+3C0h+var_438], r15
0x1402a549f  movups  xmm1, xmmword ptr cs:aDriverBasicdis+10h; "BasicDisplay"
0x1402a54a6  mov     [rsp+4C0h+var_46A], r15b
0x1402a54ab  mov     [rsp+4C0h+DeviceObject], r15
0x1402a54b0  movups  xmmword ptr [rbp+3C0h+var_108], xmm1
0x1402a54b7  mov     [rsp+4C0h+ResultLength], r15d
0x1402a54bc  movups  xmm1, xmmword ptr cs:aDriverVirtualr+10h; "VirtualRender"
0x1402a54c3  mov     [rsp+4C0h+var_46F], r12b
0x1402a54c8  movups  xmmword ptr [rbp+3C0h+var_108+0Ah], xmm0
0x1402a54cf  mov     byte ptr [rsp+4C0h+var_45C], r15b
0x1402a54d4  movups  xmm0, xmmword ptr cs:aDriverVirtualr; "\\Driver\\VirtualRender"
0x1402a54db  mov     [rsp+4C0h+var_46C], r15b
0x1402a54e0  movups  xmmword ptr [rbp+3C0h+var_D8], xmm1
0x1402a54e7  mov     [rsp+4C0h+var_470], r15b
0x1402a54ec  movaps  xmm1, xmmword ptr cs:aDriverVirtualc+10h; "VirtualComputeAccelerator"
0x1402a54f3  movups  [rbp+3C0h+var_E8], xmm0
0x1402a54fa  mov     [rsp+4C0h+var_46B], r15b
0x1402a54ff  movups  xmm0, xmmword ptr cs:aDriverVirtualr+1Ch; "lRender"
0x1402a5506  mov     [rsp+4C0h+var_450], 3
0x1402a550e  movaps  [rbp+3C0h+var_A0], xmm1
0x1402a5515  movaps  xmm1, xmmword ptr cs:aDriverVirtualc+30h; "celerator"
0x1402a551c  movups  xmmword ptr [rbp+3C0h+var_D8+0Ch], xmm0
0x1402a5523  mov     qword ptr [rbp+3C0h+var_360.Length], 1A0018h
0x1402a552b  movaps  xmm0, xmmword ptr cs:aDriverVirtualc; "\\Driver\\VirtualComputeAccelerator"
0x1402a5532  movaps  [rbp+3C0h+var_B0], xmm0
0x1402a5539  movaps  xmm0, xmmword ptr cs:aDriverVirtualc+20h; "omputeAccelerator"
0x1402a5540  movaps  [rbp+3C0h+var_90], xmm0
0x1402a5547  mov     qword ptr [rbp+3C0h+String1.Length], 220020h
0x1402a554f  mov     [rbp+3C0h+var_3A0], 280026h
0x1402a5557  mov     [rbp+3C0h+var_350], 2A0028h
0x1402a555f  mov     qword ptr [rbp+3C0h+var_380.Length], 2C002Ah
0x1402a5567  movaps  [rbp+3C0h+var_80], xmm1
0x1402a556e  mov     qword ptr [rbp+3C0h+var_370.Length], 440042h
0x1402a5576  mov     [rbp+3C0h+var_370.Buffer], rax
0x1402a557a  jz      short loc_1402A559E
0x1402a557c  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+1, r12b
0x1402a5583  jz      short loc_1402A559E
0x1402a5585  mov     dword ptr [rsp+4C0h+Exclusive], r15d
0x1402a558a  mov     r9, rcx
0x1402a558d  mov     qword ptr [rsp+4C0h+DeviceCharacteristics], rdx
0x1402a5592  lea     rdx, EventEnterDpiAddDevice
0x1402a5599  call    McTemplateK0ppq_EtwWriteTransfer
0x1402a559e  mov     rax, 0FFFFF78000000320h
0x1402a55a8  mov     rdx, rdi; ClientIdentificationAddress
0x1402a55ab  mov     rcx, rdi; DriverObject
0x1402a55ae  mov     rax, [rax]
0x1402a55b1  mov     [rbp+3C0h+var_340], rax
0x1402a55b8  call    cs:__imp_IoGetDriverObjectExtension
0x1402a55bf  nop     dword ptr [rax+rax+00h]
0x1402a55c4  mov     r13, rax
0x1402a55c7  test    rax, rax
0x1402a55ca  jz      loc_1402A740E
0x1402a55d0  cmp     dword ptr [rax+10h], 74727044h
0x1402a55d7  jnz     loc_1402A740E
0x1402a55dd  cmp     [rax+14h], r12d
0x1402a55e1  jnz     loc_1402A740E
0x1402a55e7  mov     [rsp+4C0h+var_456], r15b
0x1402a55ec  lea     rdx, [rbp+3C0h+var_3A0]
0x1402a55f0  mov     [rsp+4C0h+var_454], r15b
0x1402a55f5  mov     r8b, r12b
0x1402a55f8  mov     [rsp+4C0h+var_460], r15b
0x1402a55fd  mov     [rsp+4C0h+var_457], r15b
0x1402a5602  mov     [rsp+4C0h+var_469], r15b
0x1402a5607  lea     r15, [rdi+38h]
0x1402a560b  mov     rdi, [r15+8]
0x1402a560f  mov     rcx, r15
0x1402a5612  call    cs:__imp_RtlFindUnicodeSubstring
0x1402a5619  nop     dword ptr [rax+rax+00h]
0x1402a561e  mov     r12, 0FFFFFFFFC00000BBh
0x1402a5625  cmp     rax, rdi
0x1402a5628  jnz     short loc_1402A5643
0x1402a562a  mov     eax, 1
0x1402a562f  mov     dil, al
0x1402a5632  mov     [rsp+4C0h+var_46E], al
0x1402a5636  mov     [rsp+4C0h+var_455], al
0x1402a563a  mov     [rsp+4C0h+var_458], al
0x1402a563e  jmp     loc_1402A5B03
0x1402a5643  xor     eax, eax
0x1402a5645  lea     rcx, [rbp+3C0h+String1]; String1
0x1402a5649  mov     r8b, 1; CaseInSensitive
0x1402a564c  mov     [rsp+4C0h+var_46E], al
0x1402a5650  mov     rdx, r15; String2
0x1402a5653  mov     [rsp+4C0h+var_455], al
0x1402a5657  mov     dil, al
0x1402a565a  call    cs:__imp_RtlCompareUnicodeString
0x1402a5661  nop     dword ptr [rax+rax+00h]
0x1402a5666  xor     ecx, ecx
0x1402a5668  test    eax, eax
0x1402a566a  jnz     short loc_1402A5676
0x1402a566c  mov     [rsp+4C0h+var_458], 1
0x1402a5671  jmp     loc_1402A5B03
0x1402a5676  mov     [rsp+4C0h+var_458], cl
0x1402a567a  mov     r8b, 1; CaseInSensitive
0x1402a567d  lea     rcx, [rbp+3C0h+var_380]; String1
0x1402a5681  mov     rdx, r15; String2
0x1402a5684  call    cs:__imp_RtlCompareUnicodeString
0x1402a568b  nop     dword ptr [rax+rax+00h]
0x1402a5690  test    eax, eax
0x1402a5692  jz      short loc_1402A56AE
0x1402a5694  mov     r8b, 1; CaseInSensitive
0x1402a5697  lea     rcx, [rbp+3C0h+var_370]; String1
0x1402a569b  mov     rdx, r15; String2
0x1402a569e  call    cs:__imp_RtlCompareUnicodeString
0x1402a56a5  nop     dword ptr [rax+rax+00h]
0x1402a56aa  test    eax, eax
0x1402a56ac  jnz     short loc_1402A56B8
0x1402a56ae  mov     [rsp+4C0h+var_469], 1
0x1402a56b3  jmp     loc_1402A5B03
0x1402a56b8  mov     r8b, 1; CaseInSensitive
0x1402a56bb  lea     rcx, [rbp+3C0h+var_360]; String1
0x1402a56bf  mov     rdx, r15; String2
0x1402a56c2  call    cs:__imp_RtlCompareUnicodeString
0x1402a56c9  nop     dword ptr [rax+rax+00h]
0x1402a56ce  test    eax, eax
0x1402a56d0  jnz     short loc_1402A56DC
0x1402a56d2  mov     [rsp+4C0h+var_454], 1
0x1402a56d7  jmp     loc_1402A5B03
0x1402a56dc  mov     rdi, [rbp+3C0h+DriverObject]
0x1402a56e0  lea     rdx, [rbp+3C0h+var_350]
0x1402a56e4  mov     r8b, 1
0x1402a56e7  mov     rcx, r15
0x1402a56ea  mov     rdi, [rdi+40h]
0x1402a56ee  call    cs:__imp_RtlFindUnicodeSubstring
0x1402a56f5  nop     dword ptr [rax+rax+00h]
0x1402a56fa  cmp     rax, rdi
0x1402a56fd  jnz     loc_1402A57DD
0x1402a5703  xor     edi, edi
0x1402a5705  lea     rax, [rsp+4C0h+ResultLength]
0x1402a570a  lea     r9, [rbp+3C0h+Source1]
0x1402a570e  mov     [rbp+3C0h+Source1], rdi
0x1402a5712  mov     r8d, 100h
0x1402a5718  mov     qword ptr [rsp+4C0h+DeviceCharacteristics], rax; __int64
0x1402a571d  mov     rcx, rsi; DeviceObject
0x1402a5720  lea     edx, [rdi+1]; DeviceProperty
0x1402a5723  call    DpiGetDevicePropertyString
0x1402a5728  movsxd  rsi, eax
0x1402a572b  test    eax, eax
0x1402a572d  jns     short loc_1402A5752
0x1402a572f  mov     rdx, rsi
0x1402a5732  lea     ecx, [rdi+2]
0x1402a5735  call    cs:__imp_WdLogSingleEntry1
0x1402a573c  nop     dword ptr [rax+rax+00h]
0x1402a5741  mov     cs:WdLogGlobalForLineNumber, 17Fh
0x1402a574b  mov     al, bl
0x1402a574d  jmp     loc_1402A744A
0x1402a5752  cmp     [rsp+4C0h+ResultLength], 24h ; '$'
0x1402a5757  mov     rdi, [rbp+3C0h+Source1]
0x1402a575b  jb      short loc_1402A57AE
0x1402a575d  mov     r8d, 24h ; '$'; Length
0x1402a5763  lea     rdx, aRootBasicdispl; "ROOT\\BasicDisplay"
0x1402a576a  mov     rcx, rdi; Source1
0x1402a576d  call    cs:__imp_RtlCompareMemory
0x1402a5774  nop     dword ptr [rax+rax+00h]
0x1402a5779  cmp     rax, 24h ; '$'
0x1402a577d  jnz     short loc_1402A57AE
0x1402a577f  cmp     cs:byte_140162E52, bl
0x1402a5785  mov     [rsp+4C0h+var_46E], 1
0x1402a578a  jz      short loc_1402A57AE
0x1402a578c  mov     [rsp+4C0h+var_46F], bl
0x1402a5790  mov     esi, r12d
0x1402a5793  xor     edx, edx
0x1402a5795  lea     ecx, [rax-20h]
0x1402a5798  call    cs:__imp_WdLogSingleEntry1
0x1402a579f  nop     dword ptr [rax+rax+00h]
0x1402a57a4  mov     cs:WdLogGlobalForLineNumber, 198h
0x1402a57ae  test    rdi, rdi
0x1402a57b1  jz      short loc_1402A57C4
0x1402a57b3  xor     edx, edx; Tag
0x1402a57b5  mov     rcx, rdi; P
0x1402a57b8  call    cs:__imp_ExFreePoolWithTag
0x1402a57bf  nop     dword ptr [rax+rax+00h]
0x1402a57c4  xor     edi, edi
0x1402a57c6  test    esi, esi
0x1402a57c8  js      loc_1402A58DA
0x1402a57ce  mov     dil, [rsp+4C0h+var_46E]
0x1402a57d3  mov     [rsp+4C0h+var_456], 1
0x1402a57d8  jmp     loc_1402A5AFE
0x1402a57dd  xor     edi, edi
0x1402a57df  lea     rcx, [rbp+3C0h+DestinationString]
0x1402a57e6  mov     dword ptr [rbp+3C0h+DestinationString.Length], edi
0x1402a57ec  call    DxgkGetDeviceFamily
0x1402a57f1  cmp     eax, 5
0x1402a57f4  jnz     short loc_1402A580D
0x1402a57f6  mov     eax, dword ptr [rbp+3C0h+DestinationString.Length]
0x1402a57fc  add     eax, 0FFFFFF40h
0x1402a5801  mov     [rsp+4C0h+var_457], 1
0x1402a5806  test    eax, 0FFFFFFFDh
0x1402a580b  jz      short loc_1402A5812
0x1402a580d  mov     [rsp+4C0h+var_457], dil
0x1402a5812  mov     al, [r13+86h]
0x1402a5819  lea     rcx, [rbp+3C0h+var_418]; void *
0x1402a581d  xor     edx, edx; Val
0x1402a581f  mov     [rsp+4C0h+var_460], al
0x1402a5823  mov     dword ptr [rbp+3C0h+DestinationString.Length], edi
0x1402a5829  mov     [rbp+3C0h+var_420], rdi
0x1402a582d  lea     r8d, [rdx+68h]; Size
0x1402a5831  call    memset
0x1402a5836  mov     rdx, [r13+30h]
0x1402a583a  lea     rax, aStart; "Start"
0x1402a5841  mov     [rbp+3C0h+var_410], rax
0x1402a5845  lea     r8, [rbp+3C0h+var_420]
0x1402a5849  lea     rax, [rbp+3C0h+DestinationString]
0x1402a5850  mov     dword ptr [rbp+3C0h+var_418], 124h
0x1402a5857  xor     r9d, r9d
0x1402a585a  mov     [rbp+3C0h+var_408], rax
0x1402a585e  xor     ecx, ecx
0x1402a5860  mov     dword ptr [rbp+3C0h+var_400], 4000004h
0x1402a5867  mov     dword ptr [rbp+3C0h+var_3F0], 4
0x1402a586e  mov     qword ptr [rsp+4C0h+DeviceCharacteristics], rdi
0x1402a5873  call    cs:__imp_RtlQueryRegistryValuesEx
0x1402a587a  nop     dword ptr [rax+rax+00h]
0x1402a587f  movsxd  rsi, eax
0x1402a5882  test    eax, eax
0x1402a5884  jns     short loc_1402A58A9
0x1402a5886  mov     rdx, rsi
0x1402a5889  mov     ecx, 2
0x1402a588e  call    cs:__imp_WdLogSingleEntry1
0x1402a5895  nop     dword ptr [rax+rax+00h]
0x1402a589a  mov     cs:WdLogGlobalForLineNumber, 1C7h
0x1402a58a4  jmp     loc_1402A574B
0x1402a58a9  cmp     dword ptr [rbp+3C0h+DestinationString.Length], 3
0x1402a58b0  jz      loc_1402A5AFB
0x1402a58b6  mov     edx, dword ptr [rbp+3C0h+DestinationString.Length]
0x1402a58bc  mov     ecx, 2
0x1402a58c1  call    cs:__imp_WdLogSingleEntry1
0x1402a58c8  nop     dword ptr [rax+rax+00h]
0x1402a58cd  mov     cs:WdLogGlobalForLineNumber, 1D2h
0x1402a58d7  mov     rsi, r12
0x1402a58da  mov     r15d, [rsp+4C0h+var_45C]
0x1402a58df  mov     r12d, 1
0x1402a58e5  mov     rcx, [rsp+4C0h+DeviceObject]
0x1402a58ea  test    rcx, rcx
0x1402a58ed  jz      loc_1402A5ADA
0x1402a58f3  cmp     [rsp+4C0h+var_46C], r12b
0x1402a58f8  jnz     short loc_1402A58FF
0x1402a58fa  call    DpiFdoResetFdo
0x1402a58ff  test    r14, r14
0x1402a5902  jz      loc_1402A5A61
0x1402a5908  mov     rcx, [r14+5C8h]; P
0x1402a590f  test    rcx, rcx
0x1402a5912  jz      short loc_1402A592F
  ... truncated ...
```
