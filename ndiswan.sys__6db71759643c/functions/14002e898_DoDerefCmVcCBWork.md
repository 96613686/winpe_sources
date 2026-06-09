# DoDerefCmVcCBWork

- ea: `0x14002e898`
- end: `0x14002e8d5`
- name: `DoDerefCmVcCBWork`
- size: `61`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140001be0`
- `0x140008e5c`
- `0x140011540`
- `0x140025830`
- `0x14002f620`
- `0x140030940`
- `0x1400353d0`

## import_xrefs

- `NDIS!NdisCmCloseCallComplete` at `0x14002e8c2`
- `NDIS!NdisCmCloseCallComplete` at `0x14002e8c2`
- `NDIS!NdisMCmDeactivateVc` at `0x14002e8ad`
- `NDIS!NdisMCmDeactivateVc` at `0x14002e8ad`

## pseudocode

```c
void __fastcall DoDerefCmVcCBWork(__int64 a1)
{
  _InterlockedExchange((volatile __int32 *)(a1 + 20), 4);
  NdisMCmDeactivateVc(*(NDIS_HANDLE *)(a1 + 40));
  NdisCmCloseCallComplete(0, *(NDIS_HANDLE *)(a1 + 40), 0);
}

```

## disassembly

```asm
0x14002e898  push    rbx
0x14002e89a  sub     rsp, 20h
0x14002e89e  mov     eax, 4
0x14002e8a3  mov     rbx, rcx
0x14002e8a6  xchg    eax, [rcx+14h]
0x14002e8a9  mov     rcx, [rcx+28h]; NdisVcHandle
0x14002e8ad  call    cs:__imp_NdisMCmDeactivateVc
0x14002e8b4  nop     dword ptr [rax+rax+00h]
0x14002e8b9  mov     rdx, [rbx+28h]; NdisVcHandle
0x14002e8bd  xor     r8d, r8d; NdisPartyHandle
0x14002e8c0  xor     ecx, ecx; Status
0x14002e8c2  call    cs:__imp_NdisCmCloseCallComplete
0x14002e8c9  nop     dword ptr [rax+rax+00h]
0x14002e8ce  add     rsp, 20h
0x14002e8d2  pop     rbx
0x14002e8d3  retn
```
