# Microsoft.Crm.MetadataService.Sdk.TypeMaps.PlatformToXrmManyToManyRelationshipMetadataPropertyMap::InitializeMap

- ea: `0x73d70`
- end: `0x743a7`
- name: `Microsoft.Crm.MetadataService.Sdk.TypeMaps.PlatformToXrmManyToManyRelationshipMetadataPropertyMap::InitializeMap`
- size: `1591`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x73d70`

## string_xrefs

- `0x73e07`: `Entity1AssociatedMenuConfiguration`
- `0x74041`: `Entity2AssociatedMenuConfiguration`
- `0x74311`: `SecurityTypes`

## pseudocode

```c

```

## disassembly

```asm
0x73d70  ldarg.0
0x73d71  ldstr    aIntersectentit_1// "IntersectEntityName"
0x73d76  ldsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object> <>c::<>9__4_0
0x73d7b  dup
0x73d7c  brtrue.s loc_73D95
0x73d7e  pop
0x73d7f  ldsfld   class <>c <>c::<>9
0x73d84  ldftn    instance object <>c::<InitializeMap>b__4_0(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship source, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x73d8a  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object>::.ctor(object, native int)
0x73d8f  dup
0x73d90  stsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object> <>c::<>9__4_0
0x73d95  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase
0x73d9a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x73d9f  ldstr    aDestination// "destination"
0x73da4  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x73da9  stloc.0
0x73daa  ldloc.0
0x73dab  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.ManyToManyRelationshipMetadata
0x73db0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x73db5  call     class [System.Core]System.Linq.Expressions.UnaryExpression [System.Core]System.Linq.Expressions.Expression::Convert(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Type)
0x73dba  ldtoken  instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.ManyToManyRelationshipMetadata::get_IntersectEntityName()
0x73dbf  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x73dc4  castclass [mscorlib]System.Reflection.MethodInfo
0x73dc9  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x73dce  ldc.i4.1
0x73dcf  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x73dd4  dup
0x73dd5  ldc.i4.0
0x73dd6  ldloc.0
0x73dd7  stelem.ref
0x73dd8  call     T0x2B000071
0x73ddd  ldsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_2
0x73de2  dup
0x73de3  brtrue.s loc_73DFC
0x73de5  pop
0x73de6  ldsfld   class <>c <>c::<>9
0x73deb  ldftn    instance void <>c::<InitializeMap>b__4_2(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship source, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase destination, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x73df1  newobj   instance void class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>::.ctor(object, native int)
0x73df6  dup
0x73df7  stsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_2
0x73dfc  call     class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0> class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase>::CreateMapping(var<u1>, void, class [mscorlib]System.Func`3<var<u1>, !!T0, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>)
0x73e01  callvirt instance void class Microsoft.Crm.MetadataService.Sdk.TypeMaps.CultureNeutralPropertyMap`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase>::SetPropertyMapping(string, class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0>)
0x73e06  ldarg.0
0x73e07  ldstr    aEntity1associa// "Entity1AssociatedMenuConfiguration"
0x73e0c  ldnull
0x73e0d  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase
0x73e12  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x73e17  ldstr    aDestination// "destination"
0x73e1c  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x73e21  stloc.0
0x73e22  ldloc.0
0x73e23  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.ManyToManyRelationshipMetadata
0x73e28  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x73e2d  call     class [System.Core]System.Linq.Expressions.UnaryExpression [System.Core]System.Linq.Expressions.Expression::Convert(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Type)
0x73e32  ldtoken  instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AssociatedMenuConfiguration [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.ManyToManyRelationshipMetadata::get_Entity1AssociatedMenuConfiguration()
0x73e37  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x73e3c  castclass [mscorlib]System.Reflection.MethodInfo
0x73e41  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x73e46  ldc.i4.1
0x73e47  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x73e4c  dup
0x73e4d  ldc.i4.0
0x73e4e  ldloc.0
0x73e4f  stelem.ref
0x73e50  call     T0x2B000071
0x73e55  ldsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_4
0x73e5a  dup
0x73e5b  brtrue.s loc_73E74
0x73e5d  pop
0x73e5e  ldsfld   class <>c <>c::<>9
0x73e63  ldftn    instance void <>c::<InitializeMap>b__4_4(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship source, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase destination, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x73e69  newobj   instance void class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>::.ctor(object, native int)
0x73e6e  dup
0x73e6f  stsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_4
0x73e74  call     class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0> class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase>::CreateMapping(var<u1>, void, class [mscorlib]System.Func`3<var<u1>, !!T0, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>)
0x73e79  callvirt instance void class Microsoft.Crm.MetadataService.Sdk.TypeMaps.CultureNeutralPropertyMap`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase>::SetPropertyMapping(string, class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0>)
0x73e7e  ldarg.0
0x73e7f  ldstr    aEntity1interse// "Entity1IntersectAttribute"
0x73e84  ldsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object> <>c::<>9__4_5
0x73e89  dup
0x73e8a  brtrue.s loc_73EA3
0x73e8c  pop
0x73e8d  ldsfld   class <>c <>c::<>9
0x73e92  ldftn    instance object <>c::<InitializeMap>b__4_5(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship source, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x73e98  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object>::.ctor(object, native int)
0x73e9d  dup
0x73e9e  stsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object> <>c::<>9__4_5
0x73ea3  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase
0x73ea8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x73ead  ldstr    aDestination// "destination"
0x73eb2  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x73eb7  stloc.0
0x73eb8  ldloc.0
0x73eb9  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.ManyToManyRelationshipMetadata
0x73ebe  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x73ec3  call     class [System.Core]System.Linq.Expressions.UnaryExpression [System.Core]System.Linq.Expressions.Expression::Convert(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Type)
0x73ec8  ldtoken  instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.ManyToManyRelationshipMetadata::get_Entity1IntersectAttribute()
0x73ecd  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x73ed2  castclass [mscorlib]System.Reflection.MethodInfo
0x73ed7  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x73edc  ldc.i4.1
0x73edd  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x73ee2  dup
0x73ee3  ldc.i4.0
0x73ee4  ldloc.0
0x73ee5  stelem.ref
0x73ee6  call     T0x2B000071
0x73eeb  ldsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_7
0x73ef0  dup
0x73ef1  brtrue.s loc_73F0A
0x73ef3  pop
0x73ef4  ldsfld   class <>c <>c::<>9
0x73ef9  ldftn    instance void <>c::<InitializeMap>b__4_7(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship source, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase destination, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x73eff  newobj   instance void class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>::.ctor(object, native int)
0x73f04  dup
0x73f05  stsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_7
0x73f0a  call     class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0> class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase>::CreateMapping(var<u1>, void, class [mscorlib]System.Func`3<var<u1>, !!T0, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>)
0x73f0f  callvirt instance void class Microsoft.Crm.MetadataService.Sdk.TypeMaps.CultureNeutralPropertyMap`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase>::SetPropertyMapping(string, class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0>)
0x73f14  ldarg.0
0x73f15  ldstr    aEntity1logical// "Entity1LogicalName"
0x73f1a  ldsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object> <>c::<>9__4_8
0x73f1f  dup
0x73f20  brtrue.s loc_73F39
0x73f22  pop
0x73f23  ldsfld   class <>c <>c::<>9
0x73f28  ldftn    instance object <>c::<InitializeMap>b__4_8(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship source, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x73f2e  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object>::.ctor(object, native int)
0x73f33  dup
0x73f34  stsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object> <>c::<>9__4_8
0x73f39  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase
0x73f3e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x73f43  ldstr    aDestination// "destination"
0x73f48  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x73f4d  stloc.0
0x73f4e  ldloc.0
0x73f4f  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.ManyToManyRelationshipMetadata
0x73f54  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x73f59  call     class [System.Core]System.Linq.Expressions.UnaryExpression [System.Core]System.Linq.Expressions.Expression::Convert(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Type)
0x73f5e  ldtoken  instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.ManyToManyRelationshipMetadata::get_Entity1LogicalName()
0x73f63  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x73f68  castclass [mscorlib]System.Reflection.MethodInfo
0x73f6d  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x73f72  ldc.i4.1
0x73f73  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x73f78  dup
0x73f79  ldc.i4.0
0x73f7a  ldloc.0
0x73f7b  stelem.ref
0x73f7c  call     T0x2B000071
0x73f81  ldsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_10
0x73f86  dup
0x73f87  brtrue.s loc_73FA0
0x73f89  pop
0x73f8a  ldsfld   class <>c <>c::<>9
0x73f8f  ldftn    instance void <>c::<InitializeMap>b__4_10(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship source, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase destination, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x73f95  newobj   instance void class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>::.ctor(object, native int)
0x73f9a  dup
0x73f9b  stsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_10
0x73fa0  call     class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0> class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase>::CreateMapping(var<u1>, void, class [mscorlib]System.Func`3<var<u1>, !!T0, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>)
0x73fa5  callvirt instance void class Microsoft.Crm.MetadataService.Sdk.TypeMaps.CultureNeutralPropertyMap`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase>::SetPropertyMapping(string, class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0>)
0x73faa  ldarg.0
0x73fab  ldstr    aEntity1navigat// "Entity1NavigationPropertyName"
0x73fb0  ldsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object> <>c::<>9__4_11
0x73fb5  dup
0x73fb6  brtrue.s loc_73FCF
0x73fb8  pop
0x73fb9  ldsfld   class <>c <>c::<>9
0x73fbe  ldftn    instance object <>c::<InitializeMap>b__4_11(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship source, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x73fc4  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object>::.ctor(object, native int)
0x73fc9  dup
0x73fca  stsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object> <>c::<>9__4_11
0x73fcf  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase
0x73fd4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x73fd9  ldstr    aDestination// "destination"
0x73fde  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x73fe3  stloc.0
0x73fe4  ldloc.0
0x73fe5  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.ManyToManyRelationshipMetadata
0x73fea  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x73fef  call     class [System.Core]System.Linq.Expressions.UnaryExpression [System.Core]System.Linq.Expressions.Expression::Convert(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Type)
0x73ff4  ldtoken  instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.ManyToManyRelationshipMetadata::get_Entity1NavigationPropertyName()
0x73ff9  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x73ffe  castclass [mscorlib]System.Reflection.MethodInfo
0x74003  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x74008  ldc.i4.1
0x74009  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x7400e  dup
0x7400f  ldc.i4.0
0x74010  ldloc.0
0x74011  stelem.ref
0x74012  call     T0x2B000071
0x74017  ldsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_13
0x7401c  dup
0x7401d  brtrue.s loc_74036
0x7401f  pop
0x74020  ldsfld   class <>c <>c::<>9
0x74025  ldftn    instance void <>c::<InitializeMap>b__4_13(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship source, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase destination, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x7402b  newobj   instance void class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>::.ctor(object, native int)
0x74030  dup
0x74031  stsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_13
0x74036  call     class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0> class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase>::CreateMapping(var<u1>, void, class [mscorlib]System.Func`3<var<u1>, !!T0, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>)
0x7403b  callvirt instance void class Microsoft.Crm.MetadataService.Sdk.TypeMaps.CultureNeutralPropertyMap`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase>::SetPropertyMapping(string, class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0>)
0x74040  ldarg.0
0x74041  ldstr    aEntity2associa// "Entity2AssociatedMenuConfiguration"
0x74046  ldnull
0x74047  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase
0x7404c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x74051  ldstr    aDestination// "destination"
0x74056  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x7405b  stloc.0
0x7405c  ldloc.0
0x7405d  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.ManyToManyRelationshipMetadata
0x74062  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x74067  call     class [System.Core]System.Linq.Expressions.UnaryExpression [System.Core]System.Linq.Expressions.Expression::Convert(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Type)
0x7406c  ldtoken  instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AssociatedMenuConfiguration [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.ManyToManyRelationshipMetadata::get_Entity2AssociatedMenuConfiguration()
0x74071  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x74076  castclass [mscorlib]System.Reflection.MethodInfo
0x7407b  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x74080  ldc.i4.1
0x74081  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x74086  dup
0x74087  ldc.i4.0
0x74088  ldloc.0
0x74089  stelem.ref
0x7408a  call     T0x2B000071
0x7408f  ldsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_15
0x74094  dup
0x74095  brtrue.s loc_740AE
0x74097  pop
0x74098  ldsfld   class <>c <>c::<>9
0x7409d  ldftn    instance void <>c::<InitializeMap>b__4_15(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship source, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase destination, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x740a3  newobj   instance void class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>::.ctor(object, native int)
0x740a8  dup
0x740a9  stsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_15
0x740ae  call     class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0> class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase>::CreateMapping(var<u1>, void, class [mscorlib]System.Func`3<var<u1>, !!T0, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>)
0x740b3  callvirt instance void class Microsoft.Crm.MetadataService.Sdk.TypeMaps.CultureNeutralPropertyMap`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase>::SetPropertyMapping(string, class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0>)
0x740b8  ldarg.0
0x740b9  ldstr    aEntity2interse// "Entity2IntersectAttribute"
0x740be  ldsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object> <>c::<>9__4_16
0x740c3  dup
0x740c4  brtrue.s loc_740DD
0x740c6  pop
0x740c7  ldsfld   class <>c <>c::<>9
0x740cc  ldftn    instance object <>c::<InitializeMap>b__4_16(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship source, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x740d2  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object>::.ctor(object, native int)
0x740d7  dup
0x740d8  stsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object> <>c::<>9__4_16
0x740dd  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase
0x740e2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x740e7  ldstr    aDestination// "destination"
0x740ec  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x740f1  stloc.0
0x740f2  ldloc.0
0x740f3  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.ManyToManyRelationshipMetadata
0x740f8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x740fd  call     class [System.Core]System.Linq.Expressions.UnaryExpression [System.Core]System.Linq.Expressions.Expression::Convert(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Type)
0x74102  ldtoken  instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.ManyToManyRelationshipMetadata::get_Entity2IntersectAttribute()
0x74107  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x7410c  castclass [mscorlib]System.Reflection.MethodInfo
0x74111  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x74116  ldc.i4.1
0x74117  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x7411c  dup
0x7411d  ldc.i4.0
0x7411e  ldloc.0
0x7411f  stelem.ref
0x74120  call     T0x2B000071
0x74125  ldsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_18
0x7412a  dup
0x7412b  brtrue.s loc_74144
0x7412d  pop
0x7412e  ldsfld   class <>c <>c::<>9
0x74133  ldftn    instance void <>c::<InitializeMap>b__4_18(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship source, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase destination, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x74139  newobj   instance void class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>::.ctor(object, native int)
0x7413e  dup
0x7413f  stsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_18
0x74144  call     class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0> class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase>::CreateMapping(var<u1>, void, class [mscorlib]System.Func`3<var<u1>, !!T0, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>)
0x74149  callvirt instance void class Microsoft.Crm.MetadataService.Sdk.TypeMaps.CultureNeutralPropertyMap`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase>::SetPropertyMapping(string, class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0>)
0x7414e  ldarg.0
0x7414f  ldstr    aEntity2logical// "Entity2LogicalName"
0x74154  ldsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object> <>c::<>9__4_19
0x74159  dup
0x7415a  brtrue.s loc_74173
0x7415c  pop
0x7415d  ldsfld   class <>c <>c::<>9
0x74162  ldftn    instance object <>c::<InitializeMap>b__4_19(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship source, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x74168  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object>::.ctor(object, native int)
0x7416d  dup
0x7416e  stsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object> <>c::<>9__4_19
0x74173  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.RelationshipMetadataBase
0x74178  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7417d  ldstr    aDestination// "destination"
0x74182  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x74187  stloc.0
0x74188  ldloc.0
0x74189  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.ManyToManyRelationshipMetadata
0x7418e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x74193  call     class [System.Core]System.Linq.Expressions.UnaryExpression [System.Core]System.Linq.Expressions.Expression::Convert(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Type)
0x74198  ldtoken  instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.ManyToManyRelationshipMetadata::get_Entity2LogicalName()
0x7419d  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
  ... truncated ...
```
