# VmbusTlLoopbackDisconnect

- ea: `0x140006000`
- end: `0x140006219`
- name: `VmbusTlLoopbackDisconnect`
- size: `537`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140001fa0`
- `0x140006000`
- `0x14000a048`
- `0x14000bfe0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006030`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400060a9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006030`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400060a9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006069`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400060c1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006069`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400060c1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140006085`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140006085`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140006079`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140006079`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000615e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400061ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000615e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400061ff`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140006010`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140006010`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140006148`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400061e9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140006148`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400061e9`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140006020`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140006020`

## pseudocode

```c
void __fastcall VmbusTlLoopbackDisconnect(__int64 a1)
{
  KIRQL v2; // al
  __int64 v3; // rsi
  __int64 v4; // rbp
  KIRQL v5; // al
  int v6; // ebx
  __int64 v7; // rax
  void (__fastcall *v8)(__int64); // rax
  __int64 v9; // rax
  void (__fastcall *v10)(__int64); // rax

  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
  v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 72));
  v3 = *(_QWORD *)(a1 + 696);
  *(_QWORD *)(a1 + 696) = 0;
  if ( v3 )
  {
    v4 = *(_QWORD *)(v3 + 104);
    *(_QWORD *)(v3 + 104) = 0;
  }
  else
  {
    v4 = 0;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 72), v2);
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
  KeLeaveCriticalRegion();
  if ( v4 )
  {
    v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 72));
    v6 = *(_DWORD *)(v4 + 524);
    KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 72), v5);
    if ( v6 != 19 )
      VmbusTlCommonCancelConnection((PVOID)v4);
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"VmbusTlLoopbackDisconnect",
        496,
        v4,
        *(_QWORD *)(v4 + 8),
        (__int64)"Dereference object");
    v7 = _InterlockedDecrement64((volatile signed __int64 *)(v4 + 8));
    if ( v7 <= 0 )
    {
      if ( v7 )
        __fastfail(0xEu);
      v8 = *(void (__fastcall **)(__int64))(v4 + 80);
      if ( v8 )
        v8(v4);
      if ( *(_DWORD *)(v4 + 88) == 1 )
      {
        ExFreePoolWithTag((PVOID)v4, 0x69706E56u);
      }
      else if ( *(_DWORD *)(v4 + 88) == 2 )
      {
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v4 + 96), (PVOID)v4);
      }
    }
  }
  else
  {
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 112) + 1280LL));
  }
  if ( v3 )
  {
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"VmbusTlLoopbackDisconnect",
        505,
        v3,
        *(_QWORD *)(v3 + 8),
        (__int64)"Dereference object");
    v9 = _InterlockedDecrement64((volatile signed __int64 *)(v3 + 8));
    if ( v9 <= 0 )
    {
      if ( v9 )
        __fastfail(0xEu);
      v10 = *(void (__fastcall **)(__int64))(v3 + 80);
      if ( v10 )
        v10(v3);
      if ( *(_DWORD *)(v3 + 88) == 1 )
      {
        ExFreePoolWithTag((PVOID)v3, 0x69706E56u);
      }
      else if ( *(_DWORD *)(v3 + 88) == 2 )
      {
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v3 + 96), (PVOID)v3);
      }
    }
  }
}

```

## disassembly

