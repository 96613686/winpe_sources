# Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderFactory::ValidateConnectionString

- ea: `0x2b70`
- end: `0x2bab`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderFactory::ValidateConnectionString`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x2ab0`

## callees

- `0x2150`
- `0x2170`
- `0x21b0`
- `0x2b70`

## pseudocode

```c

```

## disassembly

```asm
0x2b70  ldarg.1
0x2b71  callvirt instance string Microsoft.Xrm.Async.Bridges.FromCommonAuth.AadAuthConnectionString::get_ClientId()
0x2b76  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x2b7b  ldarg.1
0x2b7c  callvirt instance string Microsoft.Xrm.Async.Bridges.FromCommonAuth.AadAuthConnectionString::get_AuthorityUrl()
0x2b81  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x2b86  stloc.0
0x2b87  ldarg.1
0x2b88  callvirt instance string Microsoft.Xrm.Async.Bridges.FromCommonAuth.AadAuthConnectionString::get_AppUri()
0x2b8d  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x2b92  stloc.1
0x2b93  ldloc.0
0x2b94  or
0x2b95  ldloc.1
0x2b96  or
0x2b97  brfalse.s loc_2BAA
0x2b99  ldstr    aTheConnectionS_2// "The connection string at '{0}' is not v"...
0x2b9e  ldarg.2
0x2b9f  call     string [mscorlib]System.String::Format(string, object)
0x2ba4  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string)
0x2ba9  throw
0x2baa  ret
```
