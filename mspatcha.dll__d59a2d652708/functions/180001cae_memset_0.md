# memset_0

- ea: `0x180001cae`
- end: `0x180001cb4`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `15`
- callee_count: `0`
- tags: ``

## callers

- `0x180001d10`
- `0x180002720`
- `0x180004520`
- `0x180005754`
- `0x180005934`
- `0x180005c60`
- `0x1800061e4`
- `0x18000677c`
- `0x180006858`
- `0x180006b98`
- `0x180007090`
- `0x180007bfc`
- `0x1800087b0`
- `0x180008b3c`
- `0x180008db4`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memset` at `0x180001cae`

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
0x180001cae  jmp     cs:__imp_memset
```
