# Microsoft.Crm.ConfigService.TokenService::RetrieveToken

- ea: `0x48df0`
- end: `0x48e8a`
- name: `Microsoft.Crm.ConfigService.TokenService::RetrieveToken`
- size: `154`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x39050`
- `0x444f0`
- `0x48d90`
- `0x48df0`
- `0x48e90`
- `0x48ea0`

## string_xrefs

- `0x48e18`: `AppIdUri`
- `0x48e3c`: `AppIdUri`

## pseudocode

```c

```

## disassembly

```asm
0x48df0  ldarg.0
0x48df1  ldstr    a17// "17"
0x48df6  ldc.i4.1
0x48df7  newarr   [mscorlib]System.String
0x48dfc  dup
0x48dfd  ldc.i4.0
0x48dfe  ldstr    aSecretkey// "SecretKey"
0x48e03  stelem.ref
0x48e04  call     instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.ConfigService.TokenService::RetrieveAzureApp(string appType, string[] columns)
0x48e09  stloc.0
0x48e0a  ldarg.0
0x48e0b  ldstr    a19// "19"
0x48e10  ldc.i4.2
0x48e11  newarr   [mscorlib]System.String
0x48e16  dup
0x48e17  ldc.i4.0
0x48e18  ldstr    aAppiduri// "AppIdUri"
0x48e1d  stelem.ref
0x48e1e  dup
0x48e1f  ldc.i4.1
0x48e20  ldstr    aDomain// "Domain"
0x48e25  stelem.ref
0x48e26  call     instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.ConfigService.TokenService::RetrieveAzureApp(string appType, string[] columns)
0x48e2b  dup
0x48e2c  ldstr    aDomain// "Domain"
0x48e31  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x48e36  callvirt instance string [mscorlib]System.Object::ToString()
0x48e3b  stloc.1
0x48e3c  ldstr    aAppiduri// "AppIdUri"
0x48e41  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x48e46  callvirt instance string [mscorlib]System.Object::ToString()
0x48e4b  stloc.2
0x48e4c  ldnull
0x48e4d  stloc.3
0x48e4e  ldloc.0
0x48e4f  ldstr    aSecretkey// "SecretKey"
0x48e54  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x48e59  castclass [mscorlib]System.Security.SecureString
0x48e5e  stloc.s  4
0x48e60  ldloc.s  4
0x48e62  call     string Microsoft.Crm.CrmKeyService::GetStringFromSecureString(class [mscorlib]System.Security.SecureString secureString)
0x48e67  stloc.s  5
0x48e69  ldarg.0
0x48e6a  ldloc.1
0x48e6b  ldarg.0
0x48e6c  call     instance string Microsoft.Crm.ConfigService.TokenService::get_ClientId()
0x48e71  ldloc.s  5
0x48e73  ldloc.2
0x48e74  callvirt instance class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationResult Microsoft.Crm.ConfigService.TokenService::GetAuthorizationToken(string tenantId, string appPrincipalId, string password, string resource)
0x48e79  stloc.3
0x48e7a  leave.s  loc_48E88
0x48e7c  ldloc.s  4
0x48e7e  brfalse.s loc_48E87
0x48e80  ldloc.s  4
0x48e82  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x48e87  endfinally
0x48e88  ldloc.3
0x48e89  ret
```
