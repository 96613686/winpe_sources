# RemoveExtensionProgIds

- ea: `0x1800074c0`
- end: `0x1800074c6`
- name: `RemoveExtensionProgIds`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `KERNELBASE!RemoveExtensionProgIds` at `0x1800074c0`

## pseudocode

```c
// attributes: thunk
__int64 RemoveExtensionProgIds()
{
  return __imp_RemoveExtensionProgIds();
}

```

## disassembly

```asm
0x1800074c0  jmp     cs:__imp_RemoveExtensionProgIds
```
