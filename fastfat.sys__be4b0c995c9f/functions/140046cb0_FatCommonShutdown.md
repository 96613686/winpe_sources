# FatCommonShutdown

- ea: `0x140046cb0`
- end: `0x140046f9f`
- name: `FatCommonShutdown`
- size: `751`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1400438e0`
- `0x140046fb0`

## callees

- `0x140006350`
- `0x140006dbc`
- `0x1400076a4`
- `0x140038eb4`
- `0x14003e94c`
- `0x1400465f4`
- `0x1400466c8`
- `0x140046cb0`
- `0x140048740`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140046cea`
- `ntoskrnl!KeInitializeEvent` at `0x140046cea`
- `ntoskrnl!KeClearEvent` at `0x140046e8b`
- `ntoskrnl!KeClearEvent` at `0x140046e8b`
- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x140046e39`
- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x140046e39`
- `ntoskrnl!IofCallDriver` at `0x140046e54`
- `ntoskrnl!IofCallDriver` at `0x140046e54`
- `ntoskrnl!KeWaitForSingleObject` at `0x140046e7a`
- `ntoskrnl!KeWaitForSingleObject` at `0x140046e7a`
- `ntoskrnl!CcPurgeCacheSection` at `0x140046dd6`
- `ntoskrnl!CcPurgeCacheSection` at `0x140046dd6`
- `ntoskrnl!IoDeleteDevice` at `0x140046f5d`
- `ntoskrnl!IoDeleteDevice` at `0x140046f70`
- `ntoskrnl!IoDeleteDevice` at `0x14005f8e7`
- `ntoskrnl!IoDeleteDevice` at `0x14005f8fa`
- `ntoskrnl!IoDeleteDevice` at `0x140046f5d`
- `ntoskrnl!IoDeleteDevice` at `0x140046f70`
- `ntoskrnl!IoDeleteDevice` at `0x14005f8e7`
- `ntoskrnl!IoDeleteDevice` at `0x14005f8fa`
- `ntoskrnl!IoUnregisterFileSystem` at `0x140046f37`
- `ntoskrnl!IoUnregisterFileSystem` at `0x140046f4a`
- `ntoskrnl!IoUnregisterFileSystem` at `0x14005f8c1`
- `ntoskrnl!IoUnregisterFileSystem` at `0x14005f8d4`
- `ntoskrnl!IoUnregisterFileSystem` at `0x140046f37`
- `ntoskrnl!IoUnregisterFileSystem` at `0x140046f4a`
- `ntoskrnl!IoUnregisterFileSystem` at `0x14005f8c1`
- `ntoskrnl!IoUnregisterFileSystem` at `0x14005f8d4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140046d0c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140046d0c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140046ef2`
- `ntoskrnl!ExReleaseResourceLite` at `0x140046f07`
- `ntoskrnl!ExReleaseResourceLite` at `0x140046f24`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005f8ae`
- `ntoskrnl!ExReleaseResourceLite` at `0x140046ef2`
- `ntoskrnl!ExReleaseResourceLite` at `0x140046f07`
- `ntoskrnl!ExReleaseResourceLite` at `0x140046f24`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005f8ae`

## pseudocode

