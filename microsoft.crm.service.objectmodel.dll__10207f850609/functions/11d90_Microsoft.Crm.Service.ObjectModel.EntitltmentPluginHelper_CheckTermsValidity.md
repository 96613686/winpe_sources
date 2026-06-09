# Microsoft.Crm.Service.ObjectModel.EntitltmentPluginHelper::CheckTermsValidity

- ea: `0x11d90`
- end: `0x11def`
- name: `Microsoft.Crm.Service.ObjectModel.EntitltmentPluginHelper::CheckTermsValidity`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x11df0`

## callees

- `0x11d90`

## string_xrefs

- `0x11dde`: `You can't create a case for this entitlement because there are no available terms.`

## pseudocode

```c

```

## disassembly

```asm
0x11d90  ldarg.0
0x11d91  brfalse.s loc_11DA0
0x11d93  ldarg.0
0x11d94  ldstr    aRemainingterms// "remainingterms"
0x11d99  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x11d9e  brtrue.s loc_11DA1
0x11da0  ret
0x11da1  ldarg.0
0x11da2  ldstr    aRemainingterms// "remainingterms"
0x11da7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x11dac  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x11db1  call     valuetype [mscorlib]System.Decimal [mscorlib]System.Convert::ToDecimal(object, class [mscorlib]System.IFormatProvider)
0x11db6  ldsfld   valuetype [mscorlib]System.Decimal [mscorlib]System.Decimal::Zero
0x11dbb  call     bool [mscorlib]System.Decimal::op_LessThanOrEqual(valuetype [mscorlib]System.Decimal, valuetype [mscorlib]System.Decimal)
0x11dc0  brtrue.s loc_11DDE
0x11dc2  ldarg.0
0x11dc3  ldstr    aTotalterms// "totalterms"
0x11dc8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x11dcd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x11dd2  call     string [mscorlib]System.Convert::ToString(object, class [mscorlib]System.IFormatProvider)
0x11dd7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x11ddc  brfalse.s loc_11DEE
0x11dde  ldstr    aYouCanTCreateA_0// "You can't create a case for this entitl"...
0x11de3  ldc.i4   0x80060609
0x11de8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x11ded  throw
0x11dee  ret
```
