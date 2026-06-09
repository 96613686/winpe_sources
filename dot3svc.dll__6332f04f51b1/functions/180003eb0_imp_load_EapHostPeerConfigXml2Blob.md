# __imp_load_EapHostPeerConfigXml2Blob

- ea: `0x180003eb0`
- end: `0x180003ebc`
- name: `__imp_load_EapHostPeerConfigXml2Blob`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x18000358f`

## import_xrefs

- `eappcfg!EapHostPeerConfigXml2Blob` at `0x180003eb0`

## pseudocode

```c
__int64 load_EapHostPeerConfigXml2Blob()
{
  return _tailMerge_eappcfg_dll();
}

```

## disassembly

```asm
0x180003eb0  lea     rax, __imp_EapHostPeerConfigXml2Blob
0x180003eb7  jmp     __tailMerge_eappcfg_dll
```
