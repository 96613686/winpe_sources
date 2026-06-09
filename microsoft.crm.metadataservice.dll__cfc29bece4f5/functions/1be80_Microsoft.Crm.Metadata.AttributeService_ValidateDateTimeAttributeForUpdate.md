# Microsoft.Crm.Metadata.AttributeService::ValidateDateTimeAttributeForUpdate

- ea: `0x1be80`
- end: `0x1c04d`
- name: `Microsoft.Crm.Metadata.AttributeService::ValidateDateTimeAttributeForUpdate`
- size: `461`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1ff00`
- `0x2c080`

## callees

- `0x1be80`
- `0x1c050`
- `0x1c070`
- `0x1c090`

## string_xrefs

- `0x1c01a`: `The behavior of this Date and Time attribute cannot be changed to DateOnly unless the format is also updated to Date`

## pseudocode

```c

```

## disassembly

```asm
0x1be80  ldarg.0
0x1be81  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::get_InnerEntityData()
0x1be86  ldstr    aBehavior// "behavior"
0x1be8b  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNullOrNameInvalid(string)
0x1be90  brtrue   loc_1C02A
0x1be95  ldarg.1
0x1be96  ldstr    aBehavior// "behavior"
0x1be9b  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNullOrNameInvalid(string)
0x1bea0  brtrue   loc_1C02A
0x1bea5  ldarg.0
0x1bea6  ldstr    aBehavior// "behavior"
0x1beab  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x1beb0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1beb5  call     int32 [mscorlib]System.Convert::ToInt32(object, class [mscorlib]System.IFormatProvider)
0x1beba  stloc.0
0x1bebb  ldarg.0
0x1bebc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::get_InnerEntityData()
0x1bec1  ldstr    aAttributelogic// "attributelogicaltypeid"
0x1bec6  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNullOrNameInvalid(string)
0x1becb  brtrue.s loc_1BEDF
0x1becd  ldarg.0
0x1bece  ldstr    aAttributelogic// "attributelogicaltypeid"
0x1bed3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x1bed8  castclass [mscorlib]System.String
0x1bedd  br.s     loc_1BEE0
0x1bedf  ldnull
0x1bee0  stloc.1
0x1bee1  ldarg.1
0x1bee2  ldstr    aBehavior// "behavior"
0x1bee7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1beec  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1bef1  call     int32 [mscorlib]System.Convert::ToInt32(object, class [mscorlib]System.IFormatProvider)
0x1bef6  stloc.2
0x1bef7  ldarg.1
0x1bef8  ldstr    aAttributelogic// "attributelogicaltypeid"
0x1befd  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNullOrNameInvalid(string)
0x1bf02  brtrue.s loc_1BF16
0x1bf04  ldarg.1
0x1bf05  ldstr    aAttributelogic// "attributelogicaltypeid"
0x1bf0a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1bf0f  castclass [mscorlib]System.String
0x1bf14  br.s     loc_1BF17
0x1bf16  ldnull
0x1bf17  stloc.3
0x1bf18  ldarg.1
0x1bf19  ldstr    aLogicalname// "logicalname"
0x1bf1e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNullOrNameInvalid(string)
0x1bf23  brfalse.s loc_1BF37
0x1bf25  ldarg.1
0x1bf26  ldstr    aAttributeid// "attributeid"
0x1bf2b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1bf30  callvirt instance string [mscorlib]System.Object::ToString()
0x1bf35  br.s     loc_1BF47
0x1bf37  ldarg.1
0x1bf38  ldstr    aLogicalname// "logicalname"
0x1bf3d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1bf42  callvirt instance string [mscorlib]System.Object::ToString()
0x1bf47  stloc.s  4
0x1bf49  ldloc.2
0x1bf4a  ldloc.0
0x1bf4b  call     bool Microsoft.Crm.Metadata.AttributeService::IsDateTimeBehaviorTransitionValid(int32 existingBehavior, int32 newBehavior)
0x1bf50  brtrue.s loc_1BF62
0x1bf52  ldstr    aTheBehaviorVal// "The Behavior value of this attribute ca"...
0x1bf57  ldc.i4   0x800608A1
0x1bf5c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x1bf61  throw
0x1bf62  ldloc.0
0x1bf63  ldloc.2
0x1bf64  beq.s    loc_1BF9B
0x1bf66  ldarg.1
0x1bf67  ldstr    aAttributeid// "attributeid"
0x1bf6c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1bf71  unbox.any [mscorlib]System.Guid
0x1bf76  ldloc.0
0x1bf77  ldarg.2
0x1bf78  call     bool Microsoft.Crm.Metadata.AttributeService::IsValidDateTimeBehaviorChange(valuetype [mscorlib]System.Guid attributeId, int32 newBehavior, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x1bf7d  brtrue.s loc_1BF9B
0x1bf7f  ldstr    aTheBehaviorOfT// "The behavior of this Date and Time attr"...
0x1bf84  ldloc.s  4
0x1bf86  ldstr    aCanOnlyBeChang// " can only be changed to Date Only."
0x1bf8b  call     string [mscorlib]System.String::Concat(string, string, string)
0x1bf90  ldc.i4   0x800608A0
0x1bf95  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x1bf9a  throw
0x1bf9b  ldloc.0
0x1bf9c  ldloc.2
0x1bf9d  ldarg.1
0x1bf9e  ldstr    aIscustomfield// "iscustomfield"
0x1bfa3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1bfa8  unbox.any [mscorlib]System.Boolean
0x1bfad  ldarg.0
0x1bfae  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_EntityId()
0x1bfb3  ldarg.2
0x1bfb4  ldarg.3
0x1bfb5  call     bool Microsoft.Crm.Metadata.AttributeService::CanModifyBehaviorForCustomEntity(int32 newBehavior, int32 existingBehavior, bool isCustomField, valuetype [mscorlib]System.Guid entityId, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper)
0x1bfba  brtrue.s loc_1BFCC
0x1bfbc  ldstr    aCannotModifyTh// "Cannot modify the behavior if CanModify"...
0x1bfc1  ldc.i4   0x800608A1
0x1bfc6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x1bfcb  throw
0x1bfcc  ldloc.0
0x1bfcd  ldc.i4.2
0x1bfce  beq.s    loc_1BFD4
0x1bfd0  ldloc.2
0x1bfd1  ldc.i4.2
0x1bfd2  bne.un.s loc_1C003
0x1bfd4  ldloc.1
0x1bfd5  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DateTimeAttributeFormats::get_DateTime()
0x1bfda  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1bfdf  brfalse.s loc_1C003
0x1bfe1  ldstr    aYouCanTChangeT// "You can\uFFFDt change the format value "...
0x1bfe6  ldloc.s  4
0x1bfe8  call     string [mscorlib]System.String::Concat(string, string)
0x1bfed  ldc.i4   0x800608A2
0x1bff2  ldc.i4.1
0x1bff3  newarr   [mscorlib]System.Object
0x1bff8  dup
0x1bff9  ldc.i4.0
0x1bffa  ldloc.s  4
0x1bffc  stelem.ref
0x1bffd  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32, object[])
0x1c002  throw
0x1c003  ldloc.0
0x1c004  ldc.i4.2
0x1c005  bne.un.s loc_1C02A
0x1c007  ldloc.1
0x1c008  brtrue.s loc_1C02A
0x1c00a  ldloc.3
0x1c00b  brfalse.s loc_1C02A
0x1c00d  ldloc.3
0x1c00e  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DateTimeAttributeFormats::get_DateTime()
0x1c013  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1c018  brfalse.s loc_1C02A
0x1c01a  ldstr    aTheBehaviorOfT_0// "The behavior of this Date and Time attr"...
0x1c01f  ldc.i4   0x800608A2
0x1c024  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x1c029  throw
0x1c02a  ldarg.0
0x1c02b  ldstr    aAttributelogic// "attributelogicaltypeid"
0x1c030  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x1c035  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x1c03a  bne.un.s loc_1C04C
0x1c03c  ldstr    aTheFormatPrope// "The format property cannot be changed t"...
0x1c041  ldc.i4   0x800608A2
0x1c046  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x1c04b  throw
0x1c04c  ret
```
