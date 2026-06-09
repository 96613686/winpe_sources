# HvSocketXboxProcessConnectResult

- ea: `0x140025e9c`
- end: `0x140026079`
- name: `HvSocketXboxProcessConnectResult`
- size: `477`
- prototype: `void __fastcall(__int64 P, __int64, const void *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140023890`

## callees

- `0x140001ac8`
- `0x1400023b0`
- `0x14000a048`
- `0x14000bfe0`
- `0x14001dcf8`
- `0x140025e9c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140025fd0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026059`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025fd0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026059`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140025fba`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140026043`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140025fba`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140026043`

## pseudocode

```c
void __fastcall HvSocketXboxProcessConnectResult(__int64 P, __int64 a2, const void *a3, int a4)
{
  PVOID v7; // rdi
  __int64 v8; // rax
  void (__fastcall *v9)(PVOID); // rax
  __int64 v10; // rax
  void (__fastcall *v11)(__int64); // rax
  PVOID Entry; // [rsp+50h] [rbp+8h] BYREF
  int v13; // [rsp+68h] [rbp+20h]

  v13 = a4;
  Entry = 0;
  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (const int *)"HvSocketXboxProcessConnectResult",
      1034,
      P,
      *(_QWORD *)(P + 8),
      (const int *)"Reference object");
  if ( _InterlockedIncrement64((volatile signed __int64 *)(P + 8)) <= 1 )
    __fastfail(0xEu);
  if ( HvSocketGetPendingOutboundConnectionFromPartition(P, a2, a3, (__int64)&Entry) )
  {
    v7 = Entry;
    if ( HvSocketBeginProcessingConnection((__int64)Entry) )
      VmbusTlConnectComplete(v7);
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (const int *)"HvSocketXboxProcessConnectResult",
        1050,
        (__int64)v7,
        *((_QWORD *)v7 + 1),
        (const int *)"Dereference object");
    v8 = _InterlockedDecrement64((volatile signed __int64 *)v7 + 1);
    if ( v8 <= 0 )
    {
      if ( v8 )
        __fastfail(0xEu);
      v9 = (void (__fastcall *)(PVOID))*((_QWORD *)v7 + 10);
      if ( v9 )
        v9(v7);
      if ( *((_DWORD *)v7 + 22) == 1 )
      {
        ExFreePoolWithTag(v7, 0x69706E56u);
      }
      else if ( *((_DWORD *)v7 + 22) == 2 )
      {
        ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v7 + 12), v7);
      }
    }
  }
  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (const int *)"HvSocketXboxProcessConnectResult",
      1053,
      P,
      *(_QWORD *)(P + 8),
      (const int *)"Dereference object");
  v10 = _InterlockedDecrement64((volatile signed __int64 *)(P + 8));
  if ( v10 <= 0 )
  {
    if ( v10 )
      __fastfail(0xEu);
    v11 = *(void (__fastcall **)(__int64))(P + 80);
    if ( v11 )
      v11(P);
    if ( *(_DWORD *)(P + 88) == 1 )
    {
      ExFreePoolWithTag((PVOID)P, 0x69706E56u);
    }
    else if ( *(_DWORD *)(P + 88) == 2 )
    {
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(P + 96), (PVOID)P);
    }
  }
}

