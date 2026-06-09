# Microsoft.Crm.Authentication.OpenId.OpenIdParser::GetPassiveUriFromTokenEndpoint

- ea: `0x7110`
- end: `0x7185`
- name: `Microsoft.Crm.Authentication.OpenId.OpenIdParser::GetPassiveUriFromTokenEndpoint`
- size: `117`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xbba0`

## callees

- `0x7110`

## string_xrefs

- `0x7111`: `tokenEndpoint`
- `0x7134`: `/oauth2/token`
- `0x7143`: `oauth2/token`
- `0x716b`: `Unable to get the Passive endpoint from Token endpoint {0}`

## pseudocode

```c

```

## disassembly

```asm
0x7110  ldarg.1
0x7111  ldstr    aTokenendpoint// "tokenEndpoint"
0x7116  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x711b  ldarg.1
0x711c  ldc.i4.1
0x711d  newarr   [mscorlib]System.Char
0x7122  dup
0x7123  ldc.i4.0
0x7124  ldc.i4.s 0x2F
0x7126  stelem.i2
0x7127  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x712c  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x7131  starg.s  1
0x7133  ldarg.1
0x7134  ldstr    aOauth2Token// "/oauth2/token"
0x7139  ldc.i4.5
0x713a  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x713f  brfalse.s loc_7166
0x7141  ldarg.1
0x7142  ldarg.1
0x7143  ldstr    aOauth2Token_0// "oauth2/token"
0x7148  ldc.i4.5
0x7149  callvirt instance int32 [mscorlib]System.String::LastIndexOf(string, valuetype [mscorlib]System.StringComparison)
0x714e  callvirt instance string [mscorlib]System.String::Remove(int32)
0x7153  starg.s  1
0x7155  ldarg.1
0x7156  ldstr    aWsfed// "wsfed"
0x715b  call     string [mscorlib]System.String::Concat(string, string)
0x7160  newobj   instance void [System]System.Uri::.ctor(string)
0x7165  ret
0x7166  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x716b  ldstr    aUnableToGetThe// "Unable to get the Passive endpoint from"...
0x7170  ldc.i4.1
0x7171  newarr   [mscorlib]System.Object
0x7176  dup
0x7177  ldc.i4.0
0x7178  ldarg.1
0x7179  stelem.ref
0x717a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x717f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x7184  throw
```
