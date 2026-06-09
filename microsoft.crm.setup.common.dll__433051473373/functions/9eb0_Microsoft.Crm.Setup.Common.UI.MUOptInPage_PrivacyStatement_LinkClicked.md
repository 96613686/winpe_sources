# Microsoft.Crm.Setup.Common.UI.MUOptInPage::PrivacyStatement_LinkClicked

- ea: `0x9eb0`
- end: `0x9ec1`
- name: `Microsoft.Crm.Setup.Common.UI.MUOptInPage::PrivacyStatement_LinkClicked`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x9eb5`: `http://go.microsoft.com/fwlink/p/?LinkID=627380`

## pseudocode

```c

```

## disassembly

```asm
0x9eb0  ldstr    aIexploreExe// "iexplore.exe"
0x9eb5  ldstr    aHttpGoMicrosof_0// "http://go.microsoft.com/fwlink/p/?LinkI"...
0x9eba  call     class [System]System.Diagnostics.Process [System]System.Diagnostics.Process::Start(string, string)
0x9ebf  pop
0x9ec0  ret
```
