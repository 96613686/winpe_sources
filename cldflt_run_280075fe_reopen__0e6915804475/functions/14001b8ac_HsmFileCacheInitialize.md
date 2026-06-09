# HsmFileCacheInitialize

- ea: `0x14001b8ac`
- end: `0x14001ba3f`
- name: `HsmFileCacheInitialize`
- size: `403`
- prototype: `__int64 __fastcall(PDRIVER_OBJECT DriverObject)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x140087490`

## callees

- `0x140003c50`
- `0x14000c12c`
- `0x14000dee4`
- `0x14001b8ac`

## import_xrefs

- `ntoskrnl!IoDeleteDevice` at `0x14001b9e6`
- `ntoskrnl!IoDeleteDevice` at `0x14001b9e6`
- `ntoskrnl!IoCreateDevice` at `0x14001b978`
- `ntoskrnl!IoCreateDevice` at `0x14001b978`

## pseudocode

```c
__int64 __fastcall HsmFileCacheInitialize(PDRIVER_OBJECT DriverObject)
{
  NTSTATUS v2; // edi
  struct _DEVICE_OBJECT *v3; // rcx
  __int64 DeviceCharacteristics; // [rsp+20h] [rbp-28h]
  PDEVICE_OBJECT DeviceObject; // [rsp+50h] [rbp+8h] BYREF

  DeviceObject = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids, DriverObject);
  }
  memset64(DriverObject->MajorFunction, (unsigned __int64)&HsmiFileCacheIrpNotImplemented, 0x1Cu);
  DriverObject->FastIoDispatch = 0;
  DriverObject->MajorFunction[3] = (PDRIVER_DISPATCH)HsmiFileCacheIrpRead;
  DriverObject->MajorFunction[4] = (PDRIVER_DISPATCH)&HsmiFileCacheIrpWrite;
  DriverObject->MajorFunction[5] = (PDRIVER_DISPATCH)&HsmiFileCacheIrpQueryInformation;
  DriverObject->MajorFunction[2] = (PDRIVER_DISPATCH)&HsmiFileCacheIrpClose;
  v2 = IoCreateDevice(DriverObject, 0, 0, 8u, 0x100u, 0, &DeviceObject);
  HsmDbgBreakOnStatus((unsigned int)v2);
  if ( v2 >= 0 )
  {
    v3 = 0;
    ::DeviceObject = DeviceObject;
    DeviceObject = 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      LODWORD(DeviceCharacteristics) = v2;
      WPP_SF_qd(
        WPP_GLOBAL_Control->AttachedDevice,
        19,
        WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids,
        DriverObject,
        DeviceCharacteristics);
    }
    v3 = DeviceObject;
  }
  if ( v3 )
    IoDeleteDevice(v3);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    LODWORD(DeviceCharacteristics) = v2;
    WPP_SF_qd(
      WPP_GLOBAL_Control->AttachedDevice,
      20,
      WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids,
      ::DeviceObject,
      DeviceCharacteristics);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14001b8ac  mov     [rsp+arg_8], rbx
0x14001b8b1  mov     [rsp+arg_10], rdi
0x14001b8b6  push    r14
0x14001b8b8  sub     rsp, 40h
0x14001b8bc  mov     rbx, rcx
0x14001b8bf  mov     [rsp+48h+arg_0], 0
0x14001b8c8  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b8cf  lea     r14, WPP_GLOBAL_Control
0x14001b8d6  cmp     rcx, r14
0x14001b8d9  jz      short loc_14001B900
0x14001b8db  mov     eax, [rcx+2Ch]
0x14001b8de  test    al, 8
0x14001b8e0  jz      short loc_14001B900
0x14001b8e2  cmp     byte ptr [rcx+29h], 5
0x14001b8e6  jb      short loc_14001B900
0x14001b8e8  mov     rcx, [rcx+18h]
0x14001b8ec  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x14001b8f3  mov     edx, 12h
0x14001b8f8  mov     r9, rbx
0x14001b8fb  call    WPP_SF_q
0x14001b900  lea     rax, HsmiFileCacheIrpNotImplemented
0x14001b907  mov     ecx, 1Ch
0x14001b90c  lea     rdi, [rbx+70h]
0x14001b910  mov     r9d, 8; DeviceType
0x14001b916  rep stosq
0x14001b919  lea     rax, HsmiFileCacheIrpRead
0x14001b920  mov     qword ptr [rbx+50h], 0
0x14001b928  mov     [rbx+88h], rax
0x14001b92f  xor     r8d, r8d; DeviceName
0x14001b932  lea     rax, HsmiFileCacheIrpWrite
0x14001b939  xor     edx, edx; DeviceExtensionSize
0x14001b93b  mov     [rbx+90h], rax
0x14001b942  mov     rcx, rbx; DriverObject
0x14001b945  lea     rax, HsmiFileCacheIrpQueryInformation
0x14001b94c  mov     [rbx+98h], rax
0x14001b953  lea     rax, HsmiFileCacheIrpClose
0x14001b95a  mov     [rbx+80h], rax
0x14001b961  lea     rax, [rsp+48h+arg_0]
0x14001b966  mov     [rsp+48h+DeviceObject], rax; DeviceObject
0x14001b96b  mov     [rsp+48h+Exclusive], 0; Exclusive
0x14001b970  mov     dword ptr [rsp+48h+DeviceCharacteristics], 100h; DeviceCharacteristics
0x14001b978  call    cs:__imp_IoCreateDevice
0x14001b97f  nop     dword ptr [rax+rax+00h]
0x14001b984  mov     ecx, eax
0x14001b986  mov     edi, eax
0x14001b988  call    HsmDbgBreakOnStatus
0x14001b98d  test    edi, edi
0x14001b98f  jns     short loc_14001B9CE
0x14001b991  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b998  cmp     rcx, r14
0x14001b99b  jz      short loc_14001B9C7
0x14001b99d  mov     edx, [rcx+2Ch]
0x14001b9a0  test    dl, 8
0x14001b9a3  jz      short loc_14001B9C7
0x14001b9a5  cmp     byte ptr [rcx+29h], 2
0x14001b9a9  jb      short loc_14001B9C7
0x14001b9ab  mov     rcx, [rcx+18h]
0x14001b9af  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x14001b9b6  mov     edx, 13h
0x14001b9bb  mov     dword ptr [rsp+48h+DeviceCharacteristics], edi
0x14001b9bf  mov     r9, rbx
0x14001b9c2  call    WPP_SF_qd
0x14001b9c7  mov     rcx, [rsp+48h+arg_0]
0x14001b9cc  jmp     short loc_14001B9E1
0x14001b9ce  mov     rax, [rsp+48h+arg_0]
0x14001b9d3  xor     ecx, ecx; DeviceObject
0x14001b9d5  mov     cs:DeviceObject, rax
0x14001b9dc  mov     [rsp+48h+arg_0], rcx
0x14001b9e1  test    rcx, rcx
0x14001b9e4  jz      short loc_14001B9F2
0x14001b9e6  call    cs:__imp_IoDeleteDevice
0x14001b9ed  nop     dword ptr [rax+rax+00h]
0x14001b9f2  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b9f9  cmp     rcx, r14
0x14001b9fc  jz      short loc_14001BA2B
0x14001b9fe  mov     eax, [rcx+2Ch]
0x14001ba01  test    al, 8
0x14001ba03  jz      short loc_14001BA2B
0x14001ba05  cmp     byte ptr [rcx+29h], 5
0x14001ba09  jb      short loc_14001BA2B
0x14001ba0b  mov     r9, cs:DeviceObject
0x14001ba12  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x14001ba19  mov     rcx, [rcx+18h]
0x14001ba1d  mov     edx, 14h
0x14001ba22  mov     dword ptr [rsp+48h+DeviceCharacteristics], edi
0x14001ba26  call    WPP_SF_qd
0x14001ba2b  mov     rbx, [rsp+48h+arg_8]
0x14001ba30  mov     eax, edi
0x14001ba32  mov     rdi, [rsp+48h+arg_10]
0x14001ba37  add     rsp, 40h
0x14001ba3b  pop     r14
0x14001ba3d  retn
```
