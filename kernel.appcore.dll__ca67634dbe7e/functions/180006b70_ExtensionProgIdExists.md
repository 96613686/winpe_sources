# ExtensionProgIdExists

- ea: `0x180006b70`
- end: `0x180006b76`
- name: `ExtensionProgIdExists`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `KERNELBASE!ExtensionProgIdExists` at `0x180006b70`

## pseudocode

```c
// attributes: thunk
__int64 ExtensionProgIdExists()
{
  return __imp_ExtensionProgIdExists();
}

```

## disassembly

```asm
0x180006b70  jmp     cs:__imp_ExtensionProgIdExists
```
