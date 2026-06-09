# DriverEntry

- ea: `0x1400292a4`
- end: `0x1400294fa`
- name: `DriverEntry`
- size: `598`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140029010`

## callees

- `0x14000c0d4`
- `0x140011440`
- `0x14001c880`
- `0x14002046c`
- `0x140029078`
- `0x1400292a4`

## import_xrefs

- `ntoskrnl!IoRegisterDriverReinitialization` at `0x1400294d8`
- `ntoskrnl!IoRegisterDriverReinitialization` at `0x1400294d8`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x1400293e7`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x140029414`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x1400293e7`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x140029414`
- `ntoskrnl!KeInitializeMutex` at `0x140029392`
- `ntoskrnl!KeInitializeMutex` at `0x1400293ba`
- `ntoskrnl!KeInitializeMutex` at `0x140029392`
- `ntoskrnl!KeInitializeMutex` at `0x1400293ba`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002930b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140029465`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002930b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140029465`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x1400294b9`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x1400294b9`
- `ntoskrnl!IoCreateDevice` at `0x140029344`
- `ntoskrnl!IoCreateDevice` at `0x140029344`
- `ntoskrnl!IoCreateSymbolicLink` at `0x14002947b`
- `ntoskrnl!IoCreateSymbolicLink` at `0x14002947b`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x140029431`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x140029431`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  int GlobalSettings; // edi
  char *DeviceExtension; // rsi
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-48h] BYREF
  struct _UNICODE_STRING SymbolicLinkName; // [rsp+50h] [rbp-38h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+90h] [rbp+8h] BYREF

  DeviceObject = 0;
  DestinationString = 0;
  SymbolicLinkName = 0;
  TraceLoggingRegisterEx_EtwRegister_EtwSetInformation();
  McGenEventRegister_EtwRegister();
  memset64(DriverObject->MajorFunction, (unsigned __int64)PmGlobalDispatch, 0x1Cu);
  DriverObject->DriverExtension->AddDevice = (PDRIVER_ADD_DEVICE)PmAddDevice;
  DriverObject->DriverUnload = (PDRIVER_UNLOAD)PmUnload;
  RtlInitUnicodeString(&DestinationString, L"\\Device\\PartmgrControl");
  GlobalSettings = IoCreateDevice(DriverObject, 0x1C0u, &DestinationString, 0x2Du, 0x100u, 0, &DeviceObject);
  if ( GlobalSettings < 0 )
    goto LABEL_7;
  PmControlObject = DeviceObject;
  DeviceExtension = (char *)DeviceObject->DeviceExtension;
  memset(DeviceExtension + 16, 0, 0x1B0u);
  *((_QWORD *)DeviceExtension + 1) = DriverObject;
  *(_QWORD *)DeviceExtension = off_1400131C0;
  KeInitializeMutex((PRKMUTEX)(DeviceExtension + 16), 0);
  *((_QWORD *)DeviceExtension + 10) = DeviceExtension + 72;
  *((_QWORD *)DeviceExtension + 9) = DeviceExtension + 72;
  *((_QWORD *)DeviceExtension + 12) = DeviceExtension + 88;
  *((_QWORD *)DeviceExtension + 11) = DeviceExtension + 88;
  KeInitializeMutex((PRKMUTEX)(DeviceExtension + 104), 0);
  RtlInitializeGenericTableAvl(
    (PRTL_AVL_TABLE)(DeviceExtension + 200),
    PmTableSignatureCompareRoutine,
    PmTableAllocateRoutine,
    PmTableFreeRoutine,
    DeviceExtension);
  RtlInitializeGenericTableAvl(
    (PRTL_AVL_TABLE)(DeviceExtension + 304),
    PmTableGuidCompareRoutine,
    PmTableAllocateRoutine,
    PmTableFreeRoutine,
    DeviceExtension);
  GlobalSettings = RtlDuplicateUnicodeString(1u, RegistryPath, (PUNICODE_STRING)DeviceExtension + 26);
  if ( GlobalSettings < 0
    || (GlobalSettings = PmQueryGlobalSettings((struct _CONTROL_EXTENSION *)DeviceExtension), GlobalSettings < 0)
    || (RtlInitUnicodeString(&SymbolicLinkName, L"\\DosDevices\\PartmgrControl"),
        GlobalSettings = IoCreateSymbolicLink(&SymbolicLinkName, &DestinationString),
        GlobalSettings < 0)
    || (GlobalSettings = IoRegisterPlugPlayNotification(
                           EventCategoryDeviceInterfaceChange,
                           1u,
                           VOLMGR_VOLUME_MANAGER_GUID,
                           DriverObject,
                           PmVolumeManagerNotification,
                           DeviceExtension,
                           (PVOID *)DeviceExtension + 51),
        GlobalSettings < 0) )
  {
LABEL_7:
    PmUnload(DriverObject);
  }
  else
  {
    IoRegisterDriverReinitialization(DriverObject, PmDriverReinitialization, 0);
  }
  return GlobalSettings;
}

```

