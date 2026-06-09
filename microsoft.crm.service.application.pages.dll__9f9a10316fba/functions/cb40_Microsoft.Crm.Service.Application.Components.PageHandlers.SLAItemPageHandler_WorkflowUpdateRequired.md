# Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::WorkflowUpdateRequired

- ea: `0xcb40`
- end: `0xcb7a`
- name: `Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::WorkflowUpdateRequired`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0xcac0`

## callees

- `0xcb40`

## string_xrefs

- `0xcb58`: `successconditionsxml`
- `0xcb6a`: `applicablewhenxml`

## pseudocode

```c

```

## disassembly

```asm
0xcb40  ldarg.1
0xcb41  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_Data()
0xcb46  ldstr    aWarnafter// "warnafter"
0xcb4b  callvirt instance bool [mscorlib]System.String::Contains(string)
0xcb50  brtrue.s loc_CB76
0xcb52  ldarg.1
0xcb53  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_Data()
0xcb58  ldstr    aSuccessconditi// "successconditionsxml"
0xcb5d  callvirt instance bool [mscorlib]System.String::Contains(string)
0xcb62  brtrue.s loc_CB76
0xcb64  ldarg.1
0xcb65  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_Data()
0xcb6a  ldstr    aApplicablewhen// "applicablewhenxml"
0xcb6f  callvirt instance bool [mscorlib]System.String::Contains(string)
0xcb74  brfalse.s loc_CB78
0xcb76  ldc.i4.1
0xcb77  ret
0xcb78  ldc.i4.0
0xcb79  ret
```
