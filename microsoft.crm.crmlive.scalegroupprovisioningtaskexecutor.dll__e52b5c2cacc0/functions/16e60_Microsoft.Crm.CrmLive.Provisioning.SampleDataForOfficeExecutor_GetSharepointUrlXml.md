# Microsoft.Crm.CrmLive.Provisioning.SampleDataForOfficeExecutor::GetSharepointUrlXml

- ea: `0x16e60`
- end: `0x16e8b`
- name: `Microsoft.Crm.CrmLive.Provisioning.SampleDataForOfficeExecutor::GetSharepointUrlXml`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x168f0`

## string_xrefs

- `0x16e66`: `<siteUrlsXml><siteUrl url='`
- `0x16e7a`: `'>false</siteUrl></siteUrlsXml>`

## pseudocode

```c

```

## disassembly

```asm
0x16e60  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x16e65  dup
0x16e66  ldstr    aSiteurlsxmlSit// "<siteUrlsXml><siteUrl url='"
0x16e6b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x16e70  pop
0x16e71  dup
0x16e72  ldarg.1
0x16e73  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x16e78  pop
0x16e79  dup
0x16e7a  ldstr    aFalseSiteurlSi// "'>false</siteUrl></siteUrlsXml>"
0x16e7f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x16e84  pop
0x16e85  callvirt instance string [mscorlib]System.Object::ToString()
0x16e8a  ret
```
