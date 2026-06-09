# FveUpdateSpecialRange

- ea: `0x14002b9a8`
- end: `0x14002be06`
- name: `FveUpdateSpecialRange`
- size: `1118`
- prototype: `__int64 __usercall@<rax>(__int64@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140025b9c`

## callees

- `0x14002b9a8`
- `0x14002be0c`
- `0x14002cac0`
- `0x1400d37c0`

## import_xrefs

- `ntoskrnl!IoSizeofWorkItem` at `0x14002bc8a`
- `ntoskrnl!IoSizeofWorkItem` at `0x14002bc8a`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14002bd72`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14002bd72`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14002bb71`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14002bb71`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002ba80`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002bc02`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002bc42`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002ba80`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002bc02`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002bc42`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002ba44`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002bbc3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002ba44`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002bbc3`
- `ntoskrnl!KeSetEvent` at `0x14002bb18`
- `ntoskrnl!KeSetEvent` at `0x14002bdf5`
- `ntoskrnl!KeSetEvent` at `0x14002bb18`
- `ntoskrnl!KeSetEvent` at `0x14002bdf5`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002bc62`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002bdc4`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002bc62`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002bdc4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002bd8f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002bd8f`
- `ntoskrnl!ExAllocatePool2` at `0x14002bca7`
- `ntoskrnl!ExAllocatePool2` at `0x14002bd20`
- `ntoskrnl!ExAllocatePool2` at `0x14002bca7`
- `ntoskrnl!ExAllocatePool2` at `0x14002bd20`

## pseudocode

```c
__int64 __fastcall FveUpdateSpecialRange(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  bool v6; // zf
  char v11; // di
  char i; // si
  KIRQL v13; // al
  _QWORD *v14; // rdx
  unsigned int v15; // r14d
  ULONG_PTR v16; // rdx
  void *v17; // rcx
  char *v19; // rax
  _QWORD *v20; // rdi
  KIRQL v21; // al
  _QWORD *v22; // r8
  ULONG v23; // eax
  __int64 Pool2; // rax
  struct _LOOKASIDE_LIST_EX *v25; // rax
  __int128 v26; // [rsp+60h] [rbp-41h] BYREF
  __int128 v27; // [rsp+70h] [rbp-31h]
  __int128 v28; // [rsp+80h] [rbp-21h]
  __int64 v29; // [rsp+90h] [rbp-11h]

  v29 = 0;
  v6 = *(_DWORD *)(a1 + 836) == 2;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  if ( !v6 || (v11 = 1, (*(_DWORD *)(*(_QWORD *)(a1 + 8) + 9924LL) & 0x40000000) != 0) )
    v11 = 0;
  for ( i = 0; ; i = 1 )
  {
    if ( !v11 )
      goto LABEL_5;
    if ( !*(_QWORD *)(a1 + 592) )
    {
      if ( !i )
        goto LABEL_34;
      if ( (*(_DWORD *)(*(_QWORD *)(a1 + 8) + 9924LL) & 0x4000000) != 0 )
        goto LABEL_5;
      v23 = IoSizeofWorkItem();
      Pool2 = ExAllocatePool2(64, v23 + 184, 809850438);
      *(_QWORD *)(a1 + 592) = Pool2;
      if ( !Pool2 )
        goto LABEL_5;
      FveWorkItemInitialize(
        *(_QWORD *)(a1 + 8),
        *(_QWORD *)a1,
        *(unsigned int *)(a1 + 1324),
        Pool2,
        1,
        0,
        &FveUpdateSpecialRangeWorkerCompleted,
        a1);
    }
    if ( *(_QWORD *)(a1 + 584) )
      goto LABEL_15;
    if ( i )
      break;
LABEL_34:
    KeWaitForSingleObject((PVOID)(a1 + 608), Executive, 0, 0, 0);
  }
  if ( (*(_DWORD *)(*(_QWORD *)(a1 + 8) + 9924LL) & 0x4000000) != 0 )
    goto LABEL_5;
  v25 = (struct _LOOKASIDE_LIST_EX *)ExAllocatePool2(64, 96, 809850438);
  *(_QWORD *)(a1 + 584) = v25;
  if ( !v25 )
    goto LABEL_5;
  if ( (*(_DWORD *)(*(_QWORD *)(a1 + 8) + 9924LL) & 0x4000000) != 0
    || ExInitializeLookasideListEx(v25, 0, 0, (POOL_TYPE)512, 0, 0x38u, 0x30455646u, 0) < 0 )
  {
    ExFreePoolWithTag(*(PVOID *)(a1 + 584), 0x30455646u);
    *(_QWORD *)(a1 + 584) = 0;
    goto LABEL_5;
  }
LABEL_15:
  if ( (*(_DWORD *)(*(_QWORD *)(a1 + 8) + 9924LL) & 0x4000000) != 0
    || (v19 = (char *)ExAllocateFromLookasideListEx(*(PLOOKASIDE_LIST_EX *)(a1 + 584)), (v20 = v19) == 0) )
  {
LABEL_5:
    v29 = 0;
    *((_QWORD *)&v26 + 1) = &v26;
    *(_QWORD *)&v26 = &v26;
    *(_QWORD *)&v28 = a5;
    *(_QWORD *)&v27 = a1;
    *((_QWORD *)&v28 + 1) = __PAIR64__(a2, a3);
    *((_QWORD *)&v27 + 1) = a4;
    v13 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 576));
    v14 = *(_QWORD **)(a1 + 568);
    if ( *v14 == a1 + 560 )
    {
      *((_QWORD *)&v26 + 1) = *(_QWORD *)(a1 + 568);
      *(_QWORD *)&v26 = a1 + 560;
      *v14 = &v26;
      *(_QWORD *)(a1 + 568) = &v26;
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 576), v13);
      if ( i )
        KeSetEvent((PRKEVENT)(a1 + 608), 0, 0);
      FvepUpdateSpecialRanges(a1);
      v15 = 0;
      goto LABEL_11;
    }
