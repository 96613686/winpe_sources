# Microsoft.Crm.ScaleGroupApi.Filters.ScaleGroupApiAuditFilterAttribute::GetOrganizationId

- ea: `0x2360`
- end: `0x2391`
- name: `Microsoft.Crm.ScaleGroupApi.Filters.ScaleGroupApiAuditFilterAttribute::GetOrganizationId`
- size: `49`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2120`
- `0x21e0`

## callees

- `0x2360`

## pseudocode

```c

```

## disassembly

```asm
0x2360  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2365  stloc.0
0x2366  ldarg.0
0x2367  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [System.Web.Http]System.Web.Http.Routing.IHttpRouteData::get_Values()
0x236c  ldstr    aOrganizationid// "organizationId"
0x2371  ldloca.s 1
0x2373  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x2378  brfalse.s loc_238F
0x237a  ldloc.1
0x237b  callvirt instance string [mscorlib]System.Object::ToString()
0x2380  ldloca.s 0
0x2382  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x2387  brtrue.s loc_238F
0x2389  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x238e  stloc.0
0x238f  ldloc.0
0x2390  ret
```
