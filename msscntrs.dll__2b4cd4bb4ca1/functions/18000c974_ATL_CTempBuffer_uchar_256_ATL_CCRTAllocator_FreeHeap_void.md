# ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::FreeHeap(void)

- ea: `0x18000c974`
- end: `0x18000c97e`
- name: `?FreeHeap@?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ`
- size: `10`
- prototype: `void __fastcall(void **)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18000b45c`
- `0x18000bd2c`
- `0x18000edc8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c977`

## pseudocode

```c
void __fastcall ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::FreeHeap(void **a1)
{
  free(*a1);
}

```

## disassembly

```asm
0x18000c974  mov     rcx, [rcx]
0x18000c977  jmp     cs:__imp_free
```
