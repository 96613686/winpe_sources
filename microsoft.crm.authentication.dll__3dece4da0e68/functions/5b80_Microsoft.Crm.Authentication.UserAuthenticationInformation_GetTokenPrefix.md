# Microsoft.Crm.Authentication.UserAuthenticationInformation::GetTokenPrefix

- ea: `0x5b80`
- end: `0x5ba9`
- name: `Microsoft.Crm.Authentication.UserAuthenticationInformation::GetTokenPrefix`
- size: `41`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x5e50`
- `0x5f70`
- `0x6490`

## callees

- `0x5b80`

## pseudocode

```c

```

## disassembly

```asm
0x5b80  ldarg.0
0x5b81  ldstr    aUserauth// "userAuth"
0x5b86  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x5b8b  ldarg.0
0x5b8c  ldstr    asc_19F10// ":"
0x5b91  ldc.i4.5
0x5b92  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x5b97  ldc.i4.1
0x5b98  bne.un.s loc_5BA3
0x5b9a  ldarg.0
0x5b9b  ldc.i4.0
0x5b9c  ldc.i4.1
0x5b9d  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x5ba2  ret
0x5ba3  ldsfld   string [mscorlib]System.String::Empty
0x5ba8  ret
```
