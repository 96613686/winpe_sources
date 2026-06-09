# HvSocketDeleteProviderHandle

- ea: `0x14001a6e0`
- end: `0x14001a786`
- name: `HvSocketDeleteProviderHandle`
- size: `166`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x14000a048`
- `0x14000bfe0`
- `0x14001a6e0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001a771`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a771`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001a75b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001a75b`

## string_xrefs

- `0x14001a707`: `HvSocketDeleteProviderHandle`

## pseudocode

```c
__int64 __fastcall HvSocketDeleteProviderHandle(PVOID P)
{
  signed __int64 v2; // rax
  bool v3; // cc
  signed __int64 v4; // rax
  void (__fastcall *v5)(PVOID); // rax

  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (unsigned int)"HvSocketDeleteProviderHandle",
      63,
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
0x14001a6e0  push    rbx
0x14001a6e2  sub     rsp, 30h
0x14001a6e6  mov     eax, cs:dword_140013058
0x14001a6ec  mov     rbx, rcx
0x14001a6ef  cmp     eax, 5
0x14001a6f2  jbe     short loc_14001A718
0x14001a6f4  mov     r9, [rcx+8]
0x14001a6f8  lea     rax, aDereferenceObj; "Dereference object"
0x14001a6ff  mov     r8, rcx
0x14001a702  mov     [rsp+38h+var_18], rax
0x14001a707  lea     rcx, aHvsocketdelete; "HvSocketDeleteProviderHandle"
0x14001a70e  mov     edx, 3Fh ; '?'
0x14001a713  call    HvsocketTraceReferenceCount
0x14001a718  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001a71c  lock xadd [rbx+8], rax
0x14001a722  sub     rax, 1
0x14001a726  jg      short loc_14001A77D
0x14001a728  test    rax, rax
0x14001a72b  jz      short loc_14001A736
0x14001a72d  mov     ecx, 0Eh
0x14001a732  int     29h; Win8: RtlFailFast(ecx)
0x14001a734  jmp     short loc_14001A77D
0x14001a736  mov     rax, [rbx+50h]
0x14001a73a  test    rax, rax
0x14001a73d  jz      short loc_14001A747
0x14001a73f  mov     rcx, rbx
0x14001a742  call    _guard_dispatch_icall
0x14001a747  mov     ecx, [rbx+58h]
0x14001a74a  sub     ecx, 1
0x14001a74d  jz      short loc_14001A769
0x14001a74f  cmp     ecx, 1
0x14001a752  jnz     short loc_14001A77D
0x14001a754  mov     rcx, [rbx+60h]; Lookaside
0x14001a758  mov     rdx, rbx; Entry
0x14001a75b  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001a762  nop     dword ptr [rax+rax+00h]
0x14001a767  jmp     short loc_14001A77D
0x14001a769  mov     edx, 69706E56h; Tag
0x14001a76e  mov     rcx, rbx; P
0x14001a771  call    cs:__imp_ExFreePoolWithTag
0x14001a778  nop     dword ptr [rax+rax+00h]
0x14001a77d  xor     eax, eax
0x14001a77f  add     rsp, 30h
0x14001a783  pop     rbx
0x14001a784  retn
```
