# __imp_load_GetCurrentThreadCompartmentScope

- ea: `0x18001dc10`
- end: `0x18001dc1c`
- name: `__imp_load_GetCurrentThreadCompartmentScope`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001daef`

## import_xrefs

- `IPHLPAPI!GetCurrentThreadCompartmentScope` at `0x18001dc10`

## pseudocode

```c
__int64 load_GetCurrentThreadCompartmentScope()
{
  return _tailMerge_iphlpapi_dll();
}

```

## disassembly

```asm
0x18001dc10  lea     rax, __imp_GetCurrentThreadCompartmentScope
0x18001dc17  jmp     __tailMerge_iphlpapi_dll
```
