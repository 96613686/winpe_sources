# Microsoft.Crm.MetadataService.Sdk.TypeMaps.PlatformToXrmAttributeMetadataTypeMap::InitializeBaseTypePropertyMap

- ea: `0x69a40`
- end: `0x6b2c1`
- name: `Microsoft.Crm.MetadataService.Sdk.TypeMaps.PlatformToXrmAttributeMetadataTypeMap::InitializeBaseTypePropertyMap`
- size: `6273`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x69a40`

## string_xrefs

- `0x6a0c4`: `IsValidForCreate`
- `0x6a277`: `IsValidForRead`
- `0x6a30d`: `IsValidForUpdate`
- `0x6a3a3`: `LinkedAttributeId`
- `0x6a781`: `CanBeSecuredForCreate`
- `0x6a817`: `CanBeSecuredForRead`
- `0x6a8ad`: `CanBeSecuredForUpdate`
- `0x6aa51`: `IsRenameable`

## pseudocode

```c

```

## disassembly

```asm
0x69a40  ldarg.0
0x69a41  ldstr    aIsauditenabled_0// "IsAuditEnabled"
0x69a46  ldsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object> <>c::<>9__4_0
0x69a4b  dup
0x69a4c  brtrue.s loc_69A65
0x69a4e  pop
0x69a4f  ldsfld   class <>c <>c::<>9
0x69a54  ldftn    instance object <>c::<InitializeBaseTypePropertyMap>b__4_0(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata source, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x69a5a  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object>::.ctor(object, native int)
0x69a5f  dup
0x69a60  stsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object> <>c::<>9__4_0
0x69a65  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata
0x69a6a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x69a6f  ldstr    aDestination// "destination"
0x69a74  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x69a79  stloc.0
0x69a7a  ldloc.0
0x69a7b  ldtoken  instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_IsAuditEnabled()
0x69a80  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x69a85  castclass [mscorlib]System.Reflection.MethodInfo
0x69a8a  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x69a8f  ldc.i4.1
0x69a90  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x69a95  dup
0x69a96  ldc.i4.0
0x69a97  ldloc.0
0x69a98  stelem.ref
0x69a99  call     T0x2B00006B
0x69a9e  ldsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_2
0x69aa3  dup
0x69aa4  brtrue.s loc_69ABD
0x69aa6  pop
0x69aa7  ldsfld   class <>c <>c::<>9
0x69aac  ldftn    instance void <>c::<InitializeBaseTypePropertyMap>b__4_2(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata source, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata destination, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x69ab2  newobj   instance void class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>::.ctor(object, native int)
0x69ab7  dup
0x69ab8  stsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_2
0x69abd  call     class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0> class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata>::CreateMapping(var<u1>, void, class [mscorlib]System.Func`3<var<u1>, !!T0, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>)
0x69ac2  callvirt instance void class Microsoft.Crm.MetadataService.Sdk.TypeMaps.CultureNeutralPropertyMap`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata>::SetPropertyMapping(string, class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0>)
0x69ac7  ldarg.0
0x69ac8  ldstr    aAttributeof_0// "AttributeOf"
0x69acd  ldsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object> <>c::<>9__4_3
0x69ad2  dup
0x69ad3  brtrue.s loc_69AEC
0x69ad5  pop
0x69ad6  ldsfld   class <>c <>c::<>9
0x69adb  ldftn    instance object <>c::<InitializeBaseTypePropertyMap>b__4_3(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata source, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x69ae1  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object>::.ctor(object, native int)
0x69ae6  dup
0x69ae7  stsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object> <>c::<>9__4_3
0x69aec  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata
0x69af1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x69af6  ldstr    aDestination// "destination"
0x69afb  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x69b00  stloc.0
0x69b01  ldloc.0
0x69b02  ldtoken  instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_AttributeOf()
0x69b07  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x69b0c  castclass [mscorlib]System.Reflection.MethodInfo
0x69b11  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x69b16  ldc.i4.1
0x69b17  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x69b1c  dup
0x69b1d  ldc.i4.0
0x69b1e  ldloc.0
0x69b1f  stelem.ref
0x69b20  call     T0x2B00006B
0x69b25  ldsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_5
0x69b2a  dup
0x69b2b  brtrue.s loc_69B44
0x69b2d  pop
0x69b2e  ldsfld   class <>c <>c::<>9
0x69b33  ldftn    instance void <>c::<InitializeBaseTypePropertyMap>b__4_5(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata source, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata destination, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x69b39  newobj   instance void class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>::.ctor(object, native int)
0x69b3e  dup
0x69b3f  stsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_5
0x69b44  call     class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0> class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata>::CreateMapping(var<u1>, void, class [mscorlib]System.Func`3<var<u1>, !!T0, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>)
0x69b49  callvirt instance void class Microsoft.Crm.MetadataService.Sdk.TypeMaps.CultureNeutralPropertyMap`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata>::SetPropertyMapping(string, class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0>)
0x69b4e  ldarg.0
0x69b4f  ldstr    aAttributetype// "AttributeType"
0x69b54  ldsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object> <>c::<>9__4_6
0x69b59  dup
0x69b5a  brtrue.s loc_69B73
0x69b5c  pop
0x69b5d  ldsfld   class <>c <>c::<>9
0x69b62  ldftn    instance object <>c::<InitializeBaseTypePropertyMap>b__4_6(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata source, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x69b68  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object>::.ctor(object, native int)
0x69b6d  dup
0x69b6e  stsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object> <>c::<>9__4_6
0x69b73  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata
0x69b78  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x69b7d  ldstr    aDestination// "destination"
0x69b82  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x69b87  stloc.0
0x69b88  ldloc.0
0x69b89  ldtoken  instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeTypeCode> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_AttributeType()
0x69b8e  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x69b93  castclass [mscorlib]System.Reflection.MethodInfo
0x69b98  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x69b9d  ldtoken  [mscorlib]System.Object
0x69ba2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x69ba7  call     class [System.Core]System.Linq.Expressions.UnaryExpression [System.Core]System.Linq.Expressions.Expression::Convert(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Type)
0x69bac  ldc.i4.1
0x69bad  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x69bb2  dup
0x69bb3  ldc.i4.0
0x69bb4  ldloc.0
0x69bb5  stelem.ref
0x69bb6  call     T0x2B00006B
0x69bbb  ldsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_8
0x69bc0  dup
0x69bc1  brtrue.s loc_69BDA
0x69bc3  pop
0x69bc4  ldsfld   class <>c <>c::<>9
0x69bc9  ldftn    instance void <>c::<InitializeBaseTypePropertyMap>b__4_8(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata source, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata destination, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x69bcf  newobj   instance void class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>::.ctor(object, native int)
0x69bd4  dup
0x69bd5  stsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_8
0x69bda  call     class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0> class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata>::CreateMapping(var<u1>, void, class [mscorlib]System.Func`3<var<u1>, !!T0, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>)
0x69bdf  callvirt instance void class Microsoft.Crm.MetadataService.Sdk.TypeMaps.CultureNeutralPropertyMap`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata>::SetPropertyMapping(string, class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0>)
0x69be4  ldarg.0
0x69be5  ldstr    aAttributetypen// "AttributeTypeName"
0x69bea  ldsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object> <>c::<>9__4_9
0x69bef  dup
0x69bf0  brtrue.s loc_69C09
0x69bf2  pop
0x69bf3  ldsfld   class <>c <>c::<>9
0x69bf8  ldftn    instance object <>c::<InitializeBaseTypePropertyMap>b__4_9(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata source, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x69bfe  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object>::.ctor(object, native int)
0x69c03  dup
0x69c04  stsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object> <>c::<>9__4_9
0x69c09  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata
0x69c0e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x69c13  ldstr    aDestination// "destination"
0x69c18  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x69c1d  stloc.0
0x69c1e  ldloc.0
0x69c1f  ldtoken  instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeTypeDisplayName [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_AttributeTypeName()
0x69c24  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x69c29  castclass [mscorlib]System.Reflection.MethodInfo
0x69c2e  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x69c33  ldc.i4.1
0x69c34  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x69c39  dup
0x69c3a  ldc.i4.0
0x69c3b  ldloc.0
0x69c3c  stelem.ref
0x69c3d  call     T0x2B00006B
0x69c42  ldsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_11
0x69c47  dup
0x69c48  brtrue.s loc_69C61
0x69c4a  pop
0x69c4b  ldsfld   class <>c <>c::<>9
0x69c50  ldftn    instance void <>c::<InitializeBaseTypePropertyMap>b__4_11(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata source, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata destination, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x69c56  newobj   instance void class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>::.ctor(object, native int)
0x69c5b  dup
0x69c5c  stsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_11
0x69c61  call     class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0> class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata>::CreateMapping(var<u1>, void, class [mscorlib]System.Func`3<var<u1>, !!T0, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>)
0x69c66  callvirt instance void class Microsoft.Crm.MetadataService.Sdk.TypeMaps.CultureNeutralPropertyMap`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata>::SetPropertyMapping(string, class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0>)
0x69c6b  ldarg.0
0x69c6c  ldstr    aColumnnumber_1// "ColumnNumber"
0x69c71  ldsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object> <>c::<>9__4_12
0x69c76  dup
0x69c77  brtrue.s loc_69C90
0x69c79  pop
0x69c7a  ldsfld   class <>c <>c::<>9
0x69c7f  ldftn    instance object <>c::<InitializeBaseTypePropertyMap>b__4_12(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata source, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x69c85  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object>::.ctor(object, native int)
0x69c8a  dup
0x69c8b  stsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object> <>c::<>9__4_12
0x69c90  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata
0x69c95  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x69c9a  ldstr    aDestination// "destination"
0x69c9f  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x69ca4  stloc.0
0x69ca5  ldloc.0
0x69ca6  ldtoken  instance valuetype [mscorlib]System.Nullable`1<int32> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_ColumnNumber()
0x69cab  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x69cb0  castclass [mscorlib]System.Reflection.MethodInfo
0x69cb5  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x69cba  ldtoken  [mscorlib]System.Object
0x69cbf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x69cc4  call     class [System.Core]System.Linq.Expressions.UnaryExpression [System.Core]System.Linq.Expressions.Expression::Convert(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Type)
0x69cc9  ldc.i4.1
0x69cca  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x69ccf  dup
0x69cd0  ldc.i4.0
0x69cd1  ldloc.0
0x69cd2  stelem.ref
0x69cd3  call     T0x2B00006B
0x69cd8  ldsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_14
0x69cdd  dup
0x69cde  brtrue.s loc_69CF7
0x69ce0  pop
0x69ce1  ldsfld   class <>c <>c::<>9
0x69ce6  ldftn    instance void <>c::<InitializeBaseTypePropertyMap>b__4_14(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata source, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata destination, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x69cec  newobj   instance void class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>::.ctor(object, native int)
0x69cf1  dup
0x69cf2  stsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_14
0x69cf7  call     class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0> class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata>::CreateMapping(var<u1>, void, class [mscorlib]System.Func`3<var<u1>, !!T0, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>)
0x69cfc  callvirt instance void class Microsoft.Crm.MetadataService.Sdk.TypeMaps.CultureNeutralPropertyMap`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata>::SetPropertyMapping(string, class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0>)
0x69d01  ldarg.0
0x69d02  ldstr    aDeprecatedvers_0// "DeprecatedVersion"
0x69d07  ldsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object> <>c::<>9__4_15
0x69d0c  dup
0x69d0d  brtrue.s loc_69D26
0x69d0f  pop
0x69d10  ldsfld   class <>c <>c::<>9
0x69d15  ldftn    instance object <>c::<InitializeBaseTypePropertyMap>b__4_15(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata source, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x69d1b  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object>::.ctor(object, native int)
0x69d20  dup
0x69d21  stsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object> <>c::<>9__4_15
0x69d26  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata
0x69d2b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x69d30  ldstr    aDestination// "destination"
0x69d35  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x69d3a  stloc.0
0x69d3b  ldloc.0
0x69d3c  ldtoken  instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_DeprecatedVersion()
0x69d41  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x69d46  castclass [mscorlib]System.Reflection.MethodInfo
0x69d4b  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x69d50  ldc.i4.1
0x69d51  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x69d56  dup
0x69d57  ldc.i4.0
0x69d58  ldloc.0
0x69d59  stelem.ref
0x69d5a  call     T0x2B00006B
0x69d5f  ldsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_17
0x69d64  dup
0x69d65  brtrue.s loc_69D7E
0x69d67  pop
0x69d68  ldsfld   class <>c <>c::<>9
0x69d6d  ldftn    instance void <>c::<InitializeBaseTypePropertyMap>b__4_17(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata source, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata destination, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x69d73  newobj   instance void class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>::.ctor(object, native int)
0x69d78  dup
0x69d79  stsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_17
0x69d7e  call     class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0> class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata>::CreateMapping(var<u1>, void, class [mscorlib]System.Func`3<var<u1>, !!T0, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>)
0x69d83  callvirt instance void class Microsoft.Crm.MetadataService.Sdk.TypeMaps.CultureNeutralPropertyMap`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata>::SetPropertyMapping(string, class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0>)
0x69d88  ldarg.0
0x69d89  ldstr    aDescription// "Description"
0x69d8e  ldsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object> <>c::<>9__4_18
0x69d93  dup
0x69d94  brtrue.s loc_69DAD
0x69d96  pop
0x69d97  ldsfld   class <>c <>c::<>9
0x69d9c  ldftn    instance object <>c::<InitializeBaseTypePropertyMap>b__4_18(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata source, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x69da2  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object>::.ctor(object, native int)
0x69da7  dup
0x69da8  stsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object> <>c::<>9__4_18
0x69dad  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata
0x69db2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x69db7  ldstr    aDestination// "destination"
0x69dbc  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x69dc1  stloc.0
0x69dc2  ldloc.0
0x69dc3  ldtoken  instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Label [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_Description()
0x69dc8  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x69dcd  castclass [mscorlib]System.Reflection.MethodInfo
0x69dd2  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x69dd7  ldc.i4.1
0x69dd8  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x69ddd  dup
0x69dde  ldc.i4.0
0x69ddf  ldloc.0
0x69de0  stelem.ref
0x69de1  call     T0x2B00006B
0x69de6  ldsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_20
0x69deb  dup
0x69dec  brtrue.s loc_69E05
0x69dee  pop
0x69def  ldsfld   class <>c <>c::<>9
0x69df4  ldftn    instance void <>c::<InitializeBaseTypePropertyMap>b__4_20(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata source, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata destination, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x69dfa  newobj   instance void class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>::.ctor(object, native int)
0x69dff  dup
0x69e00  stsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_20
0x69e05  ldc.i4.1
0x69e06  call     class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0> class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata>::CreateMapping(var<u1>, void, class [mscorlib]System.Func`3<var<u1>, !!T0, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>, object)
0x69e0b  callvirt instance void class Microsoft.Crm.MetadataService.Sdk.TypeMaps.CultureNeutralPropertyMap`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata>::SetPropertyMapping(string, class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0>)
0x69e10  ldarg.0
0x69e11  ldstr    aDisplayname// "DisplayName"
0x69e16  ldsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object> <>c::<>9__4_21
0x69e1b  dup
0x69e1c  brtrue.s loc_69E35
0x69e1e  pop
0x69e1f  ldsfld   class <>c <>c::<>9
0x69e24  ldftn    instance object <>c::<InitializeBaseTypePropertyMap>b__4_21(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata source, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x69e2a  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object>::.ctor(object, native int)
0x69e2f  dup
0x69e30  stsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object> <>c::<>9__4_21
0x69e35  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata
0x69e3a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x69e3f  ldstr    aDestination// "destination"
0x69e44  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x69e49  stloc.0
0x69e4a  ldloc.0
0x69e4b  ldtoken  instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Label [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_DisplayName()
0x69e50  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x69e55  castclass [mscorlib]System.Reflection.MethodInfo
  ... truncated ...
```
