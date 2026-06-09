# Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::GetOriginalRecordId

- ea: `0x13fb0`
- end: `0x1402d`
- name: `Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::GetOriginalRecordId`
- size: `125`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x13630`

## callees

- `0x13fb0`

## string_xrefs

- `0x13fbb`: `RequestUri`

## pseudocode

```c

```

## disassembly

```asm
0x13fb0  ldarg.0
0x13fb1  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x13fb6  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x13fbb  ldstr    aRequesturi// "RequestUri"
0x13fc0  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x13fc5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x13fca  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x13fcf  stloc.0
0x13fd0  ldloc.0
0x13fd1  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x13fd6  ldstr    aExtraqs// "extraqs"
0x13fdb  callvirt instance bool class [System]System.Collections.Generic.SortedDictionary`2<string, string>::ContainsKey(var<u1>)
0x13fe0  brfalse.s loc_1402B
0x13fe2  ldstr    aDummy// "dummy"
0x13fe7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x13fec  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x13ff1  stloc.1
0x13ff2  ldloc.1
0x13ff3  ldloc.0
0x13ff4  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x13ff9  ldstr    aExtraqs// "extraqs"
0x13ffe  callvirt instance var<u1> class [System]System.Collections.Generic.SortedDictionary`2<string, string>::get_Item(void)
0x14003  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::AppendToQuery(string)
0x14008  ldloc.1
0x14009  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x1400e  ldstr    aId// "id"
0x14013  callvirt instance bool class [System]System.Collections.Generic.SortedDictionary`2<string, string>::ContainsKey(var<u1>)
0x14018  brfalse.s loc_1402B
0x1401a  ldloc.1
0x1401b  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x14020  ldstr    aId// "id"
0x14025  callvirt instance var<u1> class [System]System.Collections.Generic.SortedDictionary`2<string, string>::get_Item(void)
0x1402a  ret
0x1402b  ldnull
0x1402c  ret
```
