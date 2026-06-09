# CreateStateLock

- ea: `0x180006ad0`
- end: `0x180006ad6`
- name: `CreateStateLock`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNELBASE!CreateStateLock` at `0x180006ad0`

## pseudocode

```c
// attributes: thunk
__int64 CreateStateLock()
{
  return __imp_CreateStateLock();
}

```

## disassembly

```asm
0x180006ad0  jmp     cs:__imp_CreateStateLock
```
