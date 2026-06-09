# KsCreateDevice

- ea: `0x1800553a0`
- end: `0x180055521`
- name: `KsCreateDevice`
- size: `385`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PDEVICE_OBJECT PhysicalDeviceObject, const KSDEVICE_DESCRIPTOR *Descriptor, ULONG ExtensionSize, PKSDEVICE *Device)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180055610`
- `0x18006f6a0`

## callees

- `0x180004150`
- `0x18000b7bc`
- `0x18000c4c8`
- `0x1800553a0`
- `0x180055530`

## import_xrefs

- `ntoskrnl!IoDetachDevice` at `0x180055491`
- `ntoskrnl!IoDetachDevice` at `0x180055491`
- `ntoskrnl!IoDeleteDevice` at `0x1800554a2`
- `ntoskrnl!IoDeleteDevice` at `0x1800554a2`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x180055457`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x180055457`
- `ntoskrnl!IoCreateDevice` at `0x180055403`
- `ntoskrnl!IoCreateDevice` at `0x180055403`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x180055443`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x180055443`

## pseudocode

```c
NTSTATUS __stdcall KsCreateDevice(
        PDRIVER_OBJECT DriverObject,
        PDEVICE_OBJECT PhysicalDeviceObject,
        const KSDEVICE_DESCRIPTOR *Descriptor,
        ULONG ExtensionSize,
        PKSDEVICE *Device)
{
  struct _DEVICE_OBJECT *v7; // rsi
  ULONG v9; // edx
  int v10; // ebx
  struct _KSDEVICE_HEADER_EX *DeviceHeader; // rax
  struct _DEVICE_OBJECT *v12; // rax
  struct _DEVICE_OBJECT *v13; // rdi
  PDEVICE_OBJECT SourceDevice; // [rsp+40h] [rbp-38h] BYREF

  v7 = PhysicalDeviceObject;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(PhysicalDeviceObject) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)PhysicalDeviceObject,
      1,
      18,
      (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
  }
  v9 = 8;
  SourceDevice = 0;
  if ( ExtensionSize )
    v9 = ExtensionSize;
  v10 = IoCreateDevice(DriverObject, v9 + 32, 0, 0x2Fu, 0x100u, 0, &SourceDevice);
  if ( v10 >= 0 )
  {
    SourceDevice->DeviceExtension = (char *)SourceDevice->DeviceExtension + 32;
    DeviceHeader = CKsDevice::GetDeviceHeaderEx(SourceDevice);
    IoInitializeRemoveLockEx(&DeviceHeader->RemoveLock, 0x6564534Bu, 0, 0, 0x20u);
    v12 = IoAttachDeviceToDeviceStack(SourceDevice, v7);
    v13 = v12;
    if ( !v12 )
    {
      v10 = -1073741130;
      goto LABEL_8;
    }
    SourceDevice->Flags |= 0x2000u;
    v10 = KsInitializeDevice(SourceDevice, v7, v12, Descriptor);
    if ( v10 < 0 )
    {
      IoDetachDevice(v13);
LABEL_8:
      IoDeleteDevice(SourceDevice);
      return v10;
    }
    SourceDevice->Flags &= ~0x80u;
    if ( Device )
      *Device = KsGetDeviceForDeviceObject(SourceDevice);
  }
  return v10;
}

