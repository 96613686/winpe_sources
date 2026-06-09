# <>c__DisplayClass22_0::<DeleteNavigationRef>b__0

- ea: `0x31ff0`
- end: `0x32024`
- name: `<>c__DisplayClass22_0::<DeleteNavigationRef>b__0`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x11b40`
- `0x12d50`

## string_xrefs

- `0x31ff6`: `DeleteNavigationRef`

## pseudocode

```c

```

## disassembly

```asm
0x31ff0  ldarg.0
0x31ff1  ldfld    class Microsoft.Crm.Extensibility.OData.EntityController <>c__DisplayClass22_0::<>4__this
0x31ff6  ldstr    aDeletenavigati// "DeleteNavigationRef"
0x31ffb  ldarg.0
0x31ffc  ldfld    string <>c__DisplayClass22_0::entityName
0x32001  call     instance void Microsoft.Crm.Extensibility.OData.EntityController::AddRequestInfoToTelemetry(string methodName, string entitySetName)
0x32006  ldarg.0
0x32007  ldfld    class Microsoft.Crm.Extensibility.OData.EntityController <>c__DisplayClass22_0::<>4__this
0x3200c  ldarg.0
0x3200d  ldflda   string <>c__DisplayClass22_0::entityName
0x32012  ldarg.0
0x32013  ldfld    string <>c__DisplayClass22_0::key
0x32018  ldarg.0
0x32019  ldfld    string <>c__DisplayClass22_0::navigation
0x3201e  call     instance class [System.Web.Http]System.Web.Http.IHttpActionResult Microsoft.Crm.Extensibility.OData.EntityController::DeleteNavigationRefImplementation(string& entityName, string key, string navigation)
0x32023  ret
```
