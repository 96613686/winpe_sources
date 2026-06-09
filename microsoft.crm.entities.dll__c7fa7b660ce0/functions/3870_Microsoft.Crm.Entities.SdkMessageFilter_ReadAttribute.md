# Microsoft.Crm.Entities.SdkMessageFilter::ReadAttribute

- ea: `0x3870`
- end: `0x38a1`
- name: `Microsoft.Crm.Entities.SdkMessageFilter::ReadAttribute`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x3870`

## pseudocode

```c

```

## disassembly

```asm
0x3870  ldarg.3
0x3871  ldstr    aSdkmessageproc_0// "sdkmessageprocessingstep"
0x3876  call     bool [mscorlib]System.String::op_Equality(string, string)
0x387b  brfalse.s loc_3897
0x387d  ldarg.2
0x387e  ldarg.1
0x387f  ldstr    aSdkmessageproc// "SdkMessageProcessingStep"
0x3884  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IEntityDeserializationStrategy::ReadChildEntitiesCollection(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityDeserializationContext, string)
0x3889  stloc.0
0x388a  ldarg.0
0x388b  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Entities.SdkMessageFilter::_filterSteps
0x3890  ldloc.0
0x3891  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::AddRange(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection)
0x3896  ret
0x3897  ldarg.0
0x3898  ldarg.1
0x3899  ldarg.2
0x389a  ldarg.3
0x389b  call     instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::ReadAttribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityDeserializationContext, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IEntityDeserializationStrategy, string)
0x38a0  ret
```
