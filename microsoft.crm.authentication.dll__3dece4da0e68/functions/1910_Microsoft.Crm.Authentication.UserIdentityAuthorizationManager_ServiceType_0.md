# Microsoft.Crm.Authentication.UserIdentityAuthorizationManager::ServiceType_0

- ea: `0x1910`
- end: `0x196e`
- name: `Microsoft.Crm.Authentication.UserIdentityAuthorizationManager::ServiceType_0`
- size: `94`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18e0`
- `0x1900`
- `0x31b0`

## callees

- `0x1910`

## pseudocode

```c

```

## disassembly

```asm
0x1910  ldarg.0
0x1911  ldnull
0x1912  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x1917  brfalse.s loc_196C
0x1919  ldarg.0
0x191a  callvirt instance string [System]System.Uri::get_AbsolutePath()
0x191f  ldstr    aDiscoverySvc// "Discovery.svc"
0x1924  ldc.i4.5
0x1925  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x192a  brtrue.s loc_1953
0x192c  ldarg.0
0x192d  callvirt instance string [System]System.Uri::get_AbsolutePath()
0x1932  ldstr    aDiscoverySvcWe// "Discovery.svc/web"
0x1937  ldc.i4.5
0x1938  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x193d  brtrue.s loc_1953
0x193f  ldarg.0
0x1940  callvirt instance string [System]System.Uri::get_AbsolutePath()
0x1945  ldstr    aApiDiscovery// "api/discovery"
0x194a  ldc.i4.5
0x194b  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x1950  ldc.i4.0
0x1951  blt.s    loc_1955
0x1953  ldc.i4.2
0x1954  ret
0x1955  ldarg.0
0x1956  callvirt instance string [System]System.Uri::get_AbsolutePath()
0x195b  ldstr    aDeploymentSvc// "Deployment.svc"
0x1960  ldc.i4.5
0x1961  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x1966  brfalse.s loc_196A
0x1968  ldc.i4.3
0x1969  ret
0x196a  ldc.i4.1
0x196b  ret
0x196c  ldc.i4.0
0x196d  ret
```
