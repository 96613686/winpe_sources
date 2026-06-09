# Microsoft.Crm.MetadataService.Sdk.TypeMaps.PlatformToXrmEntityMetadataTypeMap::InitializeMap

- ea: `0x6fa80`
- end: `0x7344f`
- name: `Microsoft.Crm.MetadataService.Sdk.TypeMaps.PlatformToXrmEntityMetadataTypeMap::InitializeMap`
- size: `14799`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x6fa80`

## string_xrefs

- `0x70025`: `IsDocumentRecommendationsEnabled`
- `0x70b38`: `IsQuickCreateEnabled`
- `0x720da`: `IsReadOnlyInMobileClient`
- `0x71180`: `Privileges`
- `0x71f45`: `IsRenameable`
- `0x70a0c`: `IsReadingPaneEnabled`
- `0x70aa2`: `IsAIRUpdated`
- `0x70bce`: `AutoCreateAccessTeams`
- `0x717c5`: `CanCreateAttributes`
- `0x7184c`: `CanCreateCharts`
- `0x718d3`: `CanCreateForms`
- `0x7195a`: `CanCreateViews`
- `0x7328d`: `AvailableForCreate`
- `0x73323`: `AvailableForUpdate`
- `0x733b9`: `AvailableForDelete`

## pseudocode

```c

