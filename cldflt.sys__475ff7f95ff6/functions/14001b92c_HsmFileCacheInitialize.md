# HsmFileCacheInitialize

- ea: `0x14001b92c`
- end: `0x14001babf`
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
- `0x14001b92c`

## import_xrefs

- `ntoskrnl!IoDeleteDevice` at `0x14001ba66`
- `ntoskrnl!IoDeleteDevice` at `0x14001ba66`
- `ntoskrnl!IoCreateDevice` at `0x14001b9f8`
- `ntoskrnl!IoCreateDevice` at `0x14001b9f8`

## pseudocode

```c
__int64 __fastcall HsmFileCacheInitialize(PDRIVER_OBJECT DriverObject)
{
  NTSTATUS v2; // edi
  struct _DEVICE_OBJECT *v3; // rcx
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
  DriverObject->MajorFunction[3] = (PDRIVER_DISPATCH)&HsmiFileCacheIrpRead;
  DriverObject->MajorFunction[4] = (PDRIVER_DISPATCH)&HsmiFileCacheIrpWrite;
  DriverObject->MajorFunction[5] = (PDRIVER_DISPATCH)&HsmiFileCacheIrpQueryInformation;
  DriverObject->MajorFunction[2] = (PDRIVER_DISPATCH)&HsmiFileCacheIrpClose;
  v2 = IoCreateDevice(DriverObject, 0, 0, 8u, 0x100u, 0, &DeviceObject);
  HsmDbgBreakOnStatus(v2);
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
      WPP_SF_qd(
        WPP_GLOBAL_Control->AttachedDevice,
        19,
        WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids,
        DriverObject,
        v2);
    }
    v3 = DeviceObject;
  }
  if ( v3 )
    IoDeleteDevice(v3);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qd(
      WPP_GLOBAL_Control->AttachedDevice,
      20,
      WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids,
      ::DeviceObject,
      v2);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14001b92c  mov     [rsp+arg_8], rbx
0x14001b931  mov     [rsp+arg_10], rdi
0x14001b936  push    r14
0x14001b938  sub     rsp, 40h
0x14001b93c  mov     rbx, rcx
0x14001b93f  mov     [rsp+48h+arg_0], 0
0x14001b948  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b94f  lea     r14, WPP_GLOBAL_Control
0x14001b956  cmp     rcx, r14
0x14001b959  jz      short loc_14001B980
0x14001b95b  mov     eax, [rcx+2Ch]
0x14001b95e  test    al, 8
0x14001b960  jz      short loc_14001B980
0x14001b962  cmp     byte ptr [rcx+29h], 5
0x14001b966  jb      short loc_14001B980
0x14001b968  mov     rcx, [rcx+18h]
0x14001b96c  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x14001b973  mov     edx, 12h
0x14001b978  mov     r9, rbx
0x14001b97b  call    WPP_SF_q
0x14001b980  lea     rax, HsmiFileCacheIrpNotImplemented
0x14001b987  mov     ecx, 1Ch
0x14001b98c  lea     rdi, [rbx+70h]
0x14001b990  mov     r9d, 8; DeviceType
0x14001b996  rep stosq
0x14001b999  lea     rax, HsmiFileCacheIrpRead
0x14001b9a0  mov     qword ptr [rbx+50h], 0
0x14001b9a8  mov     [rbx+88h], rax
0x14001b9af  xor     r8d, r8d; DeviceName
0x14001b9b2  lea     rax, HsmiFileCacheIrpWrite
0x14001b9b9  xor     edx, edx; DeviceExtensionSize
0x14001b9bb  mov     [rbx+90h], rax
0x14001b9c2  mov     rcx, rbx; DriverObject
0x14001b9c5  lea     rax, HsmiFileCacheIrpQueryInformation
0x14001b9cc  mov     [rbx+98h], rax
0x14001b9d3  lea     rax, HsmiFileCacheIrpClose
0x14001b9da  mov     [rbx+80h], rax
0x14001b9e1  lea     rax, [rsp+48h+arg_0]
0x14001b9e6  mov     [rsp+48h+DeviceObject], rax; DeviceObject
0x14001b9eb  mov     [rsp+48h+Exclusive], 0; Exclusive
0x14001b9f0  mov     [rsp+48h+DeviceCharacteristics], 100h; DeviceCharacteristics
0x14001b9f8  call    cs:__imp_IoCreateDevice
0x14001b9ff  nop     dword ptr [rax+rax+00h]
0x14001ba04  mov     ecx, eax
0x14001ba06  mov     edi, eax
0x14001ba08  call    HsmDbgBreakOnStatus
0x14001ba0d  test    edi, edi
0x14001ba0f  jns     short loc_14001BA4E
0x14001ba11  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ba18  cmp     rcx, r14
0x14001ba1b  jz      short loc_14001BA47
0x14001ba1d  mov     edx, [rcx+2Ch]
0x14001ba20  test    dl, 8
0x14001ba23  jz      short loc_14001BA47
0x14001ba25  cmp     byte ptr [rcx+29h], 2
0x14001ba29  jb      short loc_14001BA47
0x14001ba2b  mov     rcx, [rcx+18h]
0x14001ba2f  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x14001ba36  mov     edx, 13h
0x14001ba3b  mov     [rsp+48h+DeviceCharacteristics], edi
0x14001ba3f  mov     r9, rbx
0x14001ba42  call    WPP_SF_qd
0x14001ba47  mov     rcx, [rsp+48h+arg_0]
0x14001ba4c  jmp     short loc_14001BA61
0x14001ba4e  mov     rax, [rsp+48h+arg_0]
0x14001ba53  xor     ecx, ecx; DeviceObject
0x14001ba55  mov     cs:DeviceObject, rax
0x14001ba5c  mov     [rsp+48h+arg_0], rcx
0x14001ba61  test    rcx, rcx
0x14001ba64  jz      short loc_14001BA72
0x14001ba66  call    cs:__imp_IoDeleteDevice
0x14001ba6d  nop     dword ptr [rax+rax+00h]
0x14001ba72  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ba79  cmp     rcx, r14
0x14001ba7c  jz      short loc_14001BAAB
0x14001ba7e  mov     eax, [rcx+2Ch]
0x14001ba81  test    al, 8
0x14001ba83  jz      short loc_14001BAAB
0x14001ba85  cmp     byte ptr [rcx+29h], 5
0x14001ba89  jb      short loc_14001BAAB
0x14001ba8b  mov     r9, cs:DeviceObject
0x14001ba92  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x14001ba99  mov     rcx, [rcx+18h]
0x14001ba9d  mov     edx, 14h
0x14001baa2  mov     [rsp+48h+DeviceCharacteristics], edi
0x14001baa6  call    WPP_SF_qd
0x14001baab  mov     rbx, [rsp+48h+arg_8]
0x14001bab0  mov     eax, edi
0x14001bab2  mov     rdi, [rsp+48h+arg_10]
0x14001bab7  add     rsp, 40h
0x14001babb  pop     r14
0x14001babd  retn
```
