# PEXIMPORT_CONTEXT_HANDLE_rundown

- ea: `0x180007c80`
- end: `0x180007c87`
- name: `PEXIMPORT_CONTEXT_HANDLE_rundown`
- size: `7`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `EFSCORE!EfsDllCloseFileRaw` at `0x180007c80`

## pseudocode

```c
// attributes: thunk
__int64 PEXIMPORT_CONTEXT_HANDLE_rundown()
{
  return EfsDllCloseFileRaw();
}

```

## disassembly

```asm
0x180007c80  jmp     cs:__imp_EfsDllCloseFileRaw
```
