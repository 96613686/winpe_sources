# SetExtensionProperty

- ea: `0x180007530`
- end: `0x180007536`
- name: `SetExtensionProperty`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `KERNELBASE!SetExtensionProperty` at `0x180007530`

## pseudocode

```c
// attributes: thunk
__int64 SetExtensionProperty()
{
  return __imp_SetExtensionProperty();
}

```

## disassembly

```asm
0x180007530  jmp     cs:__imp_SetExtensionProperty
```
