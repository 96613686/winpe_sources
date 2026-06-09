# BfsInsertNotPresentPolicyEntry

- ea: `0x140007a20`
- end: `0x140007ce9`
- name: `BfsInsertNotPresentPolicyEntry`
- size: `713`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140009014`

## callees

- `0x140001008`
- `0x1400061d0`
- `0x140007a20`
- `0x140008e38`
- `0x140012ca0`
- `0x140013860`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140007c19`
- `ntoskrnl!KeInitializeEvent` at `0x140007c19`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140007a5f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140007a5f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140007a99`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140007c72`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140007a99`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140007c72`
- `ntoskrnl!RtlCopySid` at `0x140007b3e`
- `ntoskrnl!RtlCopySid` at `0x140007b79`
- `ntoskrnl!RtlCopySid` at `0x140007b3e`
- `ntoskrnl!RtlCopySid` at `0x140007b79`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007ca7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007cbd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007ca7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007cbd`
- `ntoskrnl!ExAllocatePool2` at `0x140007acf`
- `ntoskrnl!ExAllocatePool2` at `0x140007b19`
- `ntoskrnl!ExAllocatePool2` at `0x140007b9d`
- `ntoskrnl!ExAllocatePool2` at `0x140007bd4`
- `ntoskrnl!ExAllocatePool2` at `0x140007acf`
- `ntoskrnl!ExAllocatePool2` at `0x140007b19`
- `ntoskrnl!ExAllocatePool2` at `0x140007b9d`
- `ntoskrnl!ExAllocatePool2` at `0x140007bd4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140007a4e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140007a4e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140007aa5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140007c7e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140007aa5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140007c7e`

## pseudocode

```c
__int64 __fastcall BfsInsertNotPresentPolicyEntry(__int64 a1, ULONG_PTR a2, unsigned __int8 *a3, unsigned __int8 *a4)
{
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v8; // rax
  __int64 v9; // rdi
  NTSTATUS inserted; // ebx
  int v11; // r8d
  int v12; // r9d
  void *Pool2; // r14
  void *v14; // rsi
  int v15; // ecx
  bool v16; // cc
  NTSTATUS v17; // eax
  __int64 v18; // rax
  struct _KEVENT *v19; // rax
  int v21; // [rsp+20h] [rbp-58h]
  int v22; // [rsp+30h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v23; // [rsp+38h] [rbp-40h] BYREF
  int *v24; // [rsp+58h] [rbp-20h]
  __int64 v25; // [rsp+60h] [rbp-18h]

  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(a1, 0);
  v8 = BfsLookupPolicyEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 8), a2, a3, a4);
  v9 = (__int64)v8;
  if ( v8 )
  {
    inserted = 0x40000000;
    if ( LODWORD(v8[2].Linkage.Blink) != 0x10000000 )
      inserted = 0;
    ExReleasePushLockExclusiveEx(a1, 0);
    KeLeaveCriticalRegion();
    return (unsigned int)inserted;
  }
  Pool2 = (void *)ExAllocatePool2(256, 4LL * a3[1] + 8, 1400071746);
  if ( !Pool2 )
  {
    v14 = 0;
LABEL_7:
    v15 = dword_140019000;
    v16 = (unsigned int)dword_140019000 <= 3;
LABEL_8:
    inserted = -1073741801;
    if ( v16 )
      goto LABEL_22;
    v22 = -1073741801;
    goto LABEL_21;
  }
  v14 = (void *)ExAllocatePool2(256, 4LL * a4[1] + 8, 1400071746);
  if ( !v14 )
    goto LABEL_7;
  v17 = RtlCopySid(4 * a3[1] + 8, Pool2, a3);
  inserted = v17;
  if ( v17 < 0 )
  {
    v15 = dword_140019000;
    if ( (unsigned int)dword_140019000 <= 3 )
      goto LABEL_22;
    v22 = v17;
    goto LABEL_21;
  }
  inserted = RtlCopySid(4 * a4[1] + 8, v14, a4);
  if ( inserted >= 0 )
  {
    v18 = ExAllocatePool2(256, 152, 1165190722);
    v9 = v18;
    if ( !v18
      || (_InterlockedIncrement((volatile signed __int32 *)(v18 + 144)),
          v19 = (struct _KEVENT *)ExAllocatePool2(64, 24, 1987274306),
          (*(_QWORD *)(v9 + 40) = v19) == 0) )
    {
      v16 = (unsigned int)dword_140019000 <= 3;
      goto LABEL_8;
    }
    *(_QWORD *)(v9 + 32) = v14;
    *(_QWORD *)(v9 + 24) = Pool2;
    *(_DWORD *)(v9 + 56) = 2;
    v14 = 0;
    *(_DWORD *)(v9 + 104) = 0;
    *(_OWORD *)(v9 + 112) = 0;
    *(_OWORD *)(v9 + 128) = 0;
    Pool2 = 0;
    KeInitializeEvent(v19, NotificationEvent, 0);
    inserted = BfsInsertEntryHashTable(*(_QWORD *)(a1 + 8), a2, v9);
    if ( inserted >= 0 )
      goto LABEL_22;
  }
  if ( (unsigned int)dword_140019000 <= 3 )
    goto LABEL_22;
  v22 = inserted;
