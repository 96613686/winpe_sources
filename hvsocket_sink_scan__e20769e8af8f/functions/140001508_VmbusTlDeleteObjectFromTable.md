# VmbusTlDeleteObjectFromTable

- ea: `0x140001508`
- end: `0x1400015d5`
- name: `VmbusTlDeleteObjectFromTable`
- size: `205`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400093e0`
- `0x14001f1ec`

## callees

- `0x140001508`
- `0x14000a048`
- `0x14000bfe0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400015ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400015ba`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400015a4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400015a4`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14000151b`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14000151b`

## string_xrefs

- `0x140001555`: `VmbusTlDeleteObjectFromTable`

## pseudocode

```c
BOOLEAN __fastcall VmbusTlDeleteObjectFromTable(__int64 a1, struct _RTL_AVL_TABLE *a2, void *a3, __int64 a4)
{
  BOOLEAN v5; // di
  signed __int64 v6; // rax
  bool v7; // cc
  signed __int64 v8; // rax
  void (__fastcall *v9)(__int64); // rax

  v5 = RtlDeleteElementGenericTableAvl(a2, a3);
  if ( v5 )
  {
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"VmbusTlDeleteObjectFromTable",
        400,
        a4,
        *(_QWORD *)(a4 + 8),
        (__int64)"Dereference object");
    v6 = _InterlockedExchangeAdd64((volatile signed __int64 *)(a4 + 8), 0xFFFFFFFFFFFFFFFFuLL);
    v7 = v6 <= 1;
    v8 = v6 - 1;
    if ( v7 )
    {
      if ( v8 )
        __fastfail(0xEu);
      v9 = *(void (__fastcall **)(__int64))(a4 + 80);
      if ( v9 )
        v9(a4);
      if ( *(_DWORD *)(a4 + 88) == 1 )
      {
        ExFreePoolWithTag((PVOID)a4, 0x69706E56u);
      }
      else if ( *(_DWORD *)(a4 + 88) == 2 )
      {
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(a4 + 96), (PVOID)a4);
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x140001508  mov     [rsp+arg_0], rbx
0x14000150d  push    rdi
0x14000150e  sub     rsp, 30h
0x140001512  mov     rcx, rdx; Table
0x140001515  mov     rbx, r9
0x140001518  mov     rdx, r8; Buffer
0x14000151b  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x140001522  nop     dword ptr [rax+rax+00h]
0x140001527  mov     dil, al
0x14000152a  test    al, al
0x14000152c  jz      loc_1400015C6
0x140001532  mov     ecx, cs:dword_140013058
0x140001538  cmp     ecx, 5
0x14000153b  jbe     short loc_140001561
0x14000153d  mov     r9, [rbx+8]
0x140001541  lea     rax, aDereferenceObj; "Dereference object"
0x140001548  mov     r8, rbx
0x14000154b  mov     [rsp+38h+var_18], rax
0x140001550  mov     edx, 190h
0x140001555  lea     rcx, aVmbustldeleteo; "VmbusTlDeleteObjectFromTable"
0x14000155c  call    HvsocketTraceReferenceCount
0x140001561  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001565  lock xadd [rbx+8], rax
0x14000156b  sub     rax, 1
0x14000156f  jg      short loc_1400015C6
0x140001571  test    rax, rax
0x140001574  jz      short loc_14000157F
0x140001576  mov     ecx, 0Eh
0x14000157b  int     29h; Win8: RtlFailFast(ecx)
0x14000157d  jmp     short loc_1400015C6
0x14000157f  mov     rax, [rbx+50h]
0x140001583  test    rax, rax
0x140001586  jz      short loc_140001590
0x140001588  mov     rcx, rbx
0x14000158b  call    _guard_dispatch_icall
0x140001590  mov     ecx, [rbx+58h]
0x140001593  sub     ecx, 1
0x140001596  jz      short loc_1400015B2
0x140001598  cmp     ecx, 1
0x14000159b  jnz     short loc_1400015C6
0x14000159d  mov     rcx, [rbx+60h]; Lookaside
0x1400015a1  mov     rdx, rbx; Entry
0x1400015a4  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400015ab  nop     dword ptr [rax+rax+00h]
0x1400015b0  jmp     short loc_1400015C6
0x1400015b2  mov     edx, 69706E56h; Tag
0x1400015b7  mov     rcx, rbx; P
0x1400015ba  call    cs:__imp_ExFreePoolWithTag
0x1400015c1  nop     dword ptr [rax+rax+00h]
0x1400015c6  mov     rbx, [rsp+38h+arg_0]
0x1400015cb  mov     al, dil
0x1400015ce  add     rsp, 30h
0x1400015d2  pop     rdi
0x1400015d3  retn
```
