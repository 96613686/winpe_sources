# HvSocketGetPendingInboundConnection

- ea: `0x14001d728`
- end: `0x14001da9a`
- name: `HvSocketGetPendingInboundConnection`
- size: `882`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x14001b578`

## callees

- `0x140006f1c`
- `0x14000a048`
- `0x14000bfe0`
- `0x14000c0a0`
- `0x14001d728`
- `0x14001daa0`
- `0x14001f540`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001d7f1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001da72`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001d7f1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001da72`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001d7e5`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001da66`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001d7e5`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001da66`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d8a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001da3d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d8a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001da3d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001d7b3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001d8c6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001d7b3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001d8c6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001d890`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001da27`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001d890`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001da27`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001d7c6`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001d8de`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001d7c6`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001d8de`

## pseudocode

```c
char __fastcall HvSocketGetPendingInboundConnection(__int64 a1, _OWORD *a2, __int64 a3, __int64 a4, __int64 a5)
{
  char PendingInboundConnectionFromPartition; // bp
  __int64 v10; // rax
  struct _FAST_MUTEX *v11; // rcx
  __int64 v12; // rdi
  signed __int64 v13; // rax
  bool v14; // cc
  signed __int64 v15; // rax
  void (__fastcall *v16)(__int64); // rax
  _QWORD *v17; // r14
  _QWORD *v18; // rbx
  signed __int64 v19; // rax
  signed __int64 v20; // rax
  void (__fastcall *v21)(_QWORD *); // rax
  PFAST_MUTEX FastMutex[9]; // [rsp+30h] [rbp-48h] BYREF

  PendingInboundConnectionFromPartition = 0;
  if ( !memcmp(a2, &HV_GUID_ZERO, 0x10u) || !memcmp(a2, &HV_GUID_CHILDREN, 0x10u) )
  {
    KeEnterCriticalRegion();
    FastMutex[0] = (PFAST_MUTEX)(a1 + 16);
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
    v17 = *(_QWORD **)(a1 + 128);
    do
    {
      if ( v17 == (_QWORD *)(a1 + 128) )
        break;
      v18 = v17 - 27;
      if ( (unsigned int)dword_140013058 > 5 )
        HvsocketTraceReferenceCount(
          (unsigned int)"HvSocketGetPendingInboundConnection",
          1546,
          (_DWORD)v17 - 216,
          v18[1],
          (__int64)"Reference object");
      if ( _InterlockedIncrement64(v18 + 1) <= 1 )
        __fastfail(0xEu);
      if ( (!memcmp(a2, &HV_GUID_ZERO, 0x10u) || memcmp(v18 + 29, &HV_GUID_PARENT, 0x10u))
        && (unsigned __int8)HvSocketGetPendingInboundConnectionFromPartition(v17 - 27, a3, a4, a5) )
      {
        PendingInboundConnectionFromPartition = 1;
      }
      if ( (unsigned int)dword_140013058 > 5 )
        HvsocketTraceReferenceCount(
          (unsigned int)"HvSocketGetPendingInboundConnection",
          1563,
          (_DWORD)v17 - 216,
          v18[1],
          (__int64)"Dereference object");
      v19 = _InterlockedExchangeAdd64(v18 + 1, 0xFFFFFFFFFFFFFFFFuLL);
      v14 = v19 <= 1;
      v20 = v19 - 1;
      if ( v14 )
      {
        if ( v20 )
          __fastfail(0xEu);
        v21 = (void (__fastcall *)(_QWORD *))v18[10];
        if ( v21 )
          v21(v17 - 27);
        if ( *((_DWORD *)v18 + 22) == 1 )
        {
          ExFreePoolWithTag(v17 - 27, 0x69706E56u);
        }
        else if ( *((_DWORD *)v18 + 22) == 2 )
        {
          ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)v18[12], v17 - 27);
        }
      }
      v17 = (_QWORD *)*v17;
    }
    while ( !PendingInboundConnectionFromPartition );
    ExReleaseFastMutexUnsafe(FastMutex[0]);
    KeLeaveCriticalRegion();
  }
  else
  {
    *(_OWORD *)FastMutex = 0;
    if ( !(unsigned __int8)VmbusTlMapSystemIdToPartitionId(a1, a2, FastMutex) )
      *(_OWORD *)FastMutex = *a2;
    KeEnterCriticalRegion();
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
    v10 = VmbusTlFindAndReferencePartition(a1, FastMutex);
    v11 = (struct _FAST_MUTEX *)(a1 + 16);
    v12 = v10;
    ExReleaseFastMutexUnsafe(v11);
    KeLeaveCriticalRegion();
    if ( v12 )
    {
      PendingInboundConnectionFromPartition = HvSocketGetPendingInboundConnectionFromPartition(v12, a3, a4, a5);
      if ( (unsigned int)dword_140013058 > 5 )
        HvsocketTraceReferenceCount(
          (unsigned int)"HvSocketGetPendingInboundConnection",
          1591,
          v12,
          *(_QWORD *)(v12 + 8),
          (__int64)"Dereference object");
      v13 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v12 + 8), 0xFFFFFFFFFFFFFFFFuLL);
      v14 = v13 <= 1;
      v15 = v13 - 1;
      if ( v14 )
      {
        if ( v15 )
          __fastfail(0xEu);
        v16 = *(void (__fastcall **)(__int64))(v12 + 80);
        if ( v16 )
          v16(v12);
        if ( *(_DWORD *)(v12 + 88) == 1 )
        {
          ExFreePoolWithTag((PVOID)v12, 0x69706E56u);
        }
        else if ( *(_DWORD *)(v12 + 88) == 2 )
        {
          ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v12 + 96), (PVOID)v12);
        }
      }
    }
  }
  return PendingInboundConnectionFromPartition;
}

