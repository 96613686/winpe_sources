# __imp_load_EapHostPeerConfigBlob2Xml

- ea: `0x180003ec2`
- end: `0x180003ece`
- name: `__imp_load_EapHostPeerConfigBlob2Xml`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x18000358f`

## import_xrefs

- `eappcfg!EapHostPeerConfigBlob2Xml` at `0x180003ec2`

## pseudocode

```c
__int64 load_EapHostPeerConfigBlob2Xml()
{
  return _tailMerge_eappcfg_dll();
}

```

## disassembly

```asm
0x180003ec2  lea     rax, __imp_EapHostPeerConfigBlob2Xml
0x180003ec9  jmp     __tailMerge_eappcfg_dll
```
