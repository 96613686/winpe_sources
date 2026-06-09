# VmbusTlLoopbackReleaseReceiveIndications

- ea: `0x140006500`
- end: `0x1400065f5`
- name: `VmbusTlLoopbackReleaseReceiveIndications`
- size: `245`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140006500`
- `0x14000a048`
- `0x14000bfe0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000654c`
- `ntoskrnl!IofCompleteRequest` at `0x14000654c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400065e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400065e0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140006537`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400065ca`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140006537`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400065ca`

## pseudocode

```c
__int64 __fastcall VmbusTlLoopbackReleaseReceiveIndications(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v3; // rbx
  signed __int64 v4; // rax
  bool v5; // cc
  signed __int64 v6; // rax
  void (__fastcall *v7)(__int64); // rax

  v3 = a3[17];
  *(_QWORD *)(v3 + 200) = *(_QWORD *)(v3 + 184);
  *(_DWORD *)(*(_QWORD *)(v3 + 224) + 48LL) = 0;
  ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*(_QWORD *)(a2 + 112) + 832LL), a3);
  IofCompleteRequest(*(PIRP *)(v3 + 224), 2);
  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (unsigned int)"VmbusTlLoopbackReleaseReceiveIndications",
      442,
      v3,
      *(_QWORD *)(v3 + 8),
      (__int64)"Dereference object");
  v4 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v3 + 8), 0xFFFFFFFFFFFFFFFFuLL);
  v5 = v4 <= 1;
  v6 = v4 - 1;
  if ( v5 )
  {
    if ( v6 )
      __fastfail(0xEu);
    v7 = *(void (__fastcall **)(__int64))(v3 + 80);
    if ( v7 )
      v7(v3);
    if ( *(_DWORD *)(v3 + 88) == 1 )
    {
      ExFreePoolWithTag((PVOID)v3, 0x69706E56u);
    }
    else if ( *(_DWORD *)(v3 + 88) == 2 )
    {
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v3 + 96), (PVOID)v3);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140006500  push    rbx
0x140006502  sub     rsp, 30h
0x140006506  mov     rbx, [r8+88h]
0x14000650d  mov     rax, [rbx+0B8h]
0x140006514  mov     [rbx+0C8h], rax
0x14000651b  mov     rax, [rbx+0E0h]
0x140006522  mov     dword ptr [rax+30h], 0
0x140006529  mov     rcx, [rdx+70h]
0x14000652d  mov     rdx, r8; Entry
0x140006530  add     rcx, 340h; Lookaside
0x140006537  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000653e  nop     dword ptr [rax+rax+00h]
0x140006543  mov     rcx, [rbx+0E0h]; Irp
0x14000654a  mov     dl, 2; PriorityBoost
0x14000654c  call    cs:__imp_IofCompleteRequest
0x140006553  nop     dword ptr [rax+rax+00h]
0x140006558  mov     eax, cs:dword_140013058
0x14000655e  cmp     eax, 5
0x140006561  jbe     short loc_140006587
0x140006563  mov     r9, [rbx+8]
0x140006567  lea     rax, aDereferenceObj; "Dereference object"
0x14000656e  mov     r8, rbx
0x140006571  mov     [rsp+38h+var_18], rax
0x140006576  mov     edx, 1BAh
0x14000657b  lea     rcx, aVmbustlloopbac; "VmbusTlLoopbackReleaseReceiveIndication"...
0x140006582  call    HvsocketTraceReferenceCount
0x140006587  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000658b  lock xadd [rbx+8], rax
0x140006591  sub     rax, 1
0x140006595  jg      short loc_1400065EC
0x140006597  test    rax, rax
0x14000659a  jz      short loc_1400065A5
0x14000659c  mov     ecx, 0Eh
0x1400065a1  int     29h; Win8: RtlFailFast(ecx)
0x1400065a3  jmp     short loc_1400065EC
0x1400065a5  mov     rax, [rbx+50h]
0x1400065a9  test    rax, rax
0x1400065ac  jz      short loc_1400065B6
0x1400065ae  mov     rcx, rbx
0x1400065b1  call    _guard_dispatch_icall
0x1400065b6  mov     ecx, [rbx+58h]
0x1400065b9  sub     ecx, 1
0x1400065bc  jz      short loc_1400065D8
0x1400065be  cmp     ecx, 1
0x1400065c1  jnz     short loc_1400065EC
0x1400065c3  mov     rcx, [rbx+60h]; Lookaside
0x1400065c7  mov     rdx, rbx; Entry
0x1400065ca  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400065d1  nop     dword ptr [rax+rax+00h]
0x1400065d6  jmp     short loc_1400065EC
0x1400065d8  mov     edx, 69706E56h; Tag
0x1400065dd  mov     rcx, rbx; P
0x1400065e0  call    cs:__imp_ExFreePoolWithTag
0x1400065e7  nop     dword ptr [rax+rax+00h]
0x1400065ec  xor     eax, eax
0x1400065ee  add     rsp, 30h
0x1400065f2  pop     rbx
0x1400065f3  retn
```
