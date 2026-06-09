# SendControlAck

- ea: `0x140017190`
- end: `0x1400171d9`
- name: `SendControlAck`
- size: `73`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x140017fa0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400171a7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400171a7`

## pseudocode

```c
__int64 __fastcall SendControlAck(PVOID Entry, __int64 a2)
{
  ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*(_QWORD *)(a2 + 24) + 960LL), Entry);
  return SendZlb(a2, 0, *(unsigned __int16 *)(a2 + 200), *(unsigned __int16 *)(a2 + 280), 0);
}

```

## disassembly

```asm
0x140017190  push    rbx
0x140017192  sub     rsp, 30h
0x140017196  mov     rbx, rdx
0x140017199  mov     rdx, rcx; Entry
0x14001719c  mov     rcx, [rbx+18h]
0x1400171a0  add     rcx, 3C0h; Lookaside
0x1400171a7  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400171ae  nop     dword ptr [rax+rax+00h]
0x1400171b3  movzx   r9d, word ptr [rbx+118h]
0x1400171bb  xor     edx, edx
0x1400171bd  movzx   r8d, word ptr [rbx+0C8h]
0x1400171c5  mov     rcx, rbx
0x1400171c8  mov     [rsp+38h+var_18], 0
0x1400171cd  call    SendZlb
0x1400171d2  add     rsp, 30h
0x1400171d6  pop     rbx
0x1400171d7  retn
```
