# Microsoft.Crm.Setup.Common.UI.MUOptInPage::MUFaq_LinkClicked

- ea: `0x9e90`
- end: `0x9ea1`
- name: `Microsoft.Crm.Setup.Common.UI.MUOptInPage::MUFaq_LinkClicked`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x9e95`: `http://go.microsoft.com/fwlink/p/?LinkID=627255`

## pseudocode

```c

```

## disassembly

```asm
0x9e90  ldstr    aIexploreExe// "iexplore.exe"
0x9e95  ldstr    aHttpGoMicrosof// "http://go.microsoft.com/fwlink/p/?LinkI"...
0x9e9a  call     class [System]System.Diagnostics.Process [System]System.Diagnostics.Process::Start(string, string)
0x9e9f  pop
0x9ea0  ret
```
