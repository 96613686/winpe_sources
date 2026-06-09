# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)

- ea: `0x18000a4a0`
- end: `0x18000a4aa`
- name: `?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ`
- size: `10`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180008948`

## import_xrefs

- `msvcrt!free` at `0x18000a4a3`

## pseudocode

```c
void __fastcall ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(void **a1)
{
  free(*a1);
}

```

## disassembly

```asm
0x18000a4a0  mov     rcx, [rcx]
0x18000a4a3  jmp     cs:__imp_free
```
