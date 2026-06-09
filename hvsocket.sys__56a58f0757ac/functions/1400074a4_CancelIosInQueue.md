# CancelIosInQueue

- ea: `0x1400074a4`
- end: `0x140007646`
- name: `CancelIosInQueue`
- size: `418`
- prototype: `void __fastcall(__int64, __int64, char)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400045c0`
- `0x140004750`
- `0x14000764c`

## callees

- `0x1400074a4`
- `0x14000a048`
- `0x14000bfe0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400074ba`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000760f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400074ba`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000760f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007559`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007630`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007559`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007630`
- `ntoskrnl!IoCancelIrp` at `0x14000756c`
- `ntoskrnl!IoCancelIrp` at `0x14000756c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400075f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400075f7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400075e1`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400075e1`

## pseudocode

```c
void __fastcall CancelIosInQueue(__int64 a1, __int64 a2, char a3)
{
  KSPIN_LOCK *v3; // rbp
  KIRQL v6; // di
  _QWORD *v7; // rax
  __int64 v8; // rcx
  _QWORD *v9; // rdx
  volatile signed __int64 *v10; // rbx
  signed __int64 v11; // rax
  bool v12; // cc
  signed __int64 v13; // rax
  void (__fastcall *v14)(volatile signed __int64 *); // rax

  v3 = (KSPIN_LOCK *)(a2 + 16);
  v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 16));
  if ( a3 )
    *(_BYTE *)(a2 + 24) = 1;
  while ( 1 )
  {
    v7 = *(_QWORD **)a2;
    if ( *(_QWORD *)a2 == a2 )
      break;
    v8 = *v7;
    if ( *(_QWORD **)(*v7 + 8LL) != v7 || (v9 = (_QWORD *)v7[1], (_QWORD *)*v9 != v7) )
      __fastfail(3u);
    *v9 = v8;
    v10 = v7 - 13;
    *(_QWORD *)(v8 + 8) = v9;
    v7[1] = v7;
    *v7 = v7;
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"CancelIosInQueue",
        829,
        (_DWORD)v10,
        *((_QWORD *)v10 + 1),
        (__int64)"Reference object");
    if ( _InterlockedIncrement64(v10 + 1) <= 1 )
      __fastfail(0xEu);
    KeReleaseSpinLock(v3, v6);
    IoCancelIrp(*((PIRP *)v10 + 28));
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"CancelIosInQueue",
        835,
        (_DWORD)v10,
        *((_QWORD *)v10 + 1),
        (__int64)"Dereference object");
    v11 = _InterlockedExchangeAdd64(v10 + 1, 0xFFFFFFFFFFFFFFFFuLL);
    v12 = v11 <= 1;
    v13 = v11 - 1;
    if ( v12 )
    {
      if ( v13 )
        __fastfail(0xEu);
      v14 = (void (__fastcall *)(volatile signed __int64 *))*((_QWORD *)v10 + 10);
      if ( v14 )
        v14(v10);
      if ( *((_DWORD *)v10 + 22) == 1 )
      {
        ExFreePoolWithTag((PVOID)v10, 0x69706E56u);
      }
      else if ( *((_DWORD *)v10 + 22) == 2 )
      {
        ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v10 + 12), (PVOID)v10);
      }
    }
    v6 = KeAcquireSpinLockRaiseToDpc(v3);
  }
  KeReleaseSpinLock(v3, v6);
}

```

## disassembly

