# Microsoft.Crm.Metadata.EntityService::ValidateQuickCreateForUpdateEntity

- ea: `0x3a250`
- end: `0x3a3ec`
- name: `Microsoft.Crm.Metadata.EntityService::ValidateQuickCreateForUpdateEntity`
- size: `412`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x39620`

## callees

- `0x326d0`
- `0x3a250`
- `0x3d230`
- `0x3d240`
- `0x3d7b0`

## string_xrefs

- `0x3a296`: `isairupdated`
- `0x3a2ad`: `isairupdated`
- `0x3a2c1`: `isairupdated`
- `0x3a2ce`: `isairupdated`
- `0x3a25b`: `isquickcreateenabled`
- `0x3a35b`: `isquickcreateenabled`
- `0x3a36c`: `isquickcreateenabled`
- `0x3a3a0`: `isquickcreateenabled`
- `0x3a322`: `Entity {0} : Quick create is not supported for non-refreshed Entity`
- `0x3a3be`: `Entity {0} : Quick create is not supported for this Entity`

## pseudocode

```c

```

## disassembly

```asm
0x3a250  ldarg.1
0x3a251  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityUpdateInfo::get_EntityDescription()
0x3a256  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::get_InnerEntityData()
0x3a25b  ldstr    aIsquickcreatee// "isquickcreateenabled"
0x3a260  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x3a265  brtrue.s loc_3A26F
0x3a267  ldarg.1
0x3a268  callvirt instance bool Microsoft.Crm.Metadata.EntityUpdateInfo::get_IsQuickCreateEnabled()
0x3a26d  br.s     loc_3A270
0x3a26f  ldc.i4.0
0x3a270  stloc.0
0x3a271  ldloc.0
0x3a272  brfalse  loc_3A35A
0x3a277  ldarg.s  4
0x3a279  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x3a27e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0x3a283  ldarg.s  4
0x3a285  call     bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SolutionsHelper::IsInternalSolution(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x3a28a  stloc.1
0x3a28b  ldarg.1
0x3a28c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityUpdateInfo::get_EntityDescription()
0x3a291  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::get_InnerEntityData()
0x3a296  ldstr    aIsairupdated// "isairupdated"
0x3a29b  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x3a2a0  brtrue.s loc_3A2BE
0x3a2a2  ldarg.1
0x3a2a3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityUpdateInfo::get_EntityDescription()
0x3a2a8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::get_InnerEntityData()
0x3a2ad  ldstr    aIsairupdated// "isairupdated"
0x3a2b2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x3a2b7  unbox.any [mscorlib]System.Boolean
0x3a2bc  br.s     loc_3A2BF
0x3a2be  ldc.i4.0
0x3a2bf  stloc.2
0x3a2c0  ldarg.2
0x3a2c1  ldstr    aIsairupdated// "isairupdated"
0x3a2c6  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x3a2cb  brtrue.s loc_3A2DF
0x3a2cd  ldarg.2
0x3a2ce  ldstr    aIsairupdated// "isairupdated"
0x3a2d3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x3a2d8  unbox.any [mscorlib]System.Boolean
0x3a2dd  br.s     loc_3A2E0
0x3a2df  ldc.i4.0
0x3a2e0  ldarg.2
0x3a2e1  ldstr    aIsintersect// "isintersect"
0x3a2e6  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x3a2eb  brtrue.s loc_3A2FF
0x3a2ed  ldarg.2
0x3a2ee  ldstr    aIsintersect// "isintersect"
0x3a2f3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x3a2f8  unbox.any [mscorlib]System.Boolean
0x3a2fd  br.s     loc_3A300
0x3a2ff  ldc.i4.0
0x3a300  stloc.3
0x3a301  brtrue.s loc_3A308
0x3a303  ldloc.1
0x3a304  ldloc.2
0x3a305  and
0x3a306  br.s     loc_3A309
0x3a308  ldc.i4.1
0x3a309  brtrue.s loc_3A317
0x3a30b  ldarg.3
0x3a30c  brfalse.s loc_3A314
0x3a30e  ldloc.3
0x3a30f  ldc.i4.0
0x3a310  ceq
0x3a312  br.s     loc_3A318
0x3a314  ldc.i4.0
0x3a315  br.s     loc_3A318
0x3a317  ldc.i4.1
0x3a318  brtrue   loc_3A3EB
0x3a31d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3a322  ldstr    aEntity0QuickCr// "Entity {0} : Quick create is not suppor"...
0x3a327  ldc.i4.1
0x3a328  newarr   [mscorlib]System.Object
0x3a32d  dup
0x3a32e  ldc.i4.0
0x3a32f  ldarg.2
0x3a330  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataAttributes()
0x3a335  ldstr    aLogicalname// "logicalname"
0x3a33a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeInfoCollection::get_Item(string)
0x3a33f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeInfo::get_Value()
0x3a344  castclass [mscorlib]System.String
0x3a349  stelem.ref
0x3a34a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3a34f  ldc.i4   0x80040203
0x3a354  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x3a359  throw
0x3a35a  ldarg.2
0x3a35b  ldstr    aIsquickcreatee// "isquickcreateenabled"
0x3a360  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x3a365  brtrue   loc_3A3EB
0x3a36a  ldloc.0
0x3a36b  ldarg.2
0x3a36c  ldstr    aIsquickcreatee// "isquickcreateenabled"
0x3a371  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x3a376  unbox.any [mscorlib]System.Boolean
0x3a37b  beq.s    loc_3A3EB
0x3a37d  ldarg.2
0x3a37e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataAttributes()
0x3a383  ldstr    aObjecttypecode_0// "objecttypecode"
0x3a388  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeInfoCollection::get_Item(string)
0x3a38d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeInfo::get_Value()
0x3a392  unbox.any [mscorlib]System.Int32
0x3a397  call     bool Microsoft.Crm.Metadata.EntityService::IsQuickCreateOnlySupported(int32 objectTypeCode)
0x3a39c  brfalse.s loc_3A3EB
0x3a39e  ldarg.1
0x3a39f  ldarg.2
0x3a3a0  ldstr    aIsquickcreatee// "isquickcreateenabled"
0x3a3a5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x3a3aa  unbox.any [mscorlib]System.Boolean
0x3a3af  callvirt instance void Microsoft.Crm.Metadata.EntityUpdateInfo::set_IsQuickCreateEnabled(bool value)
0x3a3b4  ldnull
0x3a3b5  ldarg.s  4
0x3a3b7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x3a3bc  ldc.i4.s 0x19
0x3a3be  ldstr    aEntity0QuickCr_0// "Entity {0} : Quick create is not suppor"...
0x3a3c3  ldc.i4.1
0x3a3c4  newarr   [mscorlib]System.Object
0x3a3c9  dup
0x3a3ca  ldc.i4.0
0x3a3cb  ldarg.2
0x3a3cc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataAttributes()
0x3a3d1  ldstr    aLogicalname// "logicalname"
0x3a3d6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeInfoCollection::get_Item(string)
0x3a3db  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeInfo::get_Value()
0x3a3e0  castclass [mscorlib]System.String
0x3a3e5  stelem.ref
0x3a3e6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3a3eb  ret
```
