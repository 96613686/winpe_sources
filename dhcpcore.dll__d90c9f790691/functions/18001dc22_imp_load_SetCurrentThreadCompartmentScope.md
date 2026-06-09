# __imp_load_SetCurrentThreadCompartmentScope

- ea: `0x18001dc22`
- end: `0x18001dc2e`
- name: `__imp_load_SetCurrentThreadCompartmentScope`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001daef`

## import_xrefs

- `IPHLPAPI!SetCurrentThreadCompartmentScope` at `0x18001dc22`

## pseudocode

```c
__int64 load_SetCurrentThreadCompartmentScope()
{
  return _tailMerge_iphlpapi_dll();
}

```

## disassembly

```asm
0x18001dc22  lea     rax, __imp_SetCurrentThreadCompartmentScope
0x18001dc29  jmp     __tailMerge_iphlpapi_dll
```
