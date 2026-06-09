# Microsoft.Crm.BusinessEntities.IsComponentDeletionEnabledCondition::Evaluate

- ea: `0x83a70`
- end: `0x83b05`
- name: `Microsoft.Crm.BusinessEntities.IsComponentDeletionEnabledCondition::Evaluate`
- size: `149`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x82a40`
- `0x83a70`
- `0x83b30`
- `0x83b50`

## string_xrefs

- `0x83ad8`: `canbedeleted`
- `0x83af0`: `canbedeleted`

## pseudocode

```c

```

## disassembly

```asm
0x83a70  ldarg.1
0x83a71  ldstr    aEntity_0// "entity"
0x83a76  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x83a7b  ldarg.3
0x83a7c  ldstr    aContext// "context"
0x83a81  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x83a86  ldarg.1
0x83a87  call     bool Microsoft.Crm.BusinessEntities.IsComponentDeletionEnabledCondition::IsIncluded(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity entity)
0x83a8c  brfalse.s loc_83A98
0x83a8e  ldarg.1
0x83a8f  call     bool Microsoft.Crm.BusinessEntities.IsComponentDeletionEnabledCondition::IsExcluded(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity entity)
0x83a94  brtrue.s loc_83A98
0x83a96  ldc.i4.1
0x83a97  ret
0x83a98  ldarg.0
0x83a99  ldarg.1
0x83a9a  ldarg.3
0x83a9b  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity Microsoft.Crm.BusinessEntities.PropertyEvaluationConditionBase::RetrieveDatabaseEntity(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity entity, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x83aa0  stloc.0
0x83aa1  ldloc.0
0x83aa2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity::get_Metadata()
0x83aa7  ldstr    aIscustomizable// "iscustomizable"
0x83aac  ldarg.3
0x83aad  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IAttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntityMetadata::RetrieveAttributeByName(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x83ab2  stloc.1
0x83ab3  ldloc.1
0x83ab4  brfalse.s loc_83AD2
0x83ab6  ldloc.1
0x83ab7  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IAttributeMetadata::get_IsManagedProperty()
0x83abc  brfalse.s loc_83AD2
0x83abe  ldloc.0
0x83abf  ldstr    aIscustomizable// "iscustomizable"
0x83ac4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity::get_Item(string)
0x83ac9  unbox.any [mscorlib]System.Boolean
0x83ace  brtrue.s loc_83AD2
0x83ad0  ldc.i4.1
0x83ad1  ret
0x83ad2  ldloc.0
0x83ad3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity::get_Metadata()
0x83ad8  ldstr    aCanbedeleted// "canbedeleted"
0x83add  ldarg.3
0x83ade  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IAttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntityMetadata::RetrieveAttributeByName(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x83ae3  stloc.2
0x83ae4  ldloc.2
0x83ae5  brfalse.s loc_83B03
0x83ae7  ldloc.2
0x83ae8  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IAttributeMetadata::get_IsManagedProperty()
0x83aed  brfalse.s loc_83B03
0x83aef  ldloc.0
0x83af0  ldstr    aCanbedeleted// "canbedeleted"
0x83af5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity::get_Item(string)
0x83afa  unbox.any [mscorlib]System.Boolean
0x83aff  brtrue.s loc_83B03
0x83b01  ldc.i4.1
0x83b02  ret
0x83b03  ldc.i4.2
0x83b04  ret
```
