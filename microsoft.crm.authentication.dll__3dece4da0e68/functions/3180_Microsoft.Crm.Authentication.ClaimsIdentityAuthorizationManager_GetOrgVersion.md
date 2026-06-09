# Microsoft.Crm.Authentication.ClaimsIdentityAuthorizationManager::GetOrgVersion

- ea: `0x3180`
- end: `0x31aa`
- name: `Microsoft.Crm.Authentication.ClaimsIdentityAuthorizationManager::GetOrgVersion`
- size: `42`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x11e0`
- `0x13c0`
- `0x3800`

## callees

- `0x140f0`

## pseudocode

```c

```

## disassembly

```asm
0x3180  newobj   instance void <>c__DisplayClass1_0::.ctor()
0x3185  stloc.0
0x3186  ldloc.0
0x3187  ldarg.0
0x3188  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass1_0::orgId
0x318d  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Version> Microsoft.Crm.Authentication.ClaimsIdentityAuthorizationManager::_OrgsVersion
0x3192  ldloc.0
0x3193  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass1_0::orgId
0x3198  ldloc.0
0x3199  ldftn    instance class [mscorlib]System.Version <>c__DisplayClass1_0::<GetOrgVersion>b__0(valuetype [mscorlib]System.Guid key)
0x319f  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Version>::.ctor(object, native int)
0x31a4  callvirt instance var<u1> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Version>::GetOrAdd(void, var<u1>)
0x31a9  ret
```
