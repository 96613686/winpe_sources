# HvSocketUpdatePartitionProperties

- ea: `0x14001ae50`
- end: `0x14001b134`
- name: `HvSocketUpdatePartitionProperties`
- size: `740`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x140009df0`
- `0x14000a048`
- `0x14000bfa0`
- `0x14000bfe0`
- `0x1400190c8`
- `0x14001ae50`
- `0x14001d530`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001aedd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001b073`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001aedd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001b073`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x14001af34`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x14001af89`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x14001af34`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x14001af89`
- `ntoskrnl!ExGetPreviousMode` at `0x14001af11`
- `ntoskrnl!ExGetPreviousMode` at `0x14001af66`
- `ntoskrnl!ExGetPreviousMode` at `0x14001af11`
- `ntoskrnl!ExGetPreviousMode` at `0x14001af66`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001aed1`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001b067`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001aed1`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001b067`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001afcc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001afe3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b027`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b041`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b109`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001afcc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001afe3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b027`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b041`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b109`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001aea0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001affd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001aea0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001affd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001b0f3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001b0f3`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001aeb3`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001b00d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001aeb3`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001b00d`

## string_xrefs

- `0x14001afb5`: `HvSocketUpdatePartitionProperties`
- `0x14001b0a4`: `HvSocketUpdatePartitionProperties`

## pseudocode

```c
__int64 __fastcall HvSocketUpdatePartitionProperties(__int64 a1, __int64 *a2)
{
  __int64 v2; // rdi
  __int64 v4; // rax
  struct _FAST_MUTEX *v5; // rcx
  __int64 v6; // rdi
  int v7; // ebx
  __int128 *v8; // r9
  int v9; // edx
  __int64 v10; // rbx
  KPROCESSOR_MODE PreviousMode; // al
  __int64 v12; // r9
  __int64 v13; // rdx
  int v14; // eax
  __int64 v15; // r8
  __int64 v16; // rbx
  KPROCESSOR_MODE v17; // al
  __int64 v18; // r9
  __int64 v19; // rdx
  void *v20; // rcx
  void *v21; // rcx
  signed __int64 v22; // rax
  bool v23; // cc
  signed __int64 v24; // rax
  void (__fastcall *v25)(__int64); // rax
  PVOID P; // [rsp+30h] [rbp-40h] BYREF
  PVOID v28; // [rsp+38h] [rbp-38h] BYREF
  __int128 v29; // [rsp+40h] [rbp-30h] BYREF
  __int128 v30; // [rsp+50h] [rbp-20h] BYREF

  v2 = *(_QWORD *)(a1 + 96);
  P = 0;
  v28 = 0;
  v30 = 0;
  v30 = *HvsocketAddressInfoToPartitionId(&v29, a1 + 104);
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v2 + 16));
  v4 = HvSocketFindAndReferenceAnyPartition(v2, (__int64)&v30);
  v5 = (struct _FAST_MUTEX *)(v2 + 16);
  v6 = v4;
  ExReleaseFastMutexUnsafe(v5);
  KeLeaveCriticalRegion();
  if ( !v6 )
  {
    v7 = -1073741503;
    if ( (unsigned int)dword_140013058 <= 2 )
      goto LABEL_12;
    v8 = &v30;
    v9 = 102;
    goto LABEL_10;
  }
  v10 = *a2;
  PreviousMode = ExGetPreviousMode();
  LOBYTE(v12) = 1;
  LOBYTE(v13) = PreviousMode;
  v14 = SeCaptureSecurityDescriptor(v10, v13, 1, v12, &P);
  v7 = v14;
  if ( v14 < 0 )
  {
    if ( (unsigned int)dword_140013058 <= 2 )
      goto LABEL_12;
    v8 = (__int128 *)(v6 + 232);
    v15 = (unsigned int)v14;
    v9 = 117;
    goto LABEL_11;
  }
  v16 = a2[1];
  v17 = ExGetPreviousMode();
  LOBYTE(v18) = 1;
  LOBYTE(v19) = v17;
  v7 = SeCaptureSecurityDescriptor(v16, v19, 1, v18, &v28);
  if ( v7 >= 0 )
  {
    KeEnterCriticalRegion();
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v6 + 16));
    v20 = *(void **)(v6 + 384);
    if ( v20 )
      ExFreePoolWithTag(v20, 0);
    v21 = *(void **)(v6 + 376);
    if ( v21 )
      ExFreePoolWithTag(v21, 0);
    *(_QWORD *)(v6 + 384) = P;
    *(_QWORD *)(v6 + 376) = v28;
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v6 + 16));
    KeLeaveCriticalRegion();
    v7 = 0;
    goto LABEL_23;
  }
  if ( (unsigned int)dword_140013058 > 2 )
  {
    v8 = (__int128 *)(v6 + 232);
    v9 = 128;
LABEL_10:
    v15 = (unsigned int)v7;
LABEL_11:
    HvsocketTraceGuidError((const int *)"HvSocketUpdatePartitionProperties", v9, v15, (__int64)v8);
  }
