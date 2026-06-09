# AddExtensionProgId

- ea: `0x180006820`
- end: `0x180006826`
- name: `AddExtensionProgId`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `KERNELBASE!AddExtensionProgId` at `0x180006820`

## pseudocode

```c
// attributes: thunk
__int64 AddExtensionProgId()
{
  return __imp_AddExtensionProgId();
}

```

## disassembly

```asm
0x180006820  jmp     cs:__imp_AddExtensionProgId
```
