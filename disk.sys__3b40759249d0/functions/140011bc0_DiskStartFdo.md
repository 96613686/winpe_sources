# DiskStartFdo

- ea: `0x140011bc0`
- end: `0x140011ed0`
- name: `DiskStartFdo`
- size: `784`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400034a0`
- `0x14000f804`
- `0x140011bc0`
- `0x140012ca0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140011c96`
- `ntoskrnl!KeWaitForSingleObject` at `0x140011c96`
- `ntoskrnl!KeInitializeEvent` at `0x140011c15`
- `ntoskrnl!KeInitializeEvent` at `0x140011c15`
- `ntoskrnl!IofCallDriver` at `0x140011c6e`
- `ntoskrnl!IofCallDriver` at `0x140011c6e`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140011c57`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140011c57`
- `CLASSPNP!ClassGetDeviceParameter` at `0x140011d07`
- `CLASSPNP!ClassGetDeviceParameter` at `0x140011e67`
- `CLASSPNP!ClassGetDeviceParameter` at `0x140011d07`
- `CLASSPNP!ClassGetDeviceParameter` at `0x140011e67`

## string_xrefs

- `0x140011e4c`: `CacheIsPowerProtected`
- `0x140011cf0`: `UserWriteCacheSetting`

## pseudocode

```c
__int64 __fastcall DiskStartFdo(PDEVICE_OBJECT DeviceObject)
{
  struct _FUNCTIONAL_DEVICE_EXTENSION *DeviceExtension; // rbx
  char *DriverData; // rsi
  char v4; // di
  IRP *v5; // rax
  bool v6; // al
  ULONG *v7; // rsi
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  bool v10; // al
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp+7h] BYREF
  __int128 v13; // [rsp+60h] [rbp+17h] BYREF
  __int64 v14; // [rsp+70h] [rbp+27h]
  struct _KEVENT Event; // [rsp+78h] [rbp+2Fh] BYREF
  ULONG ParameterValue; // [rsp+B0h] [rbp+67h] BYREF
  __int64 OutputBuffer; // [rsp+B8h] [rbp+6Fh] BYREF

  DeviceExtension = (struct _FUNCTIONAL_DEVICE_EXTENSION *)DeviceObject->DeviceExtension;
  v14 = 0;
  DriverData = (char *)DeviceExtension->CommonExtension.DriverData;
  v4 = 1;
  OutputBuffer = 0;
  v13 = 0;
  ParameterValue = 0;
  memset(&Event, 0, sizeof(Event));
  IoStatusBlock = 0;
  KeInitializeEvent(&Event, SynchronizationEvent, 0);
  v5 = IoBuildDeviceIoControlRequest(0x2D0C14u, DeviceObject, 0, 0, &OutputBuffer, 8u, 0, &Event, &IoStatusBlock);
  if ( v5 && IofCallDriver(DeviceObject, v5) == 259 )
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
  DeviceExtension->DeviceFlags &= ~1u;
  v6 = (DeviceExtension->DeviceFlags & 1) != 0
    && (DeviceExtension->DeviceFlags & 0x10) == 0
    && (DeviceExtension->ScanForSpecialFlags & 0x80u) == 0;
  v7 = (ULONG *)(DriverData + 520);
  DeviceExtension->CdbForceUnitAccess = v6;
  *v7 = -1;
  ClassGetDeviceParameter(DeviceExtension, (PWSTR)L"Disk", (PWSTR)L"UserWriteCacheSetting", v7);
  if ( *v7 == -1 )
  {
    if ( (DeviceExtension->ScanForSpecialFlags & 0x10) != 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
      {
        goto LABEL_27;
      }
      v9 = 23;
    }
    else if ( !BYTE6(OutputBuffer) || HIBYTE(OutputBuffer) )
    {
      if ( !BYTE5(OutputBuffer) )
        goto LABEL_28;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
      {
        goto LABEL_27;
      }
      v9 = 25;
    }
    else
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
      {
        goto LABEL_27;
      }
      v9 = 24;
    }
    WPP_SF_q(v8->AttachedDevice, v9, WPP_05abe5c235553bdb89a3b8ecfd575366_Traceguids, DeviceObject);
LABEL_27:
    *v7 = 0;
  }
