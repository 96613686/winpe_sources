# HvSocketGetPendingOutboundConnectionFromPartition

- ea: `0x14001dcf8`
- end: `0x14001df13`
- name: `HvSocketGetPendingOutboundConnectionFromPartition`
- size: `539`
- prototype: `char __fastcall(__int64, __int64, const void *, __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, service_task`

## callers

- `0x14001bd20`
- `0x14002509c`
- `0x140025e9c`

## callees

- `0x14000a048`
- `0x14000bfe0`
- `0x14000c0a0`
- `0x14001dcf8`
- `0x140021ec0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001dd57`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001de5e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001dd57`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001de5e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001dd4b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001de52`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001dd4b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001de52`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001dee9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001dee9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001dd1d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001dd72`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001dd1d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001dd72`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001ded3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001ded3`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001dd2d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001dd82`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001dd2d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001dd82`

## pseudocode

```c
char __fastcall HvSocketGetPendingOutboundConnectionFromPartition(__int64 a1, __int64 a2, const void *a3, __int64 a4)
{
  __int64 v7; // rdi
  char v9; // r15
  _QWORD *v10; // r14
  _QWORD *v11; // rbx
  _QWORD *v12; // rsi
  _QWORD *v13; // rbp
  unsigned int v14; // eax
  signed __int64 v15; // rax
  bool v16; // cc
  signed __int64 v17; // rax
  void (__fastcall *v18)(__int64); // rax

  *(_QWORD *)a4 = 0;
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
  v7 = VmbusTlFindAndReferenceService(a1, a2);
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
  KeLeaveCriticalRegion();
  if ( !v7 )
    return 0;
  v9 = 0;
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v7 + 16));
  v10 = (_QWORD *)(v7 + 272);
  v11 = *(_QWORD **)(v7 + 272);
  v12 = v11;
  if ( v11 != (_QWORD *)(v7 + 272) )
  {
    while ( 1 )
    {
      v13 = v12 - 15;
      if ( !memcmp(v12 + 43, a3, 0x10u) )
        break;
      v12 = (_QWORD *)*v12;
      if ( v12 == v10 )
      {
        while ( 1 )
        {
          v13 = v11 - 15;
          if ( !memcmp(v11 + 43, &HV_GUID_ZERO, 0x10u) )
            goto LABEL_9;
          v11 = (_QWORD *)*v11;
          if ( v11 == v10 )
            goto LABEL_13;
        }
      }
    }
LABEL_9:
    v14 = dword_140013058;
    v9 = 1;
    *(_QWORD *)a4 = v13;
    if ( v14 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"HvSocketGetPendingOutboundConnectionFromPartition",
        1795,
        (_DWORD)v13,
        v13[1],
        (__int64)"Reference object");
    if ( _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)a4 + 8LL)) <= 1 )
      __fastfail(0xEu);
  }
LABEL_13:
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v7 + 16));
  KeLeaveCriticalRegion();
  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (unsigned int)"HvSocketGetPendingOutboundConnectionFromPartition",
      1802,
      v7,
      *(_QWORD *)(v7 + 8),
      (__int64)"Dereference object");
  v15 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v7 + 8), 0xFFFFFFFFFFFFFFFFuLL);
  v16 = v15 <= 1;
  v17 = v15 - 1;
  if ( v16 )
  {
    if ( v17 )
      __fastfail(0xEu);
    v18 = *(void (__fastcall **)(__int64))(v7 + 80);
    if ( v18 )
      v18(v7);
    if ( *(_DWORD *)(v7 + 88) == 1 )
    {
      ExFreePoolWithTag((PVOID)v7, 0x69706E56u);
    }
    else if ( *(_DWORD *)(v7 + 88) == 2 )
    {
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v7 + 96), (PVOID)v7);
    }
  }
  return v9;
}

```

## disassembly

