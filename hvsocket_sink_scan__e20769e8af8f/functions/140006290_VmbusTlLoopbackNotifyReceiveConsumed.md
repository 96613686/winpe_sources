# VmbusTlLoopbackNotifyReceiveConsumed

- ea: `0x140006290`
- end: `0x1400063b3`
- name: `VmbusTlLoopbackNotifyReceiveConsumed`
- size: `291`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x1400049a0`
- `0x140006290`
- `0x140006448`
- `0x14000975c`
- `0x14000a048`
- `0x14000bfe0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400062df`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400062df`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006307`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006307`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000639b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000639b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140006385`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140006385`

## pseudocode

```c
__int64 __fastcall VmbusTlLoopbackNotifyReceiveConsumed(__int64 a1)
{
  __int64 v2; // rax
  __int64 v3; // rbp
  __int64 v5; // rdi
  KIRQL v6; // al
  KIRQL v7; // bl
  signed __int64 v8; // rax
  bool v9; // cc
  signed __int64 v10; // rax
  void (__fastcall *v11)(__int64); // rax

  v2 = VmbusTlLoopbackReferenceEndpointDeliveryQueue();
  v3 = v2;
  if ( v2 )
  {
    v5 = *(_QWORD *)(v2 + 104);
    v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v5 + 72));
    *(_DWORD *)(v5 + 528) |= 4u;
    v7 = v6;
    VmbusTlTransitionDisconnectState(v5, 3);
    KeReleaseSpinLock((PKSPIN_LOCK)(v5 + 72), v7);
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"VmbusTlLoopbackNotifyReceiveConsumed",
        534,
        v3,
        *(_QWORD *)(v3 + 8),
        (__int64)"Dereference object");
    v8 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v3 + 8), 0xFFFFFFFFFFFFFFFFuLL);
    v9 = v8 <= 1;
    v10 = v8 - 1;
    if ( v9 )
    {
      if ( v10 )
        __fastfail(0xEu);
      v11 = *(void (__fastcall **)(__int64))(v3 + 80);
      if ( v11 )
        v11(v3);
      if ( *(_DWORD *)(v3 + 88) == 1 )
      {
        ExFreePoolWithTag((PVOID)v3, 0x69706E56u);
      }
      else if ( *(_DWORD *)(v3 + 88) == 2 )
      {
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v3 + 96), (PVOID)v3);
      }
    }
    return 0;
  }
  else
  {
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceEndpointError("VmbusTlLoopbackNotifyReceiveConsumed", 525, 3221225860LL, a1);
    return 3221225860LL;
  }
}

```

## disassembly

```asm
0x140006290  push    rbx
0x140006292  push    rbp
0x140006293  push    rsi
0x140006294  push    rdi
0x140006295  sub     rsp, 38h
0x140006299  mov     rbx, rcx
0x14000629c  call    VmbusTlLoopbackReferenceEndpointDeliveryQueue
0x1400062a1  mov     rbp, rax
0x1400062a4  test    rax, rax
0x1400062a7  jnz     short loc_1400062D7
0x1400062a9  mov     edx, cs:dword_140013058
0x1400062af  mov     edi, 0C0000184h
0x1400062b4  cmp     edx, 2
0x1400062b7  jbe     short loc_1400062D0
0x1400062b9  mov     r9, rbx
0x1400062bc  lea     rcx, aVmbustlloopbac_1; "VmbusTlLoopbackNotifyReceiveConsumed"
0x1400062c3  mov     r8d, edi
0x1400062c6  mov     edx, 20Dh
0x1400062cb  call    HvsocketTraceEndpointError
0x1400062d0  mov     eax, edi
0x1400062d2  jmp     loc_1400063A9
0x1400062d7  mov     rdi, [rax+68h]
0x1400062db  lea     rcx, [rdi+48h]; SpinLock
0x1400062df  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400062e6  nop     dword ptr [rax+rax+00h]
0x1400062eb  or      dword ptr [rdi+210h], 4
0x1400062f2  mov     edx, 3
0x1400062f7  mov     rcx, rdi
0x1400062fa  mov     bl, al
0x1400062fc  call    VmbusTlTransitionDisconnectState
0x140006301  mov     dl, bl; NewIrql
0x140006303  lea     rcx, [rdi+48h]; SpinLock
0x140006307  call    cs:__imp_KeReleaseSpinLock
0x14000630e  nop     dword ptr [rax+rax+00h]
0x140006313  mov     eax, cs:dword_140013058
0x140006319  cmp     eax, 5
0x14000631c  jbe     short loc_140006342
0x14000631e  mov     r9, [rbp+8]
0x140006322  lea     rax, aDereferenceObj; "Dereference object"
0x140006329  mov     r8, rbp
0x14000632c  mov     [rsp+58h+var_38], rax
0x140006331  mov     edx, 216h
0x140006336  lea     rcx, aVmbustlloopbac_1; "VmbusTlLoopbackNotifyReceiveConsumed"
0x14000633d  call    HvsocketTraceReferenceCount
0x140006342  or      rax, 0FFFFFFFFFFFFFFFFh
0x140006346  lock xadd [rbp+8], rax
0x14000634c  sub     rax, 1
0x140006350  jg      short loc_1400063A7
0x140006352  test    rax, rax
0x140006355  jz      short loc_140006360
0x140006357  mov     ecx, 0Eh
0x14000635c  int     29h; Win8: RtlFailFast(ecx)
0x14000635e  jmp     short loc_1400063A7
0x140006360  mov     rax, [rbp+50h]
0x140006364  test    rax, rax
0x140006367  jz      short loc_140006371
0x140006369  mov     rcx, rbp
0x14000636c  call    _guard_dispatch_icall
0x140006371  mov     ecx, [rbp+58h]
0x140006374  sub     ecx, 1
0x140006377  jz      short loc_140006393
0x140006379  cmp     ecx, 1
0x14000637c  jnz     short loc_1400063A7
0x14000637e  mov     rcx, [rbp+60h]; Lookaside
0x140006382  mov     rdx, rbp; Entry
0x140006385  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000638c  nop     dword ptr [rax+rax+00h]
0x140006391  jmp     short loc_1400063A7
0x140006393  mov     edx, 69706E56h; Tag
0x140006398  mov     rcx, rbp; P
0x14000639b  call    cs:__imp_ExFreePoolWithTag
0x1400063a2  nop     dword ptr [rax+rax+00h]
0x1400063a7  xor     eax, eax
0x1400063a9  add     rsp, 38h
0x1400063ad  pop     rdi
0x1400063ae  pop     rsi
0x1400063af  pop     rbp
0x1400063b0  pop     rbx
0x1400063b1  retn
```
