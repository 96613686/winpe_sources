# HvSocketXboxRootCancelConnect

- ea: `0x14000b390`
- end: `0x14000b518`
- name: `HvSocketXboxRootCancelConnect`
- size: `392`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x1400098f4`
- `0x14000a048`
- `0x14000b390`
- `0x14000bfe0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b3a7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b3a7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b413`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b413`
- `ntoskrnl!IoCancelIrp` at `0x14000b42c`
- `ntoskrnl!IoCancelIrp` at `0x14000b42c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b4cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b4cb`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b4b5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b4b5`

## pseudocode

```c
__int64 __fastcall HvSocketXboxRootCancelConnect(__int64 a1)
{
  unsigned int v2; // edi
  KIRQL v3; // al
  __int64 v4; // rbx
  KIRQL v5; // r14
  BOOLEAN v6; // bp
  signed __int64 v7; // rax
  bool v8; // cc
  signed __int64 v9; // rax
  void (__fastcall *v10)(__int64); // rax

  v2 = -1073741823;
  v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 72));
  v4 = *(_QWORD *)(a1 + 688);
  v5 = v3;
  if ( v4 )
  {
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"HvSocketXboxRootCancelConnect",
        392,
        *(_QWORD *)(a1 + 688),
        *(_QWORD *)(v4 + 8),
        (__int64)"Reference object");
    if ( _InterlockedIncrement64((volatile signed __int64 *)(v4 + 8)) <= 1 )
      __fastfail(0xEu);
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 72), v5);
  if ( !v4 )
    goto LABEL_19;
  v6 = IoCancelIrp(*(PIRP *)(v4 + 96));
  v2 = v6 != 0 ? 0 : 0xC0000001;
  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (unsigned int)"HvSocketXboxRootCancelConnect",
      403,
      v4,
      *(_QWORD *)(v4 + 8),
      (__int64)"Dereference object");
  v7 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v4 + 8), 0xFFFFFFFFFFFFFFFFuLL);
  v8 = v7 <= 1;
  v9 = v7 - 1;
  if ( v8 )
  {
    if ( v9 )
      __fastfail(0xEu);
    v10 = *(void (__fastcall **)(__int64))(v4 + 80);
    if ( v10 )
      v10(v4);
    if ( *(_DWORD *)(v4 + 88) == 1 )
    {
      ExFreePoolWithTag((PVOID)v4, 0x69706E56u);
    }
    else if ( *(_DWORD *)(v4 + 88) == 2 )
    {
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v4 + 96), (PVOID)v4);
    }
  }
  if ( !v6 )
  {
LABEL_19:
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceEndpointGuidError((unsigned int)"HvSocketXboxRootCancelConnect", 408, v2, a1, a1 + 140);
  }
  return v2;
}

