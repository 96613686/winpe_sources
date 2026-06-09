# DriverEntry

- ea: `0x14000c078`
- end: `0x14000c1c3`
- name: `DriverEntry`
- size: `331`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x14000c010`

## callees

- `0x14000a1a4`
- `0x14000a238`
- `0x14000c078`
- `0x14000c1cc`
- `0x14000c320`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14000c1ab`
- `ntoskrnl!KeInitializeEvent` at `0x14000c1ab`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x14000c16e`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x14000c16e`
- `ntoskrnl!IoCreateDevice` at `0x14000c126`
- `ntoskrnl!IoCreateDevice` at `0x14000c126`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  NTSTATUS result; // eax

  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_WPP_CHAT_CONTROL_GUID;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  WppLoadTracingSupport(DriverObject, RegistryPath);
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm();
  DriverObject->MajorFunction[0] = (PDRIVER_DISPATCH)&ProvCreateClose;
  DriverObject->MajorFunction[2] = (PDRIVER_DISPATCH)&ProvCreateClose;
  DriverObject->MajorFunction[15] = (PDRIVER_DISPATCH)ProvDeviceControl;
  DriverObject->DriverUnload = (PDRIVER_UNLOAD)ProvUnloadDriver;
  result = IoCreateDevice(DriverObject, 0, &DeviceName, 0x22u, 0x100u, 0, &g_deviceObject);
  if ( result >= 0 )
  {
    InitializeScheduler();
    result = IoRegisterPlugPlayNotification(
               EventCategoryDeviceInterfaceChange,
               1u,
               &GUID_CNG_CHAT_HW_PROV_INTERFACE,
               DriverObject,
               ChatDeviceCategoryChange,
               DriverObject,
               &g_pnpNotificationEntry);
    if ( result >= 0 )
    {
      g_mutexAddHardwareKey.Count = 1;
      g_mutexAddHardwareKey.Owner = 0;
      g_mutexAddHardwareKey.Contention = 0;
      KeInitializeEvent(&g_mutexAddHardwareKey.Event, SynchronizationEvent, 0);
      return RegisterCngProvider();
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000c078  push    rbx
0x14000c07a  sub     rsp, 40h
0x14000c07e  lea     rax, WPP_ThisDir_CTLGUID_WPP_CHAT_CONTROL_GUID
0x14000c085  mov     qword ptr cs:WPP_MAIN_CB.Type, 0
0x14000c090  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x14000c097  mov     rbx, rcx
0x14000c09a  mov     cs:WPP_MAIN_CB.NextDevice, 0
0x14000c0a5  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x14000c0b0  mov     cs:WPP_MAIN_CB.Timer, 1
0x14000c0bb  call    WppLoadTracingSupport
0x14000c0c0  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x14000c0cb  call    WppInitKm
0x14000c0d0  lea     rax, ProvCreateClose
0x14000c0d7  mov     r9d, 22h ; '"'; DeviceType
0x14000c0dd  mov     [rbx+70h], rax
0x14000c0e1  lea     r8, DeviceName; DeviceName
0x14000c0e8  mov     [rbx+80h], rax
0x14000c0ef  xor     edx, edx; DeviceExtensionSize
0x14000c0f1  lea     rax, ProvDeviceControl
0x14000c0f8  mov     rcx, rbx; DriverObject
0x14000c0fb  mov     [rbx+0E8h], rax
0x14000c102  lea     rax, ProvUnloadDriver
0x14000c109  mov     [rbx+68h], rax
0x14000c10d  lea     rax, g_deviceObject
0x14000c114  mov     [rsp+48h+DeviceObject], rax; DeviceObject
0x14000c119  mov     [rsp+48h+Exclusive], 0; Exclusive
0x14000c11e  mov     [rsp+48h+DeviceCharacteristics], 100h; DeviceCharacteristics
0x14000c126  call    cs:__imp_IoCreateDevice
0x14000c12d  nop     dword ptr [rax+rax+00h]
0x14000c132  test    eax, eax
0x14000c134  js      loc_14000C1BC
0x14000c13a  call    InitializeScheduler
0x14000c13f  mov     edx, 1; EventCategoryFlags
0x14000c144  lea     rax, g_pnpNotificationEntry
0x14000c14b  mov     [rsp+48h+DeviceObject], rax; NotificationEntry
0x14000c150  lea     r8, GUID_CNG_CHAT_HW_PROV_INTERFACE; EventCategoryData
0x14000c157  lea     rax, ChatDeviceCategoryChange
0x14000c15e  mov     qword ptr [rsp+48h+Exclusive], rbx; Context
0x14000c163  mov     r9, rbx; DriverObject
0x14000c166  mov     qword ptr [rsp+48h+DeviceCharacteristics], rax; CallbackRoutine
0x14000c16b  lea     ecx, [rdx+1]; EventCategory
0x14000c16e  call    cs:__imp_IoRegisterPlugPlayNotification
0x14000c175  nop     dword ptr [rax+rax+00h]
0x14000c17a  test    eax, eax
0x14000c17c  js      short loc_14000C1BC
0x14000c17e  xor     r8d, r8d; State
0x14000c181  mov     cs:g_mutexAddHardwareKey.Count, 1
0x14000c18b  lea     rcx, g_mutexAddHardwareKey.Event; Event
0x14000c192  mov     cs:g_mutexAddHardwareKey.Owner, 0
0x14000c19d  mov     cs:g_mutexAddHardwareKey.Contention, 0
0x14000c1a7  lea     edx, [r8+1]; Type
0x14000c1ab  call    cs:__imp_KeInitializeEvent
0x14000c1b2  nop     dword ptr [rax+rax+00h]
0x14000c1b7  call    RegisterCngProvider
0x14000c1bc  add     rsp, 40h
0x14000c1c0  pop     rbx
0x14000c1c1  retn
```
