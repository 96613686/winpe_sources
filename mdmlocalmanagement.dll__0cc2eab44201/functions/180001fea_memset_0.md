# memset_0

- ea: `0x180001fea`
- end: `0x180001ff0`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x1800023a0`
- `0x180002624`
- `0x1800028d4`
- `0x1800034b4`
- `0x180004210`
- `0x1800049ac`
- `0x180004db8`
- `0x1800054fc`
- `0x180005a80`
- `0x180005df8`
- `0x180006000`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memset` at `0x180001fea`

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
0x180001fea  jmp     cs:__imp_memset
```
