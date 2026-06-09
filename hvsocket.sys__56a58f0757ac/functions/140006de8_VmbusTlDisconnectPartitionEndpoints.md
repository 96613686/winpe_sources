# VmbusTlDisconnectPartitionEndpoints

- ea: `0x140006de8`
- end: `0x140006f14`
- name: `VmbusTlDisconnectPartitionEndpoints`
- size: `300`
- prototype: `void __fastcall(__int64, char)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, service_task`

## callers

- `0x14001edd0`
- `0x140023740`
- `0x140023910`

## callees

- `0x140006de8`
- `0x140008c0c`
- `0x14000a048`
- `0x14000bfe0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140006edd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006edd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140006ec7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140006ec7`

## pseudocode

```c
void __fastcall VmbusTlDisconnectPartitionEndpoints(__int64 a1, char a2)
{
  char v3; // bp
  PNPAGED_LOOKASIDE_LIST *v4; // rsi
  PNPAGED_LOOKASIDE_LIST *i; // rbx
  PNPAGED_LOOKASIDE_LIST *v6; // rdi
  PNPAGED_LOOKASIDE_LIST v7; // rax
  PNPAGED_LOOKASIDE_LIST **v8; // rcx
  signed __int64 v9; // rax
  bool v10; // cc
  signed __int64 v11; // rax
  void (__fastcall *v12)(PNPAGED_LOOKASIDE_LIST *); // rax

  v3 = *(_BYTE *)(a1 + 392) && !*(_BYTE *)(a1 + 393);
  v4 = (PNPAGED_LOOKASIDE_LIST *)(a1 + 360);
  for ( i = *(PNPAGED_LOOKASIDE_LIST **)(a1 + 360); i != v4; i = (PNPAGED_LOOKASIDE_LIST *)*i )
  {
    v6 = i - 12;
    VmbusTlCloseServiceEndpoints((__int64)(i - 12), v3);
    if ( a2 )
    {
      v7 = *i;
      if ( (PNPAGED_LOOKASIDE_LIST *)(*i)->L.ListHead.Region != i || (v8 = (PNPAGED_LOOKASIDE_LIST **)i[1], *v8 != i) )
        __fastfail(3u);
      *v8 = (PNPAGED_LOOKASIDE_LIST *)v7;
      v7->L.ListHead.Region = (ULONGLONG)v8;
      i[1] = (PNPAGED_LOOKASIDE_LIST)i;
      *i = (PNPAGED_LOOKASIDE_LIST)i;
      if ( (unsigned int)dword_140013058 > 5 )
        HvsocketTraceReferenceCount(
          (const int *)"VmbusTlDisconnectPartitionEndpoints",
          1923,
          (__int64)(i - 12),
          (__int64)v6[1],
          (const int *)"Dereference object");
      v9 = _InterlockedExchangeAdd64((volatile signed __int64 *)v6 + 1, 0xFFFFFFFFFFFFFFFFuLL);
      v10 = v9 <= 1;
      v11 = v9 - 1;
      if ( v10 )
      {
        if ( v11 )
          __fastfail(0xEu);
        v12 = (void (__fastcall *)(PNPAGED_LOOKASIDE_LIST *))v6[10];
        if ( v12 )
          v12(i - 12);
        if ( *((_DWORD *)v6 + 22) == 1 )
        {
          ExFreePoolWithTag(i - 12, 0x69706E56u);
        }
        else if ( *((_DWORD *)v6 + 22) == 2 )
        {
          ExFreeToNPagedLookasideList(*i, i - 12);
        }
      }
      i = v4;
    }
  }
}

```

## disassembly

