# Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.ServiceAvailabilityRulePage::AssignStringQueryStringGuid

- ea: `0xabe0`
- end: `0xac23`
- name: `Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.ServiceAvailabilityRulePage::AssignStringQueryStringGuid`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xa950`

## callees

- `0xabe0`

## pseudocode

```c

```

## disassembly

```asm
0xabe0  ldarg.0
0xabe1  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xabe6  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xabeb  ldarg.1
0xabec  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xabf1  stloc.0
0xabf2  ldloc.0
0xabf3  brfalse.s loc_AC1D
0xabf5  ldloc.0
0xabf6  callvirt instance int32 [mscorlib]System.String::get_Length()
0xabfb  ldc.i4.0
0xabfc  ble.s    loc_AC1D
0xabfe  ldloca.s 1
0xac00  ldloc.0
0xac01  call     instance void [mscorlib]System.Guid::.ctor(string)
0xac06  ldloca.s 1
0xac08  ldstr    aB// "B"
0xac0d  call     instance string [mscorlib]System.Guid::ToString(string)
0xac12  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xac17  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0xac1c  ret
0xac1d  ldsfld   string [mscorlib]System.String::Empty
0xac22  ret
```
