# __imp_load_URLOpenBlockingStreamW

- ea: `0x18000bd4f`
- end: `0x18000bd5b`
- name: `__imp_load_URLOpenBlockingStreamW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000bcd0`

## import_xrefs

- `urlmon!URLOpenBlockingStreamW` at `0x18000bd4f`

## pseudocode

```c
__int64 load_URLOpenBlockingStreamW()
{
  return _tailMerge_urlmon_dll();
}

```

## disassembly

```asm
0x18000bd4f  lea     rax, __imp_URLOpenBlockingStreamW
0x18000bd56  jmp     __tailMerge_urlmon_dll
```
