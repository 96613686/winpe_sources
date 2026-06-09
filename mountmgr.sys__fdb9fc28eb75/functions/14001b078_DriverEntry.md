# DriverEntry

- ea: `0x14001b078`
- end: `0x14001b572`
- name: `DriverEntry`
- size: `1274`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, registry_config, loader_planting, installer_update`

## callers

- `0x14001b010`

## callees

- `0x140001ae0`
- `0x140001b30`
- `0x140002f80`
- `0x140003280`
- `0x14000a6c0`
- `0x140010128`
- `0x140018da0`
- `0x14001b078`
- `0x14001b578`

## import_xrefs

- `ntoskrnl!IoRegisterDriverReinitialization` at `0x14001b527`
- `ntoskrnl!IoRegisterDriverReinitialization` at `0x14001b527`
- `ntoskrnl!KeInitializeMutex` at `0x14001b181`
- `ntoskrnl!KeInitializeMutex` at `0x14001b181`
- `ntoskrnl!RtlCreateRegistryKey` at `0x14001b09f`
- `ntoskrnl!RtlCreateRegistryKey` at `0x14001b09f`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001b206`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001b206`
- `ntoskrnl!PsGetHostSilo` at `0x14001b143`
- `ntoskrnl!PsGetHostSilo` at `0x14001b143`
- `ntoskrnl!IoDeleteDevice` at `0x14001b28a`
- `ntoskrnl!IoDeleteDevice` at `0x14001b388`
- `ntoskrnl!IoDeleteDevice` at `0x14001b427`
- `ntoskrnl!IoDeleteDevice` at `0x14001b4e1`
- `ntoskrnl!IoDeleteDevice` at `0x14001b28a`
- `ntoskrnl!IoDeleteDevice` at `0x14001b388`
- `ntoskrnl!IoDeleteDevice` at `0x14001b427`
- `ntoskrnl!IoDeleteDevice` at `0x14001b4e1`
- `ntoskrnl!KeInitializeSemaphore` at `0x14001b19d`
- `ntoskrnl!KeInitializeSemaphore` at `0x14001b1e9`
- `ntoskrnl!KeInitializeSemaphore` at `0x14001b19d`
- `ntoskrnl!KeInitializeSemaphore` at `0x14001b1e9`
- `ntoskrnl!ExAllocatePool2` at `0x14001b26a`
- `ntoskrnl!ExAllocatePool2` at `0x14001b26a`
- `ntoskrnl!IoRegisterShutdownNotification` at `0x14001b4ab`
- `ntoskrnl!IoRegisterShutdownNotification` at `0x14001b4ab`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x14001b3f1`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x14001b3f1`
- `ntoskrnl!EtwRegister` at `0x14001b546`
- `ntoskrnl!EtwRegister` at `0x14001b546`
- `ntoskrnl!IoCreateDevice` at `0x14001b0de`
- `ntoskrnl!IoCreateDevice` at `0x14001b0de`
- `ntoskrnl!KeInitializeEvent` at `0x14001b233`
- `ntoskrnl!KeInitializeEvent` at `0x14001b233`
- `ntoskrnl!PsFreeSiloContextSlot` at `0x14001b409`
- `ntoskrnl!PsFreeSiloContextSlot` at `0x14001b4c3`
- `ntoskrnl!PsFreeSiloContextSlot` at `0x14001b409`
- `ntoskrnl!PsFreeSiloContextSlot` at `0x14001b4c3`
- `ntoskrnl!PsAllocSiloContextSlot` at `0x14001b36e`
- `ntoskrnl!PsAllocSiloContextSlot` at `0x14001b36e`

## string_xrefs

- `0x14001b096`: `\Registry\Machine\System\MountedDevices`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  int v4; // edi
  _QWORD *DeviceExtension; // rdi
  USHORT Length; // ax
  __int64 v8; // rax
  void *Pool2; // rax
  int NoAutoMount; // eax
  int v11; // esi
  __int64 v12; // r8
  PDEVICE_OBJECT v13; // rcx
  __int64 v14; // rdx
  struct _DEVICE_OBJECT *v15; // rcx
  PDEVICE_OBJECT DeviceObject; // [rsp+90h] [rbp+18h] BYREF

  DeviceObject = 0;
  RtlCreateRegistryKey(0, (PWSTR)L"\\Registry\\Machine\\System\\MountedDevices");
  v4 = IoCreateDevice(DriverObject, 0x178u, &DeviceName, 0x12u, 0x100u, 0, &DeviceObject);
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 364);
    return v4;
  }
  DriverObject->DriverUnload = (PDRIVER_UNLOAD)MountMgrUnload;
  DeviceExtension = DeviceObject->DeviceExtension;
  memset(DeviceExtension, 0, 0x178u);
  DeviceExtension[46] = PsGetHostSilo();
  *DeviceExtension = DeviceObject;
  DeviceExtension[1] = DriverObject;
  DeviceExtension[3] = DeviceExtension + 2;
  DeviceExtension[2] = DeviceExtension + 2;
  DeviceExtension[5] = DeviceExtension + 4;
  DeviceExtension[4] = DeviceExtension + 4;
  KeInitializeMutex((PRKMUTEX)DeviceExtension + 1, 0);
  KeInitializeSemaphore((PRKSEMAPHORE)(DeviceExtension + 14), 1, 1);
  DeviceExtension[20] = DeviceExtension + 19;
  DeviceExtension[19] = DeviceExtension + 19;
  *((_DWORD *)DeviceExtension + 42) = 1;
  DeviceExtension[23] = DeviceExtension + 22;
  DeviceExtension[22] = DeviceExtension + 22;
  DeviceExtension[26] = DeviceExtension + 25;
  DeviceExtension[25] = DeviceExtension + 25;
  KeInitializeSemaphore((PRKSEMAPHORE)(DeviceExtension + 27), 0, 0x7FFFFFFF);
  *((_DWORD *)DeviceExtension + 62) = -1;
  KeInitializeSpinLock(DeviceExtension + 32);
  DeviceExtension[37] = DeviceExtension + 36;
  DeviceExtension[36] = DeviceExtension + 36;
  *((_DWORD *)DeviceExtension + 77) = 1;
  KeInitializeEvent((PRKEVENT)(DeviceExtension + 43), NotificationEvent, 0);
  Length = RegistryPath->Length;
  *((_WORD *)DeviceExtension + 132) = RegistryPath->Length;
  v8 = (unsigned __int16)(Length + 2);
  *((_WORD *)DeviceExtension + 133) = v8;
  Pool2 = (void *)ExAllocatePool2(258, (unsigned __int16)v8, 1098149453);
  DeviceExtension[34] = Pool2;
  if ( !Pool2 )
  {
    IoDeleteDevice(DeviceObject);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 365);
    return -1073741670;
  }
  memmove(Pool2, RegistryPath->Buffer, RegistryPath->Length);
  *(_WORD *)(DeviceExtension[34] + 2 * ((unsigned __int64)RegistryPath->Length >> 1)) = 0;
  NoAutoMount = MountmgrReadNoAutoMount(DeviceExtension + 33);
  DeviceExtension[42] = 1;
  *((_BYTE *)DeviceExtension + 192) = NoAutoMount == 0;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_Mountmgr;
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm();
  GlobalCreateSymbolicLink(asc_140007068, &DeviceName);
  v11 = PsAllocSiloContextSlot(0, &gSiloSlot);
  if ( v11 < 0 )
  {
    IoDeleteDevice(DeviceObject);
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      return v11;
    v14 = 366;
LABEL_15:
    WPP_SF_L(v13->AttachedDevice, v14, v12, (unsigned int)v11);
    return v11;
  }
  v11 = IoRegisterPlugPlayNotification(
          EventCategoryDeviceInterfaceChange,
          1u,
          (PVOID)&MOUNTDEV_MOUNTED_DEVICE_GUID,
          DriverObject,
          MountMgrMountedDeviceNotification,
          DeviceExtension,
          (PVOID *)DeviceExtension + 6);
  if ( v11 < 0 )
  {
    PsFreeSiloContextSlot((unsigned int)gSiloSlot);
    gSiloSlot = -1;
    IoDeleteDevice(DeviceObject);
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      return v11;
    v14 = 367;
    goto LABEL_15;
  }
  v15 = DeviceObject;
  DriverObject->MajorFunction[0] = (PDRIVER_DISPATCH)&MountMgrCreateClose;
  DriverObject->MajorFunction[2] = (PDRIVER_DISPATCH)&MountMgrCreateClose;
  DriverObject->MajorFunction[14] = (PDRIVER_DISPATCH)MountMgrDeviceControl;
  DriverObject->MajorFunction[18] = (PDRIVER_DISPATCH)&MountMgrCleanup;
  DriverObject->MajorFunction[16] = (PDRIVER_DISPATCH)&MountMgrShutdown;
  gDeviceObject = v15;
  v11 = IoRegisterShutdownNotification(v15);
  if ( v11 < 0 )
  {
    PsFreeSiloContextSlot((unsigned int)gSiloSlot);
    gSiloSlot = -1;
    IoDeleteDevice(DeviceObject);
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      return v11;
    v14 = 368;
    goto LABEL_15;
  }
  IoRegisterDriverReinitialization(DriverObject, MountMgrDriverReinitialization, DeviceExtension);
  if ( EtwRegister(&MountMgrEventProvider, 0, 0, &gEtwProvRegHandle) < 0 )
    gEtwProvRegHandle = 0;
  return 0;
}

```

