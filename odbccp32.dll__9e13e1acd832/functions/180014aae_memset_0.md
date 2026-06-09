# memset_0

- ea: `0x180014aae`
- end: `0x180014ab4`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `42`
- callee_count: `0`
- tags: ``

## callers

- `0x180001740`
- `0x180002d20`
- `0x1800033bc`
- `0x180003e10`
- `0x1800052b8`
- `0x180005c00`
- `0x180006db8`
- `0x180007594`
- `0x180007c0c`
- `0x18000829c`
- `0x180008348`
- `0x1800085c8`
- `0x18000a3b0`
- `0x18000a66c`
- `0x18000aa50`
- `0x18000aaf0`
- `0x18000ac40`
- `0x18000aeb0`
- `0x18000af80`
- `0x18000b5f0`
- `0x18000b9c0`
- `0x18000c440`
- `0x18000cfc4`
- `0x18000d500`
- `0x18000d5a8`
- `0x18000d6f4`
- `0x18000dc70`
- `0x18000ea9c`
- `0x18000f100`
- `0x18000fed0`
- `0x180010140`
- `0x18001085c`
- `0x180010a4c`
- `0x180010f40`
- `0x1800110e8`
- `0x1800116d4`
- `0x180012e90`
- `0x1800136b0`
- `0x18001418c`
- `0x180014394`
- `0x18001463c`
- `0x18001484c`

## import_xrefs

- `msvcrt!memset` at `0x180014aae`

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
0x180014aae  jmp     cs:__imp_memset
```
