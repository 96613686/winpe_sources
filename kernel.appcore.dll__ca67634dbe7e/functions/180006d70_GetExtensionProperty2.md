# GetExtensionProperty2

- ea: `0x180006d70`
- end: `0x180006d76`
- name: `GetExtensionProperty2`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `KERNELBASE!GetExtensionProperty2` at `0x180006d70`

## pseudocode

```c
// attributes: thunk
__int64 GetExtensionProperty2()
{
  return __imp_GetExtensionProperty2();
}

```

## disassembly

```asm
0x180006d70  jmp     cs:__imp_GetExtensionProperty2
```