```asm
0x1400074a4  push    rbx
0x1400074a6  push    rbp
0x1400074a7  push    rsi
0x1400074a8  push    rdi
0x1400074a9  sub     rsp, 38h
0x1400074ad  lea     rbp, [rdx+10h]
0x1400074b1  mov     bl, r8b
0x1400074b4  mov     rcx, rbp; SpinLock
0x1400074b7  mov     rsi, rdx
0x1400074ba  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400074c1  nop     dword ptr [rax+rax+00h]
0x1400074c6  mov     dil, al
0x1400074c9  test    bl, bl
0x1400074cb  jz      short loc_1400074D1
0x1400074cd  mov     byte ptr [rsi+18h], 1
0x1400074d1  mov     rax, [rsi]
0x1400074d4  cmp     rax, rsi
0x1400074d7  jz      loc_14000762A
0x1400074dd  mov     rcx, [rax]
0x1400074e0  cmp     [rcx+8], rax
0x1400074e4  jnz     loc_140007623
0x1400074ea  mov     rdx, [rax+8]
0x1400074ee  cmp     [rdx], rax
0x1400074f1  jnz     loc_140007623
0x1400074f7  mov     [rdx], rcx
0x1400074fa  lea     rbx, [rax-68h]
0x1400074fe  mov     [rcx+8], rdx
0x140007502  mov     [rax+8], rax
0x140007506  mov     [rax], rax
0x140007509  mov     eax, cs:dword_140013058
0x14000750f  cmp     eax, 5
0x140007512  jbe     short loc_140007538
0x140007514  mov     r9, [rbx+8]
0x140007518  lea     rax, aReferenceObjec; "Reference object"
0x14000751f  mov     r8, rbx
0x140007522  mov     [rsp+58h+var_38], rax
0x140007527  mov     edx, 33Dh
0x14000752c  lea     rcx, aCanceliosinque; "CancelIosInQueue"
0x140007533  call    HvsocketTraceReferenceCount
0x140007538  mov     eax, 1
0x14000753d  lock xadd [rbx+8], rax
0x140007543  inc     rax
0x140007546  cmp     rax, 1
0x14000754a  jg      short loc_140007553
0x14000754c  mov     ecx, 0Eh
0x140007551  int     29h; Win8: RtlFailFast(ecx)
0x140007553  mov     dl, dil; NewIrql
0x140007556  mov     rcx, rbp; SpinLock
0x140007559  call    cs:__imp_KeReleaseSpinLock
0x140007560  nop     dword ptr [rax+rax+00h]
0x140007565  mov     rcx, [rbx+0E0h]; Irp
0x14000756c  call    cs:__imp_IoCancelIrp
0x140007573  nop     dword ptr [rax+rax+00h]
0x140007578  mov     eax, cs:dword_140013058
0x14000757e  cmp     eax, 5
0x140007581  jbe     short loc_1400075A7
0x140007583  mov     r9, [rbx+8]
0x140007587  lea     rax, aDereferenceObj; "Dereference object"
0x14000758e  mov     r8, rbx
0x140007591  mov     [rsp+58h+var_38], rax
0x140007596  mov     edx, 343h
0x14000759b  lea     rcx, aCanceliosinque; "CancelIosInQueue"
0x1400075a2  call    HvsocketTraceReferenceCount
0x1400075a7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400075ab  lock xadd [rbx+8], rax
0x1400075b1  sub     rax, 1
0x1400075b5  jg      short loc_14000760C
0x1400075b7  test    rax, rax
0x1400075ba  jnz     short loc_140007605
0x1400075bc  mov     rax, [rbx+50h]
0x1400075c0  test    rax, rax
0x1400075c3  jz      short loc_1400075CD
0x1400075c5  mov     rcx, rbx
0x1400075c8  call    _guard_dispatch_icall
0x1400075cd  mov     ecx, [rbx+58h]
0x1400075d0  sub     ecx, 1
0x1400075d3  jz      short loc_1400075EF
0x1400075d5  cmp     ecx, 1
0x1400075d8  jnz     short loc_14000760C
0x1400075da  mov     rcx, [rbx+60h]; Lookaside
0x1400075de  mov     rdx, rbx; Entry
0x1400075e1  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400075e8  nop     dword ptr [rax+rax+00h]
0x1400075ed  jmp     short loc_14000760C
0x1400075ef  mov     edx, 69706E56h; Tag
0x1400075f4  mov     rcx, rbx; P
0x1400075f7  call    cs:__imp_ExFreePoolWithTag
0x1400075fe  nop     dword ptr [rax+rax+00h]
0x140007603  jmp     short loc_14000760C
0x140007605  mov     ecx, 0Eh
0x14000760a  int     29h; Win8: RtlFailFast(ecx)
0x14000760c  mov     rcx, rbp; SpinLock
0x14000760f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007616  nop     dword ptr [rax+rax+00h]
0x14000761b  mov     dil, al
0x14000761e  jmp     loc_1400074D1
0x140007623  mov     ecx, 3
0x140007628  int     29h; Win8: RtlFailFast(ecx)
0x14000762a  mov     dl, dil; NewIrql
0x14000762d  mov     rcx, rbp; SpinLock
0x140007630  call    cs:__imp_KeReleaseSpinLock
0x140007637  nop     dword ptr [rax+rax+00h]
0x14000763c  add     rsp, 38h
0x140007640  pop     rdi
0x140007641  pop     rsi
0x140007642  pop     rbp
0x140007643  pop     rbx
0x140007644  retn
```
