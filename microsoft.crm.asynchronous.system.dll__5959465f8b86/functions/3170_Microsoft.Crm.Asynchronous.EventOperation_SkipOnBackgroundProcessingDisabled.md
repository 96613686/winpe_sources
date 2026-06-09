# Microsoft.Crm.Asynchronous.EventOperation::SkipOnBackgroundProcessingDisabled

- ea: `0x3170`
- end: `0x31a2`
- name: `Microsoft.Crm.Asynchronous.EventOperation::SkipOnBackgroundProcessingDisabled`
- size: `50`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x2db0`

## callees

- `0x3170`

## string_xrefs

- `0x317e`: `Microsoft.Crm.ServiceBus.ServiceBusPlugin`

## pseudocode

```c

```

## disassembly

```asm
0x3170  ldarg.1
0x3171  callvirt instance bool class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.GenericSharedOrganizationData`1<class [mscorlib]System.Reflection.Assembly>::get_IsSystem()
0x3176  brfalse.s loc_318A
0x3178  ldarg.2
0x3179  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeData::get_PluginTypeSimpleName()
0x317e  ldstr    aMicrosoftCrmSe// "Microsoft.Crm.ServiceBus.ServiceBusPlug"...
0x3183  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3188  brfalse.s loc_31A0
0x318a  ldarg.0
0x318b  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0x3190  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationSettings()
0x3195  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_OrganizationId()
0x319a  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.DisableBackgroundProcessingUtility::IsBackgroundProcessingDisabled(valuetype [mscorlib]System.Guid)
0x319f  ret
0x31a0  ldc.i4.0
0x31a1  ret
```
