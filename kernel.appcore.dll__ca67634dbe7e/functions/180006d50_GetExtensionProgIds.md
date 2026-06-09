# GetExtensionProgIds

- ea: `0x180006d50`
- end: `0x180006d56`
- name: `GetExtensionProgIds`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `KERNELBASE!GetExtensionProgIds` at `0x180006d50`

## pseudocode

```c
// attributes: thunk
__int64 GetExtensionProgIds()
{
  return __imp_GetExtensionProgIds();
}

```

## disassembly

```asm
0x180006d50  jmp     cs:__imp_GetExtensionProgIds
```
