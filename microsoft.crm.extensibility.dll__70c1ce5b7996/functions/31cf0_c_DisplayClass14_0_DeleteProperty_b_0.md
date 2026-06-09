# <>c__DisplayClass14_0::<DeleteProperty>b__0

- ea: `0x31cf0`
- end: `0x31d24`
- name: `<>c__DisplayClass14_0::<DeleteProperty>b__0`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x11b40`
- `0x12570`

## string_xrefs

- `0x31cf6`: `DeleteProperty`

## pseudocode

```c

```

## disassembly

```asm
0x31cf0  ldarg.0
0x31cf1  ldfld    class Microsoft.Crm.Extensibility.OData.EntityController <>c__DisplayClass14_0::<>4__this
0x31cf6  ldstr    aDeleteproperty// "DeleteProperty"
0x31cfb  ldarg.0
0x31cfc  ldfld    string <>c__DisplayClass14_0::entityName
0x31d01  call     instance void Microsoft.Crm.Extensibility.OData.EntityController::AddRequestInfoToTelemetry(string methodName, string entitySetName)
0x31d06  ldarg.0
0x31d07  ldfld    class Microsoft.Crm.Extensibility.OData.EntityController <>c__DisplayClass14_0::<>4__this
0x31d0c  ldarg.0
0x31d0d  ldflda   string <>c__DisplayClass14_0::entityName
0x31d12  ldarg.0
0x31d13  ldfld    string <>c__DisplayClass14_0::key
0x31d18  ldarg.0
0x31d19  ldfld    string <>c__DisplayClass14_0::propertyName
0x31d1e  call     instance class [System.Web.Http]System.Web.Http.IHttpActionResult Microsoft.Crm.Extensibility.OData.EntityController::DeletePropertyImplementation(string& entityName, string key, string propertyName)
0x31d23  ret
```
