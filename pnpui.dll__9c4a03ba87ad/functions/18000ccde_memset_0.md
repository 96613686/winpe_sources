# memset_0

- ea: `0x18000ccde`
- end: `0x18000cce4`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `17`
- callee_count: `0`
- tags: ``

## callers

- `0x180002660`
- `0x180002b70`
- `0x180002f00`
- `0x180003110`
- `0x180003e94`
- `0x1800040fc`
- `0x180004398`
- `0x180004d1c`
- `0x1800050c0`
- `0x180005fd4`
- `0x180006444`
- `0x180006700`
- `0x180007080`
- `0x180007630`
- `0x180009648`
- `0x18000a3b0`
- `0x18000a6c0`

## import_xrefs

- `msvcrt!memset` at `0x18000ccde`

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
0x18000ccde  jmp     cs:__imp_memset
```
