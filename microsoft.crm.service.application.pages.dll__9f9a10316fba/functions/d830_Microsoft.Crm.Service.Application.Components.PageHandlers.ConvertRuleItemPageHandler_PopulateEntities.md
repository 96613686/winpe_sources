# Microsoft.Crm.Service.Application.Components.PageHandlers.ConvertRuleItemPageHandler::PopulateEntities

- ea: `0xd830`
- end: `0xd87a`
- name: `Microsoft.Crm.Service.Application.Components.PageHandlers.ConvertRuleItemPageHandler::PopulateEntities`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0xd770`

## callees

- `0xd830`

## pseudocode

```c

```

## disassembly

```asm
0xd830  ldsfld   string [mscorlib]System.String::Empty
0xd835  ldc.i4.1
0xd836  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::.ctor(string, valuetype [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionSorting)
0xd83b  stloc.0
0xd83c  ldloc.0
0xd83d  ldc.i4.0
0xd83e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::set_DisplayGrouping(bool)
0xd843  ldc.i4.s 0x70
0xd845  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xd84a  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xd84f  stloc.1
0xd850  ldloc.0
0xd851  ldloc.1
0xd852  ldc.i4.2
0xd853  ldnull
0xd854  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::GetDisplayName(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle, class [mscorlib]System.Globalization.CultureInfo)
0xd859  ldloc.1
0xd85a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0xd85f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::AddItem(string, string)
0xd864  ldloc.0
0xd865  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::ExecuteSort()
0xd86a  ldloc.0
0xd86b  stloc.2
0xd86c  leave.s  loc_D878
0xd86e  ldloc.0
0xd86f  brfalse.s loc_D877
0xd871  ldloc.0
0xd872  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd877  endfinally
0xd878  ldloc.2
0xd879  ret
```
