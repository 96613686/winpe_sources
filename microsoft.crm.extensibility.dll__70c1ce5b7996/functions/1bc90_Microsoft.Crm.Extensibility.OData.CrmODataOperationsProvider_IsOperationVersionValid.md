# Microsoft.Crm.Extensibility.OData.CrmODataOperationsProvider::IsOperationVersionValid

- ea: `0x1bc90`
- end: `0x1bd7b`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataOperationsProvider::IsOperationVersionValid`
- size: `235`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1be70`
- `0x1c120`
- `0x1c390`

## callees

- `0xc9a0`
- `0x1bc90`
- `0x1bd80`

## string_xrefs

- `0x1bd12`: `	SDK Message: {0} : Not exposed in v8 metadata since it employs a complex type containing navigation property.`

## pseudocode

```c

```

## disassembly

```asm
0x1bc90  ldarg.2
0x1bc91  ldc.i4.8
0x1bc92  bne.un   loc_1BD2D
0x1bc97  ldsfld   class [System]System.Collections.Generic.ISet`1<string> Microsoft.Crm.Extensibility.OData.CrmODataOperationsProvider::_sdkMessageWithComplexTypesWithNavigationProperties
0x1bc9c  ldarg.0
0x1bc9d  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkRequestDescription::get_RequestName()
0x1bca2  callvirt instance bool class [mscorlib]System.Collections.Generic.ICollection`1<string>::Contains(var<u1>)
0x1bca7  brfalse.s loc_1BCAB
0x1bca9  ldc.i4.0
0x1bcaa  ret
0x1bcab  ldarg.0
0x1bcac  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference> [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkRequestDescription::get_EdmProperties()
0x1bcb1  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference>, bool> <>c::<>9__13_0
0x1bcb6  dup
0x1bcb7  brtrue.s loc_1BCD0
0x1bcb9  pop
0x1bcba  ldsfld   class <>c <>c::<>9
0x1bcbf  ldftn    instance bool <>c::<IsOperationVersionValid>b__13_0(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference> p)
0x1bcc5  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference>, bool>::.ctor(object, native int)
0x1bcca  dup
0x1bccb  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference>, bool> <>c::<>9__13_0
0x1bcd0  call     T0x2B0000B2
0x1bcd5  brtrue.s loc_1BD11
0x1bcd7  ldarg.1
0x1bcd8  brfalse.s loc_1BD2D
0x1bcda  ldarg.1
0x1bcdb  call     instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkResponseDescription::get_EdmReturnType()
0x1bce0  dup
0x1bce1  brtrue.s loc_1BCEF
0x1bce3  pop
0x1bce4  ldloca.s 2
0x1bce6  initobj  valuetype [mscorlib]System.Nullable`1<bool>
0x1bcec  ldloc.2
0x1bced  br.s     loc_1BCFA
0x1bcef  ldnull
0x1bcf0  call     bool Microsoft.Crm.Extensibility.OData.CrmODataOperationsProvider::HasComplexTypeWithNavigationProperty(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference typeReference, [opt] class [System.Core]System.Collections.Generic.HashSet`1<class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference> unresolvedTypeReferences)
0x1bcf5  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x1bcfa  stloc.0
0x1bcfb  ldc.i4.1
0x1bcfc  stloc.1
0x1bcfd  ldloca.s 0
0x1bcff  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x1bd04  ldloc.1
0x1bd05  ceq
0x1bd07  ldloca.s 0
0x1bd09  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x1bd0e  and
0x1bd0f  brfalse.s loc_1BD2D
0x1bd11  ldc.i4.2
0x1bd12  ldstr    aSdkMessage0Not// "\tSDK Message: {0} : Not exposed in v8 "...
0x1bd17  ldc.i4.1
0x1bd18  newarr   [mscorlib]System.Object
0x1bd1d  dup
0x1bd1e  ldc.i4.0
0x1bd1f  ldarg.0
0x1bd20  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkRequestDescription::get_RequestName()
0x1bd25  stelem.ref
0x1bd26  call     void Microsoft.Crm.Extensibility.TraceUtilities::TraceFormat(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x1bd2b  ldc.i4.0
0x1bd2c  ret
0x1bd2d  ldarg.0
0x1bd2e  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkRequestDescription::get_CategoryName()
0x1bd33  ldstr    aCustomoperatio// "CustomOperation"
0x1bd38  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1bd3d  brfalse.s loc_1BD41
0x1bd3f  ldc.i4.1
0x1bd40  ret
0x1bd41  ldarg.0
0x1bd42  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkRequestDescription::get_IntroducedVersion()
0x1bd47  brfalse.s loc_1BD5C
0x1bd49  ldarg.0
0x1bd4a  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkRequestDescription::get_IntroducedVersion()
0x1bd4f  newobj   instance void [mscorlib]System.Version::.ctor(string)
0x1bd54  call     instance int32 [mscorlib]System.Version::get_Major()
0x1bd59  ldarg.2
0x1bd5a  bgt.s    loc_1BD77
0x1bd5c  ldarg.0
0x1bd5d  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkRequestDescription::get_DeprecatedVersion()
0x1bd62  brfalse.s loc_1BD79
0x1bd64  ldarg.0
0x1bd65  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkRequestDescription::get_DeprecatedVersion()
0x1bd6a  newobj   instance void [mscorlib]System.Version::.ctor(string)
0x1bd6f  call     instance int32 [mscorlib]System.Version::get_Major()
0x1bd74  ldarg.2
0x1bd75  bgt.s    loc_1BD79
0x1bd77  ldc.i4.0
0x1bd78  ret
0x1bd79  ldc.i4.1
0x1bd7a  ret
```
