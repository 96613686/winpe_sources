# Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::AssignQueryStringGuid

- ea: `0xc490`
- end: `0xc4bb`
- name: `Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::AssignQueryStringGuid`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xa450`
- `0xc160`

## callees

- `0xc490`

## pseudocode

```c

```

## disassembly

```asm
0xc490  ldarg.0
0xc491  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xc496  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xc49b  ldarg.1
0xc49c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xc4a1  stloc.0
0xc4a2  ldloc.0
0xc4a3  brfalse.s loc_C4B5
0xc4a5  ldloc.0
0xc4a6  callvirt instance int32 [mscorlib]System.String::get_Length()
0xc4ab  ldc.i4.0
0xc4ac  ble.s    loc_C4B5
0xc4ae  ldloc.0
0xc4af  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xc4b4  ret
0xc4b5  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xc4ba  ret
```
