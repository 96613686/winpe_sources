# Microsoft.Crm.Sandbox.SandboxClientBase`1::get_Destination

- ea: `0x26e0`
- end: `0x2707`
- name: `Microsoft.Crm.Sandbox.SandboxClientBase`1::get_Destination`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x26e6`: `_uriText`

## pseudocode

```c

```

## disassembly

```asm
0x26e0  ldarg.0
0x26e1  ldfld    string class Microsoft.Crm.Sandbox.SandboxClientBase`1<var<u1>>::_uriText
0x26e6  ldstr    aUritext// "_uriText"
0x26eb  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x26f0  ldarg.0
0x26f1  call     instance string class Microsoft.Crm.Sandbox.SandboxClientBase`1<var<u1>>::get_ClientId()
0x26f6  ldstr    asc_D53E// "; "
0x26fb  ldarg.0
0x26fc  ldfld    string class Microsoft.Crm.Sandbox.SandboxClientBase`1<var<u1>>::_uriText
0x2701  call     string [mscorlib]System.String::Concat(string, string, string)
0x2706  ret
```
