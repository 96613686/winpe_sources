# Microsoft.Xrm.Async.Bridges.Flighting.MasterRegKeyFlightClient::IsFeatureEnabled

- ea: `0x2d20`
- end: `0x2d70`
- name: `Microsoft.Xrm.Async.Bridges.Flighting.MasterRegKeyFlightClient::IsFeatureEnabled`
- size: `80`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x2ce0`
- `0x2d20`

## string_xrefs

- `0x2d28`: `A non-empty featureName is required.`
- `0x2d2d`: `featureName`

## pseudocode

```c

```

## disassembly

```asm
0x2d20  ldarg.1
0x2d21  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2d26  brfalse.s loc_2D38
0x2d28  ldstr    aANonEmptyFeatu// "A non-empty featureName is required."
0x2d2d  ldstr    aFeaturename// "featureName"
0x2d32  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x2d37  throw
0x2d38  ldarg.1
0x2d39  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x2d3e  stloc.0
0x2d3f  ldarg.0
0x2d40  ldfld    class Microsoft.Xrm.Async.Bridges.Providers.Crm.ICrmRegistry Microsoft.Xrm.Async.Bridges.Flighting.MasterRegKeyFlightClient::registry
0x2d45  ldloc.0
0x2d46  callvirt T0x2B000075
0x2d4b  ldloca.s 1
0x2d4d  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x2d52  pop
0x2d53  ldarg.0
0x2d54  ldfld    class Microsoft.Xrm.Async.Bridges.Flighting.IFlightClient Microsoft.Xrm.Async.Bridges.Flighting.MasterRegKeyFlightClient::innerFlightClient
0x2d59  brtrue.s loc_2D5D
0x2d5b  ldloc.1
0x2d5c  ret
0x2d5d  ldloc.1
0x2d5e  brfalse.s loc_2D6E
0x2d60  ldarg.0
0x2d61  ldfld    class Microsoft.Xrm.Async.Bridges.Flighting.IFlightClient Microsoft.Xrm.Async.Bridges.Flighting.MasterRegKeyFlightClient::innerFlightClient
0x2d66  ldarg.1
0x2d67  ldarg.2
0x2d68  callvirt instance bool Microsoft.Xrm.Async.Bridges.Flighting.IFlightClient::IsFeatureEnabled(string featureName, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> context)
0x2d6d  ret
0x2d6e  ldc.i4.0
0x2d6f  ret
```