LABEL_12:
  if ( P )
    ExFreePoolWithTag(P, 0);
  if ( v28 )
    ExFreePoolWithTag(v28, 0);
  if ( v6 )
  {
LABEL_23:
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (const int *)"HvSocketUpdatePartitionProperties",
        171,
        v6,
        *(_QWORD *)(v6 + 8),
        (const int *)"Dereference object");
    v22 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v6 + 8), 0xFFFFFFFFFFFFFFFFuLL);
    v23 = v22 <= 1;
    v24 = v22 - 1;
    if ( v23 )
    {
      if ( v24 )
        __fastfail(0xEu);
      v25 = *(void (__fastcall **)(__int64))(v6 + 80);
      if ( v25 )
        v25(v6);
      if ( *(_DWORD *)(v6 + 88) == 1 )
      {
        ExFreePoolWithTag((PVOID)v6, 0x69706E56u);
      }
      else if ( *(_DWORD *)(v6 + 88) == 2 )
      {
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v6 + 96), (PVOID)v6);
      }
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14001ae50  mov     [rsp-18h+arg_10], rbx
0x14001ae55  push    rbp
0x14001ae56  push    rsi
0x14001ae57  push    rdi
0x14001ae58  mov     rbp, rsp
0x14001ae5b  sub     rsp, 70h
0x14001ae5f  mov     rax, cs:__security_cookie
0x14001ae66  xor     rax, rsp
0x14001ae69  mov     [rbp+var_10], rax
0x14001ae6d  mov     rdi, [rcx+60h]
0x14001ae71  xorps   xmm0, xmm0
0x14001ae74  mov     rsi, rdx
0x14001ae77  mov     [rbp+P], 0
0x14001ae7f  lea     rdx, [rcx+68h]
0x14001ae83  mov     [rbp+var_38], 0
0x14001ae8b  lea     rcx, [rbp+var_30]
0x14001ae8f  movups  [rbp+var_20], xmm0
0x14001ae93  call    HvsocketAddressInfoToPartitionId
0x14001ae98  movups  xmm1, xmmword ptr [rax]
0x14001ae9b  movdqu  [rbp+var_20], xmm1
0x14001aea0  call    cs:__imp_KeEnterCriticalRegion
0x14001aea7  nop     dword ptr [rax+rax+00h]
0x14001aeac  lea     rbx, [rdi+10h]
0x14001aeb0  mov     rcx, rbx; FastMutex
0x14001aeb3  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14001aeba  nop     dword ptr [rax+rax+00h]
0x14001aebf  lea     rdx, [rbp+var_20]
0x14001aec3  mov     rcx, rdi
0x14001aec6  call    HvSocketFindAndReferenceAnyPartition
0x14001aecb  mov     rcx, rbx; FastMutex
0x14001aece  mov     rdi, rax
0x14001aed1  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14001aed8  nop     dword ptr [rax+rax+00h]
0x14001aedd  call    cs:__imp_KeLeaveCriticalRegion
0x14001aee4  nop     dword ptr [rax+rax+00h]
0x14001aee9  test    rdi, rdi
0x14001aeec  jnz     short loc_14001AF0E
0x14001aeee  mov     ecx, cs:dword_140013058
0x14001aef4  mov     ebx, 0C0000141h
0x14001aef9  cmp     ecx, 2
0x14001aefc  jbe     loc_14001AFC1
0x14001af02  lea     r9, [rbp+var_20]
0x14001af06  lea     edx, [rdi+66h]
0x14001af09  jmp     loc_14001AFB2
0x14001af0e  mov     rbx, [rsi]
0x14001af11  call    cs:__imp_ExGetPreviousMode
0x14001af18  nop     dword ptr [rax+rax+00h]
0x14001af1d  mov     r9b, 1
0x14001af20  mov     r8d, 1
0x14001af26  mov     dl, al
0x14001af28  mov     rcx, rbx
0x14001af2b  lea     rax, [rbp+P]
0x14001af2f  mov     [rsp+70h+var_50], rax
0x14001af34  call    cs:__imp_SeCaptureSecurityDescriptor
0x14001af3b  nop     dword ptr [rax+rax+00h]
0x14001af40  mov     ebx, eax
0x14001af42  test    eax, eax
0x14001af44  jns     short loc_14001AF62
0x14001af46  mov     ecx, cs:dword_140013058
0x14001af4c  cmp     ecx, 2
0x14001af4f  jbe     short loc_14001AFC1
0x14001af51  lea     r9, [rdi+0E8h]
0x14001af58  mov     r8d, eax
0x14001af5b  mov     edx, 75h ; 'u'
0x14001af60  jmp     short loc_14001AFB5
0x14001af62  mov     rbx, [rsi+8]
0x14001af66  call    cs:__imp_ExGetPreviousMode
0x14001af6d  nop     dword ptr [rax+rax+00h]
0x14001af72  mov     r9b, 1
0x14001af75  mov     r8d, 1
0x14001af7b  mov     dl, al
0x14001af7d  mov     rcx, rbx
0x14001af80  lea     rax, [rbp+var_38]
0x14001af84  mov     [rsp+70h+var_50], rax
0x14001af89  call    cs:__imp_SeCaptureSecurityDescriptor
0x14001af90  nop     dword ptr [rax+rax+00h]
0x14001af95  mov     ebx, eax
0x14001af97  test    eax, eax
0x14001af99  jns     short loc_14001AFFD
0x14001af9b  mov     eax, cs:dword_140013058
0x14001afa1  cmp     eax, 2
0x14001afa4  jbe     short loc_14001AFC1
0x14001afa6  lea     r9, [rdi+0E8h]
0x14001afad  mov     edx, 80h
0x14001afb2  mov     r8d, ebx
0x14001afb5  lea     rcx, aHvsocketupdate_0; "HvSocketUpdatePartitionProperties"
0x14001afbc  call    HvsocketTraceGuidError
0x14001afc1  mov     rcx, [rbp+P]; P
0x14001afc5  test    rcx, rcx
0x14001afc8  jz      short loc_14001AFD8
0x14001afca  xor     edx, edx; Tag
0x14001afcc  call    cs:__imp_ExFreePoolWithTag
0x14001afd3  nop     dword ptr [rax+rax+00h]
0x14001afd8  mov     rcx, [rbp+var_38]; P
0x14001afdc  test    rcx, rcx
0x14001afdf  jz      short loc_14001AFEF
0x14001afe1  xor     edx, edx; Tag
0x14001afe3  call    cs:__imp_ExFreePoolWithTag
0x14001afea  nop     dword ptr [rax+rax+00h]
0x14001afef  test    rdi, rdi
0x14001aff2  jz      loc_14001B115
0x14001aff8  jmp     loc_14001B081
0x14001affd  call    cs:__imp_KeEnterCriticalRegion
0x14001b004  nop     dword ptr [rax+rax+00h]
0x14001b009  lea     rcx, [rdi+10h]; FastMutex
0x14001b00d  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14001b014  nop     dword ptr [rax+rax+00h]
0x14001b019  mov     rcx, [rdi+180h]; P
0x14001b020  test    rcx, rcx
0x14001b023  jz      short loc_14001B033
0x14001b025  xor     edx, edx; Tag
0x14001b027  call    cs:__imp_ExFreePoolWithTag
0x14001b02e  nop     dword ptr [rax+rax+00h]
0x14001b033  mov     rcx, [rdi+178h]; P
0x14001b03a  test    rcx, rcx
0x14001b03d  jz      short loc_14001B04D
0x14001b03f  xor     edx, edx; Tag
0x14001b041  call    cs:__imp_ExFreePoolWithTag
0x14001b048  nop     dword ptr [rax+rax+00h]
0x14001b04d  mov     rax, [rbp+P]
0x14001b051  lea     rcx, [rdi+10h]; FastMutex
0x14001b055  mov     [rdi+180h], rax
0x14001b05c  mov     rax, [rbp+var_38]
0x14001b060  mov     [rdi+178h], rax
0x14001b067  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14001b06e  nop     dword ptr [rax+rax+00h]
0x14001b073  call    cs:__imp_KeLeaveCriticalRegion
0x14001b07a  nop     dword ptr [rax+rax+00h]
0x14001b07f  xor     ebx, ebx
0x14001b081  mov     eax, cs:dword_140013058
0x14001b087  cmp     eax, 5
0x14001b08a  jbe     short loc_14001B0B0
0x14001b08c  mov     r9, [rdi+8]
0x14001b090  lea     rax, aDereferenceObj; "Dereference object"
0x14001b097  mov     r8, rdi
0x14001b09a  mov     [rsp+70h+var_50], rax
0x14001b09f  mov     edx, 0ABh
0x14001b0a4  lea     rcx, aHvsocketupdate_0; "HvSocketUpdatePartitionProperties"
0x14001b0ab  call    HvsocketTraceReferenceCount
0x14001b0b0  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001b0b4  lock xadd [rdi+8], rax
0x14001b0ba  sub     rax, 1
0x14001b0be  jg      short loc_14001B115
0x14001b0c0  test    rax, rax
0x14001b0c3  jz      short loc_14001B0CE
0x14001b0c5  mov     ecx, 0Eh
0x14001b0ca  int     29h; Win8: RtlFailFast(ecx)
0x14001b0cc  jmp     short loc_14001B115
0x14001b0ce  mov     rax, [rdi+50h]
0x14001b0d2  test    rax, rax
0x14001b0d5  jz      short loc_14001B0DF
0x14001b0d7  mov     rcx, rdi
0x14001b0da  call    _guard_dispatch_icall
0x14001b0df  mov     ecx, [rdi+58h]
0x14001b0e2  sub     ecx, 1
0x14001b0e5  jz      short loc_14001B101
0x14001b0e7  cmp     ecx, 1
0x14001b0ea  jnz     short loc_14001B115
0x14001b0ec  mov     rcx, [rdi+60h]; Lookaside
0x14001b0f0  mov     rdx, rdi; Entry
0x14001b0f3  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001b0fa  nop     dword ptr [rax+rax+00h]
0x14001b0ff  jmp     short loc_14001B115
0x14001b101  mov     edx, 69706E56h; Tag
0x14001b106  mov     rcx, rdi; P
0x14001b109  call    cs:__imp_ExFreePoolWithTag
0x14001b110  nop     dword ptr [rax+rax+00h]
0x14001b115  mov     eax, ebx
0x14001b117  mov     rcx, [rbp+var_10]
0x14001b11b  xor     rcx, rsp; StackCookie
0x14001b11e  call    __security_check_cookie
0x14001b123  mov     rbx, [rsp+70h+arg_10]
0x14001b12b  add     rsp, 70h
0x14001b12f  pop     rdi
0x14001b130  pop     rsi
0x14001b131  pop     rbp
0x14001b132  retn
```
