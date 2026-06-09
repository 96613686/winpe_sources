# Microsoft.Crm.Platform.SolutionAwareComponents.MPOComponentActionHelper::SetInstancePropertiesOnEntity

- ea: `0x34810`
- end: `0x34858`
- name: `Microsoft.Crm.Platform.SolutionAwareComponents.MPOComponentActionHelper::SetInstancePropertiesOnEntity`
- size: `72`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x33260`
- `0x33470`
- `0x33780`
- `0x33c40`
- `0x34100`
- `0x34240`

## callees

- `0x35b80`
- `0x35bc0`
- `0x35be0`

## string_xrefs

- `0x34842`: `componentstate`
- `0x34827`: `overwritetime`

## pseudocode

```c

```

## disassembly

```asm
0x34810  ldarg.1
0x34811  ldstr    aSolutionid_0// "solutionid"
0x34816  ldarg.0
0x34817  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x3481c  box      [mscorlib]System.Guid
0x34821  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x34826  ldarg.1
0x34827  ldstr    aOverwritetime_0// "overwritetime"
0x3482c  ldarg.0
0x3482d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_OverwriteTime()
0x34832  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_UniversalTimeWithMilliseconds()
0x34837  box      [mscorlib]System.DateTime
0x3483c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x34841  ldarg.1
0x34842  ldstr    aComponentstate// "componentstate"
0x34847  ldarg.0
0x34848  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_ComponentState()
0x3484d  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState
0x34852  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x34857  ret
```
