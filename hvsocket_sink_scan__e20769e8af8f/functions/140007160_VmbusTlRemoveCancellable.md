# VmbusTlRemoveCancellable

- ea: `0x140007160`
- end: `0x140007274`
- name: `VmbusTlRemoveCancellable`
- size: `276`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140001ba0`
- `0x1400023b0`

## callees

- `0x140007160`
- `0x14000a048`
- `0x14000bfe0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000717e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000717e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007255`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007255`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000723a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000723a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140007224`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140007224`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140007199`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140007199`

## string_xrefs

- `0x1400071d5`: `VmbusTlRemoveCancellable`

## pseudocode

```c
__int64 __fastcall VmbusTlRemoveCancellable(__int64 a1, __int64 a2)
{
  KSPIN_LOCK *v2; // rdi
  KIRQL v4; // si
  __int64 v5; // rbx
  signed __int64 v6; // rax
  bool v7; // cc
  signed __int64 v8; // rax
  void (__fastcall *v9)(__int64); // rax
  unsigned int v10; // ebx
  __int64 Buffer; // [rsp+48h] [rbp+10h] BYREF

  Buffer = a2;
  v2 = (KSPIN_LOCK *)(a1 + 72);
  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 72));
  if ( RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)(a1 + 1016), &Buffer) )
  {
    v5 = Buffer;
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"VmbusTlRemoveCancellable",
        724,
        Buffer,
        *(_QWORD *)(Buffer + 8),
        (__int64)"Dereference object");
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
    v10 = 0;
  }
  else
  {
    v10 = -1073741275;
  }
  KeReleaseSpinLock(v2, v4);
  return v10;
}

```

## disassembly

```asm
0x140007160  mov     [rsp+arg_0], rbx
0x140007165  mov     [rsp+arg_10], rsi
0x14000716a  mov     [rsp+Buffer], rdx
0x14000716f  push    rdi
0x140007170  sub     rsp, 30h
0x140007174  lea     rdi, [rcx+48h]
0x140007178  mov     rbx, rcx
0x14000717b  mov     rcx, rdi; SpinLock
0x14000717e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007185  nop     dword ptr [rax+rax+00h]
0x14000718a  lea     rcx, [rbx+3F8h]; Table
0x140007191  mov     sil, al
0x140007194  lea     rdx, [rsp+38h+Buffer]; Buffer
0x140007199  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1400071a0  nop     dword ptr [rax+rax+00h]
0x1400071a5  test    al, al
0x1400071a7  jz      loc_14000724A
0x1400071ad  mov     ecx, cs:dword_140013058
0x1400071b3  mov     rbx, [rsp+38h+Buffer]
0x1400071b8  cmp     ecx, 5
0x1400071bb  jbe     short loc_1400071E1
0x1400071bd  mov     r9, [rbx+8]
0x1400071c1  lea     rax, aDereferenceObj; "Dereference object"
0x1400071c8  mov     r8, rbx
0x1400071cb  mov     [rsp+38h+var_18], rax
0x1400071d0  mov     edx, 2D4h
0x1400071d5  lea     rcx, aVmbustlremovec; "VmbusTlRemoveCancellable"
0x1400071dc  call    HvsocketTraceReferenceCount
0x1400071e1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400071e5  lock xadd [rbx+8], rax
0x1400071eb  sub     rax, 1
0x1400071ef  jg      short loc_140007246
0x1400071f1  test    rax, rax
0x1400071f4  jz      short loc_1400071FF
0x1400071f6  mov     ecx, 0Eh
0x1400071fb  int     29h; Win8: RtlFailFast(ecx)
0x1400071fd  jmp     short loc_140007246
0x1400071ff  mov     rax, [rbx+50h]
0x140007203  test    rax, rax
0x140007206  jz      short loc_140007210
0x140007208  mov     rcx, rbx
0x14000720b  call    _guard_dispatch_icall
0x140007210  mov     ecx, [rbx+58h]
0x140007213  sub     ecx, 1
0x140007216  jz      short loc_140007232
0x140007218  cmp     ecx, 1
0x14000721b  jnz     short loc_140007246
0x14000721d  mov     rcx, [rbx+60h]; Lookaside
0x140007221  mov     rdx, rbx; Entry
0x140007224  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000722b  nop     dword ptr [rax+rax+00h]
0x140007230  jmp     short loc_140007246
0x140007232  mov     edx, 69706E56h; Tag
0x140007237  mov     rcx, rbx; P
0x14000723a  call    cs:__imp_ExFreePoolWithTag
0x140007241  nop     dword ptr [rax+rax+00h]
0x140007246  xor     ebx, ebx
0x140007248  jmp     short loc_14000724F
0x14000724a  mov     ebx, 0C0000225h
0x14000724f  mov     dl, sil; NewIrql
0x140007252  mov     rcx, rdi; SpinLock
0x140007255  call    cs:__imp_KeReleaseSpinLock
0x14000725c  nop     dword ptr [rax+rax+00h]
0x140007261  mov     rsi, [rsp+38h+arg_10]
0x140007266  mov     eax, ebx
0x140007268  mov     rbx, [rsp+38h+arg_0]
0x14000726d  add     rsp, 30h
0x140007271  pop     rdi
0x140007272  retn
```
