# __imp_load_EapHostPeerConfigBlob2Xml

- ea: `0x18002127c`
- end: `0x180021288`
- name: `__imp_load_EapHostPeerConfigBlob2Xml`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180021191`

## import_xrefs

- `eappcfg!EapHostPeerConfigBlob2Xml` at `0x18002127c`

## pseudocode

```c
__int64 load_EapHostPeerConfigBlob2Xml()
{
  return _tailMerge_eappcfg_dll();
}

```

## disassembly

```asm
0x18002127c  lea     rax, __imp_EapHostPeerConfigBlob2Xml
0x180021283  jmp     __tailMerge_eappcfg_dll
```
