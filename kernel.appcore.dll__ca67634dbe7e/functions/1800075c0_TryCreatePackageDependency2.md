# TryCreatePackageDependency2

- ea: `0x1800075c0`
- end: `0x1800075c6`
- name: `TryCreatePackageDependency2`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNELBASE!TryCreatePackageDependency2` at `0x1800075c0`

## pseudocode

```c
// attributes: thunk
__int64 TryCreatePackageDependency2()
{
  return __imp_TryCreatePackageDependency2();
}

```

## disassembly

```asm
0x1800075c0  jmp     cs:__imp_TryCreatePackageDependency2
```
