# Microsoft.Crm.Common.Application.Pages.Dialogs.ListBasicActivityPage::RetrieveCampaignActivity

- ea: `0x19500`
- end: `0x1954c`
- name: `Microsoft.Crm.Common.Application.Pages.Dialogs.ListBasicActivityPage::RetrieveCampaignActivity`
- size: `76`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x19610`
- `0x197d0`
- `0x19950`
- `0x19aa0`
- `0x19c30`

## callees

- `0x18d80`

## string_xrefs

- `0x19526`: `scheduledend`

## pseudocode

```c

```

## disassembly

```asm
0x19500  ldarg.0
0x19501  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x19506  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1950b  ldstr    aSids// "sIds"
0x19510  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x19515  stloc.0
0x19516  ldc.i4.2
0x19517  newarr   [mscorlib]System.String
0x1951c  dup
0x1951d  ldc.i4.0
0x1951e  ldstr    aRegardingobjec_0// "regardingobjectid"
0x19523  stelem.ref
0x19524  dup
0x19525  ldc.i4.1
0x19526  ldstr    aScheduledend// "scheduledend"
0x1952b  stelem.ref
0x1952c  pop
0x1952d  ldloca.s 1
0x1952f  ldloc.0
0x19530  call     instance void [mscorlib]System.Guid::.ctor(string)
0x19535  ldstr    aCampaignactivi// "campaignactivity"
0x1953a  ldloc.1
0x1953b  ldarg.0
0x1953c  callvirt instance string[] Microsoft.Crm.Common.Application.Pages.Dialogs.ListBasicActivityPage::GetCampaignActivityColumnSet()
0x19541  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x19546  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1954b  ret
```
