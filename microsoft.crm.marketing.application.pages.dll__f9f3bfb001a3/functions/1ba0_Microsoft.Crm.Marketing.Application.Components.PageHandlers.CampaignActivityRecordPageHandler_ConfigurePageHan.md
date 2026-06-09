# Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignActivityRecordPageHandler::ConfigurePageHandler

- ea: `0x1ba0`
- end: `0x1bc7`
- name: `Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignActivityRecordPageHandler::ConfigurePageHandler`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1040`

## pseudocode

```c

```

## disassembly

```asm
0x1ba0  ldarg.0
0x1ba1  call     instance void [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::ConfigurePageHandler()
0x1ba6  ldarg.0
0x1ba7  ldarg.0
0x1ba8  call     instance class [System.Web]System.Web.HttpRequest [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_Request()
0x1bad  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1bb2  ldstr    aId// "id"
0x1bb7  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1bbc  call     bool Microsoft.Crm.Marketing.Application.Components.EntityPageHeaders.CampaignActivityConfigHeader::GetCampaignActivityPropagationFlag(string entityId)
0x1bc1  stfld    bool Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignActivityRecordPageHandler::propFlag
0x1bc6  ret
```
