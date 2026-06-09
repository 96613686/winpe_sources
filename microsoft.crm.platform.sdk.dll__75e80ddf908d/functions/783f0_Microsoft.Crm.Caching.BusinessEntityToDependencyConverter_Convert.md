# Microsoft.Crm.Caching.BusinessEntityToDependencyConverter::Convert

- ea: `0x783f0`
- end: `0x784b1`
- name: `Microsoft.Crm.Caching.BusinessEntityToDependencyConverter::Convert`
- size: `193`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x782e0`
- `0x78300`
- `0x78320`
- `0x78340`
- `0x78360`
- `0x78380`
- `0x783a0`
- `0x783c0`
- `0x783d0`
- `0x9c500`

## string_xrefs

- `0x7842e`: `dependentcomponentobjectid`
- `0x78444`: `dependentcomponenttype`
- `0x7845a`: `requiredcomponentobjectid`
- `0x78470`: `requiredcomponenttype`
- `0x78486`: `dependentcomponentbasesolutionid`
- `0x7849c`: `dependentcomponentparentid`

## pseudocode

```c

```

## disassembly

```asm
0x783f0  ldarg.1
0x783f1  ldstr    aDependency// "dependency"
0x783f6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x783fb  newobj   instance void Microsoft.Crm.Caching.DependencyData::.ctor()
0x78400  dup
0x78401  ldarg.1
0x78402  ldstr    aDependencyid// "dependencyid"
0x78407  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x7840c  unbox.any [mscorlib]System.Guid
0x78411  callvirt instance void Microsoft.Crm.Caching.DependencyData::set_DependencyId(valuetype [mscorlib]System.Guid value)
0x78416  dup
0x78417  ldarg.1
0x78418  ldstr    aDependencytype// "dependencytype"
0x7841d  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x78422  unbox.any [mscorlib]System.Int32
0x78427  callvirt instance void Microsoft.Crm.Caching.DependencyData::set_DependencyType(int32 value)
0x7842c  dup
0x7842d  ldarg.1
0x7842e  ldstr    aDependentcompo// "dependentcomponentobjectid"
0x78433  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x78438  unbox.any [mscorlib]System.Guid
0x7843d  callvirt instance void Microsoft.Crm.Caching.DependencyData::set_DependentComponentObjectId(valuetype [mscorlib]System.Guid value)
0x78442  dup
0x78443  ldarg.1
0x78444  ldstr    aDependentcompo_0// "dependentcomponenttype"
0x78449  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x7844e  unbox.any [mscorlib]System.Int32
0x78453  callvirt instance void Microsoft.Crm.Caching.DependencyData::set_DependentComponentType(int32 value)
0x78458  dup
0x78459  ldarg.1
0x7845a  ldstr    aRequiredcompon// "requiredcomponentobjectid"
0x7845f  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x78464  unbox.any [mscorlib]System.Guid
0x78469  callvirt instance void Microsoft.Crm.Caching.DependencyData::set_RequiredComponentObjectId(valuetype [mscorlib]System.Guid value)
0x7846e  dup
0x7846f  ldarg.1
0x78470  ldstr    aRequiredcompon_0// "requiredcomponenttype"
0x78475  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x7847a  unbox.any [mscorlib]System.Int32
0x7847f  callvirt instance void Microsoft.Crm.Caching.DependencyData::set_RequiredComponentType(int32 value)
0x78484  dup
0x78485  ldarg.1
0x78486  ldstr    aDependentcompo_1// "dependentcomponentbasesolutionid"
0x7848b  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x78490  unbox.any [mscorlib]System.Guid
0x78495  callvirt instance void Microsoft.Crm.Caching.DependencyData::set_DependentComponentBaseSolutionId(valuetype [mscorlib]System.Guid value)
0x7849a  dup
0x7849b  ldarg.1
0x7849c  ldstr    aDependentcompo_2// "dependentcomponentparentid"
0x784a1  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x784a6  unbox.any [mscorlib]System.Guid
0x784ab  callvirt instance void Microsoft.Crm.Caching.DependencyData::set_DependentComponentParentId(valuetype [mscorlib]System.Guid value)
0x784b0  ret
```
