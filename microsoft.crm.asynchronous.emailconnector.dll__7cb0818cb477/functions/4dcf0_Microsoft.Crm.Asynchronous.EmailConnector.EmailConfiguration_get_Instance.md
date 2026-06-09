# Microsoft.Crm.Asynchronous.EmailConnector.EmailConfiguration::get_Instance

- ea: `0x4dcf0`
- end: `0x4dd08`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.EmailConfiguration::get_Instance`
- size: `24`
- prototype: ``
- caller_count: `30`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x6e30`
- `0x8570`
- `0x88f0`
- `0x8c10`
- `0x8d00`
- `0xae80`
- `0xaf90`
- `0x13b90`
- `0x13bd0`
- `0x2f3f0`
- `0x2fce0`
- `0x32a90`
- `0x35710`
- `0x36900`
- `0x41270`
- `0x41310`
- `0x47b50`
- `0x4e9b0`
- `0x4ec90`
- `0x4fea0`
- `0x50230`
- `0x507f0`
- `0x71d10`
- `0x72600`
- `0x72e20`
- `0x76be0`
- `0x76f60`
- `0x81c00`
- `0x821e0`
- `0x82e30`

## string_xrefs

- `0x4dcf8`: `Email Configuration has not been initialized yet.`

## pseudocode

```c

```

## disassembly

```asm
0x4dcf0  ldsfld   class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IEmailConfiguration Microsoft.Crm.Asynchronous.EmailConnector.EmailConfiguration::_instance
0x4dcf5  ldnull
0x4dcf6  cgt.un
0x4dcf8  ldstr    aEmailConfigura// "Email Configuration has not been initia"...
0x4dcfd  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x4dd02  ldsfld   class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IEmailConfiguration Microsoft.Crm.Asynchronous.EmailConnector.EmailConfiguration::_instance
0x4dd07  ret
```
