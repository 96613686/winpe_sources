# VmbusTlDissociateListenerFromPartition

- ea: `0x14001f464`
- end: `0x14001f538`
- name: `VmbusTlDissociateListenerFromPartition`
- size: `212`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task`

## callers

- `0x140005280`

## callees

- `0x140009060`
- `0x14000a048`
- `0x14000bfe0`
- `0x14001f464`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001f515`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f515`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001f4ff`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001f4ff`

## pseudocode

```c
void __fastcall VmbusTlDissociateListenerFromPartition(__int64 a1)
{
  __int64 v2; // rbx
  signed __int64 v3; // rax
  bool v4; // cc
  signed __int64 v5; // rax
  void (__fastcall *v6)(__int64); // rax

  *(_BYTE *)(a1 + 172) = 0;
  VmbusTlDissociateEndpointFromService((char *)a1);
  v2 = *(_QWORD *)(a1 + 368);
  if ( v2 )
  {
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (const int *)"VmbusTlDissociateListenerFromPartition",
        1339,
        *(_QWORD *)(a1 + 368),
        *(_QWORD *)(v2 + 8),
        (const int *)"Dereference object");
    v3 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v2 + 8), 0xFFFFFFFFFFFFFFFFuLL);
    v4 = v3 <= 1;
    v5 = v3 - 1;
    if ( v4 )
    {
      if ( v5 )
        __fastfail(0xEu);
      v6 = *(void (__fastcall **)(__int64))(v2 + 80);
      if ( v6 )
        v6(v2);
      if ( *(_DWORD *)(v2 + 88) == 1 )
      {
        ExFreePoolWithTag((PVOID)v2, 0x69706E56u);
      }
      else if ( *(_DWORD *)(v2 + 88) == 2 )
      {
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v2 + 96), (PVOID)v2);
      }
    }
    *(_QWORD *)(a1 + 368) = 0;
  }
}

```

## disassembly

```asm
0x14001f464  mov     [rsp+arg_0], rbx
0x14001f469  push    rdi
0x14001f46a  sub     rsp, 30h
0x14001f46e  mov     rdi, rcx
0x14001f471  mov     byte ptr [rcx+0ACh], 0
0x14001f478  call    VmbusTlDissociateEndpointFromService
0x14001f47d  mov     rbx, [rdi+170h]
0x14001f484  test    rbx, rbx
0x14001f487  jz      loc_14001F52C
0x14001f48d  mov     eax, cs:dword_140013058
0x14001f493  cmp     eax, 5
0x14001f496  jbe     short loc_14001F4BC
0x14001f498  mov     r9, [rbx+8]
0x14001f49c  lea     rax, aDereferenceObj; "Dereference object"
0x14001f4a3  mov     r8, rbx
0x14001f4a6  mov     [rsp+38h+var_18], rax
0x14001f4ab  mov     edx, 53Bh
0x14001f4b0  lea     rcx, aVmbustldissoci_0; "VmbusTlDissociateListenerFromPartition"
0x14001f4b7  call    HvsocketTraceReferenceCount
0x14001f4bc  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001f4c0  lock xadd [rbx+8], rax
0x14001f4c6  sub     rax, 1
0x14001f4ca  jg      short loc_14001F521
0x14001f4cc  test    rax, rax
0x14001f4cf  jz      short loc_14001F4DA
0x14001f4d1  mov     ecx, 0Eh
0x14001f4d6  int     29h; Win8: RtlFailFast(ecx)
0x14001f4d8  jmp     short loc_14001F521
0x14001f4da  mov     rax, [rbx+50h]
0x14001f4de  test    rax, rax
0x14001f4e1  jz      short loc_14001F4EB
0x14001f4e3  mov     rcx, rbx
0x14001f4e6  call    _guard_dispatch_icall
0x14001f4eb  mov     ecx, [rbx+58h]
0x14001f4ee  sub     ecx, 1
0x14001f4f1  jz      short loc_14001F50D
0x14001f4f3  cmp     ecx, 1
0x14001f4f6  jnz     short loc_14001F521
0x14001f4f8  mov     rcx, [rbx+60h]; Lookaside
0x14001f4fc  mov     rdx, rbx; Entry
0x14001f4ff  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001f506  nop     dword ptr [rax+rax+00h]
0x14001f50b  jmp     short loc_14001F521
0x14001f50d  mov     edx, 69706E56h; Tag
0x14001f512  mov     rcx, rbx; P
0x14001f515  call    cs:__imp_ExFreePoolWithTag
0x14001f51c  nop     dword ptr [rax+rax+00h]
0x14001f521  mov     qword ptr [rdi+170h], 0
0x14001f52c  mov     rbx, [rsp+38h+arg_0]
0x14001f531  add     rsp, 30h
0x14001f535  pop     rdi
0x14001f536  retn
```
