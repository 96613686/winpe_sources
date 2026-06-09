# GetExtensionProperty

- ea: `0x180006d60`
- end: `0x180006d66`
- name: `GetExtensionProperty`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `KERNELBASE!GetExtensionProperty` at `0x180006d60`

## pseudocode

```c
// attributes: thunk
__int64 GetExtensionProperty()
{
  return __imp_GetExtensionProperty();
}

```

## disassembly

```asm
0x180006d60  jmp     cs:__imp_GetExtensionProperty
```
