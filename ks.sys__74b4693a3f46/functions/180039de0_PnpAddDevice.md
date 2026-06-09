# PnpAddDevice

- ea: `0x180039de0`
- end: `0x180039ee7`
- name: `PnpAddDevice`
- size: `263`
- prototype: `__int64 __fastcall(PDRIVER_OBJECT DriverObject, PDEVICE_OBJECT TargetDevice)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180012db4`
- `0x180039de0`
- `0x180055070`
- `0x180055520`

## import_xrefs

- `ntoskrnl!IoDeleteDevice` at `0x180039eb8`
- `ntoskrnl!IoDeleteDevice` at `0x180039eb8`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x180039e71`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x180039e71`
- `ntoskrnl!IoCreateDevice` at `0x180039e35`
- `ntoskrnl!IoCreateDevice` at `0x180039e35`

## pseudocode

```c
NTSTATUS __fastcall PnpAddDevice(PDRIVER_OBJECT DriverObject, PDEVICE_OBJECT TargetDevice)
{
  NTSTATUS result; // eax
  NTSTATUS DeviceHeader; // ebx
  struct _DEVICE_OBJECT *v6; // rax
  __int64 v7; // rcx
  PDEVICE_OBJECT SourceDevice; // [rsp+60h] [rbp+18h] BYREF

  SourceDevice = 0;
  if ( ((__int64)WPP_MAIN_CB.Dpc.SystemArgument1 & 1) != 0 )
    McTemplateK0_EtwWriteTransfer(DriverObject, KS_PnpAddDevice_Start);
  result = IoCreateDevice(DriverObject, 8u, 0, 0x2Fu, 0, 0, &SourceDevice);
  if ( result >= 0 )
  {
    DeviceHeader = KsAllocateDeviceHeader(
                     (KSDEVICE_HEADER *)SourceDevice->DeviceExtension,
                     1u,
                     (PKSOBJECT_CREATE_ITEM)&ItemsList);
    if ( DeviceHeader >= 0 )
    {
      v6 = IoAttachDeviceToDeviceStack(SourceDevice, TargetDevice);
      if ( v6 )
      {
        KsSetDevicePnpAndBaseObject(*(KSDEVICE_HEADER *)SourceDevice->DeviceExtension, v6, SourceDevice);
        SourceDevice->Flags |= 0x2000u;
        SourceDevice->Flags &= ~0x80u;
        return 0;
      }
      DeviceHeader = -1073741130;
    }
    IoDeleteDevice(SourceDevice);
    if ( ((__int64)WPP_MAIN_CB.Dpc.SystemArgument1 & 1) != 0 )
      McTemplateK0_EtwWriteTransfer(v7, KS_PnpAddDevice_Stop);
    return DeviceHeader;
  }
  return result;
}

```

## disassembly

```asm
0x180039de0  mov     [rsp+arg_0], rbx
0x180039de5  push    rdi
0x180039de6  sub     rsp, 40h
0x180039dea  test    byte ptr cs:WPP_MAIN_CB.Dpc.SystemArgument1, 1
0x180039df1  mov     rdi, rdx
0x180039df4  mov     rbx, rcx
0x180039df7  mov     [rsp+48h+SourceDevice], 0
0x180039e00  jz      short loc_180039E0E
0x180039e02  lea     rdx, KS_PnpAddDevice_Start
0x180039e09  call    McTemplateK0_EtwWriteTransfer
0x180039e0e  mov     r9d, 2Fh ; '/'; DeviceType
0x180039e14  lea     rax, [rsp+48h+SourceDevice]
0x180039e19  mov     [rsp+48h+DeviceObject], rax; DeviceObject
0x180039e1e  xor     r8d, r8d; DeviceName
0x180039e21  mov     [rsp+48h+Exclusive], 0; Exclusive
0x180039e26  mov     rcx, rbx; DriverObject
0x180039e29  mov     [rsp+48h+DeviceCharacteristics], 0; DeviceCharacteristics
0x180039e31  lea     edx, [r9-27h]; DeviceExtensionSize
0x180039e35  call    cs:__imp_IoCreateDevice
0x180039e3c  nop     dword ptr [rax+rax+00h]
0x180039e41  test    eax, eax
0x180039e43  js      loc_180039EDB
0x180039e49  mov     rcx, [rsp+48h+SourceDevice]
0x180039e4e  lea     r8, ItemsList; ItemsList
0x180039e55  mov     edx, 1; ItemsCount
0x180039e5a  mov     rcx, [rcx+40h]; Header
0x180039e5e  call    KsAllocateDeviceHeader
0x180039e63  mov     ebx, eax
0x180039e65  test    eax, eax
0x180039e67  js      short loc_180039EB3
0x180039e69  mov     rcx, [rsp+48h+SourceDevice]; SourceDevice
0x180039e6e  mov     rdx, rdi; TargetDevice
0x180039e71  call    cs:__imp_IoAttachDeviceToDeviceStack
0x180039e78  nop     dword ptr [rax+rax+00h]
0x180039e7d  test    rax, rax
0x180039e80  jz      short loc_180039EAE
0x180039e82  mov     r8, [rsp+48h+SourceDevice]; BaseObject
0x180039e87  mov     rdx, rax; PnpDeviceObject
0x180039e8a  mov     rcx, [r8+40h]
0x180039e8e  mov     rcx, [rcx]; Header
0x180039e91  call    KsSetDevicePnpAndBaseObject
0x180039e96  mov     rax, [rsp+48h+SourceDevice]
0x180039e9b  bts     dword ptr [rax+30h], 0Dh
0x180039ea0  mov     rax, [rsp+48h+SourceDevice]
0x180039ea5  btr     dword ptr [rax+30h], 7
0x180039eaa  xor     eax, eax
0x180039eac  jmp     short loc_180039EDB
0x180039eae  mov     ebx, 0C00002B6h
0x180039eb3  mov     rcx, [rsp+48h+SourceDevice]; DeviceObject
0x180039eb8  call    cs:__imp_IoDeleteDevice
0x180039ebf  nop     dword ptr [rax+rax+00h]
0x180039ec4  test    byte ptr cs:WPP_MAIN_CB.Dpc.SystemArgument1, 1
0x180039ecb  jz      short loc_180039ED9
0x180039ecd  lea     rdx, KS_PnpAddDevice_Stop
0x180039ed4  call    McTemplateK0_EtwWriteTransfer
0x180039ed9  mov     eax, ebx
0x180039edb  mov     rbx, [rsp+48h+arg_0]
0x180039ee0  add     rsp, 40h
0x180039ee4  pop     rdi
0x180039ee5  retn
```
