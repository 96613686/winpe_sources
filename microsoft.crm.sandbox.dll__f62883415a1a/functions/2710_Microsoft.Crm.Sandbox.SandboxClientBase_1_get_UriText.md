# Microsoft.Crm.Sandbox.SandboxClientBase`1::get_UriText

- ea: `0x2710`
- end: `0x2727`
- name: `Microsoft.Crm.Sandbox.SandboxClientBase`1::get_UriText`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x2716`: `_uriText`

## pseudocode

```c

```

## disassembly

```asm
0x2710  ldarg.0
0x2711  ldfld    string class Microsoft.Crm.Sandbox.SandboxClientBase`1<var<u1>>::_uriText
0x2716  ldstr    aUritext// "_uriText"
0x271b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2720  ldarg.0
0x2721  ldfld    string class Microsoft.Crm.Sandbox.SandboxClientBase`1<var<u1>>::_uriText
0x2726  ret
```