LABEL_37:
    __fastfail(3u);
  }
  *(_DWORD *)(v19 + 49) = 0;
  *(_WORD *)(v19 + 53) = 0;
  v19[55] = 0;
  *((_QWORD *)v19 + 1) = v19;
  *(_QWORD *)v19 = v19;
  *((_DWORD *)v19 + 10) = a3;
  *((_QWORD *)v19 + 2) = a1;
  *((_DWORD *)v19 + 11) = a2;
  *((_QWORD *)v19 + 3) = a4;
  *((_QWORD *)v19 + 4) = a5;
  v19[48] = 1;
  v21 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 576));
  v22 = *(_QWORD **)(a1 + 568);
  if ( *v22 != a1 + 560 )
    goto LABEL_37;
  *v20 = a1 + 560;
  v15 = 0;
  v20[1] = v22;
  *v22 = v20;
  *(_QWORD *)(a1 + 568) = v20;
  if ( *(_BYTE *)(a1 + 600) || i )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 576), v21);
    if ( i )
      goto LABEL_9;
  }
  else
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 576), v21);
    KeWaitForSingleObject((PVOID)(a1 + 608), Executive, 0, 0, 0);
LABEL_9:
    if ( !*(_BYTE *)(a1 + 600) )
    {
      v16 = *(_QWORD *)(a1 + 592);
      v17 = *(void **)(a1 + 8);
      *(_BYTE *)(a1 + 600) = 1;
      FvepQueueWorkItem(v17, v16, 2, 0, (__int64)FveUpdateSpecialRangeWorker, a1, a6 | 2, 0, 0);
      v15 = 259;
    }
LABEL_11:
    KeSetEvent((PRKEVENT)(a1 + 608), 0, 0);
  }
  return v15;
}

