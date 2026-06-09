# SaveStateRootFolderPath

- ea: `0x180007520`
- end: `0x180007526`
- name: `SaveStateRootFolderPath`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNELBASE!SaveStateRootFolderPath` at `0x180007520`

## pseudocode

```c
// attributes: thunk
__int64 SaveStateRootFolderPath()
{
  return __imp_SaveStateRootFolderPath();
}

```

## disassembly

```asm
0x180007520  jmp     cs:__imp_SaveStateRootFolderPath
```