```asm
0x140006000  push    rbx
0x140006002  push    rbp
0x140006003  push    rsi
0x140006004  push    rdi
0x140006005  push    r13
0x140006007  push    r14
0x140006009  sub     rsp, 38h
0x14000600d  mov     rbx, rcx
0x140006010  call    cs:__imp_KeEnterCriticalRegion
0x140006017  nop     dword ptr [rax+rax+00h]
0x14000601c  lea     rcx, [rbx+10h]; FastMutex
0x140006020  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140006027  nop     dword ptr [rax+rax+00h]
0x14000602c  lea     rcx, [rbx+48h]; SpinLock
0x140006030  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140006037  nop     dword ptr [rax+rax+00h]
0x14000603c  mov     rsi, [rbx+2B8h]
0x140006043  mov     qword ptr [rbx+2B8h], 0
0x14000604e  test    rsi, rsi
0x140006051  jz      short loc_140006061
0x140006053  mov     rbp, [rsi+68h]
0x140006057  mov     qword ptr [rsi+68h], 0
0x14000605f  jmp     short loc_140006063
0x140006061  xor     ebp, ebp
0x140006063  mov     dl, al; NewIrql
0x140006065  lea     rcx, [rbx+48h]; SpinLock
0x140006069  call    cs:__imp_KeReleaseSpinLock
0x140006070  nop     dword ptr [rax+rax+00h]
0x140006075  lea     rcx, [rbx+10h]; FastMutex
0x140006079  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140006080  nop     dword ptr [rax+rax+00h]
0x140006085  call    cs:__imp_KeLeaveCriticalRegion
0x14000608c  nop     dword ptr [rax+rax+00h]
0x140006091  or      r14, 0FFFFFFFFFFFFFFFFh
0x140006095  lea     r13, aDereferenceObj; "Dereference object"
0x14000609c  test    rbp, rbp
0x14000609f  jz      loc_14000616C
0x1400060a5  lea     rcx, [rbp+48h]; SpinLock
0x1400060a9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400060b0  nop     dword ptr [rax+rax+00h]
0x1400060b5  mov     ebx, [rbp+20Ch]
0x1400060bb  lea     rcx, [rbp+48h]; SpinLock
0x1400060bf  mov     dl, al; NewIrql
0x1400060c1  call    cs:__imp_KeReleaseSpinLock
0x1400060c8  nop     dword ptr [rax+rax+00h]
0x1400060cd  cmp     ebx, 13h
0x1400060d0  jz      short loc_1400060DF
0x1400060d2  mov     r8b, 1
0x1400060d5  xor     edx, edx
0x1400060d7  mov     rcx, rbp
0x1400060da  call    VmbusTlCommonCancelConnection
0x1400060df  mov     eax, cs:dword_140013058
0x1400060e5  cmp     eax, 5
0x1400060e8  jbe     short loc_140006107
0x1400060ea  mov     r9, [rbp+8]
0x1400060ee  lea     rcx, aVmbustlloopbac_4; "VmbusTlLoopbackDisconnect"
0x1400060f5  mov     r8, rbp
0x1400060f8  mov     [rsp+68h+var_48], r13
0x1400060fd  mov     edx, 1F0h
0x140006102  call    HvsocketTraceReferenceCount
0x140006107  mov     rax, r14
0x14000610a  lock xadd [rbp+8], rax
0x140006110  add     rax, r14
0x140006113  test    rax, rax
0x140006116  jg      short loc_140006177
0x140006118  jz      short loc_140006123
0x14000611a  mov     ecx, 0Eh
0x14000611f  int     29h; Win8: RtlFailFast(ecx)
0x140006121  jmp     short loc_140006177
0x140006123  mov     rax, [rbp+50h]
0x140006127  test    rax, rax
0x14000612a  jz      short loc_140006134
0x14000612c  mov     rcx, rbp
0x14000612f  call    _guard_dispatch_icall
0x140006134  mov     ecx, [rbp+58h]
0x140006137  sub     ecx, 1
0x14000613a  jz      short loc_140006156
0x14000613c  cmp     ecx, 1
0x14000613f  jnz     short loc_140006177
0x140006141  mov     rcx, [rbp+60h]; Lookaside
0x140006145  mov     rdx, rbp; Entry
0x140006148  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000614f  nop     dword ptr [rax+rax+00h]
0x140006154  jmp     short loc_140006177
0x140006156  mov     edx, 69706E56h; Tag
0x14000615b  mov     rcx, rbp; P
0x14000615e  call    cs:__imp_ExFreePoolWithTag
0x140006165  nop     dword ptr [rax+rax+00h]
0x14000616a  jmp     short loc_140006177
0x14000616c  mov     rax, [rbx+70h]
0x140006170  lock inc dword ptr [rax+500h]
0x140006177  test    rsi, rsi
0x14000617a  jz      loc_14000620B
0x140006180  mov     eax, cs:dword_140013058
0x140006186  cmp     eax, 5
0x140006189  jbe     short loc_1400061A8
0x14000618b  mov     r9, [rsi+8]
0x14000618f  lea     rcx, aVmbustlloopbac_4; "VmbusTlLoopbackDisconnect"
0x140006196  mov     r8, rsi
0x140006199  mov     [rsp+68h+var_48], r13
0x14000619e  mov     edx, 1F9h
0x1400061a3  call    HvsocketTraceReferenceCount
0x1400061a8  mov     rax, r14
0x1400061ab  lock xadd [rsi+8], rax
0x1400061b1  add     rax, r14
0x1400061b4  test    rax, rax
0x1400061b7  jg      short loc_14000620B
0x1400061b9  jz      short loc_1400061C4
0x1400061bb  mov     ecx, 0Eh
0x1400061c0  int     29h; Win8: RtlFailFast(ecx)
0x1400061c2  jmp     short loc_14000620B
0x1400061c4  mov     rax, [rsi+50h]
0x1400061c8  test    rax, rax
0x1400061cb  jz      short loc_1400061D5
0x1400061cd  mov     rcx, rsi
0x1400061d0  call    _guard_dispatch_icall
0x1400061d5  mov     ecx, [rsi+58h]
0x1400061d8  sub     ecx, 1
0x1400061db  jz      short loc_1400061F7
0x1400061dd  cmp     ecx, 1
0x1400061e0  jnz     short loc_14000620B
0x1400061e2  mov     rcx, [rsi+60h]; Lookaside
0x1400061e6  mov     rdx, rsi; Entry
0x1400061e9  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400061f0  nop     dword ptr [rax+rax+00h]
0x1400061f5  jmp     short loc_14000620B
0x1400061f7  mov     edx, 69706E56h; Tag
0x1400061fc  mov     rcx, rsi; P
0x1400061ff  call    cs:__imp_ExFreePoolWithTag
0x140006206  nop     dword ptr [rax+rax+00h]
0x14000620b  add     rsp, 38h
0x14000620f  pop     r14
0x140006211  pop     r13
0x140006213  pop     rdi
0x140006214  pop     rsi
0x140006215  pop     rbp
0x140006216  pop     rbx
0x140006217  retn
```