LABEL_21:
  v25 = 4;
  v24 = &v22;
  tlgWriteTransfer_EtwWriteTransfer(v15, (int)&byte_140016D91, v11, v12, v21, &v23);
LABEL_22:
  ExReleasePushLockExclusiveEx(a1, 0);
  KeLeaveCriticalRegion();
  if ( inserted < 0 )
  {
    if ( v9 )
      BfsDereferencePolicyEntryEx((PVOID)v9);
    if ( Pool2 )
      ExFreePoolWithTag(Pool2, 0);
    if ( v14 )
      ExFreePoolWithTag(v14, 0);
  }
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x140007a20  push    rbp
0x140007a22  push    rbx
0x140007a23  push    rsi
0x140007a24  push    rdi
0x140007a25  push    r12
0x140007a27  push    r13
0x140007a29  push    r14
0x140007a2b  push    r15
0x140007a2d  mov     rbp, rsp
0x140007a30  sub     rsp, 78h
0x140007a34  mov     rax, cs:__security_cookie
0x140007a3b  xor     rax, rsp
0x140007a3e  mov     [rbp+var_10], rax
0x140007a42  mov     r15, r9
0x140007a45  mov     rbx, r8
0x140007a48  mov     r12, rdx
0x140007a4b  mov     r13, rcx
0x140007a4e  call    cs:__imp_KeEnterCriticalRegion
0x140007a55  nop     dword ptr [rax+rax+00h]
0x140007a5a  xor     edx, edx
0x140007a5c  mov     rcx, r13
0x140007a5f  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140007a66  nop     dword ptr [rax+rax+00h]
0x140007a6b  mov     rcx, [r13+8]; HashTable
0x140007a6f  mov     r9, r15
0x140007a72  mov     r8, rbx
0x140007a75  mov     rdx, r12
0x140007a78  call    BfsLookupPolicyEntryHashTable
0x140007a7d  mov     rdi, rax
0x140007a80  test    rax, rax
0x140007a83  jz      short loc_140007AB6
0x140007a85  xor     edx, edx
0x140007a87  mov     ebx, 40000000h
0x140007a8c  cmp     dword ptr [rax+38h], 10000000h
0x140007a93  mov     rcx, r13
0x140007a96  cmovnz  ebx, edx
0x140007a99  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140007aa0  nop     dword ptr [rax+rax+00h]
0x140007aa5  call    cs:__imp_KeLeaveCriticalRegion
0x140007aac  nop     dword ptr [rax+rax+00h]
0x140007ab1  jmp     loc_140007CC9
0x140007ab6  movzx   edx, byte ptr [rbx+1]
0x140007aba  mov     esi, 100h
0x140007abf  mov     r8d, 53736642h
0x140007ac5  mov     ecx, esi
0x140007ac7  lea     rdx, ds:8[rdx*4]
0x140007acf  call    cs:__imp_ExAllocatePool2
0x140007ad6  nop     dword ptr [rax+rax+00h]
0x140007adb  mov     r14, rax
0x140007ade  test    rax, rax
0x140007ae1  jnz     short loc_140007B03
0x140007ae3  xor     esi, esi
0x140007ae5  mov     ecx, cs:dword_140019000
0x140007aeb  cmp     ecx, 3
0x140007aee  mov     edx, 0C0000017h
0x140007af3  mov     ebx, edx
0x140007af5  jbe     loc_140007C6D
0x140007afb  mov     [rbp+var_48], edx
0x140007afe  jmp     loc_140007C48
0x140007b03  movzx   edx, byte ptr [r15+1]
0x140007b08  mov     r8d, 53736642h
0x140007b0e  mov     rcx, rsi
0x140007b11  lea     rdx, ds:8[rdx*4]
0x140007b19  call    cs:__imp_ExAllocatePool2
0x140007b20  nop     dword ptr [rax+rax+00h]
0x140007b25  mov     rsi, rax
0x140007b28  test    rax, rax
0x140007b2b  jz      short loc_140007AE5
0x140007b2d  movzx   ecx, byte ptr [rbx+1]
0x140007b31  mov     r8, rbx; SourceSid
0x140007b34  mov     rdx, r14; DestinationSid
0x140007b37  lea     ecx, ds:8[rcx*4]; DestinationSidLength
0x140007b3e  call    cs:__imp_RtlCopySid
0x140007b45  nop     dword ptr [rax+rax+00h]
0x140007b4a  mov     ebx, eax
0x140007b4c  test    eax, eax
0x140007b4e  jns     short loc_140007B67
0x140007b50  mov     ecx, cs:dword_140019000
0x140007b56  cmp     ecx, 3
0x140007b59  jbe     loc_140007C6D
0x140007b5f  mov     [rbp+var_48], eax
0x140007b62  jmp     loc_140007C48
0x140007b67  movzx   ecx, byte ptr [r15+1]
0x140007b6c  mov     r8, r15; SourceSid
0x140007b6f  mov     rdx, rsi; DestinationSid
0x140007b72  lea     ecx, ds:8[rcx*4]; DestinationSidLength
0x140007b79  call    cs:__imp_RtlCopySid
0x140007b80  nop     dword ptr [rax+rax+00h]
0x140007b85  mov     ebx, eax
0x140007b87  test    eax, eax
0x140007b89  js      loc_140007C3A
0x140007b8f  mov     edx, 98h
0x140007b94  mov     r8d, 45736642h
0x140007b9a  lea     ecx, [rdx+68h]
0x140007b9d  call    cs:__imp_ExAllocatePool2
0x140007ba4  nop     dword ptr [rax+rax+00h]
0x140007ba9  mov     rdi, rax
0x140007bac  test    rax, rax
0x140007baf  jnz     short loc_140007BBF
0x140007bb1  mov     eax, cs:dword_140019000
0x140007bb7  cmp     eax, 3
0x140007bba  jmp     loc_140007AEE
0x140007bbf  lock inc dword ptr [rax+90h]
0x140007bc6  mov     edx, 18h
0x140007bcb  mov     r8d, 76736642h
0x140007bd1  lea     ecx, [rdx+28h]
0x140007bd4  call    cs:__imp_ExAllocatePool2
0x140007bdb  nop     dword ptr [rax+rax+00h]
0x140007be0  mov     [rdi+28h], rax
0x140007be4  test    rax, rax
0x140007be7  jz      short loc_140007BB1
0x140007be9  mov     [rdi+20h], rsi
0x140007bed  xorps   xmm0, xmm0
0x140007bf0  mov     [rdi+18h], r14
0x140007bf4  xorps   xmm1, xmm1
0x140007bf7  mov     dword ptr [rdi+38h], 2
0x140007bfe  xor     esi, esi
0x140007c00  mov     [rdi+68h], esi
0x140007c03  xor     r8d, r8d; State
0x140007c06  movups  xmmword ptr [rdi+70h], xmm0
0x140007c0a  xor     edx, edx; Type
0x140007c0c  mov     rcx, rax; Event
0x140007c0f  movups  xmmword ptr [rdi+80h], xmm1
0x140007c16  xor     r14d, r14d
0x140007c19  call    cs:__imp_KeInitializeEvent
0x140007c20  nop     dword ptr [rax+rax+00h]
0x140007c25  mov     rcx, [r13+8]
0x140007c29  mov     r8, rdi
0x140007c2c  mov     rdx, r12
0x140007c2f  call    BfsInsertEntryHashTable
0x140007c34  mov     ebx, eax
0x140007c36  test    eax, eax
0x140007c38  jns     short loc_140007C6D
0x140007c3a  mov     eax, cs:dword_140019000
0x140007c40  cmp     eax, 3
0x140007c43  jbe     short loc_140007C6D
0x140007c45  mov     [rbp+var_48], ebx
0x140007c48  lea     rax, [rbp+var_48]
0x140007c4c  mov     [rbp+var_18], 4
0x140007c54  mov     [rbp+var_20], rax
0x140007c58  lea     rdx, byte_140016D91; int
0x140007c5f  lea     rax, [rbp+var_40]
0x140007c63  mov     [rsp+78h+var_50], rax; PEVENT_DATA_DESCRIPTOR
0x140007c68  call    _tlgWriteTransfer_EtwWriteTransfer
0x140007c6d  xor     edx, edx
0x140007c6f  mov     rcx, r13
0x140007c72  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140007c79  nop     dword ptr [rax+rax+00h]
0x140007c7e  call    cs:__imp_KeLeaveCriticalRegion
0x140007c85  nop     dword ptr [rax+rax+00h]
0x140007c8a  test    ebx, ebx
0x140007c8c  jns     short loc_140007CC9
0x140007c8e  test    rdi, rdi
0x140007c91  jz      short loc_140007C9D
0x140007c93  xor     edx, edx
0x140007c95  mov     rcx, rdi; P
0x140007c98  call    BfsDereferencePolicyEntryEx
0x140007c9d  test    r14, r14
0x140007ca0  jz      short loc_140007CB3
0x140007ca2  xor     edx, edx; Tag
0x140007ca4  mov     rcx, r14; P
0x140007ca7  call    cs:__imp_ExFreePoolWithTag
0x140007cae  nop     dword ptr [rax+rax+00h]
0x140007cb3  test    rsi, rsi
0x140007cb6  jz      short loc_140007CC9
0x140007cb8  xor     edx, edx; Tag
0x140007cba  mov     rcx, rsi; P
0x140007cbd  call    cs:__imp_ExFreePoolWithTag
0x140007cc4  nop     dword ptr [rax+rax+00h]
0x140007cc9  mov     eax, ebx
0x140007ccb  mov     rcx, [rbp+var_10]
0x140007ccf  xor     rcx, rsp; StackCookie
0x140007cd2  call    __security_check_cookie
0x140007cd7  add     rsp, 78h
0x140007cdb  pop     r15
0x140007cdd  pop     r14
0x140007cdf  pop     r13
0x140007ce1  pop     r12
0x140007ce3  pop     rdi
0x140007ce4  pop     rsi
0x140007ce5  pop     rbx
0x140007ce6  pop     rbp
0x140007ce7  retn
```