```c
__int64 __fastcall FatCommonShutdown(_DWORD *Entry, IRP *a2)
{
  __int64 v3; // r9
  __int64 *v4; // rsi
  __int64 *v5; // rbx
  __int64 v6; // r14
  __int64 v7; // rcx
  __int64 NextFcbBottomUp; // rax
  __int64 v9; // r8
  __int64 v10; // r9
  IRP *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // r14
  __int64 v14; // rax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-58h] BYREF
  struct _KEVENT Object; // [rsp+60h] [rbp-48h] BYREF

  memset(&Object, 0, sizeof(Object));
  IoStatusBlock = 0;
  Entry[17] |= 0x24u;
  KeInitializeEvent(&Object, NotificationEvent, 0);
  byte_140017D4C |= 8u;
  ExAcquireResourceExclusiveLite(&Resource, (Entry[17] & 2) != 0);
  v4 = (__int64 *)qword_140017CB0;
  while ( v4 != &qword_140017CB0 )
  {
    v5 = v4 - 15;
    v4 = (__int64 *)*v4;
    if ( (v5[25] & 0x40) == 0 && *((_DWORD *)v5 + 51) == 1 )
    {
      v6 = 0;
      FatAcquireExclusiveVcb_Real(Entry, v5, 0, v3);
      while ( 1 )
      {
        NextFcbBottomUp = FatGetNextFcbBottomUp(v7, v6, v5[26]);
        v6 = NextFcbBottomUp;
        if ( !NextFcbBottomUp )
          break;
        FatAcquireExclusiveFcb(Entry, NextFcbBottomUp, v9, v10);
      }
      FatFlushVolume(Entry, v5, 1);
      if ( (v5[25] & 0x10) == 0 )
      {
        CcPurgeCacheSection((PSECTION_OBJECT_POINTERS)(v5 + 92), 0, 0, 0);
        FatMarkVolume(Entry, v5, 0);
      }
      v11 = IoBuildSynchronousFsdRequest(0x10u, (PDEVICE_OBJECT)v5[17], 0, 0, 0, &Object, &IoStatusBlock);
      if ( v11 && IofCallDriver((PDEVICE_OBJECT)v5[17], v11) >= 0 )
      {
        KeWaitForSingleObject(&Object, Executive, 0, 0, 0);
        KeClearEvent(&Object);
      }
      _InterlockedOr((volatile signed __int32 *)v5 + 50, 0x40u);
      if ( !(unsigned __int8)FatCheckForDismount(Entry, v5, 0) )
      {
        v13 = 0;
        while ( 1 )
        {
          v14 = FatGetNextFcbBottomUp(v12, v13, v5[26]);
          v13 = v14;
          if ( !v14 )
            break;
          ExReleaseResourceLite(*(PERESOURCE *)(v14 + 8));
        }
        ExReleaseResourceLite((PERESOURCE)v5 + 5);
      }
    }
  }
  FatUninitializeSqm();
  ExReleaseResourceLite(&Resource);
  IoUnregisterFileSystem(FatDiskFileSystemDeviceObject);
  IoUnregisterFileSystem(FatCdromFileSystemDeviceObject);
  IoDeleteDevice(FatDiskFileSystemDeviceObject);
  IoDeleteDevice(FatCdromFileSystemDeviceObject);
  FatCompleteRequest_Real(Entry, a2);
  return 0;
}

```

## disassembly

