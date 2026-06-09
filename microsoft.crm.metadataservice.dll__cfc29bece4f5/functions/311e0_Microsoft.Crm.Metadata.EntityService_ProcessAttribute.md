# Microsoft.Crm.Metadata.EntityService::ProcessAttribute

- ea: `0x311e0`
- end: `0x3131d`
- name: `Microsoft.Crm.Metadata.EntityService::ProcessAttribute`
- size: `317`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x310b0`

## callees

- `0x18490`
- `0x184d0`
- `0x1c130`
- `0x1e420`
- `0x1e610`
- `0x21ac0`
- `0x261d0`
- `0x311e0`
- `0x31320`
- `0x313f0`

## string_xrefs

- `0x3122b`: `Cannot create attribute {0} since the attribute is a system field`
- `0x312c7`: `Cannot update attribute {0} since the attribute is a system field`

## pseudocode

```c

```

## disassembly

```asm
0x311e0  ldarg.0
0x311e1  ldarg.3
0x311e2  call     void Microsoft.Crm.Metadata.AttributeService::ValidatePrimaryNameUniqueness(class Microsoft.Crm.Metadata.AttributeInfo attributeInfo, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x311e7  ldarg.0
0x311e8  ldarg.1
0x311e9  ldarg.s  4
0x311eb  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.EntityService::TryGetExistingAttribute(class Microsoft.Crm.Metadata.AttributeInfo attributeInfo, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity> existedAttributeList, bool lookupNameMatches)
0x311f0  stloc.0
0x311f1  ldloc.0
0x311f2  brtrue   loc_312AC
0x311f7  ldarg.2
0x311f8  ldarg.0
0x311f9  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeInfo::get_EntityId()
0x311fe  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IMetadataAction> [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::GetAttributeCreateActionDictionary(valuetype [mscorlib]System.Guid)
0x31203  stloc.1
0x31204  ldloc.1
0x31205  ldarg.0
0x31206  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_Name()
0x3120b  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IMetadataAction>::ContainsKey(var<u1>)
0x31210  brfalse.s loc_31282
0x31212  ldarg.s  5
0x31214  brfalse.s loc_3124F
0x31216  ldarg.0
0x31217  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_Name()
0x3121c  ldarg.s  6
0x3121e  ldc.i4.5
0x3121f  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x31224  brtrue.s loc_3124F
0x31226  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3122b  ldstr    aCannotCreateAt_0// "Cannot create attribute {0} since the a"...
0x31230  ldc.i4.1
0x31231  newarr   [mscorlib]System.Object
0x31236  dup
0x31237  ldc.i4.0
0x31238  ldarg.0
0x31239  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_Name()
0x3123e  stelem.ref
0x3123f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x31244  ldc.i4   0x80047009
0x31249  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x3124e  throw
0x3124f  ldloc.1
0x31250  ldarg.0
0x31251  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_Name()
0x31256  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IMetadataAction>::get_Item(void)
0x3125b  stloc.2
0x3125c  ldarg.2
0x3125d  ldloc.2
0x3125e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::GetAttributeDescription(class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IMetadataAction)
0x31263  stloc.3
0x31264  ldloc.3
0x31265  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AttributeId()
0x3126a  ldarg.0
0x3126b  ldloc.3
0x3126c  ldarg.2
0x3126d  ldloc.2
0x3126e  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::GetAttributeCreateLabels(class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IMetadataAction)
0x31273  ldarg.2
0x31274  ldarg.2
0x31275  ldloc.2
0x31276  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::GetContextModifierOption(class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.IMetadataAction)
0x3127b  ldarg.3
0x3127c  call     void Microsoft.Crm.Metadata.AttributeService::UpdateSystemAttributeInternal(valuetype [mscorlib]System.Guid attributeId, class Microsoft.Crm.Metadata.AttributeInfo newAttributeInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag systemPropertyBag, class [mscorlib]System.Collections.ArrayList localizedLabels, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption option, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x31281  ret
0x31282  ldarg.0
0x31283  call     bool Microsoft.Crm.Metadata.EntityService::IsAttributeValidForCreate(class Microsoft.Crm.Metadata.AttributeInfo attributeInfo)
0x31288  brtrue.s loc_31295
0x3128a  ldarg.2
0x3128b  callvirt instance bool [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::get_IsInternalSolutionContext()
0x31290  brfalse  loc_3131C
0x31295  ldarg.0
0x31296  ldarg.2
0x31297  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3129c  ldarg.0
0x3129d  ldc.i4.1
0x3129e  ldarg.3
0x3129f  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption Microsoft.Crm.Metadata.AttributeService::GetContextModifierOption(valuetype [mscorlib]System.Guid attributeId, class Microsoft.Crm.Metadata.AttributeInfo info, bool newAttribute, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x312a4  ldarg.3
0x312a5  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeService::CreateInternal(class Microsoft.Crm.Metadata.AttributeInfo attributeInfo, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption modifierOption, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x312aa  pop
0x312ab  ret
0x312ac  ldarg.s  5
0x312ae  brfalse.s loc_312EB
0x312b0  ldloc.0
0x312b1  ldstr    aIscustomfield// "iscustomfield"
0x312b6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x312bb  unbox.any [mscorlib]System.Boolean
0x312c0  brtrue.s loc_312EB
0x312c2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x312c7  ldstr    aCannotUpdateAt// "Cannot update attribute {0} since the a"...
0x312cc  ldc.i4.1
0x312cd  newarr   [mscorlib]System.Object
0x312d2  dup
0x312d3  ldc.i4.0
0x312d4  ldarg.0
0x312d5  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_Name()
0x312da  stelem.ref
0x312db  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x312e0  ldc.i4   0x80047009
0x312e5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x312ea  throw
0x312eb  ldloc.0
0x312ec  ldstr    aAttributeid// "attributeid"
0x312f1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x312f6  unbox.any [mscorlib]System.Guid
0x312fb  ldarg.0
0x312fc  ldarg.2
0x312fd  ldc.i4.1
0x312fe  ldloc.0
0x312ff  ldstr    aAttributeid// "attributeid"
0x31304  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x31309  unbox.any [mscorlib]System.Guid
0x3130e  ldarg.0
0x3130f  ldc.i4.0
0x31310  ldarg.3
0x31311  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption Microsoft.Crm.Metadata.AttributeService::GetContextModifierOption(valuetype [mscorlib]System.Guid attributeId, class Microsoft.Crm.Metadata.AttributeInfo info, bool newAttribute, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x31316  ldarg.3
0x31317  call     void Microsoft.Crm.Metadata.AttributeService::UpdateInternal(valuetype [mscorlib]System.Guid attributeId, class Microsoft.Crm.Metadata.AttributeInfo attributeInfo, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, bool mergeLabels, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption modifierOption, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3131c  ret
```
