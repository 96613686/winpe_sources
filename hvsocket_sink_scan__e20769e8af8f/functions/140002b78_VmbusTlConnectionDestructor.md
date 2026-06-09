# VmbusTlConnectionDestructor

- ea: `0x140002b78`
- end: `0x140002d02`
- name: `VmbusTlConnectionDestructor`
- size: `394`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400056e0`

## callees

- `0x140002b78`
- `0x14000a048`
- `0x14000bfe0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140002c2e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002ccb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002c2e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002ccb`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140002c18`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140002cb5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140002c18`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140002cb5`

## pseudocode

```c
PVOID __fastcall VmbusTlConnectionDestructor(__int64 a1)
{
  __int64 v1; // rbx
  signed __int64 v3; // rax
  bool v4; // cc
  signed __int64 v5; // rax
  void (__fastcall *v6)(__int64); // rax
  __int64 v7; // rbx
  signed __int64 v8; // rax
  signed __int64 v9; // rax
  void (__fastcall *v10)(__int64); // rax
  PVOID result; // rax

  v1 = *(_QWORD *)(a1 + 944);
  *(_QWORD *)(a1 + 944) = 0;
  if ( v1 )
  {
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"VmbusTlConnectionDestructor",
        129,
        v1,
        *(_QWORD *)(v1 + 8),
        (__int64)"Dereference object");
    v3 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v1 + 8), 0xFFFFFFFFFFFFFFFFuLL);
    v4 = v3 <= 1;
    v5 = v3 - 1;
    if ( v4 )
    {
      if ( v5 )
        __fastfail(0xEu);
      v6 = *(void (__fastcall **)(__int64))(v1 + 80);
      if ( v6 )
        v6(v1);
      if ( *(_DWORD *)(v1 + 88) == 1 )
      {
        ExFreePoolWithTag((PVOID)v1, 0x69706E56u);
      }
      else if ( *(_DWORD *)(v1 + 88) == 2 )
      {
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v1 + 96), (PVOID)v1);
      }
    }
  }
  v7 = *(_QWORD *)(a1 + 936);
  if ( v7 )
  {
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"VmbusTlConnectionDestructor",
        134,
        *(_QWORD *)(a1 + 936),
        *(_QWORD *)(v7 + 8),
        (__int64)"Dereference object");
    v8 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v7 + 8), 0xFFFFFFFFFFFFFFFFuLL);
    v4 = v8 <= 1;
    v9 = v8 - 1;
    if ( v4 )
    {
      if ( v9 )
        __fastfail(0xEu);
      v10 = *(void (__fastcall **)(__int64))(v7 + 80);
      if ( v10 )
        v10(v7);
      if ( *(_DWORD *)(v7 + 88) == 1 )
      {
        ExFreePoolWithTag((PVOID)v7, 0x69706E56u);
      }
      else if ( *(_DWORD *)(v7 + 88) == 2 )
      {
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v7 + 96), (PVOID)v7);
      }
    }
    *(_QWORD *)(a1 + 936) = 0;
  }
  result = VmbusProviderContext;
  _InterlockedIncrement((volatile signed __int32 *)VmbusProviderContext + 289);
  return result;
}

```

## disassembly

