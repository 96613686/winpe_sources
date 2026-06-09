# PEXIMPORT_CONTEXT_HANDLE_rundown

- ea: `0x1800085c0`
- end: `0x1800085c7`
- name: `PEXIMPORT_CONTEXT_HANDLE_rundown`
- size: `7`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `EFSCORE!EfsDllCloseFileRaw` at `0x1800085c0`

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
0x1800085c0  jmp     cs:__imp_EfsDllCloseFileRaw
```
