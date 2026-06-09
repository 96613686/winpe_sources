# memset_0

- ea: `0x18000bffe`
- end: `0x18000c004`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `18`
- callee_count: `0`
- tags: ``

## callers

- `0x180001870`
- `0x180002210`
- `0x180002f7c`
- `0x180003560`
- `0x1800050e0`
- `0x180005334`
- `0x180005620`
- `0x180006eb0`
- `0x180007200`
- `0x180007770`
- `0x180009158`
- `0x180009184`
- `0x1800098ac`
- `0x180009ad8`
- `0x180009cf0`
- `0x180009e80`
- `0x18000aa1c`
- `0x18000adf8`

## import_xrefs

- `msvcrt!memset` at `0x18000bffe`

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
0x18000bffe  jmp     cs:__imp_memset
```
