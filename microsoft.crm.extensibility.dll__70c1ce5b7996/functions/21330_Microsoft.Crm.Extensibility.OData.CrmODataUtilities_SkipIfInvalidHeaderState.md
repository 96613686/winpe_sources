# Microsoft.Crm.Extensibility.OData.CrmODataUtilities::SkipIfInvalidHeaderState

- ea: `0x21330`
- end: `0x2136b`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataUtilities::SkipIfInvalidHeaderState`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x11f10`

## callees

- `0x1d550`
- `0x202c0`
- `0x21330`

## string_xrefs

- `0x2133a`: `$skiptoken`
- `0x21347`: `$skiptoken`

## pseudocode

```c

```

## disassembly

```asm
0x21330  ldarg.0
0x21331  brfalse.s loc_21369
0x21333  ldsfld   string [mscorlib]System.String::Empty
0x21338  stloc.0
0x21339  ldarg.1
0x2133a  ldstr    aSkiptoken// "$skiptoken"
0x2133f  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x21344  brfalse.s loc_21352
0x21346  ldarg.1
0x21347  ldstr    aSkiptoken// "$skiptoken"
0x2134c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x21351  stloc.0
0x21352  ldloc.0
0x21353  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x21358  brtrue.s loc_21369
0x2135a  ldloc.0
0x2135b  call     class Microsoft.Crm.Extensibility.OData.CrmODataPagingCookie Microsoft.Crm.Extensibility.OData.CrmODataUtilities::DeserializePagingCookie(string batchCookie)
0x21360  callvirt instance bool Microsoft.Crm.Extensibility.OData.CrmODataPagingCookie::get_IsTracking()
0x21365  brtrue.s loc_21369
0x21367  ldc.i4.1
0x21368  ret
0x21369  ldc.i4.0
0x2136a  ret
```
