# __imp_load_SHEnableServiceObject

- ea: `0x180005a5f`
- end: `0x180005a6b`
- name: `__imp_load_SHEnableServiceObject`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x1800059e0`

## import_xrefs

- `SHELL32!SHEnableServiceObject` at `0x180005a5f`

## pseudocode

```c
__int64 load_SHEnableServiceObject()
{
  return _tailMerge_shell32_dll();
}

```

## disassembly

```asm
0x180005a5f  lea     rax, __imp_SHEnableServiceObject
0x180005a66  jmp     __tailMerge_shell32_dll
```