## disassembly

```asm
0x1400292a4  mov     rax, rsp
0x1400292a7  push    rbx
0x1400292a8  push    rbp
0x1400292a9  push    rsi
0x1400292aa  push    rdi
0x1400292ab  sub     rsp, 68h
0x1400292af  xorps   xmm0, xmm0
0x1400292b2  mov     qword ptr [rax+8], 0
0x1400292ba  movups  xmmword ptr [rax-48h], xmm0
0x1400292be  mov     rbp, rdx
0x1400292c1  mov     rbx, rcx
0x1400292c4  movups  xmmword ptr [rax-38h], xmm0
0x1400292c8  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x1400292cd  call    McGenEventRegister_EtwRegister
0x1400292d2  lea     rax, ?PmGlobalDispatch@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PmGlobalDispatch(_DEVICE_OBJECT *,_IRP *)
0x1400292d9  mov     ecx, 1Ch
0x1400292de  lea     rdi, [rbx+70h]
0x1400292e2  rep stosq
0x1400292e5  mov     rax, [rbx+30h]
0x1400292e9  lea     rcx, ?PmAddDevice@@YAJPEAU_DRIVER_OBJECT@@PEAU_DEVICE_OBJECT@@@Z; PmAddDevice(_DRIVER_OBJECT *,_DEVICE_OBJECT *)
0x1400292f0  lea     rdx, aDevicePartmgrc; "\\Device\\PartmgrControl"
0x1400292f7  mov     [rax+8], rcx
0x1400292fb  lea     rax, ?PmUnload@@YAXPEAU_DRIVER_OBJECT@@@Z; PmUnload(_DRIVER_OBJECT *)
0x140029302  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x140029307  mov     [rbx+68h], rax
0x14002930b  call    cs:__imp_RtlInitUnicodeString
0x140029312  nop     dword ptr [rax+rax+00h]
0x140029317  lea     rax, [rsp+88h+arg_0]
0x14002931f  mov     r9d, 2Dh ; '-'; DeviceType
0x140029325  mov     [rsp+88h+DeviceObject], rax; DeviceObject
0x14002932a  lea     r8, [rsp+88h+DestinationString]; DeviceName
0x14002932f  mov     [rsp+88h+Exclusive], 0; Exclusive
0x140029334  mov     edx, 1C0h; DeviceExtensionSize
0x140029339  mov     rcx, rbx; DriverObject
0x14002933c  mov     [rsp+88h+DeviceCharacteristics], 100h; DeviceCharacteristics
0x140029344  call    cs:__imp_IoCreateDevice
0x14002934b  nop     dword ptr [rax+rax+00h]
0x140029350  mov     edi, eax
0x140029352  test    eax, eax
0x140029354  js      loc_1400294E6
0x14002935a  mov     rax, [rsp+88h+arg_0]
0x140029362  xor     edx, edx; Val
0x140029364  mov     r8d, 1B0h; Size
0x14002936a  mov     cs:?PmControlObject@@3PEAU_DEVICE_OBJECT@@EA, rax; _DEVICE_OBJECT * PmControlObject
0x140029371  mov     rsi, [rax+40h]
0x140029375  lea     rcx, [rsi+10h]; void *
0x140029379  call    memset
0x14002937e  lea     rax, off_1400131C0
0x140029385  mov     [rsi+8], rbx
0x140029389  lea     rcx, [rsi+10h]; Mutex
0x14002938d  mov     [rsi], rax
0x140029390  xor     edx, edx; Level
0x140029392  call    cs:__imp_KeInitializeMutex
0x140029399  nop     dword ptr [rax+rax+00h]
0x14002939e  lea     rax, [rsi+48h]
0x1400293a2  xor     edx, edx; Level
0x1400293a4  mov     [rax+8], rax
0x1400293a8  lea     rcx, [rsi+68h]; Mutex
0x1400293ac  mov     [rax], rax
0x1400293af  lea     rax, [rsi+58h]
0x1400293b3  mov     [rax+8], rax
0x1400293b7  mov     [rax], rax
0x1400293ba  call    cs:__imp_KeInitializeMutex
0x1400293c1  nop     dword ptr [rax+rax+00h]
0x1400293c6  lea     rcx, [rsi+0C8h]; Table
0x1400293cd  mov     qword ptr [rsp+88h+DeviceCharacteristics], rsi; TableContext
0x1400293d2  lea     r9, ?PmTableFreeRoutine@@YAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x1400293d9  lea     r8, ?PmTableAllocateRoutine@@YAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x1400293e0  lea     rdx, ?PmTableSignatureCompareRoutine@@YA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x1400293e7  call    cs:__imp_RtlInitializeGenericTableAvl
0x1400293ee  nop     dword ptr [rax+rax+00h]
0x1400293f3  lea     rcx, [rsi+130h]; Table
0x1400293fa  mov     qword ptr [rsp+88h+DeviceCharacteristics], rsi; TableContext
0x1400293ff  lea     r9, ?PmTableFreeRoutine@@YAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x140029406  lea     r8, ?PmTableAllocateRoutine@@YAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x14002940d  lea     rdx, ?PmTableGuidCompareRoutine@@YA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x140029414  call    cs:__imp_RtlInitializeGenericTableAvl
0x14002941b  nop     dword ptr [rax+rax+00h]
0x140029420  mov     rdx, rbp; StringIn
0x140029423  lea     r8, [rsi+1A0h]; StringOut
0x14002942a  mov     ebp, 1
0x14002942f  mov     ecx, ebp; Flags
0x140029431  call    cs:__imp_RtlDuplicateUnicodeString
0x140029438  nop     dword ptr [rax+rax+00h]
0x14002943d  mov     edi, eax
0x14002943f  test    eax, eax
0x140029441  js      loc_1400294E6
0x140029447  mov     rcx, rsi; struct _CONTROL_EXTENSION *
0x14002944a  call    ?PmQueryGlobalSettings@@YAJPEAU_CONTROL_EXTENSION@@@Z; PmQueryGlobalSettings(_CONTROL_EXTENSION *)
0x14002944f  mov     edi, eax
0x140029451  test    eax, eax
0x140029453  js      loc_1400294E6
0x140029459  lea     rdx, aDosdevicesPart; "\\DosDevices\\PartmgrControl"
0x140029460  lea     rcx, [rsp+88h+SymbolicLinkName]; DestinationString
0x140029465  call    cs:__imp_RtlInitUnicodeString
0x14002946c  nop     dword ptr [rax+rax+00h]
0x140029471  lea     rdx, [rsp+88h+DestinationString]; DeviceName
0x140029476  lea     rcx, [rsp+88h+SymbolicLinkName]; SymbolicLinkName
0x14002947b  call    cs:__imp_IoCreateSymbolicLink
0x140029482  nop     dword ptr [rax+rax+00h]
0x140029487  mov     edi, eax
0x140029489  test    eax, eax
0x14002948b  js      short loc_1400294E6
0x14002948d  lea     rax, [rsi+198h]
0x140029494  mov     r9, rbx; DriverObject
0x140029497  mov     [rsp+88h+DeviceObject], rax; NotificationEntry
0x14002949c  lea     r8, VOLMGR_VOLUME_MANAGER_GUID; EventCategoryData
0x1400294a3  lea     rax, ?PmVolumeManagerNotification@@YAJPEAX0@Z; PmVolumeManagerNotification(void *,void *)
0x1400294aa  mov     qword ptr [rsp+88h+Exclusive], rsi; Context
0x1400294af  mov     edx, ebp; EventCategoryFlags
0x1400294b1  mov     qword ptr [rsp+88h+DeviceCharacteristics], rax; CallbackRoutine
0x1400294b6  lea     ecx, [rbp+1]; EventCategory
0x1400294b9  call    cs:__imp_IoRegisterPlugPlayNotification
0x1400294c0  nop     dword ptr [rax+rax+00h]
0x1400294c5  mov     edi, eax
0x1400294c7  test    eax, eax
0x1400294c9  js      short loc_1400294E6
0x1400294cb  xor     r8d, r8d; Context
0x1400294ce  lea     rdx, PmDriverReinitialization; DriverReinitializationRoutine
0x1400294d5  mov     rcx, rbx; DriverObject
0x1400294d8  call    cs:__imp_IoRegisterDriverReinitialization
0x1400294df  nop     dword ptr [rax+rax+00h]
0x1400294e4  jmp     short loc_1400294EE
0x1400294e6  mov     rcx, rbx; struct _DRIVER_OBJECT *
0x1400294e9  call    ?PmUnload@@YAXPEAU_DRIVER_OBJECT@@@Z; PmUnload(_DRIVER_OBJECT *)
0x1400294ee  mov     eax, edi
0x1400294f0  add     rsp, 68h
0x1400294f4  pop     rdi
0x1400294f5  pop     rsi
0x1400294f6  pop     rbp
0x1400294f7  pop     rbx
0x1400294f8  retn
```
