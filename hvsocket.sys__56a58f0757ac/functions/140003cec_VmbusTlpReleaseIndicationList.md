# VmbusTlpReleaseIndicationList

- ea: `0x140003cec`
- end: `0x140003ee0`
- name: `VmbusTlpReleaseIndicationList`
- size: `500`
- prototype: `void __fastcall(_QWORD *, _QWORD *, char)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14000309c`
- `0x1400036d0`
- `0x140005280`

## callees

- `0x140003034`
- `0x140003bc8`
- `0x140003cec`
- `0x14000a048`
- `0x14000bfe0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003d0a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003dd1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003d0a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003dd1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003d70`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003df0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003d70`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003df0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003ecb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003ecb`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140003eb5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140003eb5`

## pseudocode

```c
void __fastcall VmbusTlpReleaseIndicationList(_QWORD *a1, _QWORD *a2, char a3)
{
  KSPIN_LOCK *v3; // rbx
  KIRQL v7; // r9
  _QWORD *v8; // rax
  __int64 v9; // rdx
  _QWORD *v10; // rcx
  int v11; // r8d
  _QWORD *i; // rax
  __int64 v13; // rsi
  KIRQL v14; // bl
  _QWORD *j; // rcx
  signed __int64 v16; // rax
  bool v17; // cc
  signed __int64 v18; // rax
  void (__fastcall *v19)(__int64); // rax

  v3 = a1 + 93;
  v7 = KeAcquireSpinLockRaiseToDpc(a1 + 93);
  v8 = a2 + 5;
  v9 = a2[5];
  if ( *(_QWORD **)(v9 + 8) != a2 + 5 || (v10 = (_QWORD *)a2[6], (_QWORD *)*v10 != v8) )
    __fastfail(3u);
  *v10 = v9;
  *(_QWORD *)(v9 + 8) = v10;
  a2[6] = a2 + 5;
  *v8 = v8;
  if ( a3 )
  {
    v11 = 0;
    for ( i = a2; i; ++v11 )
      i = (_QWORD *)*i;
    a1[98] -= v11;
  }
  KeReleaseSpinLock(v3, v7);
  v13 = a1[92];
  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (const int *)"VmbusTlpReleaseIndicationList",
      295,
      a1[92],
      *(_QWORD *)(v13 + 8),
      (const int *)"Reference object");
  if ( _InterlockedIncrement64((volatile signed __int64 *)(v13 + 8)) <= 1 )
    __fastfail(0xEu);
  v14 = KeAcquireSpinLockRaiseToDpc(a1 + 9);
  VmbusTlDecrementIndicationCount(a1, a2);
  KeReleaseSpinLock(a1 + 9, v14);
  for ( j = a2; j; j = (_QWORD *)*j )
  {
    *((_DWORD *)j + 4) -= *((_DWORD *)j + 16);
    j[3] += j[8];
  }
  (*(void (__fastcall **)(__int64, _QWORD *, _QWORD *))(v13 + 152))(v13, a1, a2);
  VmbusTlpActivateDeliveryQueue((__int64)a1, 0);
  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (const int *)"VmbusTlpReleaseIndicationList",
      321,
      v13,
      *(_QWORD *)(v13 + 8),
      (const int *)"Dereference object");
  v16 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v13 + 8), 0xFFFFFFFFFFFFFFFFuLL);
  v17 = v16 <= 1;
  v18 = v16 - 1;
  if ( v17 )
  {
    if ( v18 )
      __fastfail(0xEu);
    v19 = *(void (__fastcall **)(__int64))(v13 + 80);
    if ( v19 )
      v19(v13);
    if ( *(_DWORD *)(v13 + 88) == 1 )
    {
      ExFreePoolWithTag((PVOID)v13, 0x69706E56u);
    }
    else if ( *(_DWORD *)(v13 + 88) == 2 )
    {
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v13 + 96), (PVOID)v13);
    }
  }
}

