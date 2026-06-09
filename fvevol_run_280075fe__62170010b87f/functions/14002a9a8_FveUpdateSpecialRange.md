# FveUpdateSpecialRange

- ea: `0x14002a9a8`
- end: `0x14002ae06`
- name: `FveUpdateSpecialRange`
- size: `1118`
- prototype: `__int64 __usercall@<rax>(__int64@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140024b9c`

## callees

- `0x14002a9a8`
- `0x14002ae0c`
- `0x14002bac0`
- `0x1400d0570`

## import_xrefs

- `ntoskrnl!IoSizeofWorkItem` at `0x14002ac8a`
- `ntoskrnl!IoSizeofWorkItem` at `0x14002ac8a`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14002ad72`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14002ad72`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14002ab71`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14002ab71`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002aa80`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002ac02`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002ac42`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002aa80`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002ac02`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002ac42`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002aa44`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002abc3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002aa44`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002abc3`
- `ntoskrnl!KeSetEvent` at `0x14002ab18`
- `ntoskrnl!KeSetEvent` at `0x14002adf5`
- `ntoskrnl!KeSetEvent` at `0x14002ab18`
- `ntoskrnl!KeSetEvent` at `0x14002adf5`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002ac62`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002adc4`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002ac62`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002adc4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ad8f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ad8f`
- `ntoskrnl!ExAllocatePool2` at `0x14002aca7`
- `ntoskrnl!ExAllocatePool2` at `0x14002ad20`
- `ntoskrnl!ExAllocatePool2` at `0x14002aca7`
- `ntoskrnl!ExAllocatePool2` at `0x14002ad20`

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
  if ( !v6 || (v11 = 1, (*(_DWORD *)(*(_QWORD *)(a1 + 8) + 9676LL) & 0x40000000) != 0) )
    v11 = 0;
  for ( i = 0; ; i = 1 )
  {
    if ( !v11 )
      goto LABEL_5;
    if ( !*(_QWORD *)(a1 + 592) )
    {
      if ( !i )
        goto LABEL_34;
      if ( (*(_DWORD *)(*(_QWORD *)(a1 + 8) + 9676LL) & 0x4000000) != 0 )
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
  if ( (*(_DWORD *)(*(_QWORD *)(a1 + 8) + 9676LL) & 0x4000000) != 0 )
    goto LABEL_5;
  v25 = (struct _LOOKASIDE_LIST_EX *)ExAllocatePool2(64, 96, 809850438);
  *(_QWORD *)(a1 + 584) = v25;
  if ( !v25 )
    goto LABEL_5;
  if ( (*(_DWORD *)(*(_QWORD *)(a1 + 8) + 9676LL) & 0x4000000) != 0
    || ExInitializeLookasideListEx(v25, 0, 0, (POOL_TYPE)512, 0, 0x38u, 0x30455646u, 0) < 0 )
  {
    ExFreePoolWithTag(*(PVOID *)(a1 + 584), 0x30455646u);
    *(_QWORD *)(a1 + 584) = 0;
    goto LABEL_5;
  }
LABEL_15:
  if ( (*(_DWORD *)(*(_QWORD *)(a1 + 8) + 9676LL) & 0x4000000) != 0
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
0x14002a9a8  push    rbp
0x14002a9aa  push    rbx
0x14002a9ab  push    rsi
0x14002a9ac  push    rdi
0x14002a9ad  push    r12
0x14002a9af  push    r13
0x14002a9b1  push    r14
0x14002a9b3  push    r15
0x14002a9b5  lea     rbp, [rsp-7]
0x14002a9ba  sub     rsp, 0A8h
0x14002a9c1  xorps   xmm0, xmm0
0x14002a9c4  xor     eax, eax
0x14002a9c6  xor     r13d, r13d
0x14002a9c9  mov     [rbp+3Fh+var_50], rax
0x14002a9cd  cmp     dword ptr [rcx+344h], 2
0x14002a9d4  mov     r14, r9
0x14002a9d7  mov     r15d, r8d
0x14002a9da  mov     r12d, edx
0x14002a9dd  mov     rbx, rcx
0x14002a9e0  movups  [rbp+3Fh+var_80], xmm0
0x14002a9e4  movups  [rbp+3Fh+var_70], xmm0
0x14002a9e8  movups  [rbp+3Fh+var_60], xmm0
0x14002a9ec  jz      loc_14002AC1C
0x14002a9f2  mov     dil, r13b
0x14002a9f5  mov     sil, r13b
0x14002a9f8  test    dil, dil
0x14002a9fb  jnz     loc_14002AB3C
0x14002aa01  lea     rax, [rbp+3Fh+var_80]
0x14002aa05  mov     dword ptr [rbp+3Fh+var_50+1], r13d
0x14002aa09  mov     qword ptr [rbp+3Fh+var_80+8], rax
0x14002aa0d  lea     rdi, [rbx+240h]
0x14002aa14  lea     rax, [rbp+3Fh+var_80]
0x14002aa18  mov     word ptr [rbp+3Fh+var_50+5], r13w
0x14002aa1d  mov     qword ptr [rbp+3Fh+var_80], rax
0x14002aa21  mov     rcx, rdi; SpinLock
0x14002aa24  mov     rax, [rbp+3Fh+arg_20]
0x14002aa28  mov     qword ptr [rbp+3Fh+var_60], rax
0x14002aa2c  mov     byte ptr [rbp+3Fh+var_50+7], r13b
0x14002aa30  mov     qword ptr [rbp+3Fh+var_70], rbx
0x14002aa34  mov     dword ptr [rbp+3Fh+var_60+0Ch], r12d
0x14002aa38  mov     dword ptr [rbp+3Fh+var_60+8], r15d
0x14002aa3c  mov     qword ptr [rbp+3Fh+var_70+8], r14
0x14002aa40  mov     byte ptr [rbp+3Fh+var_50], r13b
0x14002aa44  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002aa4b  nop     dword ptr [rax+rax+00h]
0x14002aa50  lea     rcx, [rbx+230h]
0x14002aa57  mov     rdx, [rcx+8]
0x14002aa5b  cmp     [rdx], rcx
0x14002aa5e  jnz     loc_14002ADE2
0x14002aa64  mov     qword ptr [rbp+3Fh+var_80+8], rdx
0x14002aa68  lea     r8, [rbp+3Fh+var_80]
0x14002aa6c  mov     qword ptr [rbp+3Fh+var_80], rcx
0x14002aa70  mov     [rdx], r8
0x14002aa73  lea     rdx, [rbp+3Fh+var_80]
0x14002aa77  mov     [rcx+8], rdx
0x14002aa7b  mov     dl, al; NewIrql
0x14002aa7d  mov     rcx, rdi; SpinLock
0x14002aa80  call    cs:__imp_KeReleaseSpinLock
0x14002aa87  nop     dword ptr [rax+rax+00h]
0x14002aa8c  test    sil, sil
0x14002aa8f  jnz     loc_14002ADE9
0x14002aa95  mov     rcx, rbx
0x14002aa98  call    FvepUpdateSpecialRanges
0x14002aa9d  mov     r14d, r13d
0x14002aaa0  jmp     short loc_14002AB0C
0x14002aaa2  cmp     [rbx+258h], r13b
0x14002aaa9  jnz     short loc_14002AB07
0x14002aaab  mov     rax, [rbp+3Fh+arg_28]
0x14002aaaf  xor     r8d, r8d
0x14002aab2  mov     r9d, [rbx+25Ch]
0x14002aab9  or      rax, 2
0x14002aabd  mov     rdx, [rbx+250h]; BugCheckParameter2
0x14002aac4  mov     rcx, [rbx+8]; Context
0x14002aac8  mov     [rsp+0E0h+var_90], r13b; char
0x14002aacd  mov     [rsp+0E0h+var_98], r13d; int
0x14002aad2  mov     [rsp+0E0h+var_A0], rax; __int64
0x14002aad7  lea     rax, FveUpdateSpecialRangeWorker
0x14002aade  mov     qword ptr [rsp+0E0h+Depth], rbx; __int64
0x14002aae3  mov     qword ptr [rsp+0E0h+Tag], rax; __int64
0x14002aae8  mov     byte ptr [rsp+0E0h+Size], r13b; char
0x14002aaed  mov     dword ptr [rsp+0E0h+Timeout], 2; int
0x14002aaf5  mov     byte ptr [rbx+258h], 1
0x14002aafc  call    FvepQueueWorkItem
0x14002ab01  mov     r14d, 103h
0x14002ab07  test    sil, sil
0x14002ab0a  jz      short loc_14002AB24
0x14002ab0c  lea     rcx, [rbx+260h]; Event
0x14002ab13  xor     r8d, r8d; Wait
0x14002ab16  xor     edx, edx; Increment
0x14002ab18  call    cs:__imp_KeSetEvent
0x14002ab1f  nop     dword ptr [rax+rax+00h]
0x14002ab24  mov     eax, r14d
0x14002ab27  add     rsp, 0A8h
0x14002ab2e  pop     r15
0x14002ab30  pop     r14
0x14002ab32  pop     r13
0x14002ab34  pop     r12
0x14002ab36  pop     rdi
0x14002ab37  pop     rsi
0x14002ab38  pop     rbx
0x14002ab39  pop     rbp
0x14002ab3a  retn
0x14002ab3c  cmp     [rbx+250h], r13
0x14002ab43  jz      loc_14002ADA7
0x14002ab49  cmp     [rbx+248h], r13
0x14002ab50  jz      loc_14002ADD8
0x14002ab56  mov     rax, [rbx+8]
0x14002ab5a  test    dword ptr [rax+25CCh], 4000000h
0x14002ab64  jnz     loc_14002AA01
0x14002ab6a  mov     rcx, [rbx+248h]; Lookaside
0x14002ab71  call    cs:__imp_ExAllocateFromLookasideListEx
0x14002ab78  nop     dword ptr [rax+rax+00h]
0x14002ab7d  mov     rdi, rax
0x14002ab80  test    rax, rax
0x14002ab83  jz      loc_14002AA01
0x14002ab89  mov     [rax+31h], r13d
0x14002ab8d  mov     [rax+35h], r13w
0x14002ab92  mov     [rax+37h], r13b
0x14002ab96  mov     [rax+8], rax
0x14002ab9a  mov     [rax], rax
0x14002ab9d  mov     [rax+28h], r15d
0x14002aba1  lea     r15, [rbx+240h]
0x14002aba8  mov     [rax+10h], rbx
0x14002abac  mov     rcx, r15; SpinLock
0x14002abaf  mov     [rax+2Ch], r12d
0x14002abb3  mov     [rax+18h], r14
0x14002abb7  mov     rax, [rbp+3Fh+arg_20]
0x14002abbb  mov     [rdi+20h], rax
0x14002abbf  mov     byte ptr [rdi+30h], 1
0x14002abc3  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002abca  nop     dword ptr [rax+rax+00h]
0x14002abcf  lea     rdx, [rbx+230h]
0x14002abd6  mov     r8, [rdx+8]
0x14002abda  cmp     [r8], rdx
0x14002abdd  jnz     loc_14002ADE2
0x14002abe3  mov     [rdi], rdx
0x14002abe6  mov     r14d, r13d
0x14002abe9  mov     [rdi+8], r8
0x14002abed  mov     [r8], rdi
0x14002abf0  mov     [rdx+8], rdi
0x14002abf4  cmp     [rbx+258h], r13b
0x14002abfb  jz      short loc_14002AC38
0x14002abfd  mov     dl, al; NewIrql
0x14002abff  mov     rcx, r15; SpinLock
0x14002ac02  call    cs:__imp_KeReleaseSpinLock
0x14002ac09  nop     dword ptr [rax+rax+00h]
0x14002ac0e  test    sil, sil
0x14002ac11  jz      loc_14002AB24
0x14002ac17  jmp     loc_14002AAA2
0x14002ac1c  mov     rax, [rcx+8]
0x14002ac20  mov     dil, 1
0x14002ac23  test    dword ptr [rax+25CCh], 40000000h
0x14002ac2d  jz      loc_14002A9F5
0x14002ac33  jmp     loc_14002A9F2
0x14002ac38  test    sil, sil
0x14002ac3b  jnz     short loc_14002ABFD
0x14002ac3d  mov     dl, al; NewIrql
0x14002ac3f  mov     rcx, r15; SpinLock
0x14002ac42  call    cs:__imp_KeReleaseSpinLock
0x14002ac49  nop     dword ptr [rax+rax+00h]
0x14002ac4e  lea     rcx, [rbx+260h]; Object
0x14002ac55  mov     [rsp+0E0h+Timeout], r13; Timeout
0x14002ac5a  xor     r9d, r9d; Alertable
0x14002ac5d  xor     r8d, r8d; WaitMode
0x14002ac60  xor     edx, edx; WaitReason
0x14002ac62  call    cs:__imp_KeWaitForSingleObject
0x14002ac69  nop     dword ptr [rax+rax+00h]
0x14002ac6e  mov     sil, 1
0x14002ac71  jmp     loc_14002AAA2
0x14002ac76  mov     rax, [rbx+8]
0x14002ac7a  test    dword ptr [rax+25CCh], 4000000h
0x14002ac84  jnz     loc_14002AA01
0x14002ac8a  call    cs:__imp_IoSizeofWorkItem
0x14002ac91  nop     dword ptr [rax+rax+00h]
0x14002ac96  mov     ecx, 40h ; '@'
0x14002ac9b  mov     r8d, 30455646h
0x14002aca1  lea     edx, [rax+0B8h]
0x14002aca7  call    cs:__imp_ExAllocatePool2
0x14002acae  nop     dword ptr [rax+rax+00h]
0x14002acb3  mov     [rbx+250h], rax
0x14002acba  test    rax, rax
0x14002acbd  jz      loc_14002AA01
0x14002acc3  mov     r8d, [rbx+52Ch]
0x14002acca  lea     rcx, FveUpdateSpecialRangeWorkerCompleted
0x14002acd1  mov     rdx, [rbx]
0x14002acd4  mov     r9, rax
0x14002acd7  mov     qword ptr [rsp+0E0h+Depth], rbx
0x14002acdc  mov     qword ptr [rsp+0E0h+Tag], rcx
0x14002ace1  mov     rcx, [rbx+8]
0x14002ace5  mov     [rsp+0E0h+Size], r13
0x14002acea  mov     dword ptr [rsp+0E0h+Timeout], 1
0x14002acf2  call    FveWorkItemInitialize
0x14002acf7  jmp     loc_14002AB49
0x14002acfc  mov     rax, [rbx+8]
0x14002ad00  test    dword ptr [rax+25CCh], 4000000h
0x14002ad0a  jnz     loc_14002AA01
0x14002ad10  mov     edx, 60h ; '`'
0x14002ad15  mov     edi, 30455646h
0x14002ad1a  mov     r8d, edi
0x14002ad1d  lea     ecx, [rdx-20h]
0x14002ad20  call    cs:__imp_ExAllocatePool2
0x14002ad27  nop     dword ptr [rax+rax+00h]
0x14002ad2c  mov     [rbx+248h], rax
0x14002ad33  test    rax, rax
0x14002ad36  jz      loc_14002AA01
0x14002ad3c  mov     rcx, [rbx+8]
0x14002ad40  test    dword ptr [rcx+25CCh], 4000000h
0x14002ad4a  jnz     short loc_14002AD86
0x14002ad4c  mov     [rsp+0E0h+Depth], r13w; Depth
0x14002ad52  mov     r9d, 200h; PoolType
0x14002ad58  mov     [rsp+0E0h+Tag], edi; Tag
0x14002ad5c  xor     r8d, r8d; Free
0x14002ad5f  mov     [rsp+0E0h+Size], 38h ; '8'; Size
0x14002ad68  xor     edx, edx; Allocate
0x14002ad6a  mov     rcx, rax; Lookaside
0x14002ad6d  mov     dword ptr [rsp+0E0h+Timeout], r13d; Flags
0x14002ad72  call    cs:__imp_ExInitializeLookasideListEx
0x14002ad79  nop     dword ptr [rax+rax+00h]
0x14002ad7e  test    eax, eax
0x14002ad80  jns     loc_14002AB56
0x14002ad86  mov     rcx, [rbx+248h]; P
0x14002ad8d  mov     edx, edi; Tag
0x14002ad8f  call    cs:__imp_ExFreePoolWithTag
0x14002ad96  nop     dword ptr [rax+rax+00h]
0x14002ad9b  mov     [rbx+248h], r13
0x14002ada2  jmp     loc_14002AA01
0x14002ada7  test    sil, sil
0x14002adaa  jnz     loc_14002AC76
0x14002adb0  lea     rcx, [rbx+260h]; Object
0x14002adb7  mov     [rsp+0E0h+Timeout], r13; Timeout
0x14002adbc  xor     r9d, r9d; Alertable
0x14002adbf  xor     r8d, r8d; WaitMode
0x14002adc2  xor     edx, edx; WaitReason
0x14002adc4  call    cs:__imp_KeWaitForSingleObject
0x14002adcb  nop     dword ptr [rax+rax+00h]
0x14002add0  mov     sil, 1
0x14002add3  jmp     loc_14002A9F8
0x14002add8  test    sil, sil
0x14002addb  jz      short loc_14002ADB0
0x14002addd  jmp     loc_14002ACFC
0x14002ade2  mov     ecx, 3
0x14002ade7  int     29h; Win8: RtlFailFast(ecx)
0x14002ade9  lea     rcx, [rbx+260h]; Event
0x14002adf0  xor     r8d, r8d; Wait
0x14002adf3  xor     edx, edx; Increment
0x14002adf5  call    cs:__imp_KeSetEvent
0x14002adfc  nop     dword ptr [rax+rax+00h]
0x14002ae01  jmp     loc_14002AA95
```
