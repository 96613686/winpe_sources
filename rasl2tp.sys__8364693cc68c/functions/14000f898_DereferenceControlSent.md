# DereferenceControlSent

- ea: `0x14000f898`
- end: `0x14000f926`
- name: `DereferenceControlSent`
- size: `142`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14000f008`
- `0x140013c74`
- `0x1400171e0`
- `0x140017330`

## callees

- `0x1400013f0`
- `0x14000f898`
- `0x14001ac30`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000f8f1`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000f907`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000f8f1`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000f907`
- `NDIS!NdisFreeNetBufferList` at `0x14000f8c3`
- `NDIS!NdisFreeNetBufferList` at `0x14000f8c3`

## pseudocode

```c
__int64 __fastcall DereferenceControlSent(PVOID Entry)
{
  unsigned __int32 v2; // edi
  __int64 v3; // rsi
  __int64 v4; // rcx

  v2 = _InterlockedDecrement((volatile signed __int32 *)Entry + 4);
  if ( !v2 )
  {
    v3 = *(_QWORD *)(*((_QWORD *)Entry + 6) + 24LL);
    NdisFreeNetBufferList(*((PNET_BUFFER_LIST *)Entry + 5));
    v4 = *((_QWORD *)Entry + 7);
    if ( v4 )
      DereferenceVc(v4);
    DereferenceTunnel(*((_QWORD *)Entry + 6));
    ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v3 + 576), *((PVOID *)Entry + 3));
    ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v3 + 704), Entry);
  }
  return v2;
}

```

## disassembly

```asm
0x14000f898  mov     [rsp+arg_0], rbx
0x14000f89d  mov     [rsp+arg_8], rsi
0x14000f8a2  push    rdi
0x14000f8a3  sub     rsp, 20h
0x14000f8a7  mov     rbx, rcx
0x14000f8aa  or      edi, 0FFFFFFFFh
0x14000f8ad  lock xadd [rcx+10h], edi
0x14000f8b2  sub     edi, 1
0x14000f8b5  jnz     short loc_14000F913
0x14000f8b7  mov     rax, [rcx+30h]
0x14000f8bb  mov     rcx, [rcx+28h]; NetBufferList
0x14000f8bf  mov     rsi, [rax+18h]
0x14000f8c3  call    cs:__imp_NdisFreeNetBufferList
0x14000f8ca  nop     dword ptr [rax+rax+00h]
0x14000f8cf  mov     rcx, [rbx+38h]
0x14000f8d3  test    rcx, rcx
0x14000f8d6  jz      short loc_14000F8DD
0x14000f8d8  call    DereferenceVc
0x14000f8dd  mov     rcx, [rbx+30h]
0x14000f8e1  call    DereferenceTunnel
0x14000f8e6  mov     rdx, [rbx+18h]; Entry
0x14000f8ea  lea     rcx, [rsi+240h]; Lookaside
0x14000f8f1  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000f8f8  nop     dword ptr [rax+rax+00h]
0x14000f8fd  lea     rcx, [rsi+2C0h]; Lookaside
0x14000f904  mov     rdx, rbx; Entry
0x14000f907  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000f90e  nop     dword ptr [rax+rax+00h]
0x14000f913  mov     rbx, [rsp+28h+arg_0]
0x14000f918  mov     eax, edi
0x14000f91a  mov     rsi, [rsp+28h+arg_8]
0x14000f91f  add     rsp, 20h
0x14000f923  pop     rdi
0x14000f924  retn
```
