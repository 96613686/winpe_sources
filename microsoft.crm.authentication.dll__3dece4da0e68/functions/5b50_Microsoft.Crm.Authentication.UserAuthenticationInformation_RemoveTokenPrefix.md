# Microsoft.Crm.Authentication.UserAuthenticationInformation::RemoveTokenPrefix

- ea: `0x5b50`
- end: `0x5b75`
- name: `Microsoft.Crm.Authentication.UserAuthenticationInformation::RemoveTokenPrefix`
- size: `37`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x5d30`
- `0x5e50`
- `0x5f70`
- `0x6330`
- `0x6360`
- `0x6410`
- `0x6490`

## callees

- `0x5b50`

## pseudocode

```c

```

## disassembly

```asm
0x5b50  ldarg.0
0x5b51  ldstr    aUserauth// "userAuth"
0x5b56  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x5b5b  ldarg.0
0x5b5c  ldstr    asc_19F10// ":"
0x5b61  ldc.i4.5
0x5b62  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x5b67  ldc.i4.1
0x5b68  bne.un.s loc_5B73
0x5b6a  ldarg.0
0x5b6b  ldc.i4.0
0x5b6c  ldc.i4.2
0x5b6d  callvirt instance string [mscorlib]System.String::Remove(int32, int32)
0x5b72  ret
0x5b73  ldarg.0
0x5b74  ret
```
