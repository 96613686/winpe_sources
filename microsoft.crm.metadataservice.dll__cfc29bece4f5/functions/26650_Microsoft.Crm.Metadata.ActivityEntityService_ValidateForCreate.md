# Microsoft.Crm.Metadata.ActivityEntityService::ValidateForCreate

- ea: `0x26650`
- end: `0x267c2`
- name: `Microsoft.Crm.Metadata.ActivityEntityService::ValidateForCreate`
- size: `370`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callees

- `0x26650`
- `0x2cb30`
- `0x2cba0`
- `0x2cc00`
- `0x2cf30`
- `0x2d030`
- `0x2d050`
- `0x2d090`
- `0x2d0b0`
- `0x2d1b0`
- `0x2d530`
- `0x36160`
- `0x361c0`
- `0x39dd0`
- `0x39ea0`

## string_xrefs

- `0x26725`: `A custom entity defined as an activity already cannot have MailMerge enabled.`

## pseudocode

```c

```

## disassembly

```asm
0x26650  ldarg.3
0x26651  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x26656  stloc.0
0x26657  ldarg.0
0x26658  ldarg.1
0x26659  ldarg.2
0x2665a  ldloc.0
0x2665b  call     instance void Microsoft.Crm.Metadata.EntityService::ValidateEntityNameAndLabels(class Microsoft.Crm.Metadata.EntityCreateInfo entityInfo, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext sqlContext)
0x26660  ldarg.1
0x26661  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OwnershipTypes Microsoft.Crm.Metadata.EntityCreateInfo::get_OwnershipTypeMask()
0x26666  ldc.i4.1
0x26667  beq.s    loc_266A0
0x26669  ldarg.1
0x2666a  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OwnershipTypes Microsoft.Crm.Metadata.EntityCreateInfo::get_OwnershipTypeMask()
0x2666f  ldc.i4.2
0x26670  beq.s    loc_266A0
0x26672  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x26677  ldstr    aOwnershiptypem_0// "OwnershipTypeMask: {0} is not valid for"...
0x2667c  ldc.i4.1
0x2667d  newarr   [mscorlib]System.Object
0x26682  dup
0x26683  ldc.i4.0
0x26684  ldarg.1
0x26685  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OwnershipTypes Microsoft.Crm.Metadata.EntityCreateInfo::get_OwnershipTypeMask()
0x2668a  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OwnershipTypes
0x2668f  stelem.ref
0x26690  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x26695  ldc.i4   0x8004F120
0x2669a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x2669f  throw
0x266a0  ldarg.1
0x266a1  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_HasRelatedActivities()
0x266a6  brfalse.s loc_266C0
0x266a8  ldarg.2
0x266a9  callvirt instance bool [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::get_IsInternalSolutionContext()
0x266ae  brtrue.s loc_266C0
0x266b0  ldstr    aACustomEntityD// "A custom entity defined as an activity "...
0x266b5  ldc.i4   0x8004F121
0x266ba  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x266bf  throw
0x266c0  ldarg.1
0x266c1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityCreateInfo::get_EntityDescription()
0x266c6  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_CanBeInCustomEntityAssociation()
0x266cb  brfalse.s loc_266DD
0x266cd  ldstr    aActivitiesCann// "Activities cannot participate in custom"...
0x266d2  ldc.i4   0x80044332
0x266d7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x266dc  throw
0x266dd  ldarg.2
0x266de  callvirt instance bool [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::get_IsInternalSolutionContext()
0x266e3  brtrue.s loc_266FD
0x266e5  ldarg.1
0x266e6  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_AvailableOffline()
0x266eb  brtrue.s loc_266FD
0x266ed  ldstr    aACustomEntityD_0// "A custom entity defined as an activity "...
0x266f2  ldc.i4   0x8004F122
0x266f7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x266fc  throw
0x266fd  ldarg.1
0x266fe  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_HasRelatedNotes()
0x26703  brtrue.s loc_2671D
0x26705  ldarg.2
0x26706  callvirt instance bool [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::get_IsInternalSolutionContext()
0x2670b  brtrue.s loc_2671D
0x2670d  ldstr    aACustomEntityD_1// "A custom entity defined as an activity "...
0x26712  ldc.i4   0x8004F123
0x26717  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x2671c  throw
0x2671d  ldarg.1
0x2671e  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_IsMailMergeEnabled()
0x26723  brfalse.s loc_26735
0x26725  ldstr    aACustomEntityD_2// "A custom entity defined as an activity "...
0x2672a  ldc.i4   0x8004F124
0x2672f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x26734  throw
0x26735  ldarg.0
0x26736  ldarg.1
0x26737  callvirt instance class Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Metadata.EntityCreateInfo::get_PrimaryField()
0x2673c  ldloc.0
0x2673d  callvirt instance void Microsoft.Crm.Metadata.EntityService::ValidatePrimaryAttributeProperties(class Microsoft.Crm.Metadata.AttributeInfo attributeInfo, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x26742  ldarg.1
0x26743  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_IsActivityParty()
0x26748  brfalse.s loc_26762
0x2674a  ldarg.2
0x2674b  callvirt instance bool [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::get_IsInternalSolutionContext()
0x26750  brtrue.s loc_26762
0x26752  ldstr    aAnEntityThatIs// "An entity that is defined as an activit"...
0x26757  ldc.i4   0x80048501
0x2675c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x26761  throw
0x26762  ldtoken  [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ActivityTypeMasks
0x26767  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2676c  ldarg.1
0x2676d  callvirt instance int32 Microsoft.Crm.Metadata.EntityCreateInfo::get_ActivityTypeMask()
0x26772  box      [mscorlib]System.Int32
0x26777  call     bool [mscorlib]System.Enum::IsDefined(class [mscorlib]System.Type, object)
0x2677c  brtrue.s loc_2678E
0x2677e  ldstr    aTheActivitytyp// "The ActivityTypeMask property must be s"...
0x26783  ldc.i4   0x80040203
0x26788  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x2678d  throw
0x2678e  ldarg.1
0x2678f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityCreateInfo::get_EntityDescription()
0x26794  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_IsCustomEntity()
0x26799  brfalse.s loc_267A7
0x2679b  ldarg.0
0x2679c  ldarg.1
0x2679d  callvirt instance string Microsoft.Crm.Metadata.EntityCreateInfo::get_EntitySetName()
0x267a2  call     instance void Microsoft.Crm.Metadata.EntityService::ValidateEntitySetNameIsCompliant(string entitySetName)
0x267a7  ldarg.1
0x267a8  callvirt instance string Microsoft.Crm.Metadata.EntityCreateInfo::get_EntitySetName()
0x267ad  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x267b2  brtrue.s loc_267C1
0x267b4  ldarg.0
0x267b5  ldarg.1
0x267b6  callvirt instance string Microsoft.Crm.Metadata.EntityCreateInfo::get_EntitySetName()
0x267bb  ldloc.0
0x267bc  call     instance void Microsoft.Crm.Metadata.EntityService::ValidateEntitySetNameIsUnique(string entitySetName, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext sqlContext)
0x267c1  ret
```
