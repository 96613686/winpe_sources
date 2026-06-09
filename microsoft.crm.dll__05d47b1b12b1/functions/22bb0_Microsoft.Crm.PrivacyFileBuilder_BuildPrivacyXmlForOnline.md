# Microsoft.Crm.PrivacyFileBuilder::BuildPrivacyXmlForOnline

- ea: `0x22bb0`
- end: `0x22bbb`
- name: `Microsoft.Crm.PrivacyFileBuilder::BuildPrivacyXmlForOnline`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x22bd0`

## string_xrefs

- `0x22bb0`: `P3PolicyOnline.xml`

## pseudocode

```c

```

## disassembly

```asm
0x22bb0  ldstr    aP3policyonline// "P3PolicyOnline.xml"
0x22bb5  call     string Microsoft.Crm.PrivacyFileBuilder::BuildPrivacyXml(string policyFileName)
0x22bba  ret
```
