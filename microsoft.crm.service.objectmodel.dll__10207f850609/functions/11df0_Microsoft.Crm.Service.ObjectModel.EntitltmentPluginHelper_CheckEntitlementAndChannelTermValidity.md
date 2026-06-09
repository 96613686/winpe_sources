# Microsoft.Crm.Service.ObjectModel.EntitltmentPluginHelper::CheckEntitlementAndChannelTermValidity

- ea: `0x11df0`
- end: `0x11e12`
- name: `Microsoft.Crm.Service.ObjectModel.EntitltmentPluginHelper::CheckEntitlementAndChannelTermValidity`
- size: `34`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x10830`
- `0x10b10`
- `0x11f70`

## callees

- `0x11d90`
- `0x11df0`

## pseudocode

```c

```

## disassembly

```asm
0x11df0  ldarg.0
0x11df1  brfalse.s loc_11E11
0x11df3  ldarg.0
0x11df4  ldstr    aRestrictcasecr// "restrictcasecreation"
0x11df9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x11dfe  unbox.any [mscorlib]System.Boolean
0x11e03  brfalse.s loc_11E11
0x11e05  ldarg.0
0x11e06  call     void Microsoft.Crm.Service.ObjectModel.EntitltmentPluginHelper::CheckTermsValidity(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity)
0x11e0b  ldarg.1
0x11e0c  call     void Microsoft.Crm.Service.ObjectModel.EntitltmentPluginHelper::CheckTermsValidity(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity)
0x11e11  ret
```
