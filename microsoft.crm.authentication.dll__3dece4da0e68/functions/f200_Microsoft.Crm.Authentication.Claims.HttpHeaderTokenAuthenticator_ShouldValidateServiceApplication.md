# Microsoft.Crm.Authentication.Claims.HttpHeaderTokenAuthenticator::ShouldValidateServiceApplication

- ea: `0xf200`
- end: `0xf225`
- name: `Microsoft.Crm.Authentication.Claims.HttpHeaderTokenAuthenticator::ShouldValidateServiceApplication`
- size: `37`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xef20`

## callees

- `0x7e10`
- `0xf200`

## pseudocode

```c

```

## disassembly

```asm
0xf200  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0xf205  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0xf20a  ldc.i4.2
0xf20b  beq.s    loc_F20F
0xf20d  ldc.i4.0
0xf20e  ret
0xf20f  ldarg.0
0xf210  isinst   [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.JwtSecurityToken
0xf215  stloc.0
0xf216  ldloc.0
0xf217  brfalse.s loc_F223
0xf219  ldloc.0
0xf21a  call     bool Microsoft.Crm.Authentication.Common.AuthenticationContextExtensions::IsApplicationServiceIdentity(class [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.JwtSecurityToken token)
0xf21f  brfalse.s loc_F223
0xf221  ldc.i4.1
0xf222  ret
0xf223  ldc.i4.0
0xf224  ret
```
