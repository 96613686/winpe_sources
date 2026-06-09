# Microsoft.Crm.Extensibility.OrganizationDataServiceVisitingQueryProvider::GetAttributeMetadataForComplexTypePropertyExpression

- ea: `0x94a0`
- end: `0x955b`
- name: `Microsoft.Crm.Extensibility.OrganizationDataServiceVisitingQueryProvider::GetAttributeMetadataForComplexTypePropertyExpression`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x9320`

## callees

- `0x94a0`

## string_xrefs

- `0x952c`: `Reference to property {0} on complex type {1} is not supported`

## pseudocode

```c

```

## disassembly

```asm
0x94a0  ldarg.1
0x94a1  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.Core]System.Linq.Expressions.Expression> [System.Core]System.Linq.Expressions.MethodCallExpression::get_Arguments()
0x94a6  ldc.i4.0
0x94a7  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.Core]System.Linq.Expressions.Expression>::get_Item(!!T0)
0x94ac  isinst   [System.Core]System.Linq.Expressions.UnaryExpression
0x94b1  stloc.0
0x94b2  ldloc.0
0x94b3  brfalse  loc_9559
0x94b8  ldloc.0
0x94b9  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.UnaryExpression::get_Operand()
0x94be  isinst   [System.Core]System.Linq.Expressions.MethodCallExpression
0x94c3  stloc.1
0x94c4  ldloc.1
0x94c5  brfalse  loc_9559
0x94ca  ldarg.1
0x94cb  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.Core]System.Linq.Expressions.Expression> [System.Core]System.Linq.Expressions.MethodCallExpression::get_Arguments()
0x94d0  ldc.i4.1
0x94d1  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.Core]System.Linq.Expressions.Expression>::get_Item(!!T0)
0x94d6  castclass [System.Core]System.Linq.Expressions.ConstantExpression
0x94db  callvirt instance object [System.Core]System.Linq.Expressions.ConstantExpression::get_Value()
0x94e0  castclass [System.Data.Services]System.Data.Services.Providers.ResourceProperty
0x94e5  stloc.2
0x94e6  ldloc.1
0x94e7  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.Core]System.Linq.Expressions.Expression> [System.Core]System.Linq.Expressions.MethodCallExpression::get_Arguments()
0x94ec  ldc.i4.1
0x94ed  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.Core]System.Linq.Expressions.Expression>::get_Item(!!T0)
0x94f2  castclass [System.Core]System.Linq.Expressions.ConstantExpression
0x94f7  callvirt instance object [System.Core]System.Linq.Expressions.ConstantExpression::get_Value()
0x94fc  castclass [System.Data.Services]System.Data.Services.Providers.ResourceProperty
0x9501  stloc.3
0x9502  ldloc.3
0x9503  brfalse.s loc_9559
0x9505  ldloc.2
0x9506  brfalse.s loc_9559
0x9508  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RuntimeTypeCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RuntimeTypeCache::get_Instance()
0x950d  ldloc.3
0x950e  callvirt instance class [System.Data.Services]System.Data.Services.Providers.ResourceType [System.Data.Services]System.Data.Services.Providers.ResourceProperty::get_ResourceType()
0x9513  ldloc.2
0x9514  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RuntimeTypeCache::IsComplexKeyProperty(class [System.Data.Services]System.Data.Services.Providers.ResourceType, class [System.Data.Services]System.Data.Services.Providers.ResourceProperty)
0x9519  brfalse.s loc_9527
0x951b  ldloc.3
0x951c  callvirt instance object [System.Data.Services]System.Data.Services.Providers.ResourceProperty::get_CustomState()
0x9521  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata
0x9526  ret
0x9527  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x952c  ldstr    aReferenceToPro// "Reference to property {0} on complex ty"...
0x9531  ldc.i4.2
0x9532  newarr   [mscorlib]System.Object
0x9537  dup
0x9538  ldc.i4.0
0x9539  ldloc.2
0x953a  callvirt instance string [System.Data.Services]System.Data.Services.Providers.ResourceProperty::get_Name()
0x953f  stelem.ref
0x9540  dup
0x9541  ldc.i4.1
0x9542  ldloc.3
0x9543  callvirt instance class [System.Data.Services]System.Data.Services.Providers.ResourceType [System.Data.Services]System.Data.Services.Providers.ResourceProperty::get_ResourceType()
0x9548  callvirt instance string [System.Data.Services]System.Data.Services.Providers.ResourceType::get_Name()
0x954d  stelem.ref
0x954e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9553  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmNotSupportedException::.ctor(string)
0x9558  throw
0x9559  ldnull
0x955a  ret
```
