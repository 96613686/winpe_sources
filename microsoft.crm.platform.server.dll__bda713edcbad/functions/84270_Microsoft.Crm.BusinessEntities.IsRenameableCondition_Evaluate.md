# Microsoft.Crm.BusinessEntities.IsRenameableCondition::Evaluate

- ea: `0x84270`
- end: `0x84401`
- name: `Microsoft.Crm.BusinessEntities.IsRenameableCondition::Evaluate`
- size: `401`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x2e90`
- `0x82a40`
- `0x82a80`
- `0x84060`
- `0x84270`
- `0x84410`

## string_xrefs

- `0x843ac`: `isrenameable`
- `0x84296`: `IsRenameableCondition should only be applied to LocalizedLabels.  Current component type = {0}`

## pseudocode

```c

```

## disassembly

```asm
0x84270  ldarg.1
0x84271  ldstr    aEntity_0// "entity"
0x84276  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x8427b  ldarg.3
0x8427c  ldstr    aContext// "context"
0x84281  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x84286  ldarg.1
0x84287  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity::get_PlatformName()
0x8428c  ldstr    aLocalizedlabel// "LocalizedLabel"
0x84291  call     bool [mscorlib]System.String::op_Equality(string, string)
0x84296  ldstr    aIsrenameableco// "IsRenameableCondition should only be ap"...
0x8429b  ldc.i4.1
0x8429c  newarr   [mscorlib]System.Object
0x842a1  dup
0x842a2  ldc.i4.0
0x842a3  ldarg.1
0x842a4  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity::get_PlatformName()
0x842a9  stelem.ref
0x842aa  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string, object[])
0x842af  ldarg.1
0x842b0  ldstr    aLabel_2// "label"
0x842b5  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity::IsNull(string)
0x842ba  brfalse.s loc_842BE
0x842bc  ldc.i4.2
0x842bd  ret
0x842be  ldarg.1
0x842bf  ldstr    aObjectcolumnna// "objectcolumnname"
0x842c4  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity::IsNull(string)
0x842c9  brtrue   loc_843FF
0x842ce  ldarg.1
0x842cf  ldstr    aObjectcolumnna// "objectcolumnname"
0x842d4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity::get_Item(string)
0x842d9  castclass [mscorlib]System.String
0x842de  ldstr    aLocalizedname// "LocalizedName"
0x842e3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x842e8  brtrue.s loc_84325
0x842ea  ldarg.1
0x842eb  ldstr    aObjectcolumnna// "objectcolumnname"
0x842f0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity::get_Item(string)
0x842f5  castclass [mscorlib]System.String
0x842fa  ldstr    aDisplayname// "DisplayName"
0x842ff  call     bool [mscorlib]System.String::op_Equality(string, string)
0x84304  brtrue.s loc_84325
0x84306  ldarg.1
0x84307  ldstr    aObjectcolumnna// "objectcolumnname"
0x8430c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity::get_Item(string)
0x84311  castclass [mscorlib]System.String
0x84316  ldstr    aDisplayname_0// "displayname"
0x8431b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x84320  brfalse  loc_843FF
0x84325  ldarg.0
0x84326  ldarg.3
0x84327  call     instance class Microsoft.Crm.Dependency.ComponentDefinition[] Microsoft.Crm.BusinessEntities.IsRenameableCondition::RetrieveRenameableComponentTypes(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x8432c  ldnull
0x8432d  stloc.0
0x8432e  ldarg.1
0x8432f  ldstr    aLabeltypecode// "labeltypecode"
0x84334  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity::IsNull(string)
0x84339  brtrue.s loc_8434E
0x8433b  ldarg.1
0x8433c  ldstr    aLabeltypecode// "labeltypecode"
0x84341  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity::get_Item(string)
0x84346  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelTypeCode
0x8434b  stloc.1
0x8434c  br.s     loc_84368
0x8434e  ldarg.0
0x8434f  ldarg.1
0x84350  ldarg.3
0x84351  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity Microsoft.Crm.BusinessEntities.PropertyEvaluationConditionBase::RetrieveDatabaseEntity(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity entity, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x84356  stloc.0
0x84357  ldloc.0
0x84358  ldstr    aLabeltypecode// "labeltypecode"
0x8435d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity::get_Item(string)
0x84362  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelTypeCode
0x84367  stloc.1
0x84368  stloc.2
0x84369  ldc.i4.0
0x8436a  stloc.3
0x8436b  br       loc_843F6
0x84370  ldloc.2
0x84371  ldloc.3
0x84372  ldelem.ref
0x84373  stloc.s  4
0x84375  ldloc.1
0x84376  ldloc.s  4
0x84378  callvirt instance int32 Microsoft.Crm.Dependency.ComponentDefinition::get_LabelTypeCode()
0x8437d  bne.un.s loc_843F2
0x8437f  ldarg.0
0x84380  ldarg.1
0x84381  ldarg.3
0x84382  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity Microsoft.Crm.BusinessEntities.PropertyEvaluationConditionBase::RetrieveParentDatabaseEntity(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity entity, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x84387  stloc.s  5
0x84389  ldloc.s  5
0x8438b  brfalse.s loc_843FF
0x8438d  ldloc.s  5
0x8438f  ldarg.3
0x84390  call     bool Microsoft.Crm.BusinessEntities.IsManagedCondition::IsEntityManaged(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity entity, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x84395  brfalse.s loc_843FF
0x84397  ldloc.s  5
0x84399  ldstr    aIscustomizable// "iscustomizable"
0x8439e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity::get_Item(string)
0x843a3  unbox.any [mscorlib]System.Boolean
0x843a8  brfalse.s loc_843BD
0x843aa  ldloc.s  5
0x843ac  ldstr    aIsrenameable// "isrenameable"
0x843b1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity::get_Item(string)
0x843b6  unbox.any [mscorlib]System.Boolean
0x843bb  brtrue.s loc_843FF
0x843bd  ldloc.0
0x843be  brtrue.s loc_843C9
0x843c0  ldarg.0
0x843c1  ldarg.1
0x843c2  ldarg.3
0x843c3  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity Microsoft.Crm.BusinessEntities.PropertyEvaluationConditionBase::RetrieveDatabaseEntity(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity entity, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x843c8  stloc.0
0x843c9  ldloc.0
0x843ca  ldstr    aLabel_2// "label"
0x843cf  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity::get_Item(string)
0x843d4  castclass [mscorlib]System.String
0x843d9  ldarg.1
0x843da  ldstr    aLabel_2// "label"
0x843df  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity::get_Item(string)
0x843e4  castclass [mscorlib]System.String
0x843e9  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x843ee  brfalse.s loc_843FF
0x843f0  ldc.i4.1
0x843f1  ret
0x843f2  ldloc.3
0x843f3  ldc.i4.1
0x843f4  add
0x843f5  stloc.3
0x843f6  ldloc.3
0x843f7  ldloc.2
0x843f8  ldlen
0x843f9  conv.i4
0x843fa  blt      loc_84370
0x843ff  ldc.i4.2
0x84400  ret
```
