# Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::GetParentPicklistAttributeList

- ea: `0xb4d0`
- end: `0xb50d`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::GetParentPicklistAttributeList`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x9600`
- `0xb4d0`

## pseudocode

```c

```

## disassembly

```asm
0xb4d0  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::.ctor()
0xb4d5  ldarg.2
0xb4d6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb4db  brtrue.s loc_B4E5
0xb4dd  ldarg.2
0xb4de  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Parse(string)
0xb4e3  br.s     loc_B4EA
0xb4e5  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xb4ea  stloc.0
0xb4eb  dup
0xb4ec  ldarg.1
0xb4ed  ldloc.0
0xb4ee  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.MultipleOptionSet::PopulateParentPicklistAttributeList(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select multipleSet, valuetype [mscorlib]System.Guid entityId, valuetype [mscorlib]System.Guid referencedOptionSetId)
0xb4f3  dup
0xb4f4  ldnull
0xb4f5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::set_Selected(string)
0xb4fa  callvirt instance string [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::get_InnerHtml()
0xb4ff  stloc.1
0xb500  leave.s  loc_B50B
0xb502  stloc.2
0xb503  ldarg.0
0xb504  ldloc.2
0xb505  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0xb50a  throw
0xb50b  ldloc.1
0xb50c  ret
```
