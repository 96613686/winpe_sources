# Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::SetSLAKPILabel

- ea: `0xc900`
- end: `0xc94f`
- name: `Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::SetSLAKPILabel`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0xc720`

## callees

- `0xc900`

## pseudocode

```c

```

## disassembly

```asm
0xc900  ldarg.1
0xc901  ldarg.2
0xc902  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0xc907  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormSection
0xc90c  stloc.0
0xc90d  ldloc.0
0xc90e  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xc913  ldc.i4.0
0xc914  callvirt instance class [System.Web]System.Web.UI.Control [System.Web]System.Web.UI.ControlCollection::get_Item(int32)
0xc919  castclass [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormRow
0xc91e  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xc923  ldc.i4.1
0xc924  callvirt instance class [System.Web]System.Web.UI.Control [System.Web]System.Web.UI.ControlCollection::get_Item(int32)
0xc929  castclass [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormCell
0xc92e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xc933  ldstr    aSlakpi// "SLAKPI"
0xc938  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc93d  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormControlWithLabel::set_Label(string)
0xc942  leave.s  loc_C94E
0xc944  ldloc.0
0xc945  brfalse.s loc_C94D
0xc947  ldloc.0
0xc948  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc94d  endfinally
0xc94e  ret
```
