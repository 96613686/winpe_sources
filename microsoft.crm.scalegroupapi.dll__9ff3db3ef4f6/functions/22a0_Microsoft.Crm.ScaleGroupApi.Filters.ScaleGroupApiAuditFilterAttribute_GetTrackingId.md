# Microsoft.Crm.ScaleGroupApi.Filters.ScaleGroupApiAuditFilterAttribute::GetTrackingId

- ea: `0x22a0`
- end: `0x22e9`
- name: `Microsoft.Crm.ScaleGroupApi.Filters.ScaleGroupApiAuditFilterAttribute::GetTrackingId`
- size: `73`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2080`
- `0x21e0`

## callees

- `0x22a0`

## pseudocode

```c

```

## disassembly

```asm
0x22a0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x22a5  stloc.0
0x22a6  ldarg.0
0x22a7  brfalse.s loc_22E7
0x22a9  ldarg.0
0x22aa  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [System.Web.Http]System.Web.Http.Routing.IHttpRouteData::get_Values()
0x22af  brfalse.s loc_22E7
0x22b1  ldarg.0
0x22b2  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [System.Web.Http]System.Web.Http.Routing.IHttpRouteData::get_Values()
0x22b7  ldstr    aTrackingid_0// "trackingid"
0x22bc  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::ContainsKey(var<u1>)
0x22c1  brfalse.s loc_22E7
0x22c3  ldarg.0
0x22c4  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [System.Web.Http]System.Web.Http.Routing.IHttpRouteData::get_Values()
0x22c9  ldstr    aTrackingid_0// "trackingid"
0x22ce  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::get_Item(void)
0x22d3  callvirt instance string [mscorlib]System.Object::ToString()
0x22d8  ldloca.s 0
0x22da  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x22df  brtrue.s loc_22E7
0x22e1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x22e6  stloc.0
0x22e7  ldloc.0
0x22e8  ret
```