```asm
0x140002b78  mov     [rsp+arg_0], rbx
0x140002b7d  mov     [rsp+arg_8], rdi
0x140002b82  push    r15
0x140002b84  sub     rsp, 30h
0x140002b88  mov     rbx, [rcx+3B0h]
0x140002b8f  lea     r15, aDereferenceObj; "Dereference object"
0x140002b96  mov     qword ptr [rcx+3B0h], 0
0x140002ba1  mov     rdi, rcx
0x140002ba4  test    rbx, rbx
0x140002ba7  jz      loc_140002C3A
0x140002bad  mov     eax, cs:dword_140013058
0x140002bb3  cmp     eax, 5
0x140002bb6  jbe     short loc_140002BD5
0x140002bb8  mov     r9, [rbx+8]
0x140002bbc  lea     rcx, aVmbustlconnect_9; "VmbusTlConnectionDestructor"
0x140002bc3  mov     r8, rbx
0x140002bc6  mov     [rsp+38h+var_18], r15
0x140002bcb  mov     edx, 81h
0x140002bd0  call    HvsocketTraceReferenceCount
0x140002bd5  or      rax, 0FFFFFFFFFFFFFFFFh
0x140002bd9  lock xadd [rbx+8], rax
0x140002bdf  sub     rax, 1
0x140002be3  jg      short loc_140002C3A
0x140002be5  test    rax, rax
0x140002be8  jz      short loc_140002BF3
0x140002bea  mov     ecx, 0Eh
0x140002bef  int     29h; Win8: RtlFailFast(ecx)
0x140002bf1  jmp     short loc_140002C3A
0x140002bf3  mov     rax, [rbx+50h]
0x140002bf7  test    rax, rax
0x140002bfa  jz      short loc_140002C04
0x140002bfc  mov     rcx, rbx
0x140002bff  call    _guard_dispatch_icall
0x140002c04  mov     ecx, [rbx+58h]
0x140002c07  sub     ecx, 1
0x140002c0a  jz      short loc_140002C26
0x140002c0c  cmp     ecx, 1
0x140002c0f  jnz     short loc_140002C3A
0x140002c11  mov     rcx, [rbx+60h]; Lookaside
0x140002c15  mov     rdx, rbx; Entry
0x140002c18  call    cs:__imp_ExFreeToNPagedLookasideList
0x140002c1f  nop     dword ptr [rax+rax+00h]
0x140002c24  jmp     short loc_140002C3A
0x140002c26  mov     edx, 69706E56h; Tag
0x140002c2b  mov     rcx, rbx; P
0x140002c2e  call    cs:__imp_ExFreePoolWithTag
0x140002c35  nop     dword ptr [rax+rax+00h]
0x140002c3a  mov     rbx, [rdi+3A8h]
0x140002c41  test    rbx, rbx
0x140002c44  jz      loc_140002CE2
0x140002c4a  mov     eax, cs:dword_140013058
0x140002c50  cmp     eax, 5
0x140002c53  jbe     short loc_140002C72
0x140002c55  mov     r9, [rbx+8]
0x140002c59  lea     rcx, aVmbustlconnect_9; "VmbusTlConnectionDestructor"
0x140002c60  mov     r8, rbx
0x140002c63  mov     [rsp+38h+var_18], r15
0x140002c68  mov     edx, 86h
0x140002c6d  call    HvsocketTraceReferenceCount
0x140002c72  or      rax, 0FFFFFFFFFFFFFFFFh
0x140002c76  lock xadd [rbx+8], rax
0x140002c7c  sub     rax, 1
0x140002c80  jg      short loc_140002CD7
0x140002c82  test    rax, rax
0x140002c85  jz      short loc_140002C90
0x140002c87  mov     ecx, 0Eh
0x140002c8c  int     29h; Win8: RtlFailFast(ecx)
0x140002c8e  jmp     short loc_140002CD7
0x140002c90  mov     rax, [rbx+50h]
0x140002c94  test    rax, rax
0x140002c97  jz      short loc_140002CA1
0x140002c99  mov     rcx, rbx
0x140002c9c  call    _guard_dispatch_icall
0x140002ca1  mov     ecx, [rbx+58h]
0x140002ca4  sub     ecx, 1
0x140002ca7  jz      short loc_140002CC3
0x140002ca9  cmp     ecx, 1
0x140002cac  jnz     short loc_140002CD7
0x140002cae  mov     rcx, [rbx+60h]; Lookaside
0x140002cb2  mov     rdx, rbx; Entry
0x140002cb5  call    cs:__imp_ExFreeToNPagedLookasideList
0x140002cbc  nop     dword ptr [rax+rax+00h]
0x140002cc1  jmp     short loc_140002CD7
0x140002cc3  mov     edx, 69706E56h; Tag
0x140002cc8  mov     rcx, rbx; P
0x140002ccb  call    cs:__imp_ExFreePoolWithTag
0x140002cd2  nop     dword ptr [rax+rax+00h]
0x140002cd7  mov     qword ptr [rdi+3A8h], 0
0x140002ce2  mov     rax, cs:VmbusProviderContext
0x140002ce9  lock inc dword ptr [rax+484h]
0x140002cf0  mov     rbx, [rsp+38h+arg_0]
0x140002cf5  mov     rdi, [rsp+38h+arg_8]
0x140002cfa  add     rsp, 30h
0x140002cfe  pop     r15
0x140002d00  retn
```
