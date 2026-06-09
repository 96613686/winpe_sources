# Microsoft.Xrm.Async.Bridges.Flighting.OrgRegKeyFlightClient::IsFeatureEnabled

- ea: `0x2d90`
- end: `0x2e0c`
- name: `Microsoft.Xrm.Async.Bridges.Flighting.OrgRegKeyFlightClient::IsFeatureEnabled`
- size: `124`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x2d90`

## string_xrefs

- `0x2d98`: `A non-empty featureName is required.`
- `0x2d9d`: `featureName`

## pseudocode

```c

```

## disassembly

```asm
0x2d90  ldarg.1
0x2d91  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2d96  brfalse.s loc_2DA8
0x2d98  ldstr    aANonEmptyFeatu// "A non-empty featureName is required."
0x2d9d  ldstr    aFeaturename// "featureName"
0x2da2  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x2da7  throw
0x2da8  ldarg.2
0x2da9  brtrue.s loc_2DB6
0x2dab  ldstr    aContext// "context"
0x2db0  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2db5  throw
0x2db6  ldarg.2
0x2db7  ldstr    aOrganizationid_0// "organizationId"
0x2dbc  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::ContainsKey(var<u1>)
0x2dc1  brtrue.s loc_2DD3
0x2dc3  ldstr    aTheContextMust// "The context must contain a key named 'o"...
0x2dc8  ldstr    aContext// "context"
0x2dcd  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x2dd2  throw
0x2dd3  ldarg.1
0x2dd4  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x2dd9  stloc.0
0x2dda  ldarg.2
0x2ddb  ldstr    aOrganizationid_0// "organizationId"
0x2de0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::get_Item(void)
0x2de5  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x2dea  stloc.1
0x2deb  ldarg.0
0x2dec  ldfld    class Microsoft.Xrm.Async.Bridges.Providers.Crm.ICrmRegistry Microsoft.Xrm.Async.Bridges.Flighting.OrgRegKeyFlightClient::registry
0x2df1  ldloc.1
0x2df2  ldstr    asc_5A68// "_"
0x2df7  ldloc.0
0x2df8  call     string [mscorlib]System.String::Concat(string, string, string)
0x2dfd  callvirt T0x2B000075
0x2e02  ldloca.s 2
0x2e04  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x2e09  pop
0x2e0a  ldloc.2
0x2e0b  ret
```
