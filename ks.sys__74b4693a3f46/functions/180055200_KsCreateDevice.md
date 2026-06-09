# KsCreateDevice

- ea: `0x180055200`
- end: `0x180055381`
- name: `KsCreateDevice`
- size: `385`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PDEVICE_OBJECT PhysicalDeviceObject, const KSDEVICE_DESCRIPTOR *Descriptor, ULONG ExtensionSize, PKSDEVICE *Device)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180055470`
- `0x18006f6a0`

## callees

- `0x180004150`
- `0x18000b7bc`
- `0x18000c4c8`
- `0x180055200`
- `0x180055390`

## import_xrefs

- `ntoskrnl!IoDetachDevice` at `0x1800552f1`
- `ntoskrnl!IoDetachDevice` at `0x1800552f1`
- `ntoskrnl!IoDeleteDevice` at `0x180055302`
- `ntoskrnl!IoDeleteDevice` at `0x180055302`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x1800552b7`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x1800552b7`
- `ntoskrnl!IoCreateDevice` at `0x180055263`
- `ntoskrnl!IoCreateDevice` at `0x180055263`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x1800552a3`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x1800552a3`

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
0x180055200  push    rbx
0x180055202  push    rbp
0x180055203  push    rsi
0x180055204  push    rdi
0x180055205  push    r14
0x180055207  sub     rsp, 50h
0x18005520b  mov     ebx, r9d
0x18005520e  mov     rbp, r8
0x180055211  mov     rsi, rdx
0x180055214  mov     rdi, rcx
0x180055217  lea     rax, WPP_RECORDER_INITIALIZED
0x18005521e  xor     r14d, r14d
0x180055221  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180055228  jnz     loc_180055349
0x18005522e  mov     edx, 8
0x180055233  mov     [rsp+78h+SourceDevice], r14
0x180055238  lea     rax, [rsp+78h+SourceDevice]
0x18005523d  test    ebx, ebx
0x18005523f  mov     [rsp+78h+DeviceObject], rax; DeviceObject
0x180055244  mov     r9d, 2Fh ; '/'; DeviceType
0x18005524a  cmovnz  edx, ebx
0x18005524d  mov     [rsp+78h+Exclusive], r14b; Exclusive
0x180055252  add     edx, 20h ; ' '; DeviceExtensionSize
0x180055255  mov     [rsp+78h+DeviceCharacteristics], 100h; DeviceCharacteristics
0x18005525d  xor     r8d, r8d; DeviceName
0x180055260  mov     rcx, rdi; DriverObject
0x180055263  call    cs:__imp_IoCreateDevice
0x18005526a  nop     dword ptr [rax+rax+00h]
0x18005526f  mov     ebx, eax
0x180055271  test    eax, eax
0x180055273  js      loc_18005530E
0x180055279  mov     rax, [rsp+78h+SourceDevice]
0x18005527e  add     qword ptr [rax+40h], 20h ; ' '
0x180055283  mov     rcx, [rsp+78h+SourceDevice]; struct _DEVICE_OBJECT *
0x180055288  call    ?GetDeviceHeaderEx@CKsDevice@@SAPEAU_KSDEVICE_HEADER_EX@@PEAU_DEVICE_OBJECT@@@Z; CKsDevice::GetDeviceHeaderEx(_DEVICE_OBJECT *)
0x18005528d  mov     rcx, rax; Lock
0x180055290  mov     [rsp+78h+DeviceCharacteristics], 20h ; ' '; RemlockSize
0x180055298  xor     r9d, r9d; HighWatermark
0x18005529b  xor     r8d, r8d; MaxLockedMinutes
0x18005529e  mov     edx, 6564534Bh; AllocateTag
0x1800552a3  call    cs:__imp_IoInitializeRemoveLockEx
0x1800552aa  nop     dword ptr [rax+rax+00h]
0x1800552af  mov     rcx, [rsp+78h+SourceDevice]; SourceDevice
0x1800552b4  mov     rdx, rsi; TargetDevice
0x1800552b7  call    cs:__imp_IoAttachDeviceToDeviceStack
0x1800552be  nop     dword ptr [rax+rax+00h]
0x1800552c3  mov     rdi, rax
0x1800552c6  test    rax, rax
0x1800552c9  jz      short loc_180055342
0x1800552cb  mov     rcx, [rsp+78h+SourceDevice]
0x1800552d0  mov     r9, rbp; Descriptor
0x1800552d3  mov     r8, rax; NextDeviceObject
0x1800552d6  mov     rdx, rsi; PhysicalDeviceObject
0x1800552d9  bts     dword ptr [rcx+30h], 0Dh
0x1800552de  mov     rcx, [rsp+78h+SourceDevice]; FunctionalDeviceObject
0x1800552e3  call    KsInitializeDevice
0x1800552e8  mov     ebx, eax
0x1800552ea  test    eax, eax
0x1800552ec  jns     short loc_18005531C
0x1800552ee  mov     rcx, rdi; TargetDevice
0x1800552f1  call    cs:__imp_IoDetachDevice
0x1800552f8  nop     dword ptr [rax+rax+00h]
0x1800552fd  mov     rcx, [rsp+78h+SourceDevice]; DeviceObject
0x180055302  call    cs:__imp_IoDeleteDevice
0x180055309  nop     dword ptr [rax+rax+00h]
0x18005530e  mov     eax, ebx
0x180055310  add     rsp, 50h
0x180055314  pop     r14
0x180055316  pop     rdi
0x180055317  pop     rsi
0x180055318  pop     rbp
0x180055319  pop     rbx
0x18005531a  retn
0x18005531c  mov     rax, [rsp+78h+SourceDevice]
0x180055321  mov     rdi, [rsp+78h+Device]
0x180055329  btr     dword ptr [rax+30h], 7
0x18005532e  test    rdi, rdi
0x180055331  jz      short loc_18005530E
0x180055333  mov     rcx, [rsp+78h+SourceDevice]; FunctionalDeviceObject
0x180055338  call    KsGetDeviceForDeviceObject
0x18005533d  mov     [rdi], rax
0x180055340  jmp     short loc_18005530E
0x180055342  mov     ebx, 0C00002B6h
0x180055347  jmp     short loc_1800552FD
0x180055349  mov     rcx, cs:WPP_GLOBAL_Control
0x180055350  cmp     [rcx+48h], r14w
0x180055355  jz      loc_18005522E
0x18005535b  mov     rcx, [rcx+40h]
0x18005535f  lea     rax, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x180055366  mov     r9d, 12h
0x18005536c  mov     qword ptr [rsp+78h+DeviceCharacteristics], rax
0x180055371  mov     dl, 5
0x180055373  lea     r8d, [r9-11h]
0x180055377  call    WPP_RECORDER_SF_
0x18005537c  jmp     loc_18005522E
```
