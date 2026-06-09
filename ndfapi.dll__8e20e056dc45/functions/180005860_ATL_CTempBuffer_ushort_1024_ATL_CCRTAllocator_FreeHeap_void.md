# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)

- ea: `0x180005860`
- end: `0x18000586a`
- name: `?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ`
- size: `10`
- prototype: `void __fastcall(void **)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800040dc`
- `0x1800046ec`
- `0x1800060c8`

## import_xrefs

- `msvcrt!free` at `0x180005863`

## pseudocode

```c
void __fastcall ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(void **a1)
{
  free(*a1);
}

```

## disassembly

```asm
0x180005860  mov     rcx, [rcx]
0x180005863  jmp     cs:__imp_free
```
