# Microsoft.Crm.MetadataService.Sdk.TypeMaps.PlatformToXrmOneToManyRelationshipMetadataPropertyMap::InitializeMap

- ea: `0x74520`
- end: `0x74b66`
- name: `Microsoft.Crm.MetadataService.Sdk.TypeMaps.PlatformToXrmOneToManyRelationshipMetadataPropertyMap::InitializeMap`
- size: `1606`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x74520`

## string_xrefs

- `0x74a2b`: `SecurityTypes`
- `0x74521`: `AssociatedMenuConfiguration`
- `0x74599`: `CascadeConfiguration`

## pseudocode

```c

```

## disassembly

```asm
0x74520  ldarg.0
0x74521  ldstr    aAssociatedmenu// "AssociatedMenuConfiguration"
0x74526  ldnull
0x74527  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase
0x7452c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x74531  ldstr    aDestination// "destination"
0x74536  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x7453b  stloc.0
0x7453c  ldloc.0
0x7453d  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata
0x74542  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x74547  call     class [System.Core]System.Linq.Expressions.UnaryExpression [System.Core]System.Linq.Expressions.Expression::Convert(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Type)
0x7454c  ldtoken  instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AssociatedMenuConfiguration [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata::get_AssociatedMenuConfiguration()
0x74551  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x74556  castclass [mscorlib]System.Reflection.MethodInfo
0x7455b  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x74560  ldc.i4.1
0x74561  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x74566  dup
0x74567  ldc.i4.0
0x74568  ldloc.0
0x74569  stelem.ref
0x7456a  call     T0x2B000071
0x7456f  ldsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_1
0x74574  dup
0x74575  brtrue.s loc_7458E
0x74577  pop
0x74578  ldsfld   class <>c <>c::<>9
0x7457d  ldftn    instance void <>c::<InitializeMap>b__4_1(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship source, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase destination, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x74583  newobj   instance void class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>::.ctor(object, native int)
0x74588  dup
0x74589  stsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_1
0x7458e  call     class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0> class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase>::CreateMapping(var<u1>, void, class [mscorlib]System.Func`3<var<u1>, !!T0, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>)
0x74593  callvirt instance void class Microsoft.Crm.MetadataService.Sdk.TypeMaps.CultureNeutralPropertyMap`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase>::SetPropertyMapping(string, class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0>)
0x74598  ldarg.0
0x74599  ldstr    aCascadeconfigu// "CascadeConfiguration"
0x7459e  ldnull
0x7459f  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase
0x745a4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x745a9  ldstr    aDestination// "destination"
0x745ae  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x745b3  stloc.0
0x745b4  ldloc.0
0x745b5  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata
0x745ba  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x745bf  call     class [System.Core]System.Linq.Expressions.UnaryExpression [System.Core]System.Linq.Expressions.Expression::Convert(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Type)
0x745c4  ldtoken  instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.CascadeConfiguration [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata::get_CascadeConfiguration()
0x745c9  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x745ce  castclass [mscorlib]System.Reflection.MethodInfo
0x745d3  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x745d8  ldc.i4.1
0x745d9  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x745de  dup
0x745df  ldc.i4.0
0x745e0  ldloc.0
0x745e1  stelem.ref
0x745e2  call     T0x2B000071
0x745e7  ldsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_3
0x745ec  dup
0x745ed  brtrue.s loc_74606
0x745ef  pop
0x745f0  ldsfld   class <>c <>c::<>9
0x745f5  ldftn    instance void <>c::<InitializeMap>b__4_3(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship source, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase destination, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x745fb  newobj   instance void class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>::.ctor(object, native int)
0x74600  dup
0x74601  stsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_3
0x74606  call     class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0> class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase>::CreateMapping(var<u1>, void, class [mscorlib]System.Func`3<var<u1>, !!T0, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>)
0x7460b  callvirt instance void class Microsoft.Crm.MetadataService.Sdk.TypeMaps.CultureNeutralPropertyMap`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase>::SetPropertyMapping(string, class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0>)
0x74610  ldarg.0
0x74611  ldstr    aIsvalidforadva_0// "IsValidForAdvancedFind"
0x74616  ldsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object> <>c::<>9__4_4
0x7461b  dup
0x7461c  brtrue.s loc_74635
0x7461e  pop
0x7461f  ldsfld   class <>c <>c::<>9
0x74624  ldftn    instance object <>c::<InitializeMap>b__4_4(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship source, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x7462a  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object>::.ctor(object, native int)
0x7462f  dup
0x74630  stsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object> <>c::<>9__4_4
0x74635  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase
0x7463a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7463f  ldstr    aDestination// "destination"
0x74644  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x74649  stloc.0
0x7464a  ldloc.0
0x7464b  ldtoken  instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase::get_IsValidForAdvancedFind()
0x74650  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x74655  castclass [mscorlib]System.Reflection.MethodInfo
0x7465a  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x7465f  ldtoken  [mscorlib]System.Object
0x74664  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x74669  call     class [System.Core]System.Linq.Expressions.UnaryExpression [System.Core]System.Linq.Expressions.Expression::Convert(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Type)
0x7466e  ldc.i4.1
0x7466f  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x74674  dup
0x74675  ldc.i4.0
0x74676  ldloc.0
0x74677  stelem.ref
0x74678  call     T0x2B000071
0x7467d  ldsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_6
0x74682  dup
0x74683  brtrue.s loc_7469C
0x74685  pop
0x74686  ldsfld   class <>c <>c::<>9
0x7468b  ldftn    instance void <>c::<InitializeMap>b__4_6(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship source, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase destination, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x74691  newobj   instance void class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>::.ctor(object, native int)
0x74696  dup
0x74697  stsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_6
0x7469c  call     class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0> class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase>::CreateMapping(var<u1>, void, class [mscorlib]System.Func`3<var<u1>, !!T0, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>)
0x746a1  callvirt instance void class Microsoft.Crm.MetadataService.Sdk.TypeMaps.CultureNeutralPropertyMap`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase>::SetPropertyMapping(string, class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0>)
0x746a6  ldarg.0
0x746a7  ldstr    aReferencedattr_0// "ReferencedAttribute"
0x746ac  ldsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object> <>c::<>9__4_7
0x746b1  dup
0x746b2  brtrue.s loc_746CB
0x746b4  pop
0x746b5  ldsfld   class <>c <>c::<>9
0x746ba  ldftn    instance object <>c::<InitializeMap>b__4_7(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship source, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x746c0  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object>::.ctor(object, native int)
0x746c5  dup
0x746c6  stsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object> <>c::<>9__4_7
0x746cb  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase
0x746d0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x746d5  ldstr    aDestination// "destination"
0x746da  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x746df  stloc.0
0x746e0  ldloc.0
0x746e1  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata
0x746e6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x746eb  call     class [System.Core]System.Linq.Expressions.UnaryExpression [System.Core]System.Linq.Expressions.Expression::Convert(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Type)
0x746f0  ldtoken  instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata::get_ReferencedAttribute()
0x746f5  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x746fa  castclass [mscorlib]System.Reflection.MethodInfo
0x746ff  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x74704  ldc.i4.1
0x74705  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x7470a  dup
0x7470b  ldc.i4.0
0x7470c  ldloc.0
0x7470d  stelem.ref
0x7470e  call     T0x2B000071
0x74713  ldsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_9
0x74718  dup
0x74719  brtrue.s loc_74732
0x7471b  pop
0x7471c  ldsfld   class <>c <>c::<>9
0x74721  ldftn    instance void <>c::<InitializeMap>b__4_9(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship source, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase destination, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x74727  newobj   instance void class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>::.ctor(object, native int)
0x7472c  dup
0x7472d  stsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_9
0x74732  call     class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0> class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase>::CreateMapping(var<u1>, void, class [mscorlib]System.Func`3<var<u1>, !!T0, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>)
0x74737  callvirt instance void class Microsoft.Crm.MetadataService.Sdk.TypeMaps.CultureNeutralPropertyMap`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase>::SetPropertyMapping(string, class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0>)
0x7473c  ldarg.0
0x7473d  ldstr    aReferencedenti_2// "ReferencedEntity"
0x74742  ldsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object> <>c::<>9__4_10
0x74747  dup
0x74748  brtrue.s loc_74761
0x7474a  pop
0x7474b  ldsfld   class <>c <>c::<>9
0x74750  ldftn    instance object <>c::<InitializeMap>b__4_10(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship source, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x74756  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object>::.ctor(object, native int)
0x7475b  dup
0x7475c  stsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object> <>c::<>9__4_10
0x74761  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase
0x74766  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7476b  ldstr    aDestination// "destination"
0x74770  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x74775  stloc.0
0x74776  ldloc.0
0x74777  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata
0x7477c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x74781  call     class [System.Core]System.Linq.Expressions.UnaryExpression [System.Core]System.Linq.Expressions.Expression::Convert(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Type)
0x74786  ldtoken  instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata::get_ReferencedEntity()
0x7478b  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x74790  castclass [mscorlib]System.Reflection.MethodInfo
0x74795  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x7479a  ldc.i4.1
0x7479b  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x747a0  dup
0x747a1  ldc.i4.0
0x747a2  ldloc.0
0x747a3  stelem.ref
0x747a4  call     T0x2B000071
0x747a9  ldsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_12
0x747ae  dup
0x747af  brtrue.s loc_747C8
0x747b1  pop
0x747b2  ldsfld   class <>c <>c::<>9
0x747b7  ldftn    instance void <>c::<InitializeMap>b__4_12(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship source, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase destination, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x747bd  newobj   instance void class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>::.ctor(object, native int)
0x747c2  dup
0x747c3  stsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_12
0x747c8  call     class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0> class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase>::CreateMapping(var<u1>, void, class [mscorlib]System.Func`3<var<u1>, !!T0, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>)
0x747cd  callvirt instance void class Microsoft.Crm.MetadataService.Sdk.TypeMaps.CultureNeutralPropertyMap`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase>::SetPropertyMapping(string, class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0>)
0x747d2  ldarg.0
0x747d3  ldstr    aReferencedenti_3// "ReferencedEntityNavigationPropertyName"
0x747d8  ldsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object> <>c::<>9__4_13
0x747dd  dup
0x747de  brtrue.s loc_747F7
0x747e0  pop
0x747e1  ldsfld   class <>c <>c::<>9
0x747e6  ldftn    instance object <>c::<InitializeMap>b__4_13(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship source, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x747ec  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object>::.ctor(object, native int)
0x747f1  dup
0x747f2  stsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object> <>c::<>9__4_13
0x747f7  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase
0x747fc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x74801  ldstr    aDestination// "destination"
0x74806  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x7480b  stloc.0
0x7480c  ldloc.0
0x7480d  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata
0x74812  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x74817  call     class [System.Core]System.Linq.Expressions.UnaryExpression [System.Core]System.Linq.Expressions.Expression::Convert(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Type)
0x7481c  ldtoken  instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata::get_ReferencedEntityNavigationPropertyName()
0x74821  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x74826  castclass [mscorlib]System.Reflection.MethodInfo
0x7482b  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x74830  ldc.i4.1
0x74831  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x74836  dup
0x74837  ldc.i4.0
0x74838  ldloc.0
0x74839  stelem.ref
0x7483a  call     T0x2B000071
0x7483f  ldsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_15
0x74844  dup
0x74845  brtrue.s loc_7485E
0x74847  pop
0x74848  ldsfld   class <>c <>c::<>9
0x7484d  ldftn    instance void <>c::<InitializeMap>b__4_15(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship source, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase destination, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x74853  newobj   instance void class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>::.ctor(object, native int)
0x74858  dup
0x74859  stsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_15
0x7485e  call     class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0> class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase>::CreateMapping(var<u1>, void, class [mscorlib]System.Func`3<var<u1>, !!T0, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>)
0x74863  callvirt instance void class Microsoft.Crm.MetadataService.Sdk.TypeMaps.CultureNeutralPropertyMap`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase>::SetPropertyMapping(string, class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0>)
0x74868  ldarg.0
0x74869  ldstr    aReferencingatt_2// "ReferencingAttribute"
0x7486e  ldsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object> <>c::<>9__4_16
0x74873  dup
0x74874  brtrue.s loc_7488D
0x74876  pop
0x74877  ldsfld   class <>c <>c::<>9
0x7487c  ldftn    instance object <>c::<InitializeMap>b__4_16(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship source, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x74882  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object>::.ctor(object, native int)
0x74887  dup
0x74888  stsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object> <>c::<>9__4_16
0x7488d  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase
0x74892  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x74897  ldstr    aDestination// "destination"
0x7489c  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x748a1  stloc.0
0x748a2  ldloc.0
0x748a3  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata
0x748a8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x748ad  call     class [System.Core]System.Linq.Expressions.UnaryExpression [System.Core]System.Linq.Expressions.Expression::Convert(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Type)
0x748b2  ldtoken  instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata::get_ReferencingAttribute()
0x748b7  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x748bc  castclass [mscorlib]System.Reflection.MethodInfo
0x748c1  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x748c6  ldc.i4.1
0x748c7  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x748cc  dup
0x748cd  ldc.i4.0
0x748ce  ldloc.0
0x748cf  stelem.ref
0x748d0  call     T0x2B000071
0x748d5  ldsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_18
0x748da  dup
0x748db  brtrue.s loc_748F4
0x748dd  pop
0x748de  ldsfld   class <>c <>c::<>9
0x748e3  ldftn    instance void <>c::<InitializeMap>b__4_18(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship source, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase destination, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x748e9  newobj   instance void class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>::.ctor(object, native int)
0x748ee  dup
0x748ef  stsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_18
0x748f4  call     class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0> class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase>::CreateMapping(var<u1>, void, class [mscorlib]System.Func`3<var<u1>, !!T0, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>)
0x748f9  callvirt instance void class Microsoft.Crm.MetadataService.Sdk.TypeMaps.CultureNeutralPropertyMap`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase>::SetPropertyMapping(string, class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0>)
0x748fe  ldarg.0
0x748ff  ldstr    aReferencingent_1// "ReferencingEntity"
0x74904  ldsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object> <>c::<>9__4_19
0x74909  dup
0x7490a  brtrue.s loc_74923
0x7490c  pop
0x7490d  ldsfld   class <>c <>c::<>9
0x74912  ldftn    instance object <>c::<InitializeMap>b__4_19(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship source, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x74918  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object>::.ctor(object, native int)
0x7491d  dup
0x7491e  stsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object> <>c::<>9__4_19
0x74923  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase
0x74928  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7492d  ldstr    aDestination// "destination"
0x74932  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x74937  stloc.0
0x74938  ldloc.0
0x74939  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata
0x7493e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x74943  call     class [System.Core]System.Linq.Expressions.UnaryExpression [System.Core]System.Linq.Expressions.Expression::Convert(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Type)
0x74948  ldtoken  instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OneToManyRelationshipMetadata::get_ReferencingEntity()
0x7494d  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
  ... truncated ...
```
