# PnpAddDevice

- ea: `0x180039e30`
- end: `0x180039f37`
- name: `PnpAddDevice`
- size: `263`
- prototype: `NTSTATUS __fastcall(PDRIVER_OBJECT DriverObject, PDEVICE_OBJECT TargetDevice, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180012db4`
- `0x180039e30`
- `0x180055210`
- `0x1800556c0`

## import_xrefs

- `ntoskrnl!IoDeleteDevice` at `0x180039f08`
- `ntoskrnl!IoDeleteDevice` at `0x180039f08`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x180039ec1`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x180039ec1`
- `ntoskrnl!IoCreateDevice` at `0x180039e85`
- `ntoskrnl!IoCreateDevice` at `0x180039e85`

## pseudocode

```c
NTSTATUS __fastcall PnpAddDevice(PDRIVER_OBJECT DriverObject, PDEVICE_OBJECT TargetDevice, __int64 a3)
{
  NTSTATUS result; // eax
  NTSTATUS DeviceHeader; // ebx
  struct _DEVICE_OBJECT *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // r8
  PDEVICE_OBJECT SourceDevice; // [rsp+60h] [rbp+18h] BYREF

  SourceDevice = 0;
  if ( ((__int64)WPP_MAIN_CB.Dpc.SystemArgument1 & 1) != 0 )
    McTemplateK0_EtwWriteTransfer((__int64)DriverObject, (const EVENT_DESCRIPTOR *)KS_PnpAddDevice_Start, a3);
  result = IoCreateDevice(DriverObject, 8u, 0, 0x2Fu, 0, 0, &SourceDevice);
  if ( result >= 0 )
  {
    DeviceHeader = KsAllocateDeviceHeader(
                     (KSDEVICE_HEADER *)SourceDevice->DeviceExtension,
                     1u,
                     (PKSOBJECT_CREATE_ITEM)&ItemsList);
    if ( DeviceHeader >= 0 )
    {
      v7 = IoAttachDeviceToDeviceStack(SourceDevice, TargetDevice);
      if ( v7 )
      {
        KsSetDevicePnpAndBaseObject(*(KSDEVICE_HEADER *)SourceDevice->DeviceExtension, v7, SourceDevice);
        SourceDevice->Flags |= 0x2000u;
        SourceDevice->Flags &= ~0x80u;
        return 0;
      }
      DeviceHeader = -1073741130;
    }
    IoDeleteDevice(SourceDevice);
    if ( ((__int64)WPP_MAIN_CB.Dpc.SystemArgument1 & 1) != 0 )
      McTemplateK0_EtwWriteTransfer(v8, (const EVENT_DESCRIPTOR *)KS_PnpAddDevice_Stop, v9);
    return DeviceHeader;
  }
  return result;
}

```

## disassembly

```asm
0x180039e30  mov     [rsp+arg_0], rbx
0x180039e35  push    rdi
0x180039e36  sub     rsp, 40h
0x180039e3a  test    byte ptr cs:WPP_MAIN_CB.Dpc.SystemArgument1, 1
0x180039e41  mov     rdi, rdx
0x180039e44  mov     rbx, rcx
0x180039e47  mov     [rsp+48h+SourceDevice], 0
0x180039e50  jz      short loc_180039E5E
0x180039e52  lea     rdx, KS_PnpAddDevice_Start
0x180039e59  call    McTemplateK0_EtwWriteTransfer
0x180039e5e  mov     r9d, 2Fh ; '/'; DeviceType
0x180039e64  lea     rax, [rsp+48h+SourceDevice]
0x180039e69  mov     [rsp+48h+DeviceObject], rax; DeviceObject
0x180039e6e  xor     r8d, r8d; DeviceName
0x180039e71  mov     [rsp+48h+Exclusive], 0; Exclusive
0x180039e76  mov     rcx, rbx; DriverObject
0x180039e79  mov     [rsp+48h+DeviceCharacteristics], 0; DeviceCharacteristics
0x180039e81  lea     edx, [r9-27h]; DeviceExtensionSize
0x180039e85  call    cs:__imp_IoCreateDevice
0x180039e8c  nop     dword ptr [rax+rax+00h]
0x180039e91  test    eax, eax
0x180039e93  js      loc_180039F2B
0x180039e99  mov     rcx, [rsp+48h+SourceDevice]
0x180039e9e  lea     r8, ItemsList; ItemsList
0x180039ea5  mov     edx, 1; ItemsCount
0x180039eaa  mov     rcx, [rcx+40h]; Header
0x180039eae  call    KsAllocateDeviceHeader
0x180039eb3  mov     ebx, eax
0x180039eb5  test    eax, eax
0x180039eb7  js      short loc_180039F03
0x180039eb9  mov     rcx, [rsp+48h+SourceDevice]; SourceDevice
0x180039ebe  mov     rdx, rdi; TargetDevice
0x180039ec1  call    cs:__imp_IoAttachDeviceToDeviceStack
0x180039ec8  nop     dword ptr [rax+rax+00h]
0x180039ecd  test    rax, rax
0x180039ed0  jz      short loc_180039EFE
0x180039ed2  mov     r8, [rsp+48h+SourceDevice]; BaseObject
0x180039ed7  mov     rdx, rax; PnpDeviceObject
0x180039eda  mov     rcx, [r8+40h]
0x180039ede  mov     rcx, [rcx]; Header
0x180039ee1  call    KsSetDevicePnpAndBaseObject
0x180039ee6  mov     rax, [rsp+48h+SourceDevice]
0x180039eeb  bts     dword ptr [rax+30h], 0Dh
0x180039ef0  mov     rax, [rsp+48h+SourceDevice]
0x180039ef5  btr     dword ptr [rax+30h], 7
0x180039efa  xor     eax, eax
0x180039efc  jmp     short loc_180039F2B
0x180039efe  mov     ebx, 0C00002B6h
0x180039f03  mov     rcx, [rsp+48h+SourceDevice]; DeviceObject
0x180039f08  call    cs:__imp_IoDeleteDevice
0x180039f0f  nop     dword ptr [rax+rax+00h]
0x180039f14  test    byte ptr cs:WPP_MAIN_CB.Dpc.SystemArgument1, 1
0x180039f1b  jz      short loc_180039F29
0x180039f1d  lea     rdx, KS_PnpAddDevice_Stop
0x180039f24  call    McTemplateK0_EtwWriteTransfer
0x180039f29  mov     eax, ebx
0x180039f2b  mov     rbx, [rsp+48h+arg_0]
0x180039f30  add     rsp, 40h
0x180039f34  pop     rdi
0x180039f35  retn
```
