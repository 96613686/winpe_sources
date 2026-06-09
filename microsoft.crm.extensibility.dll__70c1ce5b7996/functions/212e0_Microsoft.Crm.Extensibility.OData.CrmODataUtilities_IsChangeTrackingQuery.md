# Microsoft.Crm.Extensibility.OData.CrmODataUtilities::IsChangeTrackingQuery

- ea: `0x212e0`
- end: `0x212f1`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataUtilities::IsChangeTrackingQuery`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x11f10`

## callees

- `0x212e0`

## string_xrefs

- `0x212e1`: `$deltatoken`

## pseudocode

```c

```

## disassembly

```asm
0x212e0  ldarg.0
0x212e1  ldstr    aDeltatoken// "$deltatoken"
0x212e6  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x212eb  brfalse.s loc_212EF
0x212ed  ldc.i4.1
0x212ee  ret
0x212ef  ldc.i4.0
0x212f0  ret
```