```

## disassembly

```asm
0x14000b390  push    rbx
0x14000b392  push    rbp
0x14000b393  push    rsi
0x14000b394  push    rdi
0x14000b395  push    r14
0x14000b397  sub     rsp, 30h
0x14000b39b  mov     rsi, rcx
0x14000b39e  mov     edi, 0C0000001h
0x14000b3a3  add     rcx, 48h ; 'H'; SpinLock
0x14000b3a7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000b3ae  nop     dword ptr [rax+rax+00h]
0x14000b3b3  mov     rbx, [rsi+2B0h]
0x14000b3ba  mov     r14b, al
0x14000b3bd  test    rbx, rbx
0x14000b3c0  jz      short loc_14000B40C
0x14000b3c2  mov     eax, cs:dword_140013058
0x14000b3c8  cmp     eax, 5
0x14000b3cb  jbe     short loc_14000B3F1
0x14000b3cd  mov     r9, [rbx+8]
0x14000b3d1  lea     rax, aReferenceObjec; "Reference object"
0x14000b3d8  mov     r8, rbx
0x14000b3db  mov     [rsp+58h+var_38], rax
0x14000b3e0  mov     edx, 188h
0x14000b3e5  lea     rcx, aHvsocketxboxro; "HvSocketXboxRootCancelConnect"
0x14000b3ec  call    HvsocketTraceReferenceCount
0x14000b3f1  mov     eax, 1
0x14000b3f6  lock xadd [rbx+8], rax
0x14000b3fc  inc     rax
0x14000b3ff  cmp     rax, 1
0x14000b403  jg      short loc_14000B40C
0x14000b405  mov     ecx, 0Eh
0x14000b40a  int     29h; Win8: RtlFailFast(ecx)
0x14000b40c  mov     dl, r14b; NewIrql
0x14000b40f  lea     rcx, [rsi+48h]; SpinLock
0x14000b413  call    cs:__imp_KeReleaseSpinLock
0x14000b41a  nop     dword ptr [rax+rax+00h]
0x14000b41f  test    rbx, rbx
0x14000b422  jz      loc_14000B4DC
0x14000b428  mov     rcx, [rbx+60h]; Irp
0x14000b42c  call    cs:__imp_IoCancelIrp
0x14000b433  nop     dword ptr [rax+rax+00h]
0x14000b438  mov     bpl, al
0x14000b43b  neg     al
0x14000b43d  mov     eax, cs:dword_140013058
0x14000b443  sbb     ecx, ecx
0x14000b445  not     ecx
0x14000b447  and     edi, ecx
0x14000b449  cmp     eax, 5
0x14000b44c  jbe     short loc_14000B472
0x14000b44e  mov     r9, [rbx+8]
0x14000b452  lea     rax, aDereferenceObj; "Dereference object"
0x14000b459  mov     r8, rbx
0x14000b45c  mov     [rsp+58h+var_38], rax
0x14000b461  mov     edx, 193h
0x14000b466  lea     rcx, aHvsocketxboxro; "HvSocketXboxRootCancelConnect"
0x14000b46d  call    HvsocketTraceReferenceCount
0x14000b472  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000b476  lock xadd [rbx+8], rax
0x14000b47c  sub     rax, 1
0x14000b480  jg      short loc_14000B4D7
0x14000b482  test    rax, rax
0x14000b485  jz      short loc_14000B490
0x14000b487  mov     ecx, 0Eh
0x14000b48c  int     29h; Win8: RtlFailFast(ecx)
0x14000b48e  jmp     short loc_14000B4D7
0x14000b490  mov     rax, [rbx+50h]
0x14000b494  test    rax, rax
0x14000b497  jz      short loc_14000B4A1
0x14000b499  mov     rcx, rbx
0x14000b49c  call    _guard_dispatch_icall
0x14000b4a1  mov     ecx, [rbx+58h]
0x14000b4a4  sub     ecx, 1
0x14000b4a7  jz      short loc_14000B4C3
0x14000b4a9  cmp     ecx, 1
0x14000b4ac  jnz     short loc_14000B4D7
0x14000b4ae  mov     rcx, [rbx+60h]; Lookaside
0x14000b4b2  mov     rdx, rbx; Entry
0x14000b4b5  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000b4bc  nop     dword ptr [rax+rax+00h]
0x14000b4c1  jmp     short loc_14000B4D7
0x14000b4c3  mov     edx, 69706E56h; Tag
0x14000b4c8  mov     rcx, rbx; P
0x14000b4cb  call    cs:__imp_ExFreePoolWithTag
0x14000b4d2  nop     dword ptr [rax+rax+00h]
0x14000b4d7  test    bpl, bpl
0x14000b4da  jnz     short loc_14000B50A
0x14000b4dc  mov     edx, cs:dword_140013058
0x14000b4e2  cmp     edx, 2
0x14000b4e5  jbe     short loc_14000B50A
0x14000b4e7  lea     rdx, [rsi+8Ch]
0x14000b4ee  mov     r9, rsi
0x14000b4f1  mov     [rsp+58h+var_38], rdx
0x14000b4f6  lea     rcx, aHvsocketxboxro; "HvSocketXboxRootCancelConnect"
0x14000b4fd  mov     edx, 198h
0x14000b502  mov     r8d, edi
0x14000b505  call    HvsocketTraceEndpointGuidError
0x14000b50a  mov     eax, edi
0x14000b50c  add     rsp, 30h
0x14000b510  pop     r14
0x14000b512  pop     rdi
0x14000b513  pop     rsi
0x14000b514  pop     rbp
0x14000b515  pop     rbx
0x14000b516  retn
```
