# Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::AssignStringQueryStringGuid

- ea: `0xc4c0`
- end: `0xc503`
- name: `Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::AssignStringQueryStringGuid`
- size: `67`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x9d10`
- `0xa450`
- `0xb0e0`

## callees

- `0xc4c0`

## pseudocode

```c

```

## disassembly

```asm
0xc4c0  ldarg.0
0xc4c1  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xc4c6  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xc4cb  ldarg.1
0xc4cc  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xc4d1  stloc.0
0xc4d2  ldloc.0
0xc4d3  brfalse.s loc_C4FD
0xc4d5  ldloc.0
0xc4d6  callvirt instance int32 [mscorlib]System.String::get_Length()
0xc4db  ldc.i4.0
0xc4dc  ble.s    loc_C4FD
0xc4de  ldloca.s 1
0xc4e0  ldloc.0
0xc4e1  call     instance void [mscorlib]System.Guid::.ctor(string)
0xc4e6  ldloca.s 1
0xc4e8  ldstr    aB// "B"
0xc4ed  call     instance string [mscorlib]System.Guid::ToString(string)
0xc4f2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc4f7  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0xc4fc  ret
0xc4fd  ldsfld   string [mscorlib]System.String::Empty
0xc502  ret
```
