# Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderFactory::ReplaceAudienceUri

- ea: `0x2bb0`
- end: `0x2bc6`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderFactory::ReplaceAudienceUri`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x2ab0`

## callees

- `0x2160`
- `0x2bb0`

## pseudocode

```c

```

## disassembly

```asm
0x2bb0  ldarg.1
0x2bb1  ldnull
0x2bb2  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x2bb7  brfalse.s loc_2BC5
0x2bb9  ldarg.2
0x2bba  ldarg.1
0x2bbb  callvirt instance string [mscorlib]System.Object::ToString()
0x2bc0  callvirt instance void Microsoft.Xrm.Async.Bridges.FromCommonAuth.AadAuthConnectionString::set_AppUri(string value)
0x2bc5  ret
```