LABEL_28:
  if ( (int)DiskGetCacheInformation(DeviceExtension, &v13) < 0 )
    goto LABEL_40;
  if ( BYTE2(v13) != 1 )
  {
    if ( *v7 != 1 )
      goto LABEL_40;
    BYTE2(v13) = 1;
    goto LABEL_39;
  }
  DeviceExtension->DeviceFlags |= 1u;
  v10 = (DeviceExtension->DeviceFlags & 1) != 0
     && (DeviceExtension->DeviceFlags & 0x10) == 0
     && (DeviceExtension->ScanForSpecialFlags & 0x80u) == 0;
  DeviceExtension->CdbForceUnitAccess = v10;
  if ( !*v7 )
  {
    BYTE2(v13) = 0;
LABEL_39:
    DiskSetCacheInformation((__int64)DeviceExtension, &v13);
  }
LABEL_40:
  DeviceExtension->DeviceFlags &= ~0x10u;
  ClassGetDeviceParameter(DeviceExtension, (PWSTR)L"Disk", (PWSTR)L"CacheIsPowerProtected", &ParameterValue);
  if ( ParameterValue == 1 )
    DeviceExtension->DeviceFlags |= 0x10u;
  if ( (DeviceExtension->DeviceFlags & 1) == 0
    || (DeviceExtension->DeviceFlags & 0x10) != 0
    || (DeviceExtension->ScanForSpecialFlags & 0x80u) != 0 )
  {
    v4 = 0;
  }
  DeviceExtension->CdbForceUnitAccess = v4;
  return 0;
}

