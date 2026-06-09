# memset_0

- ea: `0x180002cbc`
- end: `0x180002cc2`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `25`
- callee_count: `0`
- tags: ``

## callers

- `0x180003bd0`
- `0x180003e50`
- `0x1800040fc`
- `0x1800046a8`
- `0x1800050a4`
- `0x180006384`
- `0x1800065a4`
- `0x180007070`
- `0x180007430`
- `0x1800075ac`
- `0x18000797c`
- `0x180009a00`
- `0x18000a2a4`
- `0x18000f004`
- `0x180010864`
- `0x180012254`
- `0x180012b58`
- `0x180012d2c`
- `0x180017558`
- `0x180017b94`
- `0x18001b094`
- `0x18001beb4`
- `0x18001d064`
- `0x18001dc54`
- `0x18001e38c`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memset` at `0x180002cbc`

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
0x180002cbc  jmp     cs:__imp_memset
```
