# memset_0

- ea: `0x18001a3ee`
- end: `0x18001a3f4`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `71`
- callee_count: `0`
- tags: ``

## callers

- `0x180001ed4`
- `0x180002328`
- `0x1800027e0`
- `0x180003100`
- `0x180003304`
- `0x1800034c8`
- `0x180003cc0`
- `0x18000490c`
- `0x180004a8c`
- `0x180004b30`
- `0x180004d78`
- `0x180005368`
- `0x180006468`
- `0x180006904`
- `0x180006ed8`
- `0x180007a80`
- `0x180007efc`
- `0x18000803c`
- `0x180008a70`
- `0x180008f80`
- `0x180009a70`
- `0x18000a260`
- `0x18000a5c0`
- `0x18000aaa0`
- `0x18000bf10`
- `0x18000ce60`
- `0x18000d6ac`
- `0x18000d90c`
- `0x18000dd80`
- `0x18000dee0`
- `0x18000e950`
- `0x18000ebc8`
- `0x180010340`
- `0x1800108f0`
- `0x18001225c`
- `0x180012634`
- `0x1800128dc`
- `0x180012ee4`
- `0x180013b6c`
- `0x180014070`
- `0x180014590`
- `0x1800152b8`
- `0x180016910`
- `0x180018580`
- `0x18001b314`
- `0x18001bbe0`
- `0x18001dabc`
- `0x18001e110`
- `0x18001e81c`
- `0x18001ed84`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memset` at `0x18001a3ee`

## pseudocode

```c
// attributes: thunk
void *__cdecl memset_0(void *a1, int Val, size_t Size)
{
  return memset(a1, Val, Size);
}

```

## disassembly

```asm
0x18001a3ee  jmp     cs:__imp_memset
```
