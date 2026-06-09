# VmbusTlXPartRootCancelConnect

- ea: `0x14000add0`
- end: `0x14000af20`
- name: `VmbusTlXPartRootCancelConnect`
- size: `336`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x14000a048`
- `0x14000add0`
- `0x14000bfe0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000ade8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000ade8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ae53`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ae53`
- `ntoskrnl!IoCancelIrp` at `0x14000ae6c`
- `ntoskrnl!IoCancelIrp` at `0x14000ae6c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000af08`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000af08`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000aef2`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000aef2`

## pseudocode

```c
__int64 __fastcall VmbusTlXPartRootCancelConnect(__int64 a1)
{
  KSPIN_LOCK *v1; // rsi
  unsigned int v3; // edi
  KIRQL v4; // al
  __int64 v5; // rbx
  KIRQL v6; // bp
  signed __int64 v7; // rax
  bool v8; // cc
  signed __int64 v9; // rax
  void (__fastcall *v10)(__int64); // rax

  v1 = (KSPIN_LOCK *)(a1 + 72);
  v3 = -1073741823;
  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 72));
  v5 = *(_QWORD *)(a1 + 688);
  v6 = v4;
  if ( v5 )
  {
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"VmbusTlXPartRootCancelConnect",
        420,
        v5,
        *(_QWORD *)(v5 + 8),
        (__int64)"Reference object");
    if ( _InterlockedIncrement64((volatile signed __int64 *)(v5 + 8)) <= 1 )
      __fastfail(0xEu);
  }
  KeReleaseSpinLock(v1, v6);
  if ( v5 )
  {
    v3 = IoCancelIrp(*(PIRP *)(v5 + 96)) != 0 ? 0 : 0xC0000001;
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"VmbusTlXPartRootCancelConnect",
        431,
        v5,
        *(_QWORD *)(v5 + 8),
        (__int64)"Dereference object");
    v7 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v5 + 8), 0xFFFFFFFFFFFFFFFFuLL);
    v8 = v7 <= 1;
    v9 = v7 - 1;
    if ( v8 )
    {
      if ( v9 )
        __fastfail(0xEu);
      v10 = *(void (__fastcall **)(__int64))(v5 + 80);
      if ( v10 )
        v10(v5);
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
  return v3;
}

```

## disassembly

```asm
0x14000add0  push    rbx
0x14000add2  push    rbp
0x14000add3  push    rsi
0x14000add4  push    rdi
0x14000add5  sub     rsp, 38h
0x14000add9  lea     rsi, [rcx+48h]
0x14000addd  mov     rbx, rcx
0x14000ade0  mov     rcx, rsi; SpinLock
0x14000ade3  mov     edi, 0C0000001h
0x14000ade8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000adef  nop     dword ptr [rax+rax+00h]
0x14000adf4  mov     rbx, [rbx+2B0h]
0x14000adfb  mov     bpl, al
0x14000adfe  test    rbx, rbx
0x14000ae01  jz      short loc_14000AE4D
0x14000ae03  mov     eax, cs:dword_140013058
0x14000ae09  cmp     eax, 5
0x14000ae0c  jbe     short loc_14000AE32
0x14000ae0e  mov     r9, [rbx+8]
0x14000ae12  lea     rax, aReferenceObjec; "Reference object"
0x14000ae19  mov     r8, rbx
0x14000ae1c  mov     [rsp+58h+var_38], rax
0x14000ae21  mov     edx, 1A4h
0x14000ae26  lea     rcx, aVmbustlxpartro_1; "VmbusTlXPartRootCancelConnect"
0x14000ae2d  call    HvsocketTraceReferenceCount
0x14000ae32  mov     eax, 1
0x14000ae37  lock xadd [rbx+8], rax
0x14000ae3d  inc     rax
0x14000ae40  cmp     rax, 1
0x14000ae44  jg      short loc_14000AE4D
0x14000ae46  mov     ecx, 0Eh
0x14000ae4b  int     29h; Win8: RtlFailFast(ecx)
0x14000ae4d  mov     dl, bpl; NewIrql
0x14000ae50  mov     rcx, rsi; SpinLock
0x14000ae53  call    cs:__imp_KeReleaseSpinLock
0x14000ae5a  nop     dword ptr [rax+rax+00h]
0x14000ae5f  test    rbx, rbx
0x14000ae62  jz      loc_14000AF14
0x14000ae68  mov     rcx, [rbx+60h]; Irp
0x14000ae6c  call    cs:__imp_IoCancelIrp
0x14000ae73  nop     dword ptr [rax+rax+00h]
0x14000ae78  neg     al
0x14000ae7a  mov     eax, cs:dword_140013058
0x14000ae80  sbb     ecx, ecx
0x14000ae82  not     ecx
0x14000ae84  and     edi, ecx
0x14000ae86  cmp     eax, 5
0x14000ae89  jbe     short loc_14000AEAF
0x14000ae8b  mov     r9, [rbx+8]
0x14000ae8f  lea     rax, aDereferenceObj; "Dereference object"
0x14000ae96  mov     r8, rbx
0x14000ae99  mov     [rsp+58h+var_38], rax
0x14000ae9e  mov     edx, 1AFh
0x14000aea3  lea     rcx, aVmbustlxpartro_1; "VmbusTlXPartRootCancelConnect"
0x14000aeaa  call    HvsocketTraceReferenceCount
0x14000aeaf  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000aeb3  lock xadd [rbx+8], rax
0x14000aeb9  sub     rax, 1
0x14000aebd  jg      short loc_14000AF14
0x14000aebf  test    rax, rax
0x14000aec2  jz      short loc_14000AECD
0x14000aec4  mov     ecx, 0Eh
0x14000aec9  int     29h; Win8: RtlFailFast(ecx)
0x14000aecb  jmp     short loc_14000AF14
0x14000aecd  mov     rax, [rbx+50h]
0x14000aed1  test    rax, rax
0x14000aed4  jz      short loc_14000AEDE
0x14000aed6  mov     rcx, rbx
0x14000aed9  call    _guard_dispatch_icall
0x14000aede  mov     ecx, [rbx+58h]
0x14000aee1  sub     ecx, 1
0x14000aee4  jz      short loc_14000AF00
0x14000aee6  cmp     ecx, 1
0x14000aee9  jnz     short loc_14000AF14
0x14000aeeb  mov     rcx, [rbx+60h]; Lookaside
0x14000aeef  mov     rdx, rbx; Entry
0x14000aef2  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000aef9  nop     dword ptr [rax+rax+00h]
0x14000aefe  jmp     short loc_14000AF14
0x14000af00  mov     edx, 69706E56h; Tag
0x14000af05  mov     rcx, rbx; P
0x14000af08  call    cs:__imp_ExFreePoolWithTag
0x14000af0f  nop     dword ptr [rax+rax+00h]
0x14000af14  mov     eax, edi
0x14000af16  add     rsp, 38h
0x14000af1a  pop     rdi
0x14000af1b  pop     rsi
0x14000af1c  pop     rbp
0x14000af1d  pop     rbx
0x14000af1e  retn
```
