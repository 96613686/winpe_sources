# HvSocketDeleteAddressInfo

- ea: `0x140018700`
- end: `0x1400187a6`
- name: `HvSocketDeleteAddressInfo`
- size: `166`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x14000a048`
- `0x14000bfe0`
- `0x140018700`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140018791`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018791`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001877b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001877b`

## string_xrefs

- `0x140018727`: `HvSocketDeleteAddressInfo`

## pseudocode

```c
__int64 __fastcall HvSocketDeleteAddressInfo(PVOID P)
{
  signed __int64 v2; // rax
  bool v3; // cc
  signed __int64 v4; // rax
  void (__fastcall *v5)(PVOID); // rax

  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (unsigned int)"HvSocketDeleteAddressInfo",
      234,
      (_DWORD)P,
      *((_QWORD *)P + 1),
      (__int64)"Dereference object");
  v2 = _InterlockedExchangeAdd64((volatile signed __int64 *)P + 1, 0xFFFFFFFFFFFFFFFFuLL);
  v3 = v2 <= 1;
  v4 = v2 - 1;
  if ( v3 )
  {
    if ( v4 )
      __fastfail(0xEu);
    v5 = (void (__fastcall *)(PVOID))*((_QWORD *)P + 10);
    if ( v5 )
      v5(P);
    if ( *((_DWORD *)P + 22) == 1 )
    {
      ExFreePoolWithTag(P, 0x69706E56u);
    }
    else if ( *((_DWORD *)P + 22) == 2 )
    {
      ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)P + 12), P);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140018700  push    rbx
0x140018702  sub     rsp, 30h
0x140018706  mov     eax, cs:dword_140013058
0x14001870c  mov     rbx, rcx
0x14001870f  cmp     eax, 5
0x140018712  jbe     short loc_140018738
0x140018714  mov     r9, [rcx+8]
0x140018718  lea     rax, aDereferenceObj; "Dereference object"
0x14001871f  mov     r8, rcx
0x140018722  mov     [rsp+38h+var_18], rax
0x140018727  lea     rcx, aHvsocketdelete_0; "HvSocketDeleteAddressInfo"
0x14001872e  mov     edx, 0EAh
0x140018733  call    HvsocketTraceReferenceCount
0x140018738  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001873c  lock xadd [rbx+8], rax
0x140018742  sub     rax, 1
0x140018746  jg      short loc_14001879D
0x140018748  test    rax, rax
0x14001874b  jz      short loc_140018756
0x14001874d  mov     ecx, 0Eh
0x140018752  int     29h; Win8: RtlFailFast(ecx)
0x140018754  jmp     short loc_14001879D
0x140018756  mov     rax, [rbx+50h]
0x14001875a  test    rax, rax
0x14001875d  jz      short loc_140018767
0x14001875f  mov     rcx, rbx
0x140018762  call    _guard_dispatch_icall
0x140018767  mov     ecx, [rbx+58h]
0x14001876a  sub     ecx, 1
0x14001876d  jz      short loc_140018789
0x14001876f  cmp     ecx, 1
0x140018772  jnz     short loc_14001879D
0x140018774  mov     rcx, [rbx+60h]; Lookaside
0x140018778  mov     rdx, rbx; Entry
0x14001877b  call    cs:__imp_ExFreeToNPagedLookasideList
0x140018782  nop     dword ptr [rax+rax+00h]
0x140018787  jmp     short loc_14001879D
0x140018789  mov     edx, 69706E56h; Tag
0x14001878e  mov     rcx, rbx; P
0x140018791  call    cs:__imp_ExFreePoolWithTag
0x140018798  nop     dword ptr [rax+rax+00h]
0x14001879d  xor     eax, eax
0x14001879f  add     rsp, 30h
0x1400187a3  pop     rbx
0x1400187a4  retn
```