```

## disassembly

```asm
0x140025e9c  mov     r11, rsp
0x140025e9f  mov     [r11+10h], rbx
0x140025ea3  mov     [r11+18h], rbp
0x140025ea7  mov     [r11+20h], r9d
0x140025eab  push    rsi
0x140025eac  push    rdi
0x140025ead  push    r12
0x140025eaf  sub     rsp, 30h
0x140025eb3  mov     eax, cs:dword_140013058
0x140025eb9  mov     rdi, r8
0x140025ebc  mov     qword ptr [r11+8], 0
0x140025ec4  mov     rsi, rdx
0x140025ec7  mov     rbx, rcx
0x140025eca  cmp     eax, 5
0x140025ecd  jbe     short loc_140025EF2
0x140025ecf  mov     r9, [rcx+8]
0x140025ed3  lea     rax, aReferenceObjec; "Reference object"
0x140025eda  mov     r8, rcx
0x140025edd  mov     [r11-28h], rax
0x140025ee1  lea     rcx, aHvsocketxboxpr; "HvSocketXboxProcessConnectResult"
0x140025ee8  mov     edx, 40Ah
0x140025eed  call    HvsocketTraceReferenceCount
0x140025ef2  mov     eax, 1
0x140025ef7  lock xadd [rbx+8], rax
0x140025efd  inc     rax
0x140025f00  mov     ebp, 0Eh
0x140025f05  cmp     rax, 1
0x140025f09  jg      short loc_140025F0F
0x140025f0b  mov     ecx, ebp
0x140025f0d  int     29h; Win8: RtlFailFast(ecx)
0x140025f0f  lea     r9, [rsp+48h+Entry]
0x140025f14  mov     r8, rdi
0x140025f17  mov     rdx, rsi
0x140025f1a  mov     rcx, rbx
0x140025f1d  call    HvSocketGetPendingOutboundConnectionFromPartition
0x140025f22  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140025f26  lea     r12, aDereferenceObj; "Dereference object"
0x140025f2d  test    al, al
0x140025f2f  jz      loc_140025FDC
0x140025f35  mov     rdi, [rsp+48h+Entry]
0x140025f3a  mov     rcx, rdi
0x140025f3d  call    HvSocketBeginProcessingConnection
0x140025f42  test    al, al
0x140025f44  jz      short loc_140025F53
0x140025f46  lea     rdx, [rsp+48h+arg_18]
0x140025f4b  mov     rcx, rdi; P
0x140025f4e  call    VmbusTlConnectComplete
0x140025f53  mov     eax, cs:dword_140013058
0x140025f59  cmp     eax, 5
0x140025f5c  jbe     short loc_140025F7B
0x140025f5e  mov     r9, [rdi+8]
0x140025f62  lea     rcx, aHvsocketxboxpr; "HvSocketXboxProcessConnectResult"
0x140025f69  mov     r8, rdi
0x140025f6c  mov     [rsp+48h+var_28], r12
0x140025f71  mov     edx, 41Ah
0x140025f76  call    HvsocketTraceReferenceCount
0x140025f7b  mov     rax, rsi
0x140025f7e  lock xadd [rdi+8], rax
0x140025f84  add     rax, rsi
0x140025f87  test    rax, rax
0x140025f8a  jg      short loc_140025FDC
0x140025f8c  jz      short loc_140025F95
0x140025f8e  mov     rcx, rbp
0x140025f91  int     29h; Win8: RtlFailFast(ecx)
0x140025f93  jmp     short loc_140025FDC
0x140025f95  mov     rax, [rdi+50h]
0x140025f99  test    rax, rax
0x140025f9c  jz      short loc_140025FA6
0x140025f9e  mov     rcx, rdi
0x140025fa1  call    _guard_dispatch_icall
0x140025fa6  mov     ecx, [rdi+58h]
0x140025fa9  sub     ecx, 1
0x140025fac  jz      short loc_140025FC8
0x140025fae  cmp     ecx, 1
0x140025fb1  jnz     short loc_140025FDC
0x140025fb3  mov     rcx, [rdi+60h]; Lookaside
0x140025fb7  mov     rdx, rdi; Entry
0x140025fba  call    cs:__imp_ExFreeToNPagedLookasideList
0x140025fc1  nop     dword ptr [rax+rax+00h]
0x140025fc6  jmp     short loc_140025FDC
0x140025fc8  mov     edx, 69706E56h; Tag
0x140025fcd  mov     rcx, rdi; P
0x140025fd0  call    cs:__imp_ExFreePoolWithTag
0x140025fd7  nop     dword ptr [rax+rax+00h]
0x140025fdc  mov     eax, cs:dword_140013058
0x140025fe2  cmp     eax, 5
0x140025fe5  jbe     short loc_140026004
0x140025fe7  mov     r9, [rbx+8]
0x140025feb  lea     rcx, aHvsocketxboxpr; "HvSocketXboxProcessConnectResult"
0x140025ff2  mov     r8, rbx
0x140025ff5  mov     [rsp+48h+var_28], r12
0x140025ffa  mov     edx, 41Dh
0x140025fff  call    HvsocketTraceReferenceCount
0x140026004  mov     rax, rsi
0x140026007  lock xadd [rbx+8], rax
0x14002600d  add     rax, rsi
0x140026010  test    rax, rax
0x140026013  jg      short loc_140026065
0x140026015  jz      short loc_14002601E
0x140026017  mov     rcx, rbp
0x14002601a  int     29h; Win8: RtlFailFast(ecx)
0x14002601c  jmp     short loc_140026065
0x14002601e  mov     rax, [rbx+50h]
0x140026022  test    rax, rax
0x140026025  jz      short loc_14002602F
0x140026027  mov     rcx, rbx
0x14002602a  call    _guard_dispatch_icall
0x14002602f  mov     ecx, [rbx+58h]
0x140026032  sub     ecx, 1
0x140026035  jz      short loc_140026051
0x140026037  cmp     ecx, 1
0x14002603a  jnz     short loc_140026065
0x14002603c  mov     rcx, [rbx+60h]; Lookaside
0x140026040  mov     rdx, rbx; Entry
0x140026043  call    cs:__imp_ExFreeToNPagedLookasideList
0x14002604a  nop     dword ptr [rax+rax+00h]
0x14002604f  jmp     short loc_140026065
0x140026051  mov     edx, 69706E56h; Tag
0x140026056  mov     rcx, rbx; P
0x140026059  call    cs:__imp_ExFreePoolWithTag
0x140026060  nop     dword ptr [rax+rax+00h]
0x140026065  mov     rbx, [rsp+48h+arg_8]
0x14002606a  mov     rbp, [rsp+48h+arg_10]
0x14002606f  add     rsp, 30h
0x140026073  pop     r12
0x140026075  pop     rdi
0x140026076  pop     rsi
0x140026077  retn
```
