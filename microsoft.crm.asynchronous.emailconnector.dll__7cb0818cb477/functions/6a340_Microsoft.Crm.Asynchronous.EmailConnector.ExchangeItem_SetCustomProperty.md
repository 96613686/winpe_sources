# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::SetCustomProperty

- ea: `0x6a340`
- end: `0x6a4c1`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::SetCustomProperty`
- size: `385`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x6a2a0`

## callees

- `0xb8e0`
- `0xb910`
- `0xb930`
- `0x69840`
- `0x6a340`
- `0x81700`

## string_xrefs

- `0x6a40a`: `crmLinkState`
- `0x6a44a`: `crmLinkStateTracker`

## pseudocode

```c

```

## disassembly

```asm
0x6a340  ldarg.0
0x6a341  call     instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::get_Item()
0x6a346  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeHelper::ExtractExtendedPropertiesFromCustomPropertyAppointment(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item item)
0x6a34b  stloc.0
0x6a34c  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x6a351  stloc.1
0x6a352  call     class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeHelper::GetSSSCustomPropertyDefinition()
0x6a357  stloc.2
0x6a358  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType>::.ctor()
0x6a35d  pop
0x6a35e  ldloc.0
0x6a35f  brfalse  loc_6A4C0
0x6a364  ldloc.0
0x6a365  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Count()
0x6a36a  ldc.i4.0
0x6a36b  ble      loc_6A4C0
0x6a370  ldloc.0
0x6a371  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::GetEnumerator()
0x6a376  stloc.s  4
0x6a378  br       loc_6A47A
0x6a37d  ldloca.s 4
0x6a37f  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>::get_Current()
0x6a384  stloc.s  5
0x6a386  ldloca.s 5
0x6a388  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x6a38d  stloc.s  6
0x6a38f  ldloc.s  6
0x6a391  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x6a396  stloc.s  7
0x6a398  ldloc.s  7
0x6a39a  ldc.i4   0x3E6B5E3F
0x6a39f  bgt.un.s loc_6A3C4
0x6a3a1  ldloc.s  7
0x6a3a3  ldc.i4   0x1033BBD5
0x6a3a8  beq.s    loc_6A418
0x6a3aa  ldloc.s  7
0x6a3ac  ldc.i4   0x2B9C97CC
0x6a3b1  beq.s    loc_6A408
0x6a3b3  ldloc.s  7
0x6a3b5  ldc.i4   0x3E6B5E3F
0x6a3ba  beq      loc_6A458
0x6a3bf  br       loc_6A466
0x6a3c4  ldloc.s  7
0x6a3c6  ldc.i4   0xCACA87A0
0x6a3cb  bgt.un.s loc_6A3E4
0x6a3cd  ldloc.s  7
0x6a3cf  ldc.i4   0x638256FA
0x6a3d4  beq.s    loc_6A3F8
0x6a3d6  ldloc.s  7
0x6a3d8  ldc.i4   0xCACA87A0
0x6a3dd  beq.s    loc_6A448
0x6a3df  br       loc_6A466
0x6a3e4  ldloc.s  7
0x6a3e6  ldc.i4   0xF3B6BC27
0x6a3eb  beq.s    loc_6A428
0x6a3ed  ldloc.s  7
0x6a3ef  ldc.i4   0xF93751D6
0x6a3f4  beq.s    loc_6A438
0x6a3f6  br.s     loc_6A466
0x6a3f8  ldloc.s  6
0x6a3fa  ldstr    aCrmid// "crmid"
0x6a3ff  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6a404  brtrue.s loc_6A47A
0x6a406  br.s     loc_6A466
0x6a408  ldloc.s  6
0x6a40a  ldstr    aCrmlinkstate// "crmLinkState"
0x6a40f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6a414  brtrue.s loc_6A47A
0x6a416  br.s     loc_6A466
0x6a418  ldloc.s  6
0x6a41a  ldstr    aCrmregardingid// "crmRegardingId"
0x6a41f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6a424  brtrue.s loc_6A47A
0x6a426  br.s     loc_6A466
0x6a428  ldloc.s  6
0x6a42a  ldstr    aCrmregardingob// "crmRegardingObjectType"
0x6a42f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6a434  brtrue.s loc_6A47A
0x6a436  br.s     loc_6A466
0x6a438  ldloc.s  6
0x6a43a  ldstr    aRegarding// "Regarding"
0x6a43f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6a444  brtrue.s loc_6A47A
0x6a446  br.s     loc_6A466
0x6a448  ldloc.s  6
0x6a44a  ldstr    aCrmlinkstatetr// "crmLinkStateTracker"
0x6a44f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6a454  brtrue.s loc_6A47A
0x6a456  br.s     loc_6A466
0x6a458  ldloc.s  6
0x6a45a  ldstr    aCrmisfollowed// "crmIsFollowed"
0x6a45f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6a464  brtrue.s loc_6A47A
0x6a466  ldloc.1
0x6a467  ldloca.s 5
0x6a469  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x6a46e  ldloca.s 5
0x6a470  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x6a475  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x6a47a  ldloca.s 4
0x6a47c  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>::MoveNext()
0x6a481  brtrue   loc_6A37D
0x6a486  leave.s  loc_6A496
0x6a488  ldloca.s 4
0x6a48a  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>
0x6a490  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6a495  endfinally
0x6a496  ldloc.1
0x6a497  call     string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeHelper::SerializeCustomProperties(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> customProperties)
0x6a49c  stloc.3
0x6a49d  ldloc.3
0x6a49e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6a4a3  brtrue.s loc_6A4B3
0x6a4a5  ldarg.0
0x6a4a6  call     instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::get_Item()
0x6a4ab  ldloc.2
0x6a4ac  ldloc.3
0x6a4ad  callvirt instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::SetExtendedProperty(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition, object)
0x6a4b2  ret
0x6a4b3  ldarg.0
0x6a4b4  call     instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::get_Item()
0x6a4b9  ldloc.2
0x6a4ba  callvirt instance bool [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::RemoveExtendedProperty(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition)
0x6a4bf  pop
0x6a4c0  ret
```
