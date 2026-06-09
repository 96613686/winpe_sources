# MRxSmbPreparseName_0

- ea: `0x140028e80`
- end: `0x140028e87`
- name: `MRxSmbPreparseName_0`
- size: `7`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `reparse_path`

## import_xrefs

- `mrxsmb!MRxSmbPreparseName` at `0x140028e80`

## pseudocode

```c
// attributes: thunk
__int64 MRxSmbPreparseName_0()
{
  return MRxSmbPreparseName();
}

```

## disassembly

```asm
0x140028e80  jmp     cs:__imp_MRxSmbPreparseName
```
