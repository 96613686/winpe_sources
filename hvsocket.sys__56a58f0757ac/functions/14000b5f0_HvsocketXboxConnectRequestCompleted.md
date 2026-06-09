# HvsocketXboxConnectRequestCompleted

- ea: `0x14000b5f0`
- end: `0x14000b725`
- name: `HvsocketXboxConnectRequestCompleted`
- size: `309`
- prototype: `__int64 __fastcall(__int64, __int64, KSPIN_LOCK *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400263d0`

## callees

- `0x1400023b0`
- `0x14000a048`
- `0x14000b5f0`
- `0x14000bfe0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b610`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b610`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b63f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b63f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b6dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b6dc`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b6c6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b6c6`

## string_xrefs

- `0x14000b677`: `HvsocketXboxConnectRequestCompleted`

## pseudocode

```c
__int64 __fastcall HvsocketXboxConnectRequestCompleted(__int64 a1, __int64 a2, KSPIN_LOCK *a3)
{
  KIRQL v4; // al
  __int64 v5; // rdi
  signed __int64 v6; // rax
  bool v7; // cc
  signed __int64 v8; // rax
  void (__fastcall *v9)(__int64); // rax

  v4 = KeAcquireSpinLockRaiseToDpc(a3 + 9);
  v5 = a3[86];
  a3[86] = 0;
  KeReleaseSpinLock(a3 + 9, v4);
  if ( v5 )
  {
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (const int *)"HvsocketXboxConnectRequestCompleted",
        350,
        v5,
        *(_QWORD *)(v5 + 8),
        (const int *)"Dereference object");
    v6 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v5 + 8), 0xFFFFFFFFFFFFFFFFuLL);
    v7 = v6 <= 1;
    v8 = v6 - 1;
    if ( v7 )
    {
      if ( v8 )
        __fastfail(0xEu);
      v9 = *(void (__fastcall **)(__int64))(v5 + 80);
      if ( v9 )
        v9(v5);
      if ( *(_DWORD *)(v5 + 88) == 1 )
      {
        ExFreePoolWithTag((PVOID)v5, 0x69706E56u);
      }
      else if ( *(_DWORD *)(v5 + 88) == 2 )
      {
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v5 + 96), (PVOID)v5);
      }
    }
  }
  VmbusTlConnectComplete(a3);
  return 3221225494LL;
}

```

## disassembly

```asm
0x14000b5f0  mov     [rsp+arg_0], rbx
0x14000b5f5  mov     [rsp+arg_10], rbp
0x14000b5fa  push    rsi
0x14000b5fb  push    rdi
0x14000b5fc  push    r14
0x14000b5fe  sub     rsp, 30h
0x14000b602  mov     esi, [rdx+30h]
0x14000b605  lea     rcx, [r8+48h]; SpinLock
0x14000b609  mov     [rsp+48h+arg_8], esi
0x14000b60d  mov     rbp, r8
0x14000b610  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000b617  nop     dword ptr [rax+rax+00h]
0x14000b61c  mov     r14b, [rbp+204h]
0x14000b623  lea     rcx, [rbp+48h]; SpinLock
0x14000b627  mov     rdi, [rbp+2B0h]
0x14000b62e  mov     dl, al; NewIrql
0x14000b630  mov     qword ptr [rbp+2B0h], 0
0x14000b63b  and     r14b, 1
0x14000b63f  call    cs:__imp_KeReleaseSpinLock
0x14000b646  nop     dword ptr [rax+rax+00h]
0x14000b64b  test    rdi, rdi
0x14000b64e  jz      loc_14000B6E8
0x14000b654  mov     eax, cs:dword_140013058
0x14000b65a  cmp     eax, 5
0x14000b65d  jbe     short loc_14000B683
0x14000b65f  mov     r9, [rdi+8]
0x14000b663  lea     rax, aDereferenceObj; "Dereference object"
0x14000b66a  mov     r8, rdi
0x14000b66d  mov     [rsp+48h+var_28], rax
0x14000b672  mov     edx, 15Eh
0x14000b677  lea     rcx, aHvsocketxboxco; "HvsocketXboxConnectRequestCompleted"
0x14000b67e  call    HvsocketTraceReferenceCount
0x14000b683  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000b687  lock xadd [rdi+8], rax
0x14000b68d  sub     rax, 1
0x14000b691  jg      short loc_14000B6E8
0x14000b693  test    rax, rax
0x14000b696  jz      short loc_14000B6A1
0x14000b698  mov     ecx, 0Eh
0x14000b69d  int     29h; Win8: RtlFailFast(ecx)
0x14000b69f  jmp     short loc_14000B6E8
0x14000b6a1  mov     rax, [rdi+50h]
0x14000b6a5  test    rax, rax
0x14000b6a8  jz      short loc_14000B6B2
0x14000b6aa  mov     rcx, rdi
0x14000b6ad  call    _guard_dispatch_icall
0x14000b6b2  mov     ecx, [rdi+58h]
0x14000b6b5  sub     ecx, 1
0x14000b6b8  jz      short loc_14000B6D4
0x14000b6ba  cmp     ecx, 1
0x14000b6bd  jnz     short loc_14000B6E8
0x14000b6bf  mov     rcx, [rdi+60h]; Lookaside
0x14000b6c3  mov     rdx, rdi; Entry
0x14000b6c6  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000b6cd  nop     dword ptr [rax+rax+00h]
0x14000b6d2  jmp     short loc_14000B6E8
0x14000b6d4  mov     edx, 69706E56h; Tag
0x14000b6d9  mov     rcx, rdi; P
0x14000b6dc  call    cs:__imp_ExFreePoolWithTag
0x14000b6e3  nop     dword ptr [rax+rax+00h]
0x14000b6e8  test    r14b, r14b
0x14000b6eb  jz      short loc_14000B6FF
0x14000b6ed  cmp     esi, 0C0000120h
0x14000b6f3  mov     eax, 0C00000B5h
0x14000b6f8  cmovz   esi, eax
0x14000b6fb  mov     [rsp+48h+arg_8], esi
0x14000b6ff  lea     rdx, [rsp+48h+arg_8]
0x14000b704  mov     rcx, rbp; P
0x14000b707  call    VmbusTlConnectComplete
0x14000b70c  mov     rbx, [rsp+48h+arg_0]
0x14000b711  mov     eax, 0C0000016h
0x14000b716  mov     rbp, [rsp+48h+arg_10]
0x14000b71b  add     rsp, 30h
0x14000b71f  pop     r14
0x14000b721  pop     rdi
0x14000b722  pop     rsi
0x14000b723  retn
```
