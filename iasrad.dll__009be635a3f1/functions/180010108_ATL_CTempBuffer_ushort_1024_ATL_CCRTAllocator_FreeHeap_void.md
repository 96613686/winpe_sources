# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)

- ea: `0x180010108`
- end: `0x180010112`
- name: `?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ`
- size: `10`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x18000e3bc`
- `0x18002f757`
- `0x18002f76d`
- `0x18002f783`
- `0x18002f799`
- `0x18002f7c4`

## import_xrefs

- `msvcrt!free` at `0x18001010b`

## pseudocode

```c
void __fastcall ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(void **a1)
{
  free(*a1);
}

```

## disassembly

```asm
0x180010108  mov     rcx, [rcx]
0x18001010b  jmp     cs:__imp_free
```
