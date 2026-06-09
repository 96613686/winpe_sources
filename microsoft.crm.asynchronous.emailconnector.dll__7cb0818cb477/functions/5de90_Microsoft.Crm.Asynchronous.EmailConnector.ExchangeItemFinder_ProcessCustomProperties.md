# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemFinder::ProcessCustomProperties

- ea: `0x5de90`
- end: `0x5e04d`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemFinder::ProcessCustomProperties`
- size: `445`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x5e050`

## callees

- `0x5de90`
- `0x68510`

## string_xrefs

- `0x5dede`: `crmLinkState`
- `0x5df61`: `crmLinkState`

## pseudocode

```c

```

## disassembly

```asm
0x5de90  ldnull
0x5de91  stloc.0
0x5de92  ldarg.1
0x5de93  brfalse  loc_5E04C
0x5de98  ldarg.1
0x5de99  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Count()
0x5de9e  ldc.i4.0
0x5de9f  ble      loc_5E04C
0x5dea4  ldarg.1
0x5dea5  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::GetEnumerator()
0x5deaa  stloc.1
0x5deab  br       loc_5E030
0x5deb0  ldloca.s 1
0x5deb2  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>::get_Current()
0x5deb7  stloc.2
0x5deb8  ldloca.s 2
0x5deba  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x5debf  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5dec4  stloc.3
0x5dec5  ldloca.s 2
0x5dec7  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x5decc  stloc.s  4
0x5dece  ldloc.s  4
0x5ded0  ldstr    aCrmid// "crmid"
0x5ded5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5deda  brtrue.s loc_5DF33
0x5dedc  ldloc.s  4
0x5dede  ldstr    aCrmlinkstate// "crmLinkState"
0x5dee3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5dee8  brtrue.s loc_5DF61
0x5deea  ldloc.s  4
0x5deec  ldstr    aCrmregardingid// "crmRegardingId"
0x5def1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5def6  brtrue   loc_5DF8F
0x5defb  ldloc.s  4
0x5defd  ldstr    aCrmregardingob// "crmRegardingObjectType"
0x5df02  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5df07  brtrue   loc_5DFBA
0x5df0c  ldloc.s  4
0x5df0e  ldstr    aRegarding// "Regarding"
0x5df13  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5df18  brtrue   loc_5DFE2
0x5df1d  ldloc.s  4
0x5df1f  ldstr    aCrmisfollowed// "crmIsFollowed"
0x5df24  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5df29  brtrue   loc_5E00A
0x5df2e  br       loc_5E030
0x5df33  ldstr    aCrmid// "crmid"
0x5df38  call     class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::GetExtendedPropertyDefinition(string propertyName)
0x5df3d  stloc.0
0x5df3e  ldloc.3
0x5df3f  brfalse.s loc_5DF4E
0x5df41  ldarg.0
0x5df42  ldloc.0
0x5df43  callvirt instance bool [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::RemoveExtendedProperty(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition)
0x5df48  pop
0x5df49  br       loc_5E030
0x5df4e  ldarg.0
0x5df4f  ldloc.0
0x5df50  ldloca.s 2
0x5df52  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x5df57  callvirt instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::SetExtendedProperty(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition, object)
0x5df5c  br       loc_5E030
0x5df61  ldstr    aCrmlinkstate// "crmLinkState"
0x5df66  call     class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::GetExtendedPropertyDefinition(string propertyName)
0x5df6b  stloc.0
0x5df6c  ldloc.3
0x5df6d  brfalse.s loc_5DF7C
0x5df6f  ldarg.0
0x5df70  ldloc.0
0x5df71  callvirt instance bool [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::RemoveExtendedProperty(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition)
0x5df76  pop
0x5df77  br       loc_5E030
0x5df7c  ldarg.0
0x5df7d  ldloc.0
0x5df7e  ldloca.s 2
0x5df80  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x5df85  callvirt instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::SetExtendedProperty(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition, object)
0x5df8a  br       loc_5E030
0x5df8f  ldstr    aCrmregardingid// "crmRegardingId"
0x5df94  call     class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::GetExtendedPropertyDefinition(string propertyName)
0x5df99  stloc.0
0x5df9a  ldloc.3
0x5df9b  brfalse.s loc_5DFAA
0x5df9d  ldarg.0
0x5df9e  ldloc.0
0x5df9f  callvirt instance bool [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::RemoveExtendedProperty(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition)
0x5dfa4  pop
0x5dfa5  br       loc_5E030
0x5dfaa  ldarg.0
0x5dfab  ldloc.0
0x5dfac  ldloca.s 2
0x5dfae  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x5dfb3  callvirt instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::SetExtendedProperty(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition, object)
0x5dfb8  br.s     loc_5E030
0x5dfba  ldstr    aCrmregardingob// "crmRegardingObjectType"
0x5dfbf  call     class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::GetExtendedPropertyDefinition(string propertyName)
0x5dfc4  stloc.0
0x5dfc5  ldloc.3
0x5dfc6  brfalse.s loc_5DFD2
0x5dfc8  ldarg.0
0x5dfc9  ldloc.0
0x5dfca  callvirt instance bool [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::RemoveExtendedProperty(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition)
0x5dfcf  pop
0x5dfd0  br.s     loc_5E030
0x5dfd2  ldarg.0
0x5dfd3  ldloc.0
0x5dfd4  ldloca.s 2
0x5dfd6  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x5dfdb  callvirt instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::SetExtendedProperty(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition, object)
0x5dfe0  br.s     loc_5E030
0x5dfe2  ldstr    aCrmregardingna// "crmRegardingName"
0x5dfe7  call     class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::GetExtendedPropertyDefinition(string propertyName)
0x5dfec  stloc.0
0x5dfed  ldloc.3
0x5dfee  brfalse.s loc_5DFFA
0x5dff0  ldarg.0
0x5dff1  ldloc.0
0x5dff2  callvirt instance bool [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::RemoveExtendedProperty(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition)
0x5dff7  pop
0x5dff8  br.s     loc_5E030
0x5dffa  ldarg.0
0x5dffb  ldloc.0
0x5dffc  ldloca.s 2
0x5dffe  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x5e003  callvirt instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::SetExtendedProperty(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition, object)
0x5e008  br.s     loc_5E030
0x5e00a  ldstr    aCrmisfollowed// "crmIsFollowed"
0x5e00f  call     class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::GetExtendedPropertyDefinition(string propertyName)
0x5e014  stloc.0
0x5e015  ldloc.3
0x5e016  brfalse.s loc_5E022
0x5e018  ldarg.0
0x5e019  ldloc.0
0x5e01a  callvirt instance bool [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::RemoveExtendedProperty(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition)
0x5e01f  pop
0x5e020  br.s     loc_5E030
0x5e022  ldarg.0
0x5e023  ldloc.0
0x5e024  ldloca.s 2
0x5e026  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x5e02b  callvirt instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::SetExtendedProperty(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition, object)
0x5e030  ldloca.s 1
0x5e032  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>::MoveNext()
0x5e037  brtrue   loc_5DEB0
0x5e03c  leave.s  loc_5E04C
0x5e03e  ldloca.s 1
0x5e040  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>
0x5e046  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5e04b  endfinally
0x5e04c  ret
```
