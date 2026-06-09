# Microsoft.Crm.PrivacyFileBuilder::BuildPrivacyXmlForOnPremise

- ea: `0x22bc0`
- end: `0x22bcb`
- name: `Microsoft.Crm.PrivacyFileBuilder::BuildPrivacyXmlForOnPremise`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x22bd0`

## string_xrefs

- `0x22bc0`: `P3PolicyOnPremise.xml`

## pseudocode

```c

```

## disassembly

```asm
0x22bc0  ldstr    aP3policyonprem// "P3PolicyOnPremise.xml"
0x22bc5  call     string Microsoft.Crm.PrivacyFileBuilder::BuildPrivacyXml(string policyFileName)
0x22bca  ret
```
