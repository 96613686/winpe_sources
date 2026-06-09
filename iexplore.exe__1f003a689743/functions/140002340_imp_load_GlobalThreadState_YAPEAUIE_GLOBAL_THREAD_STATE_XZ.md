# __imp_load_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ

- ea: `0x140002340`
- end: `0x14000234c`
- name: `__imp_load_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x1400022c1`

## import_xrefs

- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x140002340`

## pseudocode

```c
__int64 load__GlobalThreadState__YAPEAUIE_GLOBAL_THREAD_STATE__XZ()
{
  return _tailMerge_msiso_dll();
}

```

## disassembly

```asm
0x140002340  lea     rax, __imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x140002347  jmp     __tailMerge_msiso_dll
```