```

## disassembly

```asm
0x14001d728  mov     [rsp+arg_0], rbx
0x14001d72d  mov     [rsp+arg_18], r9
0x14001d732  mov     [rsp+arg_10], r8
0x14001d737  push    rbp
0x14001d738  push    rsi
0x14001d739  push    rdi
0x14001d73a  push    r12
0x14001d73c  push    r13
0x14001d73e  push    r14
0x14001d740  push    r15
0x14001d742  sub     rsp, 40h
0x14001d746  mov     rsi, rdx
0x14001d749  mov     r15, r8
0x14001d74c  mov     rdi, rcx
0x14001d74f  lea     rdx, HV_GUID_ZERO; Buf2
0x14001d756  mov     ebx, 10h
0x14001d75b  mov     rcx, rsi; Buf1
0x14001d75e  mov     r8d, ebx; Size
0x14001d761  mov     r14, r9
0x14001d764  xor     bpl, bpl
0x14001d767  call    memcmp
0x14001d76c  test    eax, eax
0x14001d76e  jz      loc_14001D8C6
0x14001d774  mov     r8d, ebx; Size
0x14001d777  lea     rdx, HV_GUID_CHILDREN; Buf2
0x14001d77e  mov     rcx, rsi; Buf1
0x14001d781  call    memcmp
0x14001d786  test    eax, eax
0x14001d788  jz      loc_14001D8C6
0x14001d78e  xorps   xmm0, xmm0
0x14001d791  lea     r8, [rsp+78h+FastMutex]
0x14001d796  mov     rdx, rsi
0x14001d799  mov     rcx, rdi
0x14001d79c  movups  xmmword ptr [rsp+78h+FastMutex], xmm0
0x14001d7a1  call    VmbusTlMapSystemIdToPartitionId
0x14001d7a6  test    al, al
0x14001d7a8  jnz     short loc_14001D7B3
0x14001d7aa  movups  xmm0, xmmword ptr [rsi]
0x14001d7ad  movdqu  xmmword ptr [rsp+78h+FastMutex], xmm0
0x14001d7b3  call    cs:__imp_KeEnterCriticalRegion
0x14001d7ba  nop     dword ptr [rax+rax+00h]
0x14001d7bf  lea     rbx, [rdi+10h]
0x14001d7c3  mov     rcx, rbx; FastMutex
0x14001d7c6  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14001d7cd  nop     dword ptr [rax+rax+00h]
0x14001d7d2  lea     rdx, [rsp+78h+FastMutex]
0x14001d7d7  mov     rcx, rdi
0x14001d7da  call    VmbusTlFindAndReferencePartition
0x14001d7df  mov     rcx, rbx; FastMutex
0x14001d7e2  mov     rdi, rax
0x14001d7e5  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14001d7ec  nop     dword ptr [rax+rax+00h]
0x14001d7f1  call    cs:__imp_KeLeaveCriticalRegion
0x14001d7f8  nop     dword ptr [rax+rax+00h]
0x14001d7fd  test    rdi, rdi
0x14001d800  jz      loc_14001DA7E
0x14001d806  mov     r9, [rsp+78h+arg_20]
0x14001d80e  mov     r8, r14
0x14001d811  mov     rdx, r15
0x14001d814  mov     rcx, rdi
0x14001d817  call    HvSocketGetPendingInboundConnectionFromPartition
0x14001d81c  mov     ecx, cs:dword_140013058
0x14001d822  mov     bpl, al
0x14001d825  cmp     ecx, 5
0x14001d828  jbe     short loc_14001D84E
0x14001d82a  mov     r9, [rdi+8]
0x14001d82e  lea     r15, aDereferenceObj; "Dereference object"
0x14001d835  mov     r8, rdi
0x14001d838  mov     [rsp+78h+var_58], r15
0x14001d83d  mov     edx, 637h
0x14001d842  lea     rcx, aHvsocketgetpen_1; "HvSocketGetPendingInboundConnection"
0x14001d849  call    HvsocketTraceReferenceCount
0x14001d84e  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001d852  lock xadd [rdi+8], rax
0x14001d858  sub     rax, 1
0x14001d85c  jg      loc_14001DA7E
0x14001d862  test    rax, rax
0x14001d865  jnz     short loc_14001D8BA
0x14001d867  mov     rax, [rdi+50h]
0x14001d86b  test    rax, rax
0x14001d86e  jz      short loc_14001D878
0x14001d870  mov     rcx, rdi
0x14001d873  call    _guard_dispatch_icall
0x14001d878  mov     ecx, [rdi+58h]
0x14001d87b  sub     ecx, 1
0x14001d87e  jz      short loc_14001D8A1
0x14001d880  cmp     ecx, 1
0x14001d883  jnz     loc_14001DA7E
0x14001d889  mov     rcx, [rdi+60h]; Lookaside
0x14001d88d  mov     rdx, rdi; Entry
0x14001d890  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001d897  nop     dword ptr [rax+rax+00h]
0x14001d89c  jmp     loc_14001DA7E
0x14001d8a1  mov     edx, 69706E56h; Tag
0x14001d8a6  mov     rcx, rdi; P
0x14001d8a9  call    cs:__imp_ExFreePoolWithTag
0x14001d8b0  nop     dword ptr [rax+rax+00h]
0x14001d8b5  jmp     loc_14001DA7E
0x14001d8ba  mov     ecx, 0Eh
0x14001d8bf  int     29h; Win8: RtlFailFast(ecx)
0x14001d8c1  jmp     loc_14001DA7E
0x14001d8c6  call    cs:__imp_KeEnterCriticalRegion
0x14001d8cd  nop     dword ptr [rax+rax+00h]
0x14001d8d2  lea     r12, [rdi+10h]
0x14001d8d6  mov     rcx, r12; FastMutex
0x14001d8d9  mov     [rsp+78h+FastMutex], r12
0x14001d8de  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14001d8e5  nop     dword ptr [rax+rax+00h]
0x14001d8ea  mov     r12, [rsp+78h+arg_18]
0x14001d8f2  lea     r13, [rdi+80h]
0x14001d8f9  mov     r14, [r13+0]
0x14001d8fd  lea     r15, aDereferenceObj; "Dereference object"
0x14001d904  mov     edi, 0Eh
0x14001d909  lea     ecx, [rdi-0Dh]
0x14001d90c  cmp     r14, r13
0x14001d90f  jz      loc_14001DA61
0x14001d915  mov     eax, cs:dword_140013058
0x14001d91b  lea     rbx, [r14-0D8h]
0x14001d922  cmp     eax, 5
0x14001d925  jbe     short loc_14001D950
0x14001d927  mov     r9, [rbx+8]
0x14001d92b  lea     rax, aReferenceObjec; "Reference object"
0x14001d932  mov     r8, rbx
0x14001d935  mov     [rsp+78h+var_58], rax
0x14001d93a  mov     edx, 60Ah
0x14001d93f  lea     rcx, aHvsocketgetpen_1; "HvSocketGetPendingInboundConnection"
0x14001d946  call    HvsocketTraceReferenceCount
0x14001d94b  mov     ecx, 1
0x14001d950  mov     rax, rcx
0x14001d953  lock xadd [rbx+8], rax
0x14001d959  add     rax, rcx
0x14001d95c  cmp     rax, rcx
0x14001d95f  jg      short loc_14001D966
0x14001d961  mov     rcx, rdi
0x14001d964  int     29h; Win8: RtlFailFast(ecx)
0x14001d966  mov     r8d, 10h; Size
0x14001d96c  lea     rdx, HV_GUID_ZERO; Buf2
0x14001d973  mov     rcx, rsi; Buf1
0x14001d976  call    memcmp
0x14001d97b  test    eax, eax
0x14001d97d  jz      short loc_14001D99C
0x14001d97f  lea     rcx, [rbx+0E8h]; Buf1
0x14001d986  mov     r8d, 10h; Size
0x14001d98c  lea     rdx, HV_GUID_PARENT; Buf2
0x14001d993  call    memcmp
0x14001d998  test    eax, eax
0x14001d99a  jz      short loc_14001D9C5
0x14001d99c  mov     r9, [rsp+78h+arg_20]
0x14001d9a4  mov     r8, r12
0x14001d9a7  mov     rdx, [rsp+78h+arg_10]
0x14001d9af  mov     rcx, rbx
0x14001d9b2  call    HvSocketGetPendingInboundConnectionFromPartition
0x14001d9b7  test    al, al
0x14001d9b9  movzx   ebp, bpl
0x14001d9bd  mov     eax, 1
0x14001d9c2  cmovnz  ebp, eax
0x14001d9c5  mov     eax, cs:dword_140013058
0x14001d9cb  cmp     eax, 5
0x14001d9ce  jbe     short loc_14001D9ED
0x14001d9d0  mov     r9, [rbx+8]
0x14001d9d4  lea     rcx, aHvsocketgetpen_1; "HvSocketGetPendingInboundConnection"
0x14001d9db  mov     r8, rbx
0x14001d9de  mov     [rsp+78h+var_58], r15
0x14001d9e3  mov     edx, 61Bh
0x14001d9e8  call    HvsocketTraceReferenceCount
0x14001d9ed  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001d9f1  lock xadd [rbx+8], rax
0x14001d9f7  sub     rax, 1
0x14001d9fb  jg      short loc_14001DA50
0x14001d9fd  test    rax, rax
0x14001da00  jnz     short loc_14001DA4B
0x14001da02  mov     rax, [rbx+50h]
0x14001da06  test    rax, rax
0x14001da09  jz      short loc_14001DA13
0x14001da0b  mov     rcx, rbx
0x14001da0e  call    _guard_dispatch_icall
0x14001da13  mov     ecx, [rbx+58h]
0x14001da16  sub     ecx, 1
0x14001da19  jz      short loc_14001DA35
0x14001da1b  cmp     ecx, 1
0x14001da1e  jnz     short loc_14001DA50
0x14001da20  mov     rcx, [rbx+60h]; Lookaside
0x14001da24  mov     rdx, rbx; Entry
0x14001da27  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001da2e  nop     dword ptr [rax+rax+00h]
0x14001da33  jmp     short loc_14001DA50
0x14001da35  mov     edx, 69706E56h; Tag
0x14001da3a  mov     rcx, rbx; P
0x14001da3d  call    cs:__imp_ExFreePoolWithTag
0x14001da44  nop     dword ptr [rax+rax+00h]
0x14001da49  jmp     short loc_14001DA50
0x14001da4b  mov     rcx, rdi
0x14001da4e  int     29h; Win8: RtlFailFast(ecx)
0x14001da50  mov     r14, [r14]
0x14001da53  mov     ecx, 1
0x14001da58  test    bpl, bpl
0x14001da5b  jz      loc_14001D90C
0x14001da61  mov     rcx, [rsp+78h+FastMutex]; FastMutex
0x14001da66  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14001da6d  nop     dword ptr [rax+rax+00h]
0x14001da72  call    cs:__imp_KeLeaveCriticalRegion
0x14001da79  nop     dword ptr [rax+rax+00h]
0x14001da7e  mov     rbx, [rsp+78h+arg_0]
0x14001da86  mov     al, bpl
0x14001da89  add     rsp, 40h
0x14001da8d  pop     r15
0x14001da8f  pop     r14
0x14001da91  pop     r13
0x14001da93  pop     r12
0x14001da95  pop     rdi
0x14001da96  pop     rsi
0x14001da97  pop     rbp
0x14001da98  retn
```
