# memset_0

- ea: `0x18001ecee`
- end: `0x18001ecf4`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `35`
- callee_count: `0`
- tags: ``

## callers

- `0x1800027e4`
- `0x180002970`
- `0x180002e00`
- `0x1800032c0`
- `0x180003a10`
- `0x180004404`
- `0x180005bc0`
- `0x180006650`
- `0x18000676c`
- `0x180006a48`
- `0x180006db0`
- `0x180006fd4`
- `0x1800085c0`
- `0x180008880`
- `0x180008ca0`
- `0x180009db0`
- `0x18000b560`
- `0x18000b8d0`
- `0x18000bd20`
- `0x18000e5ec`
- `0x18000ec9c`
- `0x1800103d0`
- `0x180010480`
- `0x180010574`
- `0x1800119d4`
- `0x1800129bc`
- `0x180012ae0`
- `0x180013d54`
- `0x180014ee0`
- `0x180015438`
- `0x180016824`
- `0x1800169d4`
- `0x180016f70`
- `0x18001d668`
- `0x18001e5f0`

## import_xrefs

- `msvcrt!memset` at `0x18001ecee`

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
0x18001ecee  jmp     cs:__imp_memset
```
