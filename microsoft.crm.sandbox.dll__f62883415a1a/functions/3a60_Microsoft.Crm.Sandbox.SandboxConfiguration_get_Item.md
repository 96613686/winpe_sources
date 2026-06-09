# Microsoft.Crm.Sandbox.SandboxConfiguration::get_Item

- ea: `0x3a60`
- end: `0x3a6d`
- name: `Microsoft.Crm.Sandbox.SandboxConfiguration::get_Item`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x3a61`: `SandboxConfiguration.get should never be called`

## pseudocode

```c

```

## disassembly

```asm
0x3a60  ldc.i4.0
0x3a61  ldstr    aSandboxconfigu// "SandboxConfiguration.get should never b"...
0x3a66  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x3a6b  ldarg.1
0x3a6c  ret
```
