# Microsoft.Xrm.Async.Bridges.Flighting.FlightClientExtensions::IsCloudAsyncFlightEnabled

- ea: `0x2c90`
- end: `0x2cc1`
- name: `Microsoft.Xrm.Async.Bridges.Flighting.FlightClientExtensions::IsCloudAsyncFlightEnabled`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x2ce0`

## pseudocode

```c

```

## disassembly

```asm
0x2c90  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x2c95  dup
0x2c96  ldstr    aOrganizationid_0// "organizationId"
0x2c9b  ldarga.s 2
0x2c9d  constrained. [mscorlib]System.Guid
0x2ca3  callvirt instance string [mscorlib]System.Object::ToString()
0x2ca8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x2cad  stloc.0
0x2cae  ldarg.0
0x2caf  ldstr    aCloudasync// "CloudAsync:"
0x2cb4  ldarg.1
0x2cb5  call     string [mscorlib]System.String::Concat(string, string)
0x2cba  ldloc.0
0x2cbb  callvirt instance bool Microsoft.Xrm.Async.Bridges.Flighting.IFlightClient::IsFeatureEnabled(string featureName, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> context)
0x2cc0  ret
```
