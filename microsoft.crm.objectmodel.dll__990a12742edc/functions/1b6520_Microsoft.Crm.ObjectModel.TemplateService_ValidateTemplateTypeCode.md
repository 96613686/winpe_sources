# Microsoft.Crm.ObjectModel.TemplateService::ValidateTemplateTypeCode

- ea: `0x1b6520`
- end: `0x1b663c`
- name: `Microsoft.Crm.ObjectModel.TemplateService::ValidateTemplateTypeCode`
- size: `284`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1b61c0`
- `0x1b6640`

## callees

- `0x1b6520`

## string_xrefs

- `0x1b6524`: `templatetypecode`
- `0x1b653c`: `templatetypecode`
- `0x1b6558`: `templatetypecode`
- `0x1b6598`: `templatetypecode`
- `0x1b65de`: `templatetypecode`
- `0x1b661b`: `templatetypecode`
- `0x1b6530`: `The template type code is missing.`
- `0x1b660d`: `Template type code {0} is invalid`

## pseudocode

```c

```

## disassembly

```asm
0x1b6520  ldarg.2
0x1b6521  brtrue.s loc_1B653B
0x1b6523  ldarg.1
0x1b6524  ldstr    aTemplatetypeco// "templatetypecode"
0x1b6529  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x1b652e  brfalse.s loc_1B653B
0x1b6530  ldstr    aTheTemplateTyp// "The template type code is missing."
0x1b6535  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x1b653a  throw
0x1b653b  ldarg.1
0x1b653c  ldstr    aTemplatetypeco// "templatetypecode"
0x1b6541  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x1b6546  brtrue   loc_1B663B
0x1b654b  ldarg.1
0x1b654c  isinst   [Microsoft.Crm.Common.Entities]Microsoft.Crm.Common.Entities.Template
0x1b6551  stloc.0
0x1b6552  ldloc.0
0x1b6553  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x1b6558  ldstr    aTemplatetypeco// "templatetypecode"
0x1b655d  ldc.i4.1
0x1b655e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x1b6563  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PicklistAttributeMetadata
0x1b6568  stloc.1
0x1b6569  ldarg.3
0x1b656a  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1b656f  ldloc.1
0x1b6570  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumAttributeMetadata::get_OptionSetId()
0x1b6575  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEnumOptionByValueDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEnumOptionsByOptionSetId(valuetype [mscorlib]System.Guid)
0x1b657a  stloc.2
0x1b657b  ldloc.2
0x1b657c  brfalse.s loc_1B65C2
0x1b657e  ldloc.2
0x1b657f  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Generic.IDictionary`2<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::get_Values()
0x1b6584  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::GetEnumerator()
0x1b6589  stloc.3
0x1b658a  br.s     loc_1B65AE
0x1b658c  ldloc.3
0x1b658d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::get_Current()
0x1b6592  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Value()
0x1b6597  ldloc.0
0x1b6598  ldstr    aTemplatetypeco// "templatetypecode"
0x1b659d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1b65a2  unbox.any [mscorlib]System.Int32
0x1b65a7  bne.un.s loc_1B65AE
0x1b65a9  leave    loc_1B663B
0x1b65ae  ldloc.3
0x1b65af  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1b65b4  brtrue.s loc_1B658C
0x1b65b6  leave.s  loc_1B6608
0x1b65b8  ldloc.3
0x1b65b9  brfalse.s loc_1B65C1
0x1b65bb  ldloc.3
0x1b65bc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1b65c1  endfinally
0x1b65c2  ldloc.1
0x1b65c3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IPicklistOptionsByValueCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PicklistAttributeMetadata::get_PicklistOptions()
0x1b65c8  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PicklistOption>::GetEnumerator()
0x1b65cd  stloc.s  4
0x1b65cf  br.s     loc_1B65F1
0x1b65d1  ldloc.s  4
0x1b65d3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PicklistOption>::get_Current()
0x1b65d8  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Value()
0x1b65dd  ldloc.0
0x1b65de  ldstr    aTemplatetypeco// "templatetypecode"
0x1b65e3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1b65e8  unbox.any [mscorlib]System.Int32
0x1b65ed  bne.un.s loc_1B65F1
0x1b65ef  leave.s  loc_1B663B
0x1b65f1  ldloc.s  4
0x1b65f3  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1b65f8  brtrue.s loc_1B65D1
0x1b65fa  leave.s  loc_1B6608
0x1b65fc  ldloc.s  4
0x1b65fe  brfalse.s loc_1B6607
0x1b6600  ldloc.s  4
0x1b6602  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1b6607  endfinally
0x1b6608  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1b660d  ldstr    aTemplateTypeCo// "Template type code {0} is invalid"
0x1b6612  ldc.i4.1
0x1b6613  newarr   [mscorlib]System.Object
0x1b6618  dup
0x1b6619  ldc.i4.0
0x1b661a  ldloc.0
0x1b661b  ldstr    aTemplatetypeco// "templatetypecode"
0x1b6620  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1b6625  unbox.any [mscorlib]System.Int32
0x1b662a  box      [mscorlib]System.Int32
0x1b662f  stelem.ref
0x1b6630  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1b6635  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x1b663a  throw
0x1b663b  ret
```
