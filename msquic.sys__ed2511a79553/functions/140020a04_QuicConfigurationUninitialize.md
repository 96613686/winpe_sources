# QuicConfigurationUninitialize

- ea: `0x140020a04`
- end: `0x140020b1c`
- name: `QuicConfigurationUninitialize`
- size: `280`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400207e0`

## callees

- `0x140020a04`
- `0x1400291f0`
- `0x14002bfd8`
- `0x140033984`
- `0x1400368f0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140020a25`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140020a25`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140020a3b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140020a3b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140020a60`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140020a60`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020b09`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020b09`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140020a6c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140020a6c`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x140020aa6`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x140020ac0`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x140020aa6`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x140020ac0`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140020add`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140020add`

## pseudocode

```c
void __fastcall QuicConfigurationUninitialize(char *P)
{
  __int64 v2; // rcx
  _QWORD *v3; // rax
  struct _SecHandle *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  __int64 v7; // rcx

  if ( (byte_14005C489 & 4) != 0 )
    McTemplateU0p_EtwWriteTransfer((__int64)P, (const EVENT_DESCRIPTOR *)QuicConfigurationCleanup, (__int64)P);
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(*((_QWORD *)P + 2) + 56LL, 0);
  v2 = *((_QWORD *)P + 3);
  v3 = (_QWORD *)*((_QWORD *)P + 4);
  *v3 = v2;
  *(_QWORD *)(v2 + 8) = v3;
  ExReleasePushLockExclusiveEx(*((_QWORD *)P + 2) + 56LL, 0);
  KeLeaveCriticalRegion();
  v4 = (struct _SecHandle *)*((_QWORD *)P + 6);
  if ( v4 )
    CxPlatTlsSecConfigDelete(v4);
  CxPlatStorageClose(*((PVOID *)P + 11));
  CxPlatStorageClose(*((PVOID *)P + 9));
  v5 = (void *)*((_QWORD *)P + 8);
  if ( v5 )
    ObfDereferenceObjectWithTag(v5, 0x30306351u);
  v6 = (void *)*((_QWORD *)P + 10);
  if ( v6 )
    ObfDereferenceObjectWithTag(v6, 0x33346351u);
  QuicSettingsCleanup(P + 96);
  ExReleaseRundownProtection((PEX_RUNDOWN_REF)(*((_QWORD *)P + 2) + 128LL));
  if ( (byte_14005C489 & 4) != 0 )
    McTemplateU0p_EtwWriteTransfer(v7, (const EVENT_DESCRIPTOR *)QuicConfigurationDestroyed, (__int64)P);
  ExFreePoolWithTag(P, 0x36316351u);
}

```

## disassembly

```asm
0x140020a04  push    rbx
0x140020a06  sub     rsp, 20h
0x140020a0a  test    cs:byte_14005C489, 4
0x140020a11  mov     rbx, rcx
0x140020a14  jz      short loc_140020A25
0x140020a16  mov     r8, rcx
0x140020a19  lea     rdx, QuicConfigurationCleanup
0x140020a20  call    McTemplateU0p_EtwWriteTransfer
0x140020a25  call    cs:__imp_KeEnterCriticalRegion
0x140020a2c  nop     dword ptr [rax+rax+00h]
0x140020a31  mov     rcx, [rbx+10h]
0x140020a35  xor     edx, edx
0x140020a37  add     rcx, 38h ; '8'
0x140020a3b  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140020a42  nop     dword ptr [rax+rax+00h]
0x140020a47  mov     rcx, [rbx+18h]
0x140020a4b  xor     edx, edx
0x140020a4d  mov     rax, [rbx+20h]
0x140020a51  mov     [rax], rcx
0x140020a54  mov     [rcx+8], rax
0x140020a58  mov     rcx, [rbx+10h]
0x140020a5c  add     rcx, 38h ; '8'
0x140020a60  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140020a67  nop     dword ptr [rax+rax+00h]
0x140020a6c  call    cs:__imp_KeLeaveCriticalRegion
0x140020a73  nop     dword ptr [rax+rax+00h]
0x140020a78  mov     rcx, [rbx+30h]; P
0x140020a7c  test    rcx, rcx
0x140020a7f  jz      short loc_140020A86
0x140020a81  call    CxPlatTlsSecConfigDelete
0x140020a86  mov     rcx, [rbx+58h]; P
0x140020a8a  call    CxPlatStorageClose
0x140020a8f  mov     rcx, [rbx+48h]; P
0x140020a93  call    CxPlatStorageClose
0x140020a98  mov     rcx, [rbx+40h]; Object
0x140020a9c  test    rcx, rcx
0x140020a9f  jz      short loc_140020AB2
0x140020aa1  mov     edx, 30306351h; Tag
0x140020aa6  call    cs:__imp_ObfDereferenceObjectWithTag
0x140020aad  nop     dword ptr [rax+rax+00h]
0x140020ab2  mov     rcx, [rbx+50h]; Object
0x140020ab6  test    rcx, rcx
0x140020ab9  jz      short loc_140020ACC
0x140020abb  mov     edx, 33346351h; Tag
0x140020ac0  call    cs:__imp_ObfDereferenceObjectWithTag
0x140020ac7  nop     dword ptr [rax+rax+00h]
0x140020acc  lea     rcx, [rbx+60h]
0x140020ad0  call    QuicSettingsCleanup
0x140020ad5  mov     rcx, [rbx+10h]
0x140020ad9  sub     rcx, 0FFFFFFFFFFFFFF80h; RunRef
0x140020add  call    cs:__imp_ExReleaseRundownProtection
0x140020ae4  nop     dword ptr [rax+rax+00h]
0x140020ae9  test    cs:byte_14005C489, 4
0x140020af0  jz      short loc_140020B01
0x140020af2  mov     r8, rbx
0x140020af5  lea     rdx, QuicConfigurationDestroyed
0x140020afc  call    McTemplateU0p_EtwWriteTransfer
0x140020b01  mov     edx, 36316351h; Tag
0x140020b06  mov     rcx, rbx; P
0x140020b09  call    cs:__imp_ExFreePoolWithTag
0x140020b10  nop     dword ptr [rax+rax+00h]
0x140020b15  add     rsp, 20h
0x140020b19  pop     rbx
0x140020b1a  retn
```
