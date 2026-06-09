# Microsoft.Crm.Common.Application.WebServices.YammerConfigWebService::BeginAdminGroupAutoComplete

- ea: `0x740`
- end: `0x763`
- name: `Microsoft.Crm.Common.Application.WebServices.YammerConfigWebService::BeginAdminGroupAutoComplete`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x520`

## pseudocode

```c

```

## disassembly

```asm
0x740  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x745  call     void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.YammerState::EnsureUserCanConfigureYammer(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation)
0x74a  ldarg.0
0x74b  call     instance class [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.YammerProxy Microsoft.Crm.Common.Application.WebServices.YammerConfigWebService::GetProxy()
0x750  ldarg.1
0x751  ldstr    aGroup7// "group:7"
0x756  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<string> [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.YammerProxy::AutoCompleteAsync(string, string)
0x75b  ldarg.2
0x75c  ldarg.3
0x75d  call     T0x2B000005
0x762  ret
```
