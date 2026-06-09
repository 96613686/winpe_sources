# Microsoft.Crm.Common.Application.Platform.ActivityBase::FixStateCode_0

- ea: `0x2710`
- end: `0x277d`
- name: `Microsoft.Crm.Common.Application.Platform.ActivityBase::FixStateCode_0`
- size: `109`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x26f0`

## callees

- `0x2710`

## pseudocode

```c

```

## disassembly

```asm
0x2710  ldarg.0
0x2711  ldstr    aStatuscode// "statuscode"
0x2716  call     instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x271b  stloc.0
0x271c  ldloc.0
0x271d  brfalse.s loc_277C
0x271f  ldloc.0
0x2720  unbox.any [mscorlib]System.Int32
0x2725  stloc.1
0x2726  ldarg.0
0x2727  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Metadata()
0x272c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x2731  ldstr    aStatuscode// "statuscode"
0x2736  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Item(!!T0)
0x273b  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StatusAttributeMetadata
0x2740  stloc.2
0x2741  ldloc.2
0x2742  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IStatusOptionsByValueCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StatusAttributeMetadata::get_StatusOptions()
0x2747  ldloc.1
0x2748  callvirt instance bool class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEnumOptionsByValueCollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StatusOption>::ContainsValue(int32)
0x274d  brfalse.s loc_277C
0x274f  ldloc.2
0x2750  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IStatusOptionsByValueCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StatusAttributeMetadata::get_StatusOptions()
0x2755  ldloc.1
0x2756  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEnumOptionsByValueCollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StatusOption>::get_Item(!!T0)
0x275b  stloc.3
0x275c  ldarg.0
0x275d  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_EntityName()
0x2762  ldloc.3
0x2763  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StatusOption::get_State()
0x2768  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::ConvertStateCodeToString(string, int32)
0x276d  stloc.s  4
0x276f  ldarg.0
0x2770  ldstr    aStatecode// "statecode"
0x2775  ldloc.s  4
0x2777  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x277c  ret
```