```asm
0x140046cb0  mov     r11, rsp
0x140046cb3  mov     [r11+10h], rdx
0x140046cb7  mov     [r11+8], rcx
0x140046cbb  push    rbx
0x140046cbc  push    rsi
0x140046cbd  push    rdi
0x140046cbe  push    r14
0x140046cc0  sub     rsp, 88h
0x140046cc7  mov     rdi, rcx
0x140046cca  xorps   xmm0, xmm0
0x140046ccd  xor     eax, eax
0x140046ccf  movups  xmmword ptr [rsp+0A8h+Object.Header], xmm0
0x140046cd4  mov     [r11-38h], rax
0x140046cd8  movups  xmmword ptr [rsp+0A8h+var_58], xmm0
0x140046cdd  or      dword ptr [rcx+44h], 24h
0x140046ce1  xor     r8d, r8d; State
0x140046ce4  xor     edx, edx; Type
0x140046ce6  lea     rcx, [r11-48h]; Event
0x140046cea  call    cs:__imp_KeInitializeEvent
0x140046cf1  nop     dword ptr [rax+rax+00h]
0x140046cf6  or      cs:byte_140017D4C, 8
0x140046cfd  mov     edx, [rdi+44h]
0x140046d00  shr     edx, 1
0x140046d02  and     dl, 1; Wait
0x140046d05  lea     rcx, Resource; Resource
0x140046d0c  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140046d13  nop     dword ptr [rax+rax+00h]
0x140046d18  nop
0x140046d19  mov     rsi, cs:qword_140017CB0
0x140046d20  mov     [rsp+0A8h+var_68], rsi
0x140046d25  lea     rax, qword_140017CB0
0x140046d2c  cmp     rsi, rax
0x140046d2f  jz      loc_140046F18
0x140046d35  lea     rbx, [rsi-78h]
0x140046d39  mov     [rsp+0A8h+var_60], rbx
0x140046d3e  mov     rsi, [rsi]
0x140046d41  mov     [rsp+0A8h+var_68], rsi
0x140046d46  lea     rcx, [rbx+0C8h]
0x140046d4d  mov     eax, [rcx]
0x140046d4f  test    al, 40h
0x140046d51  jnz     loc_140046F13
0x140046d57  cmp     dword ptr [rbx+0CCh], 1
0x140046d5e  jnz     loc_140046F13
0x140046d64  mov     [rsp+0A8h+arg_10], rcx
0x140046d6c  xor     r14d, r14d
0x140046d6f  xor     r8d, r8d
0x140046d72  mov     rdx, rbx
0x140046d75  mov     rcx, rdi
0x140046d78  call    FatAcquireExclusiveVcb_Real
0x140046d7d  lea     r8, [rbx+0D0h]
0x140046d84  mov     [rsp+0A8h+arg_18], r8
0x140046d8c  mov     r8, [r8]
0x140046d8f  mov     rdx, r14
0x140046d92  call    FatGetNextFcbBottomUp
0x140046d97  mov     r14, rax
0x140046d9a  test    rax, rax
0x140046d9d  jz      short loc_140046DAC
0x140046d9f  mov     rdx, rax
0x140046da2  mov     rcx, rdi
0x140046da5  call    FatAcquireExclusiveFcb
0x140046daa  jmp     short loc_140046D7D
0x140046dac  mov     r8d, 1
0x140046db2  mov     rdx, rbx
0x140046db5  mov     rcx, rdi
0x140046db8  call    FatFlushVolume
0x140046dbd  mov     eax, [rbx+0C8h]
0x140046dc3  test    al, 10h
0x140046dc5  jnz     short loc_140046DF0
0x140046dc7  lea     rcx, [rbx+2E0h]; SectionObjectPointer
0x140046dce  xor     r9d, r9d; Flags
0x140046dd1  xor     r8d, r8d; Length
0x140046dd4  xor     edx, edx; FileOffset
0x140046dd6  call    cs:__imp_CcPurgeCacheSection
0x140046ddd  nop     dword ptr [rax+rax+00h]
0x140046de2  xor     r8d, r8d
0x140046de5  mov     rdx, rbx
0x140046de8  mov     rcx, rdi
0x140046deb  call    FatMarkVolume
0x140046df0  jmp     short loc_140046E0B
0x140046df2  mov     rdi, [rsp+0A8h+arg_0]
0x140046dfa  mov     dword ptr [rdi+48h], 0
0x140046e01  mov     rsi, [rsp+0A8h+var_68]
0x140046e06  mov     rbx, [rsp+0A8h+var_60]
0x140046e0b  lea     rax, [rsp+0A8h+var_58]
0x140046e10  mov     [rsp+0A8h+IoStatusBlock], rax; IoStatusBlock
0x140046e15  lea     rax, [rsp+0A8h+Object]
0x140046e1a  mov     [rsp+0A8h+Event], rax; Event
0x140046e1f  mov     [rsp+0A8h+StartingOffset], 0; StartingOffset
0x140046e28  xor     r9d, r9d; Length
0x140046e2b  xor     r8d, r8d; Buffer
0x140046e2e  mov     rdx, [rbx+88h]; DeviceObject
0x140046e35  lea     ecx, [r9+10h]; MajorFunction
0x140046e39  call    cs:__imp_IoBuildSynchronousFsdRequest
0x140046e40  nop     dword ptr [rax+rax+00h]
0x140046e45  test    rax, rax
0x140046e48  jz      short loc_140046E97
0x140046e4a  mov     rdx, rax; Irp
0x140046e4d  mov     rcx, [rbx+88h]; DeviceObject
0x140046e54  call    cs:__imp_IofCallDriver
0x140046e5b  nop     dword ptr [rax+rax+00h]
0x140046e60  test    eax, eax
0x140046e62  js      short loc_140046E97
0x140046e64  mov     [rsp+0A8h+StartingOffset], 0; Timeout
0x140046e6d  xor     r9d, r9d; Alertable
0x140046e70  xor     r8d, r8d; WaitMode
0x140046e73  xor     edx, edx; WaitReason
0x140046e75  lea     rcx, [rsp+0A8h+Object]; Object
0x140046e7a  call    cs:__imp_KeWaitForSingleObject
0x140046e81  nop     dword ptr [rax+rax+00h]
0x140046e86  lea     rcx, [rsp+0A8h+Object]; Event
0x140046e8b  call    cs:__imp_KeClearEvent
0x140046e92  nop     dword ptr [rax+rax+00h]
0x140046e97  jmp     short loc_140046EB2
0x140046e99  mov     rdi, [rsp+0A8h+arg_0]
0x140046ea1  mov     dword ptr [rdi+48h], 0
0x140046ea8  mov     rsi, [rsp+0A8h+var_68]
0x140046ead  mov     rbx, [rsp+0A8h+var_60]
0x140046eb2  mov     rax, [rsp+0A8h+arg_10]
0x140046eba  lock or dword ptr [rax], 40h
0x140046ebe  xor     r8d, r8d
0x140046ec1  mov     rdx, rbx
0x140046ec4  mov     rcx, rdi
0x140046ec7  call    FatCheckForDismount
0x140046ecc  test    al, al
0x140046ece  jnz     short loc_140046F13
0x140046ed0  xor     r14d, r14d
0x140046ed3  mov     r8, [rsp+0A8h+arg_18]
0x140046edb  mov     r8, [r8]
0x140046ede  mov     rdx, r14
0x140046ee1  call    FatGetNextFcbBottomUp
0x140046ee6  mov     r14, rax
0x140046ee9  test    rax, rax
0x140046eec  jz      short loc_140046F00
0x140046eee  mov     rcx, [rax+8]; Resource
0x140046ef2  call    cs:__imp_ExReleaseResourceLite
0x140046ef9  nop     dword ptr [rax+rax+00h]
0x140046efe  jmp     short loc_140046ED3
0x140046f00  lea     rcx, [rbx+208h]; Resource
0x140046f07  call    cs:__imp_ExReleaseResourceLite
0x140046f0e  nop     dword ptr [rax+rax+00h]
0x140046f13  jmp     loc_140046D25
0x140046f18  call    FatUninitializeSqm
0x140046f1d  lea     rcx, Resource; Resource
0x140046f24  call    cs:__imp_ExReleaseResourceLite
0x140046f2b  nop     dword ptr [rax+rax+00h]
0x140046f30  mov     rcx, cs:FatDiskFileSystemDeviceObject; DeviceObject
0x140046f37  call    cs:__imp_IoUnregisterFileSystem
0x140046f3e  nop     dword ptr [rax+rax+00h]
0x140046f43  mov     rcx, cs:FatCdromFileSystemDeviceObject; DeviceObject
0x140046f4a  call    cs:__imp_IoUnregisterFileSystem
0x140046f51  nop     dword ptr [rax+rax+00h]
0x140046f56  mov     rcx, cs:FatDiskFileSystemDeviceObject; DeviceObject
0x140046f5d  call    cs:__imp_IoDeleteDevice
0x140046f64  nop     dword ptr [rax+rax+00h]
0x140046f69  mov     rcx, cs:FatCdromFileSystemDeviceObject; DeviceObject
0x140046f70  call    cs:__imp_IoDeleteDevice
0x140046f77  nop     dword ptr [rax+rax+00h]
0x140046f7c  xor     r8d, r8d
0x140046f7f  mov     rdx, [rsp+0A8h+Irp]; Irp
0x140046f87  mov     rcx, rdi; Entry
0x140046f8a  call    FatCompleteRequest_Real
0x140046f8f  xor     eax, eax
0x140046f91  add     rsp, 88h
0x140046f98  pop     r14
0x140046f9a  pop     rdi
0x140046f9b  pop     rsi
0x140046f9c  pop     rbx
0x140046f9d  retn
0x14005f899  push    rbp
0x14005f89b  sub     rsp, 40h
0x14005f89f  mov     rbp, rdx
0x14005f8a2  call    FatUninitializeSqm
0x14005f8a7  lea     rcx, Resource; Resource
0x14005f8ae  call    cs:__imp_ExReleaseResourceLite
0x14005f8b5  nop     dword ptr [rax+rax+00h]
0x14005f8ba  mov     rcx, cs:FatDiskFileSystemDeviceObject; DeviceObject
0x14005f8c1  call    cs:__imp_IoUnregisterFileSystem
0x14005f8c8  nop     dword ptr [rax+rax+00h]
0x14005f8cd  mov     rcx, cs:FatCdromFileSystemDeviceObject; DeviceObject
0x14005f8d4  call    cs:__imp_IoUnregisterFileSystem
0x14005f8db  nop     dword ptr [rax+rax+00h]
0x14005f8e0  mov     rcx, cs:FatDiskFileSystemDeviceObject; DeviceObject
0x14005f8e7  call    cs:__imp_IoDeleteDevice
0x14005f8ee  nop     dword ptr [rax+rax+00h]
0x14005f8f3  mov     rcx, cs:FatCdromFileSystemDeviceObject; DeviceObject
0x14005f8fa  call    cs:__imp_IoDeleteDevice
0x14005f901  nop     dword ptr [rax+rax+00h]
0x14005f906  xor     r8d, r8d
0x14005f909  mov     rdx, [rbp+0B8h]; Irp
0x14005f910  mov     rcx, [rbp+0B0h]; Entry
0x14005f917  call    FatCompleteRequest_Real
0x14005f91c  nop
0x14005f91d  add     rsp, 40h
0x14005f921  pop     rbp
0x14005f922  retn
```