```

## disassembly

```asm
0x14002b9a8  push    rbp
0x14002b9aa  push    rbx
0x14002b9ab  push    rsi
0x14002b9ac  push    rdi
0x14002b9ad  push    r12
0x14002b9af  push    r13
0x14002b9b1  push    r14
0x14002b9b3  push    r15
0x14002b9b5  lea     rbp, [rsp-7]
0x14002b9ba  sub     rsp, 0A8h
0x14002b9c1  xorps   xmm0, xmm0
0x14002b9c4  xor     eax, eax
0x14002b9c6  xor     r13d, r13d
0x14002b9c9  mov     [rbp+3Fh+var_50], rax
0x14002b9cd  cmp     dword ptr [rcx+344h], 2
0x14002b9d4  mov     r14, r9
0x14002b9d7  mov     r15d, r8d
0x14002b9da  mov     r12d, edx
0x14002b9dd  mov     rbx, rcx
0x14002b9e0  movups  [rbp+3Fh+var_80], xmm0
0x14002b9e4  movups  [rbp+3Fh+var_70], xmm0
0x14002b9e8  movups  [rbp+3Fh+var_60], xmm0
0x14002b9ec  jz      loc_14002BC1C
0x14002b9f2  mov     dil, r13b
0x14002b9f5  mov     sil, r13b
0x14002b9f8  test    dil, dil
0x14002b9fb  jnz     loc_14002BB3C
0x14002ba01  lea     rax, [rbp+3Fh+var_80]
0x14002ba05  mov     dword ptr [rbp+3Fh+var_50+1], r13d
0x14002ba09  mov     qword ptr [rbp+3Fh+var_80+8], rax
0x14002ba0d  lea     rdi, [rbx+240h]
0x14002ba14  lea     rax, [rbp+3Fh+var_80]
0x14002ba18  mov     word ptr [rbp+3Fh+var_50+5], r13w
0x14002ba1d  mov     qword ptr [rbp+3Fh+var_80], rax
0x14002ba21  mov     rcx, rdi; SpinLock
0x14002ba24  mov     rax, [rbp+3Fh+arg_20]
0x14002ba28  mov     qword ptr [rbp+3Fh+var_60], rax
0x14002ba2c  mov     byte ptr [rbp+3Fh+var_50+7], r13b
0x14002ba30  mov     qword ptr [rbp+3Fh+var_70], rbx
0x14002ba34  mov     dword ptr [rbp+3Fh+var_60+0Ch], r12d
0x14002ba38  mov     dword ptr [rbp+3Fh+var_60+8], r15d
0x14002ba3c  mov     qword ptr [rbp+3Fh+var_70+8], r14
0x14002ba40  mov     byte ptr [rbp+3Fh+var_50], r13b
0x14002ba44  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002ba4b  nop     dword ptr [rax+rax+00h]
0x14002ba50  lea     rcx, [rbx+230h]
0x14002ba57  mov     rdx, [rcx+8]
0x14002ba5b  cmp     [rdx], rcx
0x14002ba5e  jnz     loc_14002BDE2
0x14002ba64  mov     qword ptr [rbp+3Fh+var_80+8], rdx
0x14002ba68  lea     r8, [rbp+3Fh+var_80]
0x14002ba6c  mov     qword ptr [rbp+3Fh+var_80], rcx
0x14002ba70  mov     [rdx], r8
0x14002ba73  lea     rdx, [rbp+3Fh+var_80]
0x14002ba77  mov     [rcx+8], rdx
0x14002ba7b  mov     dl, al; NewIrql
0x14002ba7d  mov     rcx, rdi; SpinLock
0x14002ba80  call    cs:__imp_KeReleaseSpinLock
0x14002ba87  nop     dword ptr [rax+rax+00h]
0x14002ba8c  test    sil, sil
0x14002ba8f  jnz     loc_14002BDE9
0x14002ba95  mov     rcx, rbx
0x14002ba98  call    FvepUpdateSpecialRanges
0x14002ba9d  mov     r14d, r13d
0x14002baa0  jmp     short loc_14002BB0C
0x14002baa2  cmp     [rbx+258h], r13b
0x14002baa9  jnz     short loc_14002BB07
0x14002baab  mov     rax, [rbp+3Fh+arg_28]
0x14002baaf  xor     r8d, r8d
0x14002bab2  mov     r9d, [rbx+25Ch]
0x14002bab9  or      rax, 2
0x14002babd  mov     rdx, [rbx+250h]; BugCheckParameter2
0x14002bac4  mov     rcx, [rbx+8]; Context
0x14002bac8  mov     [rsp+0E0h+var_90], r13b; char
0x14002bacd  mov     [rsp+0E0h+var_98], r13d; int
0x14002bad2  mov     [rsp+0E0h+var_A0], rax; __int64
0x14002bad7  lea     rax, FveUpdateSpecialRangeWorker
0x14002bade  mov     qword ptr [rsp+0E0h+Depth], rbx; __int64
0x14002bae3  mov     qword ptr [rsp+0E0h+Tag], rax; __int64
0x14002bae8  mov     byte ptr [rsp+0E0h+Size], r13b; char
0x14002baed  mov     dword ptr [rsp+0E0h+Timeout], 2; int
0x14002baf5  mov     byte ptr [rbx+258h], 1
0x14002bafc  call    FvepQueueWorkItem
0x14002bb01  mov     r14d, 103h
0x14002bb07  test    sil, sil
0x14002bb0a  jz      short loc_14002BB24
0x14002bb0c  lea     rcx, [rbx+260h]; Event
0x14002bb13  xor     r8d, r8d; Wait
0x14002bb16  xor     edx, edx; Increment
0x14002bb18  call    cs:__imp_KeSetEvent
0x14002bb1f  nop     dword ptr [rax+rax+00h]
0x14002bb24  mov     eax, r14d
0x14002bb27  add     rsp, 0A8h
0x14002bb2e  pop     r15
0x14002bb30  pop     r14
0x14002bb32  pop     r13
0x14002bb34  pop     r12
0x14002bb36  pop     rdi
0x14002bb37  pop     rsi
0x14002bb38  pop     rbx
0x14002bb39  pop     rbp
0x14002bb3a  retn
0x14002bb3c  cmp     [rbx+250h], r13
0x14002bb43  jz      loc_14002BDA7
0x14002bb49  cmp     [rbx+248h], r13
0x14002bb50  jz      loc_14002BDD8
0x14002bb56  mov     rax, [rbx+8]
0x14002bb5a  test    dword ptr [rax+26C4h], 4000000h
0x14002bb64  jnz     loc_14002BA01
0x14002bb6a  mov     rcx, [rbx+248h]; Lookaside
0x14002bb71  call    cs:__imp_ExAllocateFromLookasideListEx
0x14002bb78  nop     dword ptr [rax+rax+00h]
0x14002bb7d  mov     rdi, rax
0x14002bb80  test    rax, rax
0x14002bb83  jz      loc_14002BA01
0x14002bb89  mov     [rax+31h], r13d
0x14002bb8d  mov     [rax+35h], r13w
0x14002bb92  mov     [rax+37h], r13b
0x14002bb96  mov     [rax+8], rax
0x14002bb9a  mov     [rax], rax
0x14002bb9d  mov     [rax+28h], r15d
0x14002bba1  lea     r15, [rbx+240h]
0x14002bba8  mov     [rax+10h], rbx
0x14002bbac  mov     rcx, r15; SpinLock
0x14002bbaf  mov     [rax+2Ch], r12d
0x14002bbb3  mov     [rax+18h], r14
0x14002bbb7  mov     rax, [rbp+3Fh+arg_20]
0x14002bbbb  mov     [rdi+20h], rax
0x14002bbbf  mov     byte ptr [rdi+30h], 1
0x14002bbc3  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002bbca  nop     dword ptr [rax+rax+00h]
0x14002bbcf  lea     rdx, [rbx+230h]
0x14002bbd6  mov     r8, [rdx+8]
0x14002bbda  cmp     [r8], rdx
0x14002bbdd  jnz     loc_14002BDE2
0x14002bbe3  mov     [rdi], rdx
0x14002bbe6  mov     r14d, r13d
0x14002bbe9  mov     [rdi+8], r8
0x14002bbed  mov     [r8], rdi
0x14002bbf0  mov     [rdx+8], rdi
0x14002bbf4  cmp     [rbx+258h], r13b
0x14002bbfb  jz      short loc_14002BC38
0x14002bbfd  mov     dl, al; NewIrql
0x14002bbff  mov     rcx, r15; SpinLock
0x14002bc02  call    cs:__imp_KeReleaseSpinLock
0x14002bc09  nop     dword ptr [rax+rax+00h]
0x14002bc0e  test    sil, sil
0x14002bc11  jz      loc_14002BB24
0x14002bc17  jmp     loc_14002BAA2
0x14002bc1c  mov     rax, [rcx+8]
0x14002bc20  mov     dil, 1
0x14002bc23  test    dword ptr [rax+26C4h], 40000000h
0x14002bc2d  jz      loc_14002B9F5
0x14002bc33  jmp     loc_14002B9F2
0x14002bc38  test    sil, sil
0x14002bc3b  jnz     short loc_14002BBFD
0x14002bc3d  mov     dl, al; NewIrql
0x14002bc3f  mov     rcx, r15; SpinLock
0x14002bc42  call    cs:__imp_KeReleaseSpinLock
0x14002bc49  nop     dword ptr [rax+rax+00h]
0x14002bc4e  lea     rcx, [rbx+260h]; Object
0x14002bc55  mov     [rsp+0E0h+Timeout], r13; Timeout
0x14002bc5a  xor     r9d, r9d; Alertable
0x14002bc5d  xor     r8d, r8d; WaitMode
0x14002bc60  xor     edx, edx; WaitReason
0x14002bc62  call    cs:__imp_KeWaitForSingleObject
0x14002bc69  nop     dword ptr [rax+rax+00h]
0x14002bc6e  mov     sil, 1
0x14002bc71  jmp     loc_14002BAA2
0x14002bc76  mov     rax, [rbx+8]
0x14002bc7a  test    dword ptr [rax+26C4h], 4000000h
0x14002bc84  jnz     loc_14002BA01
0x14002bc8a  call    cs:__imp_IoSizeofWorkItem
0x14002bc91  nop     dword ptr [rax+rax+00h]
0x14002bc96  mov     ecx, 40h ; '@'
0x14002bc9b  mov     r8d, 30455646h
0x14002bca1  lea     edx, [rax+0B8h]
0x14002bca7  call    cs:__imp_ExAllocatePool2
0x14002bcae  nop     dword ptr [rax+rax+00h]
0x14002bcb3  mov     [rbx+250h], rax
0x14002bcba  test    rax, rax
0x14002bcbd  jz      loc_14002BA01
0x14002bcc3  mov     r8d, [rbx+52Ch]
0x14002bcca  lea     rcx, FveUpdateSpecialRangeWorkerCompleted
0x14002bcd1  mov     rdx, [rbx]
0x14002bcd4  mov     r9, rax
0x14002bcd7  mov     qword ptr [rsp+0E0h+Depth], rbx
0x14002bcdc  mov     qword ptr [rsp+0E0h+Tag], rcx
0x14002bce1  mov     rcx, [rbx+8]
0x14002bce5  mov     [rsp+0E0h+Size], r13
0x14002bcea  mov     dword ptr [rsp+0E0h+Timeout], 1
0x14002bcf2  call    FveWorkItemInitialize
0x14002bcf7  jmp     loc_14002BB49
0x14002bcfc  mov     rax, [rbx+8]
0x14002bd00  test    dword ptr [rax+26C4h], 4000000h
0x14002bd0a  jnz     loc_14002BA01
0x14002bd10  mov     edx, 60h ; '`'
0x14002bd15  mov     edi, 30455646h
0x14002bd1a  mov     r8d, edi
0x14002bd1d  lea     ecx, [rdx-20h]
0x14002bd20  call    cs:__imp_ExAllocatePool2
0x14002bd27  nop     dword ptr [rax+rax+00h]
0x14002bd2c  mov     [rbx+248h], rax
0x14002bd33  test    rax, rax
0x14002bd36  jz      loc_14002BA01
0x14002bd3c  mov     rcx, [rbx+8]
0x14002bd40  test    dword ptr [rcx+26C4h], 4000000h
0x14002bd4a  jnz     short loc_14002BD86
0x14002bd4c  mov     [rsp+0E0h+Depth], r13w; Depth
0x14002bd52  mov     r9d, 200h; PoolType
0x14002bd58  mov     [rsp+0E0h+Tag], edi; Tag
0x14002bd5c  xor     r8d, r8d; Free
0x14002bd5f  mov     [rsp+0E0h+Size], 38h ; '8'; Size
0x14002bd68  xor     edx, edx; Allocate
0x14002bd6a  mov     rcx, rax; Lookaside
0x14002bd6d  mov     dword ptr [rsp+0E0h+Timeout], r13d; Flags
0x14002bd72  call    cs:__imp_ExInitializeLookasideListEx
0x14002bd79  nop     dword ptr [rax+rax+00h]
0x14002bd7e  test    eax, eax
0x14002bd80  jns     loc_14002BB56
0x14002bd86  mov     rcx, [rbx+248h]; P
0x14002bd8d  mov     edx, edi; Tag
0x14002bd8f  call    cs:__imp_ExFreePoolWithTag
0x14002bd96  nop     dword ptr [rax+rax+00h]
0x14002bd9b  mov     [rbx+248h], r13
0x14002bda2  jmp     loc_14002BA01
0x14002bda7  test    sil, sil
0x14002bdaa  jnz     loc_14002BC76
0x14002bdb0  lea     rcx, [rbx+260h]; Object
0x14002bdb7  mov     [rsp+0E0h+Timeout], r13; Timeout
0x14002bdbc  xor     r9d, r9d; Alertable
0x14002bdbf  xor     r8d, r8d; WaitMode
0x14002bdc2  xor     edx, edx; WaitReason
0x14002bdc4  call    cs:__imp_KeWaitForSingleObject
0x14002bdcb  nop     dword ptr [rax+rax+00h]
0x14002bdd0  mov     sil, 1
0x14002bdd3  jmp     loc_14002B9F8
0x14002bdd8  test    sil, sil
0x14002bddb  jz      short loc_14002BDB0
0x14002bddd  jmp     loc_14002BCFC
0x14002bde2  mov     ecx, 3
0x14002bde7  int     29h; Win8: RtlFailFast(ecx)
0x14002bde9  lea     rcx, [rbx+260h]; Event
0x14002bdf0  xor     r8d, r8d; Wait
0x14002bdf3  xor     edx, edx; Increment
0x14002bdf5  call    cs:__imp_KeSetEvent
0x14002bdfc  nop     dword ptr [rax+rax+00h]
0x14002be01  jmp     loc_14002BA95
```
