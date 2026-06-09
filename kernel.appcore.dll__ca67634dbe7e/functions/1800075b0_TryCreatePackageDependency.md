# TryCreatePackageDependency

- ea: `0x1800075b0`
- end: `0x1800075b6`
- name: `TryCreatePackageDependency`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNELBASE!TryCreatePackageDependency` at `0x1800075b0`

## pseudocode

```c
// attributes: thunk
__int64 TryCreatePackageDependency()
{
  return __imp_TryCreatePackageDependency();
}

```

## disassembly

```asm
0x1800075b0  jmp     cs:__imp_TryCreatePackageDependency
```