```

## disassembly

```asm
0x140011bc0  mov     [rsp-8+arg_10], rbx
0x140011bc5  mov     [rsp-8+arg_18], rsi
0x140011bca  push    rbp
0x140011bcb  push    rdi
0x140011bcc  push    r14
0x140011bce  lea     rbp, [rsp-47h]
0x140011bd3  sub     rsp, 90h
0x140011bda  mov     rbx, [rcx+40h]
0x140011bde  xor     eax, eax
0x140011be0  xorps   xmm0, xmm0
0x140011be3  mov     [rbp+57h+var_30], rax
0x140011be7  mov     r14, rcx
0x140011bea  mov     [rbp+57h+Event.Header.WaitListHead.Blink], rax
0x140011bee  xor     r8d, r8d; State
0x140011bf1  lea     rcx, [rbp+57h+Event]; Event
0x140011bf5  mov     rsi, [rbx+60h]
0x140011bf9  lea     edi, [rax+1]
0x140011bfc  mov     edx, edi; Type
0x140011bfe  mov     [rbp+57h+arg_8], 0
0x140011c06  movups  [rbp+57h+var_40], xmm0
0x140011c0a  mov     [rbp+57h+ParameterValue], eax
0x140011c0d  movups  xmmword ptr [rbp+57h+Event.Header], xmm0
0x140011c11  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x140011c15  call    cs:__imp_KeInitializeEvent
0x140011c1c  nop     dword ptr [rax+rax+00h]
0x140011c21  lea     rax, [rbp+57h+var_50]
0x140011c25  xor     r9d, r9d; InputBufferLength
0x140011c28  mov     [rsp+0A0h+IoStatusBlock], rax; IoStatusBlock
0x140011c2d  xor     r8d, r8d; InputBuffer
0x140011c30  lea     rax, [rbp+57h+Event]
0x140011c34  mov     rdx, r14; DeviceObject
0x140011c37  mov     [rsp+0A0h+var_68], rax; Event
0x140011c3c  mov     ecx, 2D0C14h; IoControlCode
0x140011c41  mov     [rsp+0A0h+InternalDeviceIoControl], 0; InternalDeviceIoControl
0x140011c46  lea     rax, [rbp+57h+arg_8]
0x140011c4a  mov     [rsp+0A0h+OutputBufferLength], 8; OutputBufferLength
0x140011c52  mov     [rsp+0A0h+OutputBuffer], rax; OutputBuffer
0x140011c57  call    cs:__imp_IoBuildDeviceIoControlRequest
0x140011c5e  nop     dword ptr [rax+rax+00h]
0x140011c63  test    rax, rax
0x140011c66  jz      short loc_140011CA2
0x140011c68  mov     rdx, rax; Irp
0x140011c6b  mov     rcx, r14; DeviceObject
0x140011c6e  call    cs:__imp_IofCallDriver
0x140011c75  nop     dword ptr [rax+rax+00h]
0x140011c7a  cmp     eax, 103h
0x140011c7f  jnz     short loc_140011CA2
0x140011c81  xor     r9d, r9d; Alertable
0x140011c84  mov     [rsp+0A0h+OutputBuffer], 0; Timeout
0x140011c8d  xor     r8d, r8d; WaitMode
0x140011c90  lea     rcx, [rbp+57h+Event]; Object
0x140011c94  xor     edx, edx; WaitReason
0x140011c96  call    cs:__imp_KeWaitForSingleObject
0x140011c9d  nop     dword ptr [rax+rax+00h]
0x140011ca2  movzx   eax, word ptr [rbx+280h]
0x140011ca9  mov     ecx, 0FFFEh
0x140011cae  and     ax, cx
0x140011cb1  mov     [rbx+280h], ax
0x140011cb8  movzx   eax, word ptr [rbx+280h]
0x140011cbf  test    dil, al
0x140011cc2  jz      short loc_140011CDE
0x140011cc4  movzx   eax, word ptr [rbx+280h]
0x140011ccb  test    al, 10h
0x140011ccd  jnz     short loc_140011CDE
0x140011ccf  mov     eax, [rbx+36Ch]
0x140011cd5  test    al, al
0x140011cd7  js      short loc_140011CDE
0x140011cd9  mov     al, dil
0x140011cdc  jmp     short loc_140011CE0
0x140011cde  xor     al, al
0x140011ce0  add     rsi, 208h
0x140011ce7  mov     [rbx+283h], al
0x140011ced  mov     r9, rsi; ParameterValue
0x140011cf0  lea     r8, ParameterName; "UserWriteCacheSetting"
0x140011cf7  lea     rdx, SubkeyName; "Disk"
0x140011cfe  mov     rcx, rbx; FdoExtension
0x140011d01  mov     dword ptr [rsi], 0FFFFFFFFh
0x140011d07  call    cs:__imp_ClassGetDeviceParameter
0x140011d0e  nop     dword ptr [rax+rax+00h]
0x140011d13  cmp     dword ptr [rsi], 0FFFFFFFFh
0x140011d16  jnz     loc_140011DC8
0x140011d1c  mov     eax, [rbx+36Ch]
0x140011d22  test    al, 10h
0x140011d24  jz      short loc_140011D51
0x140011d26  mov     rcx, cs:WPP_GLOBAL_Control
0x140011d2d  lea     rax, WPP_GLOBAL_Control
0x140011d34  cmp     rcx, rax
0x140011d37  jz      loc_140011DC2
0x140011d3d  mov     eax, [rcx+2Ch]
0x140011d40  test    al, 2
0x140011d42  jz      short loc_140011DC2
0x140011d44  cmp     byte ptr [rcx+29h], 3
0x140011d48  jb      short loc_140011DC2
0x140011d4a  mov     edx, 17h
0x140011d4f  jmp     short loc_140011DAF
0x140011d51  cmp     byte ptr [rbp+57h+arg_8+6], 0
0x140011d55  jz      short loc_140011D84
0x140011d57  cmp     byte ptr [rbp+57h+arg_8+7], 0
0x140011d5b  jnz     short loc_140011D84
0x140011d5d  mov     rcx, cs:WPP_GLOBAL_Control
0x140011d64  lea     rax, WPP_GLOBAL_Control
0x140011d6b  cmp     rcx, rax
0x140011d6e  jz      short loc_140011DC2
0x140011d70  mov     eax, [rcx+2Ch]
0x140011d73  test    al, 2
0x140011d75  jz      short loc_140011DC2
0x140011d77  cmp     byte ptr [rcx+29h], 3
0x140011d7b  jb      short loc_140011DC2
0x140011d7d  mov     edx, 18h
0x140011d82  jmp     short loc_140011DAF
0x140011d84  cmp     byte ptr [rbp+57h+arg_8+5], 0
0x140011d88  jz      short loc_140011DC8
0x140011d8a  mov     rcx, cs:WPP_GLOBAL_Control
0x140011d91  lea     rax, WPP_GLOBAL_Control
0x140011d98  cmp     rcx, rax
0x140011d9b  jz      short loc_140011DC2
0x140011d9d  mov     eax, [rcx+2Ch]
0x140011da0  test    al, 2
0x140011da2  jz      short loc_140011DC2
0x140011da4  cmp     byte ptr [rcx+29h], 3
0x140011da8  jb      short loc_140011DC2
0x140011daa  mov     edx, 19h
0x140011daf  mov     rcx, [rcx+18h]
0x140011db3  lea     r8, WPP_05abe5c235553bdb89a3b8ecfd575366_Traceguids
0x140011dba  mov     r9, r14
0x140011dbd  call    WPP_SF_q
0x140011dc2  mov     dword ptr [rsi], 0
0x140011dc8  lea     rdx, [rbp+57h+var_40]
0x140011dcc  mov     rcx, rbx
0x140011dcf  call    DiskGetCacheInformation
0x140011dd4  test    eax, eax
0x140011dd6  js      short loc_140011E3C
0x140011dd8  cmp     byte ptr [rbp+57h+var_40+2], dil
0x140011ddc  jnz     short loc_140011E28
0x140011dde  movzx   eax, word ptr [rbx+280h]
0x140011de5  or      ax, di
0x140011de8  mov     [rbx+280h], ax
0x140011def  movzx   eax, word ptr [rbx+280h]
0x140011df6  test    dil, al
0x140011df9  jz      short loc_140011E15
0x140011dfb  movzx   eax, word ptr [rbx+280h]
0x140011e02  test    al, 10h
0x140011e04  jnz     short loc_140011E15
0x140011e06  mov     eax, [rbx+36Ch]
0x140011e0c  test    al, al
0x140011e0e  js      short loc_140011E15
0x140011e10  mov     al, dil
0x140011e13  jmp     short loc_140011E17
0x140011e15  xor     al, al
0x140011e17  mov     [rbx+283h], al
0x140011e1d  cmp     dword ptr [rsi], 0
0x140011e20  jnz     short loc_140011E3C
0x140011e22  mov     byte ptr [rbp+57h+var_40+2], 0
0x140011e26  jmp     short loc_140011E30
0x140011e28  cmp     [rsi], edi
0x140011e2a  jnz     short loc_140011E3C
0x140011e2c  mov     byte ptr [rbp+57h+var_40+2], dil
0x140011e30  lea     rdx, [rbp+57h+var_40]
0x140011e34  mov     rcx, rbx
0x140011e37  call    DiskSetCacheInformation
0x140011e3c  movzx   eax, word ptr [rbx+280h]
0x140011e43  lea     r9, [rbp+57h+ParameterValue]; ParameterValue
0x140011e47  mov     ecx, 0FFEFh
0x140011e4c  lea     r8, aCacheispowerpr; "CacheIsPowerProtected"
0x140011e53  and     ax, cx
0x140011e56  lea     rdx, SubkeyName; "Disk"
0x140011e5d  mov     rcx, rbx; FdoExtension
0x140011e60  mov     [rbx+280h], ax
0x140011e67  call    cs:__imp_ClassGetDeviceParameter
0x140011e6e  nop     dword ptr [rax+rax+00h]
0x140011e73  cmp     [rbp+57h+ParameterValue], edi
0x140011e76  jnz     short loc_140011E8A
0x140011e78  movzx   eax, word ptr [rbx+280h]
0x140011e7f  or      ax, 10h
0x140011e83  mov     [rbx+280h], ax
0x140011e8a  movzx   eax, word ptr [rbx+280h]
0x140011e91  test    dil, al
0x140011e94  jz      short loc_140011EAB
0x140011e96  movzx   eax, word ptr [rbx+280h]
0x140011e9d  test    al, 10h
0x140011e9f  jnz     short loc_140011EAB
0x140011ea1  mov     eax, [rbx+36Ch]
0x140011ea7  test    al, al
0x140011ea9  jns     short loc_140011EAE
0x140011eab  xor     dil, dil
0x140011eae  lea     r11, [rsp+0A0h+var_10]
0x140011eb6  mov     [rbx+283h], dil
0x140011ebd  mov     rbx, [r11+30h]
0x140011ec1  xor     eax, eax
0x140011ec3  mov     rsi, [r11+38h]
0x140011ec7  mov     rsp, r11
0x140011eca  pop     r14
0x140011ecc  pop     rdi
0x140011ecd  pop     rbp
0x140011ece  retn
```
