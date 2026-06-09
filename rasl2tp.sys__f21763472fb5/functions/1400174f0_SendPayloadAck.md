# SendPayloadAck

- ea: `0x1400174f0`
- end: `0x140017546`
- name: `SendPayloadAck`
- size: `86`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x140017fa0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001750e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001750e`

## pseudocode

```c
__int64 __fastcall SendPayloadAck(PVOID Entry, __int64 a2, __int64 a3)
{
  int v3; // edi

  v3 = a2;
  ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*(_QWORD *)(a2 + 24) + 960LL), Entry);
  return SendZlb(v3, a3, *(unsigned __int16 *)(a3 + 226), *(unsigned __int16 *)(a3 + 280), 0);
}

```

## disassembly

```asm
0x1400174f0  mov     [rsp+arg_0], rbx
0x1400174f5  push    rdi
0x1400174f6  sub     rsp, 30h
0x1400174fa  mov     rdi, rdx
0x1400174fd  mov     rbx, r8
0x140017500  mov     rdx, rcx; Entry
0x140017503  mov     rcx, [rdi+18h]
0x140017507  add     rcx, 3C0h; Lookaside
0x14001750e  call    cs:__imp_ExFreeToNPagedLookasideList
0x140017515  nop     dword ptr [rax+rax+00h]
0x14001751a  movzx   r9d, word ptr [rbx+118h]
0x140017522  mov     rdx, rbx
0x140017525  movzx   r8d, word ptr [rbx+0E2h]
0x14001752d  mov     rcx, rdi
0x140017530  mov     [rsp+38h+var_18], 0
0x140017535  call    SendZlb
0x14001753a  mov     rbx, [rsp+38h+arg_0]
0x14001753f  add     rsp, 30h
0x140017543  pop     rdi
0x140017544  retn
```
