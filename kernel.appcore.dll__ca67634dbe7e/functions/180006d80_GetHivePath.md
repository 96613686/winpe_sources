# GetHivePath

- ea: `0x180006d80`
- end: `0x180006d86`
- name: `GetHivePath`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNELBASE!GetHivePath` at `0x180006d80`

## pseudocode

```c
// attributes: thunk
__int64 GetHivePath()
{
  return __imp_GetHivePath();
}

```

## disassembly

```asm
0x180006d80  jmp     cs:__imp_GetHivePath
```