## disassembly

```asm
0x14001b078  mov     rax, rsp
0x14001b07b  push    rbx
0x14001b07c  push    rsi
0x14001b07d  push    rdi
0x14001b07e  push    r12
0x14001b080  push    r14
0x14001b082  push    r15
0x14001b084  sub     rsp, 48h
0x14001b088  mov     rsi, rdx
0x14001b08b  mov     qword ptr [rax+18h], 0
0x14001b093  mov     rbx, rcx
0x14001b096  lea     rdx, Path; "\\Registry\\Machine\\System\\MountedDev"...
0x14001b09d  xor     ecx, ecx; RelativeTo
0x14001b09f  call    cs:__imp_RtlCreateRegistryKey
0x14001b0a6  nop     dword ptr [rax+rax+00h]
0x14001b0ab  lea     rax, [rsp+78h+arg_10]
0x14001b0b3  mov     r14d, 178h
0x14001b0b9  mov     [rsp+78h+DeviceObject], rax; DeviceObject
0x14001b0be  lea     r8, DeviceName; DeviceName
0x14001b0c5  mov     [rsp+78h+Exclusive], 0; Exclusive
0x14001b0ca  mov     r9d, 12h; DeviceType
0x14001b0d0  mov     edx, r14d; DeviceExtensionSize
0x14001b0d3  mov     [rsp+78h+DeviceCharacteristics], 100h; DeviceCharacteristics
0x14001b0db  mov     rcx, rbx; DriverObject
0x14001b0de  call    cs:__imp_IoCreateDevice
0x14001b0e5  nop     dword ptr [rax+rax+00h]
0x14001b0ea  mov     edi, eax
0x14001b0ec  test    eax, eax
0x14001b0ee  jns     short loc_14001B11F
0x14001b0f0  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b0f7  lea     rdx, WPP_GLOBAL_Control
0x14001b0fe  cmp     rcx, rdx
0x14001b101  jz      short loc_14001B118
0x14001b103  mov     edx, [rcx+2Ch]
0x14001b106  test    dl, 4
0x14001b109  jz      short loc_14001B118
0x14001b10b  mov     rcx, [rcx+18h]
0x14001b10f  lea     edx, [r14-0Ch]
0x14001b113  call    WPP_SF_
0x14001b118  mov     eax, edi
0x14001b11a  jmp     loc_14001B563
0x14001b11f  lea     rax, MountMgrUnload
0x14001b126  mov     r8, r14; Size
0x14001b129  mov     [rbx+68h], rax
0x14001b12d  xor     edx, edx; Val
0x14001b12f  mov     rax, [rsp+78h+arg_10]
0x14001b137  mov     rdi, [rax+40h]
0x14001b13b  mov     rcx, rdi; void *
0x14001b13e  call    memset
0x14001b143  call    cs:__imp_PsGetHostSilo
0x14001b14a  nop     dword ptr [rax+rax+00h]
0x14001b14f  mov     [rdi+170h], rax
0x14001b156  lea     rcx, [rdi+38h]; Mutex
0x14001b15a  mov     rax, [rsp+78h+arg_10]
0x14001b162  xor     edx, edx; Level
0x14001b164  mov     [rdi], rax
0x14001b167  lea     rax, [rdi+10h]
0x14001b16b  mov     [rdi+8], rbx
0x14001b16f  mov     [rax+8], rax
0x14001b173  mov     [rax], rax
0x14001b176  lea     rax, [rdi+20h]
0x14001b17a  mov     [rax+8], rax
0x14001b17e  mov     [rax], rax
0x14001b181  call    cs:__imp_KeInitializeMutex
0x14001b188  nop     dword ptr [rax+rax+00h]
0x14001b18d  mov     r15d, 1
0x14001b193  lea     rcx, [rdi+70h]; Semaphore
0x14001b197  mov     r8d, r15d; Limit
0x14001b19a  mov     edx, r15d; Count
0x14001b19d  call    cs:__imp_KeInitializeSemaphore
0x14001b1a4  nop     dword ptr [rax+rax+00h]
0x14001b1a9  lea     rax, [rdi+98h]
0x14001b1b0  xor     edx, edx; Count
0x14001b1b2  mov     [rax+8], rax
0x14001b1b6  lea     rcx, [rdi+0D8h]; Semaphore
0x14001b1bd  mov     [rax], rax
0x14001b1c0  mov     r8d, 7FFFFFFFh; Limit
0x14001b1c6  mov     [rdi+0A8h], r15d
0x14001b1cd  lea     rax, [rdi+0B0h]
0x14001b1d4  mov     [rax+8], rax
0x14001b1d8  mov     [rax], rax
0x14001b1db  lea     rax, [rdi+0C8h]
0x14001b1e2  mov     [rax+8], rax
0x14001b1e6  mov     [rax], rax
0x14001b1e9  call    cs:__imp_KeInitializeSemaphore
0x14001b1f0  nop     dword ptr [rax+rax+00h]
0x14001b1f5  lea     rcx, [rdi+100h]; SpinLock
0x14001b1fc  mov     dword ptr [rdi+0F8h], 0FFFFFFFFh
0x14001b206  call    cs:__imp_KeInitializeSpinLock
0x14001b20d  nop     dword ptr [rax+rax+00h]
0x14001b212  lea     rax, [rdi+120h]
0x14001b219  xor     r8d, r8d; State
0x14001b21c  mov     [rax+8], rax
0x14001b220  lea     rcx, [rdi+158h]; Event
0x14001b227  mov     [rax], rax
0x14001b22a  xor     edx, edx; Type
0x14001b22c  mov     [rdi+134h], r15d
0x14001b233  call    cs:__imp_KeInitializeEvent
0x14001b23a  nop     dword ptr [rax+rax+00h]
0x14001b23f  movzx   eax, word ptr [rsi]
0x14001b242  lea     r14, [rdi+108h]
0x14001b249  mov     [r14], ax
0x14001b24d  lea     r12d, [r15+1]
0x14001b251  add     ax, r12w
0x14001b255  mov     ecx, 102h
0x14001b25a  movzx   edx, ax
0x14001b25d  mov     r8d, 41746E4Dh
0x14001b263  mov     [rdi+10Ah], dx
0x14001b26a  call    cs:__imp_ExAllocatePool2
0x14001b271  nop     dword ptr [rax+rax+00h]
0x14001b276  mov     [rdi+110h], rax
0x14001b27d  test    rax, rax
0x14001b280  jnz     short loc_14001B2C8
0x14001b282  mov     rcx, [rsp+78h+arg_10]; DeviceObject
0x14001b28a  call    cs:__imp_IoDeleteDevice
0x14001b291  nop     dword ptr [rax+rax+00h]
0x14001b296  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b29d  lea     rdx, WPP_GLOBAL_Control
0x14001b2a4  cmp     rcx, rdx
0x14001b2a7  jz      short loc_14001B2BE
0x14001b2a9  mov     eax, [rcx+2Ch]
0x14001b2ac  test    al, 4
0x14001b2ae  jz      short loc_14001B2BE
0x14001b2b0  mov     rcx, [rcx+18h]
0x14001b2b4  mov     edx, 16Dh
0x14001b2b9  call    WPP_SF_
0x14001b2be  mov     eax, 0C000009Ah
0x14001b2c3  jmp     loc_14001B563
0x14001b2c8  movzx   r8d, word ptr [rsi]; Size
0x14001b2cc  mov     rcx, rax; void *
0x14001b2cf  mov     rdx, [rsi+8]; Src
0x14001b2d3  call    memmove
0x14001b2d8  movzx   r8d, word ptr [rsi]
0x14001b2dc  xor     eax, eax
0x14001b2de  mov     rdx, [rdi+110h]
0x14001b2e5  mov     rcx, r14
0x14001b2e8  shr     r8, 1
0x14001b2eb  mov     [rdx+r8*2], ax
0x14001b2f0  call    MountmgrReadNoAutoMount
0x14001b2f5  mov     [rdi+150h], r15
0x14001b2fc  test    eax, eax
0x14001b2fe  setz    al
0x14001b301  mov     [rdi+0C0h], al
0x14001b307  lea     rax, WPP_ThisDir_CTLGUID_Mountmgr
0x14001b30e  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x14001b315  mov     qword ptr cs:WPP_MAIN_CB.Type, 0
0x14001b320  mov     cs:WPP_MAIN_CB.NextDevice, 0
0x14001b32b  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x14001b336  mov     cs:WPP_MAIN_CB.Timer, r15
0x14001b33d  call    WppLoadTracingSupport
0x14001b342  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x14001b34d  call    WppInitKm
0x14001b352  lea     rdx, DeviceName
0x14001b359  lea     rcx, asc_140007068; ":<"
0x14001b360  call    GlobalCreateSymbolicLink
0x14001b365  lea     rdx, gSiloSlot
0x14001b36c  xor     ecx, ecx
0x14001b36e  call    cs:__imp_PsAllocSiloContextSlot
0x14001b375  nop     dword ptr [rax+rax+00h]
0x14001b37a  mov     esi, eax
0x14001b37c  test    eax, eax
0x14001b37e  jns     short loc_14001B3C7
0x14001b380  mov     rcx, [rsp+78h+arg_10]; DeviceObject
0x14001b388  call    cs:__imp_IoDeleteDevice
0x14001b38f  nop     dword ptr [rax+rax+00h]
0x14001b394  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b39b  lea     rdx, WPP_GLOBAL_Control
0x14001b3a2  cmp     rcx, rdx
0x14001b3a5  jz      short loc_14001B3C0
0x14001b3a7  mov     edx, [rcx+2Ch]
0x14001b3aa  test    r15b, dl
0x14001b3ad  jz      short loc_14001B3C0
0x14001b3af  mov     edx, 16Eh
0x14001b3b4  mov     rcx, [rcx+18h]
0x14001b3b8  mov     r9d, esi
0x14001b3bb  call    WPP_SF_L
0x14001b3c0  mov     eax, esi
0x14001b3c2  jmp     loc_14001B563
0x14001b3c7  lea     rax, [rdi+30h]
0x14001b3cb  mov     r9, rbx; DriverObject
0x14001b3ce  mov     [rsp+78h+DeviceObject], rax; NotificationEntry
0x14001b3d3  lea     r8, MOUNTDEV_MOUNTED_DEVICE_GUID; EventCategoryData
0x14001b3da  lea     rax, MountMgrMountedDeviceNotification
0x14001b3e1  mov     qword ptr [rsp+78h+Exclusive], rdi; Context
0x14001b3e6  mov     edx, r15d; EventCategoryFlags
0x14001b3e9  mov     qword ptr [rsp+78h+DeviceCharacteristics], rax; CallbackRoutine
0x14001b3ee  mov     ecx, r12d; EventCategory
0x14001b3f1  call    cs:__imp_IoRegisterPlugPlayNotification
0x14001b3f8  nop     dword ptr [rax+rax+00h]
0x14001b3fd  mov     esi, eax
0x14001b3ff  test    eax, eax
0x14001b401  jns     short loc_14001B460
0x14001b403  mov     ecx, cs:gSiloSlot
0x14001b409  call    cs:__imp_PsFreeSiloContextSlot
0x14001b410  nop     dword ptr [rax+rax+00h]
0x14001b415  mov     rcx, [rsp+78h+arg_10]; DeviceObject
0x14001b41d  mov     cs:gSiloSlot, 0FFFFFFFFh
0x14001b427  call    cs:__imp_IoDeleteDevice
0x14001b42e  nop     dword ptr [rax+rax+00h]
0x14001b433  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b43a  lea     rdx, WPP_GLOBAL_Control
0x14001b441  cmp     rcx, rdx
0x14001b444  jz      loc_14001B3C0
0x14001b44a  mov     eax, [rcx+2Ch]
0x14001b44d  test    r15b, al
0x14001b450  jz      loc_14001B3C0
0x14001b456  mov     edx, 16Fh
0x14001b45b  jmp     loc_14001B3B4
0x14001b460  mov     rcx, [rsp+78h+arg_10]; DeviceObject
0x14001b468  lea     rax, MountMgrCreateClose
0x14001b46f  mov     [rbx+70h], rax
0x14001b473  mov     [rbx+80h], rax
0x14001b47a  lea     rax, MountMgrDeviceControl
0x14001b481  mov     [rbx+0E0h], rax
0x14001b488  lea     rax, MountMgrCleanup
0x14001b48f  mov     [rbx+100h], rax
0x14001b496  lea     rax, MountMgrShutdown
0x14001b49d  mov     [rbx+0F0h], rax
0x14001b4a4  mov     cs:gDeviceObject, rcx
0x14001b4ab  call    cs:__imp_IoRegisterShutdownNotification
0x14001b4b2  nop     dword ptr [rax+rax+00h]
0x14001b4b7  mov     esi, eax
0x14001b4b9  test    eax, eax
0x14001b4bb  jns     short loc_14001B51A
0x14001b4bd  mov     ecx, cs:gSiloSlot
0x14001b4c3  call    cs:__imp_PsFreeSiloContextSlot
0x14001b4ca  nop     dword ptr [rax+rax+00h]
0x14001b4cf  mov     rcx, [rsp+78h+arg_10]; DeviceObject
0x14001b4d7  mov     cs:gSiloSlot, 0FFFFFFFFh
0x14001b4e1  call    cs:__imp_IoDeleteDevice
0x14001b4e8  nop     dword ptr [rax+rax+00h]
0x14001b4ed  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b4f4  lea     rdx, WPP_GLOBAL_Control
0x14001b4fb  cmp     rcx, rdx
0x14001b4fe  jz      loc_14001B3C0
0x14001b504  mov     eax, [rcx+2Ch]
0x14001b507  test    r15b, al
0x14001b50a  jz      loc_14001B3C0
0x14001b510  mov     edx, 170h
0x14001b515  jmp     loc_14001B3B4
0x14001b51a  mov     r8, rdi; Context
0x14001b51d  lea     rdx, MountMgrDriverReinitialization; DriverReinitializationRoutine
0x14001b524  mov     rcx, rbx; DriverObject
0x14001b527  call    cs:__imp_IoRegisterDriverReinitialization
0x14001b52e  nop     dword ptr [rax+rax+00h]
0x14001b533  lea     r9, gEtwProvRegHandle; RegHandle
0x14001b53a  xor     r8d, r8d; CallbackContext
0x14001b53d  xor     edx, edx; EnableCallback
0x14001b53f  lea     rcx, MountMgrEventProvider; ProviderId
0x14001b546  call    cs:__imp_EtwRegister
0x14001b54d  nop     dword ptr [rax+rax+00h]
0x14001b552  test    eax, eax
0x14001b554  jns     short loc_14001B561
0x14001b556  mov     cs:gEtwProvRegHandle, 0
0x14001b561  xor     eax, eax
0x14001b563  add     rsp, 48h
0x14001b567  pop     r15
0x14001b569  pop     r14
0x14001b56b  pop     r12
0x14001b56d  pop     rdi
0x14001b56e  pop     rsi
0x14001b56f  pop     rbx
0x14001b570  retn
```
