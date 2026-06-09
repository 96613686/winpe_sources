# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)

- ea: `0x14000ce40`
- end: `0x14000ce4a`
- name: `?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ`
- size: `10`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x14000c654`
- `0x14000d708`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000ce43`

## pseudocode

```c
void __fastcall ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(void **a1)
{
  free(*a1);
}

```

## disassembly

```asm
0x14000ce40  mov     rcx, [rcx]
0x14000ce43  jmp     cs:__imp_free
```
