# <>c__DisplayClass24_0::<DeleteNavigationEntity>b__0

- ea: `0x320b0`
- end: `0x320ea`
- name: `<>c__DisplayClass24_0::<DeleteNavigationEntity>b__0`
- size: `58`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x11b40`
- `0x12e90`

## string_xrefs

- `0x320b6`: `DeleteNavigationEntity`

## pseudocode

```c

```

## disassembly

```asm
0x320b0  ldarg.0
0x320b1  ldfld    class Microsoft.Crm.Extensibility.OData.EntityController <>c__DisplayClass24_0::<>4__this
0x320b6  ldstr    aDeletenavigati_1// "DeleteNavigationEntity"
0x320bb  ldarg.0
0x320bc  ldfld    string <>c__DisplayClass24_0::entityName
0x320c1  call     instance void Microsoft.Crm.Extensibility.OData.EntityController::AddRequestInfoToTelemetry(string methodName, string entitySetName)
0x320c6  ldarg.0
0x320c7  ldfld    class Microsoft.Crm.Extensibility.OData.EntityController <>c__DisplayClass24_0::<>4__this
0x320cc  ldarg.0
0x320cd  ldflda   string <>c__DisplayClass24_0::entityName
0x320d2  ldarg.0
0x320d3  ldfld    string <>c__DisplayClass24_0::key
0x320d8  ldarg.0
0x320d9  ldfld    string <>c__DisplayClass24_0::navigation
0x320de  ldarg.0
0x320df  ldfld    string <>c__DisplayClass24_0::navigationKey
0x320e4  call     instance class [System.Web.Http]System.Web.Http.IHttpActionResult Microsoft.Crm.Extensibility.OData.EntityController::DeleteNavigationEntityImplementation(string& entityName, string key, string navigation, string navigationKey)
0x320e9  ret
```
