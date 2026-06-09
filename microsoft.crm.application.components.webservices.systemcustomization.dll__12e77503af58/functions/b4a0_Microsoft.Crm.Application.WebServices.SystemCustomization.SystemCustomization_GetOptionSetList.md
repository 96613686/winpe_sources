# Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::GetOptionSetList

- ea: `0xb4a0`
- end: `0xb4c5`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::GetOptionSetList`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x9540`
- `0xb4a0`

## pseudocode

```c

```

## disassembly

```asm
0xb4a0  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::.ctor()
0xb4a5  dup
0xb4a6  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.MultipleOptionSet::PopulateOptionsList(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select multipleSet)
0xb4ab  dup
0xb4ac  ldnull
0xb4ad  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::set_Selected(string)
0xb4b2  callvirt instance string [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::get_InnerHtml()
0xb4b7  stloc.0
0xb4b8  leave.s  loc_B4C3
0xb4ba  stloc.1
0xb4bb  ldarg.0
0xb4bc  ldloc.1
0xb4bd  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0xb4c2  throw
0xb4c3  ldloc.0
0xb4c4  ret
```