```asm
0x140006de8  push    rbx
0x140006dea  push    rbp
0x140006deb  push    rsi
0x140006dec  push    rdi
0x140006ded  push    r14
0x140006def  sub     rsp, 30h
0x140006df3  cmp     byte ptr [rcx+188h], 0
0x140006dfa  mov     r14b, dl
0x140006dfd  jz      short loc_140006E0D
0x140006dff  cmp     byte ptr [rcx+189h], 0
0x140006e06  jnz     short loc_140006E0D
0x140006e08  mov     bpl, 1
0x140006e0b  jmp     short loc_140006E10
0x140006e0d  xor     bpl, bpl
0x140006e10  lea     rsi, [rcx+168h]
0x140006e17  mov     rbx, [rsi]
0x140006e1a  jmp     loc_140006EF8
0x140006e1f  lea     rdi, [rbx-60h]
0x140006e23  mov     dl, bpl
0x140006e26  mov     rcx, rdi
0x140006e29  call    VmbusTlCloseServiceEndpoints
0x140006e2e  test    r14b, r14b
0x140006e31  jz      loc_140006EF5
0x140006e37  mov     rax, [rbx]
0x140006e3a  cmp     [rax+8], rbx
0x140006e3e  jnz     loc_140006F0D
0x140006e44  mov     rcx, [rbx+8]
0x140006e48  cmp     [rcx], rbx
0x140006e4b  jnz     loc_140006F0D
0x140006e51  mov     [rcx], rax
0x140006e54  mov     [rax+8], rcx
0x140006e58  mov     [rbx+8], rbx
0x140006e5c  mov     [rbx], rbx
0x140006e5f  mov     eax, cs:dword_140013058
0x140006e65  cmp     eax, 5
0x140006e68  jbe     short loc_140006E8E
0x140006e6a  mov     r9, [rdi+8]
0x140006e6e  lea     rax, aDereferenceObj; "Dereference object"
0x140006e75  mov     r8, rdi
0x140006e78  mov     [rsp+58h+var_38], rax
0x140006e7d  mov     edx, 783h
0x140006e82  lea     rcx, aVmbustldisconn; "VmbusTlDisconnectPartitionEndpoints"
0x140006e89  call    HvsocketTraceReferenceCount
0x140006e8e  or      rax, 0FFFFFFFFFFFFFFFFh
0x140006e92  lock xadd [rdi+8], rax
0x140006e98  sub     rax, 1
0x140006e9c  jg      short loc_140006EF2
0x140006e9e  test    rax, rax
0x140006ea1  jnz     short loc_140006EEB
0x140006ea3  mov     rax, [rdi+50h]
0x140006ea7  test    rax, rax
0x140006eaa  jz      short loc_140006EB4
0x140006eac  mov     rcx, rdi
0x140006eaf  call    _guard_dispatch_icall
0x140006eb4  mov     ecx, [rdi+58h]
0x140006eb7  sub     ecx, 1
0x140006eba  jz      short loc_140006ED5
0x140006ebc  cmp     ecx, 1
0x140006ebf  jnz     short loc_140006EF2
0x140006ec1  mov     rcx, [rbx]; Lookaside
0x140006ec4  mov     rdx, rdi; Entry
0x140006ec7  call    cs:__imp_ExFreeToNPagedLookasideList
0x140006ece  nop     dword ptr [rax+rax+00h]
0x140006ed3  jmp     short loc_140006EF2
0x140006ed5  mov     edx, 69706E56h; Tag
0x140006eda  mov     rcx, rdi; P
0x140006edd  call    cs:__imp_ExFreePoolWithTag
0x140006ee4  nop     dword ptr [rax+rax+00h]
0x140006ee9  jmp     short loc_140006EF2
0x140006eeb  mov     ecx, 0Eh
0x140006ef0  int     29h; Win8: RtlFailFast(ecx)
0x140006ef2  mov     rbx, rsi
0x140006ef5  mov     rbx, [rbx]
0x140006ef8  cmp     rbx, rsi
0x140006efb  jnz     loc_140006E1F
0x140006f01  add     rsp, 30h
0x140006f05  pop     r14
0x140006f07  pop     rdi
0x140006f08  pop     rsi
0x140006f09  pop     rbp
0x140006f0a  pop     rbx
0x140006f0b  retn
0x140006f0d  mov     ecx, 3
0x140006f12  int     29h; Win8: RtlFailFast(ecx)
```
