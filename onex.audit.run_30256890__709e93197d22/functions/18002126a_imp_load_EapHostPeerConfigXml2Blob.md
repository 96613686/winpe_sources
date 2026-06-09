# __imp_load_EapHostPeerConfigXml2Blob

- ea: `0x18002126a`
- end: `0x180021276`
- name: `__imp_load_EapHostPeerConfigXml2Blob`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180021191`

## import_xrefs

- `eappcfg!EapHostPeerConfigXml2Blob` at `0x18002126a`

## pseudocode

```c
__int64 load_EapHostPeerConfigXml2Blob()
{
  return _tailMerge_eappcfg_dll();
}

```

## disassembly

```asm
0x18002126a  lea     rax, __imp_EapHostPeerConfigXml2Blob
0x180021271  jmp     __tailMerge_eappcfg_dll
```
