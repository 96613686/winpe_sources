# operator delete(void *)

- ea: `0x18000d9dc`
- end: `0x18000d9e3`
- name: `??3@YAXPEAX@Z`
- size: `7`
- prototype: `void __cdecl(void *Block)`
- caller_count: `4`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180001200`
- `0x180001990`
- `0x180018676`
- `0x180018958`

## import_xrefs

- `msvcrt!free` at `0x18000d9dc`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  free(Block);
}

```

## disassembly

```asm
0x18000d9dc  jmp     cs:__imp_free
```
