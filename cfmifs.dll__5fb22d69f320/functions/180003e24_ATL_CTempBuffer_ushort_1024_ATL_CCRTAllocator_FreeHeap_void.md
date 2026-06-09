# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)

- ea: `0x180003e24`
- end: `0x180003e2e`
- name: `?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ`
- size: `10`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180002d44`
- `0x180004818`

## import_xrefs

- `msvcrt!free` at `0x180003e27`

## pseudocode

```c
void __fastcall ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(void **a1)
{
  free(*a1);
}

```

## disassembly

```asm
0x180003e24  mov     rcx, [rcx]
0x180003e27  jmp     cs:__imp_free
```
