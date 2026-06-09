# <>c__DisplayClass8_0::<DeleteEntity>b__0

- ea: `0x31ac0`
- end: `0x31aee`
- name: `<>c__DisplayClass8_0::<DeleteEntity>b__0`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x11b40`
- `0x11eb0`

## string_xrefs

- `0x31ac6`: `DeleteEntity`

## pseudocode

```c

```

## disassembly

```asm
0x31ac0  ldarg.0
0x31ac1  ldfld    class Microsoft.Crm.Extensibility.OData.EntityController <>c__DisplayClass8_0::<>4__this
0x31ac6  ldstr    aDeleteentity// "DeleteEntity"
0x31acb  ldarg.0
0x31acc  ldfld    string <>c__DisplayClass8_0::entityName
0x31ad1  call     instance void Microsoft.Crm.Extensibility.OData.EntityController::AddRequestInfoToTelemetry(string methodName, string entitySetName)
0x31ad6  ldarg.0
0x31ad7  ldfld    class Microsoft.Crm.Extensibility.OData.EntityController <>c__DisplayClass8_0::<>4__this
0x31adc  ldarg.0
0x31add  ldflda   string <>c__DisplayClass8_0::entityName
0x31ae2  ldarg.0
0x31ae3  ldfld    string <>c__DisplayClass8_0::key
0x31ae8  call     instance class [System.Web.Http]System.Web.Http.IHttpActionResult Microsoft.Crm.Extensibility.OData.EntityController::DeleteEntityImplementation(string& entityName, string key)
0x31aed  ret
```