```

## disassembly

```asm
0x1800553a0  push    rbx
0x1800553a2  push    rbp
0x1800553a3  push    rsi
0x1800553a4  push    rdi
0x1800553a5  push    r14
0x1800553a7  sub     rsp, 50h
0x1800553ab  mov     ebx, r9d
0x1800553ae  mov     rbp, r8
0x1800553b1  mov     rsi, rdx
0x1800553b4  mov     rdi, rcx
0x1800553b7  lea     rax, WPP_RECORDER_INITIALIZED
0x1800553be  xor     r14d, r14d
0x1800553c1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800553c8  jnz     loc_1800554E9
0x1800553ce  mov     edx, 8
0x1800553d3  mov     [rsp+78h+SourceDevice], r14
0x1800553d8  lea     rax, [rsp+78h+SourceDevice]
0x1800553dd  test    ebx, ebx
0x1800553df  mov     [rsp+78h+DeviceObject], rax; DeviceObject
0x1800553e4  mov     r9d, 2Fh ; '/'; DeviceType
0x1800553ea  cmovnz  edx, ebx
0x1800553ed  mov     [rsp+78h+Exclusive], r14b; Exclusive
0x1800553f2  add     edx, 20h ; ' '; DeviceExtensionSize
0x1800553f5  mov     [rsp+78h+DeviceCharacteristics], 100h; DeviceCharacteristics
0x1800553fd  xor     r8d, r8d; DeviceName
0x180055400  mov     rcx, rdi; DriverObject
0x180055403  call    cs:__imp_IoCreateDevice
0x18005540a  nop     dword ptr [rax+rax+00h]
0x18005540f  mov     ebx, eax
0x180055411  test    eax, eax
0x180055413  js      loc_1800554AE
0x180055419  mov     rax, [rsp+78h+SourceDevice]
0x18005541e  add     qword ptr [rax+40h], 20h ; ' '
0x180055423  mov     rcx, [rsp+78h+SourceDevice]; struct _DEVICE_OBJECT *
0x180055428  call    ?GetDeviceHeaderEx@CKsDevice@@SAPEAU_KSDEVICE_HEADER_EX@@PEAU_DEVICE_OBJECT@@@Z; CKsDevice::GetDeviceHeaderEx(_DEVICE_OBJECT *)
0x18005542d  mov     rcx, rax; Lock
0x180055430  mov     [rsp+78h+DeviceCharacteristics], 20h ; ' '; RemlockSize
0x180055438  xor     r9d, r9d; HighWatermark
0x18005543b  xor     r8d, r8d; MaxLockedMinutes
0x18005543e  mov     edx, 6564534Bh; AllocateTag
0x180055443  call    cs:__imp_IoInitializeRemoveLockEx
0x18005544a  nop     dword ptr [rax+rax+00h]
0x18005544f  mov     rcx, [rsp+78h+SourceDevice]; SourceDevice
0x180055454  mov     rdx, rsi; TargetDevice
0x180055457  call    cs:__imp_IoAttachDeviceToDeviceStack
0x18005545e  nop     dword ptr [rax+rax+00h]
0x180055463  mov     rdi, rax
0x180055466  test    rax, rax
0x180055469  jz      short loc_1800554E2
0x18005546b  mov     rcx, [rsp+78h+SourceDevice]
0x180055470  mov     r9, rbp; Descriptor
0x180055473  mov     r8, rax; NextDeviceObject
0x180055476  mov     rdx, rsi; PhysicalDeviceObject
0x180055479  bts     dword ptr [rcx+30h], 0Dh
0x18005547e  mov     rcx, [rsp+78h+SourceDevice]; FunctionalDeviceObject
0x180055483  call    KsInitializeDevice
0x180055488  mov     ebx, eax
0x18005548a  test    eax, eax
0x18005548c  jns     short loc_1800554BC
0x18005548e  mov     rcx, rdi; TargetDevice
0x180055491  call    cs:__imp_IoDetachDevice
0x180055498  nop     dword ptr [rax+rax+00h]
0x18005549d  mov     rcx, [rsp+78h+SourceDevice]; DeviceObject
0x1800554a2  call    cs:__imp_IoDeleteDevice
0x1800554a9  nop     dword ptr [rax+rax+00h]
0x1800554ae  mov     eax, ebx
0x1800554b0  add     rsp, 50h
0x1800554b4  pop     r14
0x1800554b6  pop     rdi
0x1800554b7  pop     rsi
0x1800554b8  pop     rbp
0x1800554b9  pop     rbx
0x1800554ba  retn
0x1800554bc  mov     rax, [rsp+78h+SourceDevice]
0x1800554c1  mov     rdi, [rsp+78h+Device]
0x1800554c9  btr     dword ptr [rax+30h], 7
0x1800554ce  test    rdi, rdi
0x1800554d1  jz      short loc_1800554AE
0x1800554d3  mov     rcx, [rsp+78h+SourceDevice]; FunctionalDeviceObject
0x1800554d8  call    KsGetDeviceForDeviceObject
0x1800554dd  mov     [rdi], rax
0x1800554e0  jmp     short loc_1800554AE
0x1800554e2  mov     ebx, 0C00002B6h
0x1800554e7  jmp     short loc_18005549D
0x1800554e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800554f0  cmp     [rcx+48h], r14w
0x1800554f5  jz      loc_1800553CE
0x1800554fb  mov     rcx, [rcx+40h]
0x1800554ff  lea     rax, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x180055506  mov     r9d, 12h
0x18005550c  mov     qword ptr [rsp+78h+DeviceCharacteristics], rax
0x180055511  mov     dl, 5
0x180055513  lea     r8d, [r9-11h]
0x180055517  call    WPP_RECORDER_SF_
0x18005551c  jmp     loc_1800553CE
```
