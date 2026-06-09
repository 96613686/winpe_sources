# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)

- ea: `0x140006e04`
- end: `0x140006e0e`
- name: `?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ`
- size: `10`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140005ae8`
- `0x1400061bc`
- `0x140007880`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140006e07`

## pseudocode

```c
void __fastcall ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(void **a1)
{
  free(*a1);
}

```

## disassembly

```asm
0x140006e04  mov     rcx, [rcx]
0x140006e07  jmp     cs:__imp_free
```