```

## disassembly

```asm
0x6fa80  ldarg.0
0x6fa81  ldstr    aActivitytypema_0// "ActivityTypeMask"
0x6fa86  ldsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object> <>c::<>9__4_0
0x6fa8b  dup
0x6fa8c  brtrue.s loc_6FAA5
0x6fa8e  pop
0x6fa8f  ldsfld   class <>c <>c::<>9
0x6fa94  ldftn    instance object <>c::<InitializeMap>b__4_0(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata source, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x6fa9a  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object>::.ctor(object, native int)
0x6fa9f  dup
0x6faa0  stsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object> <>c::<>9__4_0
0x6faa5  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata
0x6faaa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6faaf  ldstr    aDestination// "destination"
0x6fab4  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x6fab9  stloc.0
0x6faba  ldloc.0
0x6fabb  ldtoken  instance valuetype [mscorlib]System.Nullable`1<int32> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_ActivityTypeMask()
0x6fac0  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x6fac5  castclass [mscorlib]System.Reflection.MethodInfo
0x6faca  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x6facf  ldtoken  [mscorlib]System.Object
0x6fad4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6fad9  call     class [System.Core]System.Linq.Expressions.UnaryExpression [System.Core]System.Linq.Expressions.Expression::Convert(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Type)
0x6fade  ldc.i4.1
0x6fadf  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x6fae4  dup
0x6fae5  ldc.i4.0
0x6fae6  ldloc.0
0x6fae7  stelem.ref
0x6fae8  call     T0x2B00000E
0x6faed  ldsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_2
0x6faf2  dup
0x6faf3  brtrue.s loc_6FB0C
0x6faf5  pop
0x6faf6  ldsfld   class <>c <>c::<>9
0x6fafb  ldftn    instance void <>c::<InitializeMap>b__4_2(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata source, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata destination, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x6fb01  newobj   instance void class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>::.ctor(object, native int)
0x6fb06  dup
0x6fb07  stsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_2
0x6fb0c  call     class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0> class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata>::CreateMapping(var<u1>, void, class [mscorlib]System.Func`3<var<u1>, !!T0, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>)
0x6fb11  callvirt instance void class Microsoft.Crm.MetadataService.Sdk.TypeMaps.CultureNeutralPropertyMap`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata>::SetPropertyMapping(string, class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0>)
0x6fb16  ldarg.0
0x6fb17  ldstr    aAttributes_0// "Attributes"
0x6fb1c  ldnull
0x6fb1d  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata
0x6fb22  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6fb27  ldstr    aDestination// "destination"
0x6fb2c  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x6fb31  stloc.0
0x6fb32  ldloc.0
0x6fb33  ldtoken  instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata[] [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_Attributes()
0x6fb38  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x6fb3d  castclass [mscorlib]System.Reflection.MethodInfo
0x6fb42  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x6fb47  ldc.i4.1
0x6fb48  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x6fb4d  dup
0x6fb4e  ldc.i4.0
0x6fb4f  ldloc.0
0x6fb50  stelem.ref
0x6fb51  call     T0x2B00000E
0x6fb56  ldsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_4
0x6fb5b  dup
0x6fb5c  brtrue.s loc_6FB75
0x6fb5e  pop
0x6fb5f  ldsfld   class <>c <>c::<>9
0x6fb64  ldftn    instance void <>c::<InitializeMap>b__4_4(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata source, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata destination, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x6fb6a  newobj   instance void class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>::.ctor(object, native int)
0x6fb6f  dup
0x6fb70  stsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_4
0x6fb75  ldc.i4.1
0x6fb76  call     class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0> class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata>::CreateMapping(var<u1>, void, class [mscorlib]System.Func`3<var<u1>, !!T0, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>, object)
0x6fb7b  callvirt instance void class Microsoft.Crm.MetadataService.Sdk.TypeMaps.CultureNeutralPropertyMap`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata>::SetPropertyMapping(string, class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0>)
0x6fb80  ldarg.0
0x6fb81  ldstr    aAutoroutetoown_2// "AutoRouteToOwnerQueue"
0x6fb86  ldsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object> <>c::<>9__4_5
0x6fb8b  dup
0x6fb8c  brtrue.s loc_6FBA5
0x6fb8e  pop
0x6fb8f  ldsfld   class <>c <>c::<>9
0x6fb94  ldftn    instance object <>c::<InitializeMap>b__4_5(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata source, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x6fb9a  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object>::.ctor(object, native int)
0x6fb9f  dup
0x6fba0  stsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object> <>c::<>9__4_5
0x6fba5  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata
0x6fbaa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6fbaf  ldstr    aDestination// "destination"
0x6fbb4  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x6fbb9  stloc.0
0x6fbba  ldloc.0
0x6fbbb  ldtoken  instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_AutoRouteToOwnerQueue()
0x6fbc0  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x6fbc5  castclass [mscorlib]System.Reflection.MethodInfo
0x6fbca  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x6fbcf  ldtoken  [mscorlib]System.Object
0x6fbd4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6fbd9  call     class [System.Core]System.Linq.Expressions.UnaryExpression [System.Core]System.Linq.Expressions.Expression::Convert(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Type)
0x6fbde  ldc.i4.1
0x6fbdf  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x6fbe4  dup
0x6fbe5  ldc.i4.0
0x6fbe6  ldloc.0
0x6fbe7  stelem.ref
0x6fbe8  call     T0x2B00000E
0x6fbed  ldsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_7
0x6fbf2  dup
0x6fbf3  brtrue.s loc_6FC0C
0x6fbf5  pop
0x6fbf6  ldsfld   class <>c <>c::<>9
0x6fbfb  ldftn    instance void <>c::<InitializeMap>b__4_7(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata source, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata destination, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x6fc01  newobj   instance void class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>::.ctor(object, native int)
0x6fc06  dup
0x6fc07  stsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_7
0x6fc0c  call     class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0> class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata>::CreateMapping(var<u1>, void, class [mscorlib]System.Func`3<var<u1>, !!T0, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>)
0x6fc11  callvirt instance void class Microsoft.Crm.MetadataService.Sdk.TypeMaps.CultureNeutralPropertyMap`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata>::SetPropertyMapping(string, class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0>)
0x6fc16  ldarg.0
0x6fc17  ldstr    aCantriggerwork_0// "CanTriggerWorkflow"
0x6fc1c  ldsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object> <>c::<>9__4_8
0x6fc21  dup
0x6fc22  brtrue.s loc_6FC3B
0x6fc24  pop
0x6fc25  ldsfld   class <>c <>c::<>9
0x6fc2a  ldftn    instance object <>c::<InitializeMap>b__4_8(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata source, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x6fc30  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object>::.ctor(object, native int)
0x6fc35  dup
0x6fc36  stsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object> <>c::<>9__4_8
0x6fc3b  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata
0x6fc40  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6fc45  ldstr    aDestination// "destination"
0x6fc4a  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x6fc4f  stloc.0
0x6fc50  ldloc.0
0x6fc51  ldtoken  instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_CanTriggerWorkflow()
0x6fc56  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x6fc5b  castclass [mscorlib]System.Reflection.MethodInfo
0x6fc60  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x6fc65  ldtoken  [mscorlib]System.Object
0x6fc6a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6fc6f  call     class [System.Core]System.Linq.Expressions.UnaryExpression [System.Core]System.Linq.Expressions.Expression::Convert(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Type)
0x6fc74  ldc.i4.1
0x6fc75  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x6fc7a  dup
0x6fc7b  ldc.i4.0
0x6fc7c  ldloc.0
0x6fc7d  stelem.ref
0x6fc7e  call     T0x2B00000E
0x6fc83  ldsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_10
0x6fc88  dup
0x6fc89  brtrue.s loc_6FCA2
0x6fc8b  pop
0x6fc8c  ldsfld   class <>c <>c::<>9
0x6fc91  ldftn    instance void <>c::<InitializeMap>b__4_10(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata source, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata destination, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x6fc97  newobj   instance void class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>::.ctor(object, native int)
0x6fc9c  dup
0x6fc9d  stsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_10
0x6fca2  call     class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0> class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata>::CreateMapping(var<u1>, void, class [mscorlib]System.Func`3<var<u1>, !!T0, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>)
0x6fca7  callvirt instance void class Microsoft.Crm.MetadataService.Sdk.TypeMaps.CultureNeutralPropertyMap`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata>::SetPropertyMapping(string, class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0>)
0x6fcac  ldarg.0
0x6fcad  ldstr    aDescription// "Description"
0x6fcb2  ldnull
0x6fcb3  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata
0x6fcb8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6fcbd  ldstr    aDestination// "destination"
0x6fcc2  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x6fcc7  stloc.0
0x6fcc8  ldloc.0
0x6fcc9  ldtoken  instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Label [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_Description()
0x6fcce  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x6fcd3  castclass [mscorlib]System.Reflection.MethodInfo
0x6fcd8  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x6fcdd  ldc.i4.1
0x6fcde  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x6fce3  dup
0x6fce4  ldc.i4.0
0x6fce5  ldloc.0
0x6fce6  stelem.ref
0x6fce7  call     T0x2B00000E
0x6fcec  ldsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_12
0x6fcf1  dup
0x6fcf2  brtrue.s loc_6FD0B
0x6fcf4  pop
0x6fcf5  ldsfld   class <>c <>c::<>9
0x6fcfa  ldftn    instance void <>c::<InitializeMap>b__4_12(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata source, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata destination, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x6fd00  newobj   instance void class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>::.ctor(object, native int)
0x6fd05  dup
0x6fd06  stsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_12
0x6fd0b  ldc.i4.1
0x6fd0c  call     class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0> class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata>::CreateMapping(var<u1>, void, class [mscorlib]System.Func`3<var<u1>, !!T0, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>, object)
0x6fd11  callvirt instance void class Microsoft.Crm.MetadataService.Sdk.TypeMaps.CultureNeutralPropertyMap`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata>::SetPropertyMapping(string, class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0>)
0x6fd16  ldarg.0
0x6fd17  ldstr    aDisplaycollect_2// "DisplayCollectionName"
0x6fd1c  ldnull
0x6fd1d  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata
0x6fd22  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6fd27  ldstr    aDestination// "destination"
0x6fd2c  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x6fd31  stloc.0
0x6fd32  ldloc.0
0x6fd33  ldtoken  instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Label [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_DisplayCollectionName()
0x6fd38  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x6fd3d  castclass [mscorlib]System.Reflection.MethodInfo
0x6fd42  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x6fd47  ldc.i4.1
0x6fd48  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x6fd4d  dup
0x6fd4e  ldc.i4.0
0x6fd4f  ldloc.0
0x6fd50  stelem.ref
0x6fd51  call     T0x2B00000E
0x6fd56  ldsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_14
0x6fd5b  dup
0x6fd5c  brtrue.s loc_6FD75
0x6fd5e  pop
0x6fd5f  ldsfld   class <>c <>c::<>9
0x6fd64  ldftn    instance void <>c::<InitializeMap>b__4_14(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata source, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata destination, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x6fd6a  newobj   instance void class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>::.ctor(object, native int)
0x6fd6f  dup
0x6fd70  stsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_14
0x6fd75  ldc.i4.1
0x6fd76  call     class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0> class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata>::CreateMapping(var<u1>, void, class [mscorlib]System.Func`3<var<u1>, !!T0, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>, object)
0x6fd7b  callvirt instance void class Microsoft.Crm.MetadataService.Sdk.TypeMaps.CultureNeutralPropertyMap`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata>::SetPropertyMapping(string, class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0>)
0x6fd80  ldarg.0
0x6fd81  ldstr    aDisplayname// "DisplayName"
0x6fd86  ldnull
0x6fd87  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata
0x6fd8c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6fd91  ldstr    aDestination// "destination"
0x6fd96  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x6fd9b  stloc.0
0x6fd9c  ldloc.0
0x6fd9d  ldtoken  instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Label [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_DisplayName()
0x6fda2  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x6fda7  castclass [mscorlib]System.Reflection.MethodInfo
0x6fdac  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x6fdb1  ldc.i4.1
0x6fdb2  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x6fdb7  dup
0x6fdb8  ldc.i4.0
0x6fdb9  ldloc.0
0x6fdba  stelem.ref
0x6fdbb  call     T0x2B00000E
0x6fdc0  ldsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_16
0x6fdc5  dup
0x6fdc6  brtrue.s loc_6FDDF
0x6fdc8  pop
0x6fdc9  ldsfld   class <>c <>c::<>9
0x6fdce  ldftn    instance void <>c::<InitializeMap>b__4_16(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata source, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata destination, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x6fdd4  newobj   instance void class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>::.ctor(object, native int)
0x6fdd9  dup
0x6fdda  stsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_16
0x6fddf  ldc.i4.1
0x6fde0  call     class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0> class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata>::CreateMapping(var<u1>, void, class [mscorlib]System.Func`3<var<u1>, !!T0, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>, object)
0x6fde5  callvirt instance void class Microsoft.Crm.MetadataService.Sdk.TypeMaps.CultureNeutralPropertyMap`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata>::SetPropertyMapping(string, class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0>)
0x6fdea  ldarg.0
0x6fdeb  ldstr    aHaschanged// "HasChanged"
0x6fdf0  ldnull
0x6fdf1  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata
0x6fdf6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6fdfb  ldstr    aDestination// "destination"
0x6fe00  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x6fe05  stloc.0
0x6fe06  ldloc.0
0x6fe07  ldtoken  instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase::get_HasChanged()
0x6fe0c  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x6fe11  castclass [mscorlib]System.Reflection.MethodInfo
0x6fe16  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x6fe1b  ldtoken  [mscorlib]System.Object
0x6fe20  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6fe25  call     class [System.Core]System.Linq.Expressions.UnaryExpression [System.Core]System.Linq.Expressions.Expression::Convert(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Type)
0x6fe2a  ldc.i4.1
0x6fe2b  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x6fe30  dup
0x6fe31  ldc.i4.0
0x6fe32  ldloc.0
0x6fe33  stelem.ref
0x6fe34  call     T0x2B00000E
0x6fe39  ldsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_18
0x6fe3e  dup
0x6fe3f  brtrue.s loc_6FE58
0x6fe41  pop
0x6fe42  ldsfld   class <>c <>c::<>9
0x6fe47  ldftn    instance void <>c::<InitializeMap>b__4_18(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata source, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata destination, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x6fe4d  newobj   instance void class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>::.ctor(object, native int)
0x6fe52  dup
0x6fe53  stsfld   class [mscorlib]System.Action`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext> <>c::<>9__4_18
0x6fe58  call     class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0> class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata>::CreateMapping(var<u1>, void, class [mscorlib]System.Func`3<var<u1>, !!T0, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext>)
0x6fe5d  callvirt instance void class Microsoft.Crm.MetadataService.Sdk.TypeMaps.CultureNeutralPropertyMap`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata>::SetPropertyMapping(string, class Microsoft.Crm.MetadataService.Sdk.TypeMaps.PropertyMapping`2<var<u1>, !!T0>)
0x6fe62  ldarg.0
0x6fe63  ldstr    aIsdocumentmana_0// "IsDocumentManagementEnabled"
0x6fe68  ldsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object> <>c::<>9__4_19
0x6fe6d  dup
0x6fe6e  brtrue.s loc_6FE87
0x6fe70  pop
0x6fe71  ldsfld   class <>c <>c::<>9
0x6fe76  ldftn    instance object <>c::<InitializeMap>b__4_19(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata source, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext context)
0x6fe7c  newobj   instance void class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object>::.ctor(object, native int)
0x6fe81  dup
0x6fe82  stsfld   class [mscorlib]System.Func`3<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class Microsoft.Crm.Sdk.Metadata.MetadataConversionContext, object> <>c::<>9__4_19
0x6fe87  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata
  ... truncated ...
```
