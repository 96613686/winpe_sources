# VmbusTlIoRequestDestructor

- ea: `0x140008860`
- end: `0x140008933`
- name: `VmbusTlIoRequestDestructor`
- size: `211`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x140008860`
- `0x14000a048`
- `0x14000bfe0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140008905`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008905`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400088ef`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400088ef`

## pseudocode

```c
void __fastcall VmbusTlIoRequestDestructor(__int64 a1)
{
  __int64 v1; // rbx
  signed __int64 v3; // rax
  bool v4; // cc
  signed __int64 v5; // rax
  void (__fastcall *v6)(__int64); // rax

  v1 = *(_QWORD *)(a1 + 232);
  if ( v1 )
  {
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (const int *)"VmbusTlIoRequestDestructor",
        176,
        *(_QWORD *)(a1 + 232),
        *(_QWORD *)(v1 + 8),
        (const int *)"Dereference object");
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
    *(_QWORD *)(a1 + 224) = 0;
    *(_QWORD *)(a1 + 232) = 0;
  }
}

```

## disassembly

```asm
0x140008860  mov     [rsp+arg_0], rbx
0x140008865  push    rdi
0x140008866  sub     rsp, 30h
0x14000886a  mov     rbx, [rcx+0E8h]
0x140008871  mov     rdi, rcx
0x140008874  test    rbx, rbx
0x140008877  jz      loc_140008927
0x14000887d  mov     eax, cs:dword_140013058
0x140008883  cmp     eax, 5
0x140008886  jbe     short loc_1400088AC
0x140008888  mov     r9, [rbx+8]
0x14000888c  lea     rax, aDereferenceObj; "Dereference object"
0x140008893  mov     r8, rbx
0x140008896  mov     [rsp+38h+var_18], rax
0x14000889b  mov     edx, 0B0h
0x1400088a0  lea     rcx, aVmbustlioreque; "VmbusTlIoRequestDestructor"
0x1400088a7  call    HvsocketTraceReferenceCount
0x1400088ac  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400088b0  lock xadd [rbx+8], rax
0x1400088b6  sub     rax, 1
0x1400088ba  jg      short loc_140008911
0x1400088bc  test    rax, rax
0x1400088bf  jz      short loc_1400088CA
0x1400088c1  mov     ecx, 0Eh
0x1400088c6  int     29h; Win8: RtlFailFast(ecx)
0x1400088c8  jmp     short loc_140008911
0x1400088ca  mov     rax, [rbx+50h]
0x1400088ce  test    rax, rax
0x1400088d1  jz      short loc_1400088DB
0x1400088d3  mov     rcx, rbx
0x1400088d6  call    _guard_dispatch_icall
0x1400088db  mov     ecx, [rbx+58h]
0x1400088de  sub     ecx, 1
0x1400088e1  jz      short loc_1400088FD
0x1400088e3  cmp     ecx, 1
0x1400088e6  jnz     short loc_140008911
0x1400088e8  mov     rcx, [rbx+60h]; Lookaside
0x1400088ec  mov     rdx, rbx; Entry
0x1400088ef  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400088f6  nop     dword ptr [rax+rax+00h]
0x1400088fb  jmp     short loc_140008911
0x1400088fd  mov     edx, 69706E56h; Tag
0x140008902  mov     rcx, rbx; P
0x140008905  call    cs:__imp_ExFreePoolWithTag
0x14000890c  nop     dword ptr [rax+rax+00h]
0x140008911  mov     qword ptr [rdi+0E0h], 0
0x14000891c  mov     qword ptr [rdi+0E8h], 0
0x140008927  mov     rbx, [rsp+38h+arg_0]
0x14000892c  add     rsp, 30h
0x140008930  pop     rdi
0x140008931  retn
```
