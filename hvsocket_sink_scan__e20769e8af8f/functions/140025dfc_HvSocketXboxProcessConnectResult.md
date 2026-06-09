# HvSocketXboxProcessConnectResult

- ea: `0x140025dfc`
- end: `0x140025fd9`
- name: `HvSocketXboxProcessConnectResult`
- size: `477`
- prototype: `void __fastcall(PVOID P, __int64, __int64, int)`
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
- `0x140025dfc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140025f30`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025fb9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025f30`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025fb9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140025f1a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140025fa3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140025f1a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140025fa3`

## pseudocode

```c
void __fastcall HvSocketXboxProcessConnectResult(PVOID P, __int64 a2, __int64 a3, int a4)
{
  PVOID v7; // rdi
  __int64 v8; // rax
  void (__fastcall *v9)(PVOID); // rax
  __int64 v10; // rax
  void (__fastcall *v11)(PVOID); // rax
  PVOID Entry; // [rsp+50h] [rbp+8h] BYREF
  int v13; // [rsp+68h] [rbp+20h]

  v13 = a4;
  Entry = 0;
  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (unsigned int)"HvSocketXboxProcessConnectResult",
      1034,
      (_DWORD)P,
      *((_QWORD *)P + 1),
      (__int64)"Reference object");
  if ( _InterlockedIncrement64((volatile signed __int64 *)P + 1) <= 1 )
    __fastfail(0xEu);
  if ( (unsigned __int8)HvSocketGetPendingOutboundConnectionFromPartition(P, a2, a3, &Entry) )
  {
    v7 = Entry;
    if ( (unsigned __int8)HvSocketBeginProcessingConnection(Entry) )
      VmbusTlConnectComplete(v7);
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"HvSocketXboxProcessConnectResult",
        1050,
        (_DWORD)v7,
        *((_QWORD *)v7 + 1),
        (__int64)"Dereference object");
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
      (unsigned int)"HvSocketXboxProcessConnectResult",
      1053,
      (_DWORD)P,
      *((_QWORD *)P + 1),
      (__int64)"Dereference object");
  v10 = _InterlockedDecrement64((volatile signed __int64 *)P + 1);
  if ( v10 <= 0 )
  {
    if ( v10 )
      __fastfail(0xEu);
    v11 = (void (__fastcall *)(PVOID))*((_QWORD *)P + 10);
    if ( v11 )
      v11(P);
    if ( *((_DWORD *)P + 22) == 1 )
    {
      ExFreePoolWithTag(P, 0x69706E56u);
    }
    else if ( *((_DWORD *)P + 22) == 2 )
    {
      ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)P + 12), P);
    }
  }
}

```

## disassembly

