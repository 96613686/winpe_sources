# GetCurrentPackagePath2

- ea: `0x180006ce0`
- end: `0x180006ce6`
- name: `GetCurrentPackagePath2`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNELBASE!GetCurrentPackagePath2` at `0x180006ce0`

## pseudocode

```c
// attributes: thunk
__int64 GetCurrentPackagePath2()
{
  return __imp_GetCurrentPackagePath2();
}

```

## disassembly

```asm
0x180006ce0  jmp     cs:__imp_GetCurrentPackagePath2
```
