# <>c__DisplayClass23_0::<DeleteNavigationKeyRef>b__0

- ea: `0x32050`
- end: `0x3208a`
- name: `<>c__DisplayClass23_0::<DeleteNavigationKeyRef>b__0`
- size: `58`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x11b40`
- `0x12df0`

## string_xrefs

- `0x32056`: `DeleteNavigationKeyRef`

## pseudocode

```c

```

## disassembly

```asm
0x32050  ldarg.0
0x32051  ldfld    class Microsoft.Crm.Extensibility.OData.EntityController <>c__DisplayClass23_0::<>4__this
0x32056  ldstr    aDeletenavigati_0// "DeleteNavigationKeyRef"
0x3205b  ldarg.0
0x3205c  ldfld    string <>c__DisplayClass23_0::entityName
0x32061  call     instance void Microsoft.Crm.Extensibility.OData.EntityController::AddRequestInfoToTelemetry(string methodName, string entitySetName)
0x32066  ldarg.0
0x32067  ldfld    class Microsoft.Crm.Extensibility.OData.EntityController <>c__DisplayClass23_0::<>4__this
0x3206c  ldarg.0
0x3206d  ldflda   string <>c__DisplayClass23_0::entityName
0x32072  ldarg.0
0x32073  ldfld    string <>c__DisplayClass23_0::key
0x32078  ldarg.0
0x32079  ldfld    string <>c__DisplayClass23_0::navigation
0x3207e  ldarg.0
0x3207f  ldfld    string <>c__DisplayClass23_0::navigationKey
0x32084  call     instance class [System.Web.Http]System.Web.Http.IHttpActionResult Microsoft.Crm.Extensibility.OData.EntityController::DeleteNavigationKeyRefImplementation(string& entityName, string key, string navigation, string navigationKey)
0x32089  ret
```