```asm
0x140025dfc  mov     r11, rsp
0x140025dff  mov     [r11+10h], rbx
0x140025e03  mov     [r11+18h], rbp
0x140025e07  mov     [r11+20h], r9d
0x140025e0b  push    rsi
0x140025e0c  push    rdi
0x140025e0d  push    r12
0x140025e0f  sub     rsp, 30h
0x140025e13  mov     eax, cs:dword_140013058
0x140025e19  mov     rdi, r8
0x140025e1c  mov     qword ptr [r11+8], 0
0x140025e24  mov     rsi, rdx
0x140025e27  mov     rbx, rcx
0x140025e2a  cmp     eax, 5
0x140025e2d  jbe     short loc_140025E52
0x140025e2f  mov     r9, [rcx+8]
0x140025e33  lea     rax, aReferenceObjec; "Reference object"
0x140025e3a  mov     r8, rcx
0x140025e3d  mov     [r11-28h], rax
0x140025e41  lea     rcx, aHvsocketxboxpr; "HvSocketXboxProcessConnectResult"
0x140025e48  mov     edx, 40Ah
0x140025e4d  call    HvsocketTraceReferenceCount
0x140025e52  mov     eax, 1
0x140025e57  lock xadd [rbx+8], rax
0x140025e5d  inc     rax
0x140025e60  mov     ebp, 0Eh
0x140025e65  cmp     rax, 1
0x140025e69  jg      short loc_140025E6F
0x140025e6b  mov     ecx, ebp
0x140025e6d  int     29h; Win8: RtlFailFast(ecx)
0x140025e6f  lea     r9, [rsp+48h+Entry]
0x140025e74  mov     r8, rdi
0x140025e77  mov     rdx, rsi
0x140025e7a  mov     rcx, rbx
0x140025e7d  call    HvSocketGetPendingOutboundConnectionFromPartition
0x140025e82  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140025e86  lea     r12, aDereferenceObj; "Dereference object"
0x140025e8d  test    al, al
0x140025e8f  jz      loc_140025F3C
0x140025e95  mov     rdi, [rsp+48h+Entry]
0x140025e9a  mov     rcx, rdi
0x140025e9d  call    HvSocketBeginProcessingConnection
0x140025ea2  test    al, al
0x140025ea4  jz      short loc_140025EB3
0x140025ea6  lea     rdx, [rsp+48h+arg_18]
0x140025eab  mov     rcx, rdi; P
0x140025eae  call    VmbusTlConnectComplete
0x140025eb3  mov     eax, cs:dword_140013058
0x140025eb9  cmp     eax, 5
0x140025ebc  jbe     short loc_140025EDB
0x140025ebe  mov     r9, [rdi+8]
0x140025ec2  lea     rcx, aHvsocketxboxpr; "HvSocketXboxProcessConnectResult"
0x140025ec9  mov     r8, rdi
0x140025ecc  mov     [rsp+48h+var_28], r12
0x140025ed1  mov     edx, 41Ah
0x140025ed6  call    HvsocketTraceReferenceCount
0x140025edb  mov     rax, rsi
0x140025ede  lock xadd [rdi+8], rax
0x140025ee4  add     rax, rsi
0x140025ee7  test    rax, rax
0x140025eea  jg      short loc_140025F3C
0x140025eec  jz      short loc_140025EF5
0x140025eee  mov     rcx, rbp
0x140025ef1  int     29h; Win8: RtlFailFast(ecx)
0x140025ef3  jmp     short loc_140025F3C
0x140025ef5  mov     rax, [rdi+50h]
0x140025ef9  test    rax, rax
0x140025efc  jz      short loc_140025F06
0x140025efe  mov     rcx, rdi
0x140025f01  call    _guard_dispatch_icall
0x140025f06  mov     ecx, [rdi+58h]
0x140025f09  sub     ecx, 1
0x140025f0c  jz      short loc_140025F28
0x140025f0e  cmp     ecx, 1
0x140025f11  jnz     short loc_140025F3C
0x140025f13  mov     rcx, [rdi+60h]; Lookaside
0x140025f17  mov     rdx, rdi; Entry
0x140025f1a  call    cs:__imp_ExFreeToNPagedLookasideList
0x140025f21  nop     dword ptr [rax+rax+00h]
0x140025f26  jmp     short loc_140025F3C
0x140025f28  mov     edx, 69706E56h; Tag
0x140025f2d  mov     rcx, rdi; P
0x140025f30  call    cs:__imp_ExFreePoolWithTag
0x140025f37  nop     dword ptr [rax+rax+00h]
0x140025f3c  mov     eax, cs:dword_140013058
0x140025f42  cmp     eax, 5
0x140025f45  jbe     short loc_140025F64
0x140025f47  mov     r9, [rbx+8]
0x140025f4b  lea     rcx, aHvsocketxboxpr; "HvSocketXboxProcessConnectResult"
0x140025f52  mov     r8, rbx
0x140025f55  mov     [rsp+48h+var_28], r12
0x140025f5a  mov     edx, 41Dh
0x140025f5f  call    HvsocketTraceReferenceCount
0x140025f64  mov     rax, rsi
0x140025f67  lock xadd [rbx+8], rax
0x140025f6d  add     rax, rsi
0x140025f70  test    rax, rax
0x140025f73  jg      short loc_140025FC5
0x140025f75  jz      short loc_140025F7E
0x140025f77  mov     rcx, rbp
0x140025f7a  int     29h; Win8: RtlFailFast(ecx)
0x140025f7c  jmp     short loc_140025FC5
0x140025f7e  mov     rax, [rbx+50h]
0x140025f82  test    rax, rax
0x140025f85  jz      short loc_140025F8F
0x140025f87  mov     rcx, rbx
0x140025f8a  call    _guard_dispatch_icall
0x140025f8f  mov     ecx, [rbx+58h]
0x140025f92  sub     ecx, 1
0x140025f95  jz      short loc_140025FB1
0x140025f97  cmp     ecx, 1
0x140025f9a  jnz     short loc_140025FC5
0x140025f9c  mov     rcx, [rbx+60h]; Lookaside
0x140025fa0  mov     rdx, rbx; Entry
0x140025fa3  call    cs:__imp_ExFreeToNPagedLookasideList
0x140025faa  nop     dword ptr [rax+rax+00h]
0x140025faf  jmp     short loc_140025FC5
0x140025fb1  mov     edx, 69706E56h; Tag
0x140025fb6  mov     rcx, rbx; P
0x140025fb9  call    cs:__imp_ExFreePoolWithTag
0x140025fc0  nop     dword ptr [rax+rax+00h]
0x140025fc5  mov     rbx, [rsp+48h+arg_8]
0x140025fca  mov     rbp, [rsp+48h+arg_10]
0x140025fcf  add     rsp, 30h
0x140025fd3  pop     r12
0x140025fd5  pop     rdi
0x140025fd6  pop     rsi
0x140025fd7  retn
```