```asm
0x14001dcf8  mov     [rsp+Buf2], r8
0x14001dcfd  push    rbx
0x14001dcfe  push    rbp
0x14001dcff  push    rsi
0x14001dd00  push    rdi
0x14001dd01  push    r12
0x14001dd03  push    r13
0x14001dd05  push    r14
0x14001dd07  push    r15
0x14001dd09  sub     rsp, 38h
0x14001dd0d  mov     r12, r9
0x14001dd10  mov     qword ptr [r9], 0
0x14001dd17  mov     rdi, rdx
0x14001dd1a  mov     rsi, rcx
0x14001dd1d  call    cs:__imp_KeEnterCriticalRegion
0x14001dd24  nop     dword ptr [rax+rax+00h]
0x14001dd29  lea     rcx, [rsi+10h]; FastMutex
0x14001dd2d  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14001dd34  nop     dword ptr [rax+rax+00h]
0x14001dd39  mov     rdx, rdi
0x14001dd3c  mov     rcx, rsi
0x14001dd3f  call    VmbusTlFindAndReferenceService
0x14001dd44  lea     rcx, [rsi+10h]; FastMutex
0x14001dd48  mov     rdi, rax
0x14001dd4b  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14001dd52  nop     dword ptr [rax+rax+00h]
0x14001dd57  call    cs:__imp_KeLeaveCriticalRegion
0x14001dd5e  nop     dword ptr [rax+rax+00h]
0x14001dd63  test    rdi, rdi
0x14001dd66  jnz     short loc_14001DD6F
0x14001dd68  xor     al, al
0x14001dd6a  jmp     loc_14001DF01
0x14001dd6f  xor     r15b, r15b
0x14001dd72  call    cs:__imp_KeEnterCriticalRegion
0x14001dd79  nop     dword ptr [rax+rax+00h]
0x14001dd7e  lea     rcx, [rdi+10h]; FastMutex
0x14001dd82  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14001dd89  nop     dword ptr [rax+rax+00h]
0x14001dd8e  lea     r14, [rdi+110h]
0x14001dd95  mov     rbx, [r14]
0x14001dd98  mov     rsi, rbx
0x14001dd9b  cmp     rbx, r14
0x14001dd9e  jz      loc_14001DE4E
0x14001dda4  mov     rdx, [rsp+78h+Buf2]; Buf2
0x14001ddac  lea     rbp, [rsi-78h]
0x14001ddb0  lea     rcx, [rbp+1D0h]; Buf1
0x14001ddb7  mov     r8d, 10h; Size
0x14001ddbd  call    memcmp
0x14001ddc2  test    eax, eax
0x14001ddc4  jz      short loc_14001DDF9
0x14001ddc6  mov     rsi, [rsi]
0x14001ddc9  cmp     rsi, r14
0x14001ddcc  jnz     short loc_14001DDA4
0x14001ddce  lea     rbp, [rbx-78h]
0x14001ddd2  mov     r8d, 10h; Size
0x14001ddd8  lea     rcx, [rbp+1D0h]; Buf1
0x14001dddf  lea     rdx, HV_GUID_ZERO; Buf2
0x14001dde6  call    memcmp
0x14001ddeb  test    eax, eax
0x14001dded  jz      short loc_14001DDF9
0x14001ddef  mov     rbx, [rbx]
0x14001ddf2  cmp     rbx, r14
0x14001ddf5  jnz     short loc_14001DDCE
0x14001ddf7  jmp     short loc_14001DE4E
0x14001ddf9  mov     eax, cs:dword_140013058
0x14001ddff  mov     r15b, 1
0x14001de02  mov     [r12], rbp
0x14001de06  cmp     eax, 5
0x14001de09  jbe     short loc_14001DE2F
0x14001de0b  mov     r9, [rbp+8]
0x14001de0f  lea     rax, aReferenceObjec; "Reference object"
0x14001de16  mov     r8, rbp
0x14001de19  mov     [rsp+78h+var_58], rax
0x14001de1e  mov     edx, 703h
0x14001de23  lea     rcx, aHvsocketgetpen_0; "HvSocketGetPendingOutboundConnectionFro"...
0x14001de2a  call    HvsocketTraceReferenceCount
0x14001de2f  mov     rax, [r12]
0x14001de33  mov     edx, 1
0x14001de38  lock xadd [rax+8], rdx
0x14001de3e  inc     rdx
0x14001de41  cmp     rdx, 1
0x14001de45  jg      short loc_14001DE4E
0x14001de47  mov     ecx, 0Eh
0x14001de4c  int     29h; Win8: RtlFailFast(ecx)
0x14001de4e  lea     rcx, [rdi+10h]; FastMutex
0x14001de52  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14001de59  nop     dword ptr [rax+rax+00h]
0x14001de5e  call    cs:__imp_KeLeaveCriticalRegion
0x14001de65  nop     dword ptr [rax+rax+00h]
0x14001de6a  mov     eax, cs:dword_140013058
0x14001de70  cmp     eax, 5
0x14001de73  jbe     short loc_14001DE99
0x14001de75  mov     r9, [rdi+8]
0x14001de79  lea     rax, aDereferenceObj; "Dereference object"
0x14001de80  mov     r8, rdi
0x14001de83  mov     [rsp+78h+var_58], rax
0x14001de88  mov     edx, 70Ah
0x14001de8d  lea     rcx, aHvsocketgetpen_0; "HvSocketGetPendingOutboundConnectionFro"...
0x14001de94  call    HvsocketTraceReferenceCount
0x14001de99  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001de9d  lock xadd [rdi+8], rax
0x14001dea3  sub     rax, 1
0x14001dea7  jg      short loc_14001DEFE
0x14001dea9  test    rax, rax
0x14001deac  jnz     short loc_14001DEF7
0x14001deae  mov     rax, [rdi+50h]
0x14001deb2  test    rax, rax
0x14001deb5  jz      short loc_14001DEBF
0x14001deb7  mov     rcx, rdi
0x14001deba  call    _guard_dispatch_icall
0x14001debf  mov     ecx, [rdi+58h]
0x14001dec2  sub     ecx, 1
0x14001dec5  jz      short loc_14001DEE1
0x14001dec7  cmp     ecx, 1
0x14001deca  jnz     short loc_14001DEFE
0x14001decc  mov     rcx, [rdi+60h]; Lookaside
0x14001ded0  mov     rdx, rdi; Entry
0x14001ded3  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001deda  nop     dword ptr [rax+rax+00h]
0x14001dedf  jmp     short loc_14001DEFE
0x14001dee1  mov     edx, 69706E56h; Tag
0x14001dee6  mov     rcx, rdi; P
0x14001dee9  call    cs:__imp_ExFreePoolWithTag
0x14001def0  nop     dword ptr [rax+rax+00h]
0x14001def5  jmp     short loc_14001DEFE
0x14001def7  mov     ecx, 0Eh
0x14001defc  int     29h; Win8: RtlFailFast(ecx)
0x14001defe  mov     al, r15b
0x14001df01  add     rsp, 38h
0x14001df05  pop     r15
0x14001df07  pop     r14
0x14001df09  pop     r13
0x14001df0b  pop     r12
0x14001df0d  pop     rdi
0x14001df0e  pop     rsi
0x14001df0f  pop     rbp
0x14001df10  pop     rbx
0x14001df11  retn
```