```

## disassembly

```asm
0x140003cec  push    rbx
0x140003cee  push    rbp
0x140003cef  push    rsi
0x140003cf0  push    rdi
0x140003cf1  push    r14
0x140003cf3  sub     rsp, 30h
0x140003cf7  lea     rbx, [rcx+2E8h]
0x140003cfe  mov     rbp, rcx
0x140003d01  mov     rcx, rbx; SpinLock
0x140003d04  mov     dil, r8b
0x140003d07  mov     r14, rdx
0x140003d0a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003d11  nop     dword ptr [rax+rax+00h]
0x140003d16  mov     r9b, al
0x140003d19  lea     rax, [r14+28h]
0x140003d1d  mov     rdx, [rax]
0x140003d20  cmp     [rdx+8], rax
0x140003d24  jnz     loc_140003ED9
0x140003d2a  mov     rcx, [rax+8]
0x140003d2e  cmp     [rcx], rax
0x140003d31  jnz     loc_140003ED9
0x140003d37  mov     [rcx], rdx
0x140003d3a  mov     [rdx+8], rcx
0x140003d3e  mov     [rax+8], rax
0x140003d42  mov     [rax], rax
0x140003d45  test    dil, dil
0x140003d48  jz      short loc_140003D6A
0x140003d4a  xor     r8d, r8d
0x140003d4d  mov     rax, r14
0x140003d50  test    r14, r14
0x140003d53  jz      short loc_140003D60
0x140003d55  mov     rax, [rax]
0x140003d58  inc     r8d
0x140003d5b  test    rax, rax
0x140003d5e  jnz     short loc_140003D55
0x140003d60  movsxd  rax, r8d
0x140003d63  sub     [rbp+310h], rax
0x140003d6a  mov     dl, r9b; NewIrql
0x140003d6d  mov     rcx, rbx; SpinLock
0x140003d70  call    cs:__imp_KeReleaseSpinLock
0x140003d77  nop     dword ptr [rax+rax+00h]
0x140003d7c  mov     eax, cs:dword_140013058
0x140003d82  mov     rsi, [rbp+2E0h]
0x140003d89  cmp     eax, 5
0x140003d8c  jbe     short loc_140003DB2
0x140003d8e  mov     r9, [rsi+8]
0x140003d92  lea     rax, aReferenceObjec; "Reference object"
0x140003d99  mov     r8, rsi
0x140003d9c  mov     [rsp+58h+var_38], rax
0x140003da1  mov     edx, 127h
0x140003da6  lea     rcx, aVmbustlpreleas; "VmbusTlpReleaseIndicationList"
0x140003dad  call    HvsocketTraceReferenceCount
0x140003db2  mov     eax, 1
0x140003db7  lock xadd [rsi+8], rax
0x140003dbd  inc     rax
0x140003dc0  cmp     rax, 1
0x140003dc4  jg      short loc_140003DCD
0x140003dc6  mov     ecx, 0Eh
0x140003dcb  int     29h; Win8: RtlFailFast(ecx)
0x140003dcd  lea     rcx, [rbp+48h]; SpinLock
0x140003dd1  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003dd8  nop     dword ptr [rax+rax+00h]
0x140003ddd  mov     rdx, r14
0x140003de0  mov     rcx, rbp
0x140003de3  mov     bl, al
0x140003de5  call    VmbusTlDecrementIndicationCount
0x140003dea  mov     dl, bl; NewIrql
0x140003dec  lea     rcx, [rbp+48h]; SpinLock
0x140003df0  call    cs:__imp_KeReleaseSpinLock
0x140003df7  nop     dword ptr [rax+rax+00h]
0x140003dfc  mov     rcx, r14
0x140003dff  test    r14, r14
0x140003e02  jz      short loc_140003E1A
0x140003e04  mov     eax, [rcx+40h]
0x140003e07  sub     [rcx+10h], eax
0x140003e0a  mov     rax, [rcx+40h]
0x140003e0e  add     [rcx+18h], rax
0x140003e12  mov     rcx, [rcx]
0x140003e15  test    rcx, rcx
0x140003e18  jnz     short loc_140003E04
0x140003e1a  mov     rax, [rsi+98h]
0x140003e21  mov     r8, r14
0x140003e24  mov     rdx, rbp
0x140003e27  mov     rcx, rsi
0x140003e2a  call    _guard_dispatch_icall
0x140003e2f  xor     edx, edx
0x140003e31  mov     rcx, rbp
0x140003e34  call    VmbusTlpActivateDeliveryQueue
0x140003e39  mov     eax, cs:dword_140013058
0x140003e3f  cmp     eax, 5
0x140003e42  jbe     short loc_140003E68
0x140003e44  mov     r9, [rsi+8]
0x140003e48  lea     rax, aDereferenceObj; "Dereference object"
0x140003e4f  mov     r8, rsi
0x140003e52  mov     [rsp+58h+var_38], rax
0x140003e57  mov     edx, 141h
0x140003e5c  lea     rcx, aVmbustlpreleas; "VmbusTlpReleaseIndicationList"
0x140003e63  call    HvsocketTraceReferenceCount
0x140003e68  or      rax, 0FFFFFFFFFFFFFFFFh
0x140003e6c  lock xadd [rsi+8], rax
0x140003e72  sub     rax, 1
0x140003e76  jg      short loc_140003E84
0x140003e78  test    rax, rax
0x140003e7b  jz      short loc_140003E90
0x140003e7d  mov     ecx, 0Eh
0x140003e82  int     29h; Win8: RtlFailFast(ecx)
0x140003e84  add     rsp, 30h
0x140003e88  pop     r14
0x140003e8a  pop     rdi
0x140003e8b  pop     rsi
0x140003e8c  pop     rbp
0x140003e8d  pop     rbx
0x140003e8e  retn
0x140003e90  mov     rax, [rsi+50h]
0x140003e94  test    rax, rax
0x140003e97  jz      short loc_140003EA1
0x140003e99  mov     rcx, rsi
0x140003e9c  call    _guard_dispatch_icall
0x140003ea1  mov     ecx, [rsi+58h]
0x140003ea4  sub     ecx, 1
0x140003ea7  jz      short loc_140003EC3
0x140003ea9  cmp     ecx, 1
0x140003eac  jnz     short loc_140003E84
0x140003eae  mov     rcx, [rsi+60h]; Lookaside
0x140003eb2  mov     rdx, rsi; Entry
0x140003eb5  call    cs:__imp_ExFreeToNPagedLookasideList
0x140003ebc  nop     dword ptr [rax+rax+00h]
0x140003ec1  jmp     short loc_140003E84
0x140003ec3  mov     edx, 69706E56h; Tag
0x140003ec8  mov     rcx, rsi; P
0x140003ecb  call    cs:__imp_ExFreePoolWithTag
0x140003ed2  nop     dword ptr [rax+rax+00h]
0x140003ed7  jmp     short loc_140003E84
0x140003ed9  mov     ecx, 3
0x140003ede  int     29h; Win8: RtlFailFast(ecx)
```
