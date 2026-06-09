# Microsoft.Crm.Metadata.EntityKeyService::ValidateAllAttributes

- ea: `0x2e1f0`
- end: `0x2e464`
- name: `Microsoft.Crm.Metadata.EntityKeyService::ValidateAllAttributes`
- size: `628`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x2de80`

## callees

- `0x2d860`
- `0x2d870`
- `0x2d8b0`
- `0x2dfd0`
- `0x2e1f0`
- `0x2ebd0`

## string_xrefs

- `0x2e2e9`: `The following duplicate attribute names were provided for this key definition: {0}. Remove the duplicates and try again.`

## pseudocode

```c

```

## disassembly

```asm
0x2e1f0  ldarg.0
0x2e1f1  ldarg.1
0x2e1f2  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.EntityKeyCreateInfo::get_EntityId()
0x2e1f7  ldarg.3
0x2e1f8  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x2e1fd  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection Microsoft.Crm.Metadata.EntityKeyService::GetAllAttributes(valuetype [mscorlib]System.Guid entityId, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x2e202  stloc.0
0x2e203  ldarg.1
0x2e204  callvirt instance valuetype [mscorlib]System.Guid[] Microsoft.Crm.Metadata.EntityKeyCreateInfo::get_KeyAttributeIds()
0x2e209  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid> <>c::<>9__14_0
0x2e20e  dup
0x2e20f  brtrue.s loc_2E228
0x2e211  pop
0x2e212  ldsfld   class <>c <>c::<>9
0x2e217  ldftn    instance valuetype [mscorlib]System.Guid <>c::<ValidateAllAttributes>b__14_0(valuetype [mscorlib]System.Guid id)
0x2e21d  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::.ctor(object, native int)
0x2e222  dup
0x2e223  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid> <>c::<>9__14_0
0x2e228  call     T0x2B00001D
0x2e22d  ldsfld   class [mscorlib]System.Func`2<class [System.Core]System.Linq.IGrouping`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>, bool> <>c::<>9__14_1
0x2e232  dup
0x2e233  brtrue.s loc_2E24C
0x2e235  pop
0x2e236  ldsfld   class <>c <>c::<>9
0x2e23b  ldftn    instance bool <>c::<ValidateAllAttributes>b__14_1(class [System.Core]System.Linq.IGrouping`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid> grp)
0x2e241  newobj   instance void class [mscorlib]System.Func`2<class [System.Core]System.Linq.IGrouping`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>, bool>::.ctor(object, native int)
0x2e246  dup
0x2e247  stsfld   class [mscorlib]System.Func`2<class [System.Core]System.Linq.IGrouping`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>, bool> <>c::<>9__14_1
0x2e24c  call     T0x2B00001E
0x2e251  ldsfld   class [mscorlib]System.Func`2<class [System.Core]System.Linq.IGrouping`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>, valuetype [mscorlib]System.Guid> <>c::<>9__14_2
0x2e256  dup
0x2e257  brtrue.s loc_2E270
0x2e259  pop
0x2e25a  ldsfld   class <>c <>c::<>9
0x2e25f  ldftn    instance valuetype [mscorlib]System.Guid <>c::<ValidateAllAttributes>b__14_2(class [System.Core]System.Linq.IGrouping`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid> grp)
0x2e265  newobj   instance void class [mscorlib]System.Func`2<class [System.Core]System.Linq.IGrouping`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>, valuetype [mscorlib]System.Guid>::.ctor(object, native int)
0x2e26a  dup
0x2e26b  stsfld   class [mscorlib]System.Func`2<class [System.Core]System.Linq.IGrouping`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>, valuetype [mscorlib]System.Guid> <>c::<>9__14_2
0x2e270  call     T0x2B00001F
0x2e275  stloc.1
0x2e276  ldloc.1
0x2e277  brfalse  loc_2E31E
0x2e27c  ldloc.1
0x2e27d  call     T0x2B000020
0x2e282  brfalse  loc_2E31E
0x2e287  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x2e28c  stloc.s  4
0x2e28e  ldloc.1
0x2e28f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid>::GetEnumerator()
0x2e294  stloc.s  5
0x2e296  br.s     loc_2E2CD
0x2e298  ldloc.s  5
0x2e29a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Guid>::get_Current()
0x2e29f  stloc.s  6
0x2e2a1  ldarg.3
0x2e2a2  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2e2a7  ldloc.s  6
0x2e2a9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetAttribute(valuetype [mscorlib]System.Guid)
0x2e2ae  stloc.s  7
0x2e2b0  ldloc.s  7
0x2e2b2  brfalse.s loc_2E2CD
0x2e2b4  ldloc.s  4
0x2e2b6  ldloc.s  7
0x2e2b8  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Name()
0x2e2bd  ldstr    asc_83CFE// ", "
0x2e2c2  call     string [mscorlib]System.String::Concat(string, string)
0x2e2c7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2e2cc  pop
0x2e2cd  ldloc.s  5
0x2e2cf  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2e2d4  brtrue.s loc_2E298
0x2e2d6  leave.s  loc_2E2E4
0x2e2d8  ldloc.s  5
0x2e2da  brfalse.s loc_2E2E3
0x2e2dc  ldloc.s  5
0x2e2de  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2e2e3  endfinally
0x2e2e4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2e2e9  ldstr    aTheFollowingDu// "The following duplicate attribute names"...
0x2e2ee  ldc.i4.1
0x2e2ef  newarr   [mscorlib]System.Object
0x2e2f4  dup
0x2e2f5  ldc.i4.0
0x2e2f6  ldloc.s  4
0x2e2f8  callvirt instance string [mscorlib]System.Object::ToString()
0x2e2fd  ldc.i4.2
0x2e2fe  newarr   [mscorlib]System.Char
0x2e303  dup
0x2e304  ldc.i4.0
0x2e305  ldc.i4.s 0x2C
0x2e307  stelem.i2
0x2e308  dup
0x2e309  ldc.i4.1
0x2e30a  ldc.i4.s 0x20
0x2e30c  stelem.i2
0x2e30d  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x2e312  stelem.ref
0x2e313  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2e318  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmNotSupportedException::.ctor(string)
0x2e31d  throw
0x2e31e  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::.ctor()
0x2e323  stloc.2
0x2e324  ldloc.0
0x2e325  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::GetEnumerator()
0x2e32a  stloc.s  8
0x2e32c  br.s     loc_2E350
0x2e32e  ldloc.s  8
0x2e330  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Current()
0x2e335  stloc.s  9
0x2e337  ldloc.2
0x2e338  ldloc.s  9
0x2e33a  ldstr    aAttributeid// "attributeid"
0x2e33f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x2e344  unbox.any [mscorlib]System.Guid
0x2e349  ldloc.s  9
0x2e34b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::Add(var<u1>, !!T0)
0x2e350  ldloc.s  8
0x2e352  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2e357  brtrue.s loc_2E32E
0x2e359  leave.s  loc_2E367
0x2e35b  ldloc.s  8
0x2e35d  brfalse.s loc_2E366
0x2e35f  ldloc.s  8
0x2e361  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2e366  endfinally
0x2e367  ldc.i4.0
0x2e368  conv.i8
0x2e369  stloc.3
0x2e36a  ldarg.1
0x2e36b  callvirt instance valuetype [mscorlib]System.Guid[] Microsoft.Crm.Metadata.EntityKeyCreateInfo::get_KeyAttributeIds()
0x2e370  stloc.s  0xA
0x2e372  ldc.i4.0
0x2e373  stloc.s  0xB
0x2e375  br       loc_2E458
0x2e37a  ldloc.s  0xA
0x2e37c  ldloc.s  0xB
0x2e37e  ldelem   [mscorlib]System.Guid
0x2e383  stloc.s  0xC
0x2e385  ldloc.2
0x2e386  ldloc.s  0xC
0x2e388  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::ContainsKey(var<u1>)
0x2e38d  brfalse.s loc_2E3B5
0x2e38f  ldarg.0
0x2e390  ldloc.2
0x2e391  ldloc.s  0xC
0x2e393  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Item(void)
0x2e398  call     instance void Microsoft.Crm.Metadata.EntityKeyService::ValidateAttributeForAlternateKey(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity attribute)
0x2e39d  ldloc.3
0x2e39e  ldloc.2
0x2e39f  ldloc.s  0xC
0x2e3a1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Item(void)
0x2e3a6  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity)
0x2e3ab  call     int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityKeyMetadata::GetAttributeSizeForIndex(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription)
0x2e3b0  conv.i8
0x2e3b1  add
0x2e3b2  stloc.3
0x2e3b3  br.s     loc_2E429
0x2e3b5  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x2e3ba  ldarg.1
0x2e3bb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityKeyDescriptionPropertyBag Microsoft.Crm.Metadata.EntityKeyCreateInfo::get_EntityKeyDescription()
0x2e3c0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityKeyDescription::get_EntityId()
0x2e3c5  ldstr    aEntity_0// "Entity"
0x2e3ca  ldc.i4.1
0x2e3cb  newarr   [mscorlib]System.String
0x2e3d0  dup
0x2e3d1  ldc.i4.0
0x2e3d2  ldstr    aName// "name"
0x2e3d7  stelem.ref
0x2e3d8  ldarg.3
0x2e3d9  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x2e3de  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntity(valuetype [mscorlib]System.Guid, string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x2e3e3  stloc.s  0xD
0x2e3e5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2e3ea  ldstr    aAttribute0IsNo// "Attribute: {0} is not part of {1} Entit"...
0x2e3ef  ldc.i4.2
0x2e3f0  newarr   [mscorlib]System.Object
0x2e3f5  dup
0x2e3f6  ldc.i4.0
0x2e3f7  ldloc.2
0x2e3f8  ldloc.s  0xC
0x2e3fa  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Item(void)
0x2e3ff  ldstr    aName// "name"
0x2e404  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x2e409  stelem.ref
0x2e40a  dup
0x2e40b  ldc.i4.1
0x2e40c  ldloc.s  0xD
0x2e40e  ldstr    aName// "name"
0x2e413  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x2e418  stelem.ref
0x2e419  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2e41e  ldc.i4   0x8006088F
0x2e423  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x2e428  throw
0x2e429  ldloc.3
0x2e42a  ldarg.2
0x2e42b  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_MaximumIndexSizeInBytes()
0x2e430  conv.i8
0x2e431  ble.s    loc_2E452
0x2e433  ldc.i4   0x80060895
0x2e438  ldc.i4.1
0x2e439  newarr   [mscorlib]System.Object
0x2e43e  dup
0x2e43f  ldc.i4.0
0x2e440  ldarg.2
0x2e441  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_MaximumIndexSizeInBytes()
0x2e446  box      [mscorlib]System.Int32
0x2e44b  stelem.ref
0x2e44c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x2e451  throw
0x2e452  ldloc.s  0xB
0x2e454  ldc.i4.1
0x2e455  add
0x2e456  stloc.s  0xB
0x2e458  ldloc.s  0xB
0x2e45a  ldloc.s  0xA
0x2e45c  ldlen
0x2e45d  conv.i4
0x2e45e  blt      loc_2E37A
0x2e463  ret
```
