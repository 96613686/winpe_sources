# Microsoft.Crm.Entities.SdkMessage::ReadAttribute

- ea: `0x3760`
- end: `0x37b7`
- name: `Microsoft.Crm.Entities.SdkMessage::ReadAttribute`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x3760`

## pseudocode

```c

```

## disassembly

```asm
0x3760  ldarg.3
0x3761  ldstr    aSdkmessagefilt_0// "sdkmessagefilters"
0x3766  call     bool [mscorlib]System.String::op_Equality(string, string)
0x376b  brfalse.s loc_3786
0x376d  ldarg.2
0x376e  ldarg.1
0x376f  ldstr    aSdkmessagefilt// "SdkMessageFilter"
0x3774  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IEntityDeserializationStrategy::ReadChildEntitiesCollection(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityDeserializationContext, string)
0x3779  stloc.0
0x377a  ldarg.0
0x377b  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Entities.SdkMessage::_requestFilters
0x3780  ldloc.0
0x3781  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::AddRange(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection)
0x3786  ldarg.3
0x3787  ldstr    aSdkmessagepair_0// "sdkmessagepairs"
0x378c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3791  brfalse.s loc_37AD
0x3793  ldarg.2
0x3794  ldarg.1
0x3795  ldstr    aSdkmessagepair// "SdkMessagePair"
0x379a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IEntityDeserializationStrategy::ReadChildEntitiesCollection(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityDeserializationContext, string)
0x379f  stloc.1
0x37a0  ldarg.0
0x37a1  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Entities.SdkMessage::_messagePairs
0x37a6  ldloc.1
0x37a7  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::AddRange(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection)
0x37ac  ret
0x37ad  ldarg.0
0x37ae  ldarg.1
0x37af  ldarg.2
0x37b0  ldarg.3
0x37b1  call     instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::ReadAttribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityDeserializationContext, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IEntityDeserializationStrategy, string)
0x37b6  ret
```
