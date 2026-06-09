# Microsoft.Crm.Extensibility.OData.CrmODataUtilities::TryReturnTrackingFieldFromNextLink

- ea: `0x212a0`
- end: `0x212d5`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataUtilities::TryReturnTrackingFieldFromNextLink`
- size: `53`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x21270`
- `0x21290`

## callees

- `0x1d550`
- `0x202c0`
- `0x212a0`

## string_xrefs

- `0x212a7`: `$skiptoken`
- `0x212b4`: `$skiptoken`

## pseudocode

```c

```

## disassembly

```asm
0x212a0  ldsfld   string [mscorlib]System.String::Empty
0x212a5  stloc.0
0x212a6  ldarg.0
0x212a7  ldstr    aSkiptoken// "$skiptoken"
0x212ac  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x212b1  brfalse.s loc_212BF
0x212b3  ldarg.0
0x212b4  ldstr    aSkiptoken// "$skiptoken"
0x212b9  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x212be  stloc.0
0x212bf  ldloc.0
0x212c0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x212c5  brtrue.s loc_212D3
0x212c7  ldloc.0
0x212c8  call     class Microsoft.Crm.Extensibility.OData.CrmODataPagingCookie Microsoft.Crm.Extensibility.OData.CrmODataUtilities::DeserializePagingCookie(string batchCookie)
0x212cd  callvirt instance bool Microsoft.Crm.Extensibility.OData.CrmODataPagingCookie::get_IsTracking()
0x212d2  ret
0x212d3  ldarg.1
0x212d4  ret
```
