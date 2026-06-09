# EnumerateExtensionNames

- ea: `0x180006b40`
- end: `0x180006b46`
- name: `EnumerateExtensionNames`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `KERNELBASE!EnumerateExtensionNames` at `0x180006b40`

## pseudocode

```c
// attributes: thunk
__int64 EnumerateExtensionNames()
{
  return __imp_EnumerateExtensionNames();
}

```

## disassembly

```asm
0x180006b40  jmp     cs:__imp_EnumerateExtensionNames
```
