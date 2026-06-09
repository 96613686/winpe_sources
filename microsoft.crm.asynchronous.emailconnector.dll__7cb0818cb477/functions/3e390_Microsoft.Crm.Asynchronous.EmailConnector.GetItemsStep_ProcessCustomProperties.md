# Microsoft.Crm.Asynchronous.EmailConnector.GetItemsStep::ProcessCustomProperties

- ea: `0x3e390`
- end: `0x3e6d9`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.GetItemsStep::ProcessCustomProperties`
- size: `841`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x3dcb0`

## callees

- `0xb8c0`
- `0x15860`
- `0x15880`
- `0x15890`
- `0x3e390`
- `0x41af0`
- `0x41c30`
- `0x41c70`
- `0x41c90`
- `0x41ca0`
- `0x41cc0`
- `0x41cd0`
- `0x41ce0`
- `0x41cf0`
- `0x81700`

## string_xrefs

- `0x3e470`: `crmLinkState`
- `0x3e4c8`: `crmLinkStateTracker`

## pseudocode

```c

```

## disassembly

```asm
0x3e390  ldarg.2
0x3e391  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeHelper::ExtractExtendedPropertiesFromCustomPropertyEmail(class Microsoft.Crm.Asynchronous.EmailConnector.MessageType message)
0x3e396  stloc.0
0x3e397  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType>::.ctor()
0x3e39c  stloc.1
0x3e39d  ldloc.0
0x3e39e  brfalse  loc_3E6D2
0x3e3a3  ldloc.0
0x3e3a4  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Count()
0x3e3a9  ldc.i4.0
0x3e3aa  ble      loc_3E6D2
0x3e3af  ldloc.0
0x3e3b0  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::GetEnumerator()
0x3e3b5  stloc.2
0x3e3b6  br       loc_3E6B6
0x3e3bb  ldloca.s 2
0x3e3bd  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>::get_Current()
0x3e3c2  stloc.3
0x3e3c3  ldloca.s 3
0x3e3c5  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x3e3ca  stloc.s  4
0x3e3cc  ldloc.s  4
0x3e3ce  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x3e3d3  stloc.s  5
0x3e3d5  ldloc.s  5
0x3e3d7  ldc.i4   0x3E6B5E3F
0x3e3dc  bgt.un.s loc_3E41E
0x3e3de  ldloc.s  5
0x3e3e0  ldc.i4   0x2B9C97CC
0x3e3e5  bgt.un.s loc_3E401
0x3e3e7  ldloc.s  5
0x3e3e9  ldc.i4   0x1033BBD5
0x3e3ee  beq      loc_3E484
0x3e3f3  ldloc.s  5
0x3e3f5  ldc.i4   0x2B9C97CC
0x3e3fa  beq.s    loc_3E46E
0x3e3fc  br       loc_3E69D
0x3e401  ldloc.s  5
0x3e403  ldc.i4   0x395AF4FD
0x3e408  beq      loc_3E4F2
0x3e40d  ldloc.s  5
0x3e40f  ldc.i4   0x3E6B5E3F
0x3e414  beq      loc_3E4DC
0x3e419  br       loc_3E69D
0x3e41e  ldloc.s  5
0x3e420  ldc.i4   0xCACA87A0
0x3e425  bgt.un.s loc_3E441
0x3e427  ldloc.s  5
0x3e429  ldc.i4   0x638256FA
0x3e42e  beq.s    loc_3E458
0x3e430  ldloc.s  5
0x3e432  ldc.i4   0xCACA87A0
0x3e437  beq      loc_3E4C6
0x3e43c  br       loc_3E69D
0x3e441  ldloc.s  5
0x3e443  ldc.i4   0xF3B6BC27
0x3e448  beq.s    loc_3E49A
0x3e44a  ldloc.s  5
0x3e44c  ldc.i4   0xF93751D6
0x3e451  beq.s    loc_3E4B0
0x3e453  br       loc_3E69D
0x3e458  ldloc.s  4
0x3e45a  ldstr    aCrmid// "crmid"
0x3e45f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3e464  brtrue   loc_3E508
0x3e469  br       loc_3E69D
0x3e46e  ldloc.s  4
0x3e470  ldstr    aCrmlinkstate// "crmLinkState"
0x3e475  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3e47a  brtrue   loc_3E53C
0x3e47f  br       loc_3E69D
0x3e484  ldloc.s  4
0x3e486  ldstr    aCrmregardingid// "crmRegardingId"
0x3e48b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3e490  brtrue   loc_3E570
0x3e495  br       loc_3E69D
0x3e49a  ldloc.s  4
0x3e49c  ldstr    aCrmregardingob// "crmRegardingObjectType"
0x3e4a1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3e4a6  brtrue   loc_3E5A4
0x3e4ab  br       loc_3E69D
0x3e4b0  ldloc.s  4
0x3e4b2  ldstr    aRegarding// "Regarding"
0x3e4b7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3e4bc  brtrue   loc_3E5D8
0x3e4c1  br       loc_3E69D
0x3e4c6  ldloc.s  4
0x3e4c8  ldstr    aCrmlinkstatetr// "crmLinkStateTracker"
0x3e4cd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3e4d2  brtrue   loc_3E60C
0x3e4d7  br       loc_3E69D
0x3e4dc  ldloc.s  4
0x3e4de  ldstr    aCrmisfollowed// "crmIsFollowed"
0x3e4e3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3e4e8  brtrue   loc_3E63D
0x3e4ed  br       loc_3E69D
0x3e4f2  ldloc.s  4
0x3e4f4  ldstr    aCrmcategorytra// "crmCategoryTracker"
0x3e4f9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3e4fe  brtrue   loc_3E66E
0x3e503  br       loc_3E69D
0x3e508  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType::.ctor()
0x3e50d  stloc.s  6
0x3e50f  ldloc.s  6
0x3e511  ldarg.0
0x3e512  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3e517  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.PathToExtendedFieldType Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::GetCrmIdExtendedFieldTypePath()
0x3e51c  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType::set_ExtendedFieldURI(class Microsoft.Crm.Asynchronous.EmailConnector.PathToExtendedFieldType value)
0x3e521  ldloc.s  6
0x3e523  ldloca.s 3
0x3e525  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x3e52a  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType::set_Item(object value)
0x3e52f  ldloc.1
0x3e530  ldloc.s  6
0x3e532  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType>::Add(var<u1>)
0x3e537  br       loc_3E69D
0x3e53c  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType::.ctor()
0x3e541  stloc.s  7
0x3e543  ldloc.s  7
0x3e545  ldarg.0
0x3e546  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3e54b  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.PathToExtendedFieldType Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::GetLinkStateExtendedFieldTypePath()
0x3e550  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType::set_ExtendedFieldURI(class Microsoft.Crm.Asynchronous.EmailConnector.PathToExtendedFieldType value)
0x3e555  ldloc.s  7
0x3e557  ldloca.s 3
0x3e559  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x3e55e  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType::set_Item(object value)
0x3e563  ldloc.1
0x3e564  ldloc.s  7
0x3e566  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType>::Add(var<u1>)
0x3e56b  br       loc_3E69D
0x3e570  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType::.ctor()
0x3e575  stloc.s  8
0x3e577  ldloc.s  8
0x3e579  ldarg.0
0x3e57a  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3e57f  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.PathToExtendedFieldType Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::GetRegardingIdExtendedFieldTypePath()
0x3e584  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType::set_ExtendedFieldURI(class Microsoft.Crm.Asynchronous.EmailConnector.PathToExtendedFieldType value)
0x3e589  ldloc.s  8
0x3e58b  ldloca.s 3
0x3e58d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x3e592  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType::set_Item(object value)
0x3e597  ldloc.1
0x3e598  ldloc.s  8
0x3e59a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType>::Add(var<u1>)
0x3e59f  br       loc_3E69D
0x3e5a4  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType::.ctor()
0x3e5a9  stloc.s  9
0x3e5ab  ldloc.s  9
0x3e5ad  ldarg.0
0x3e5ae  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3e5b3  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.PathToExtendedFieldType Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::GetRegardingObjectTypeExtendedFieldTypePath()
0x3e5b8  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType::set_ExtendedFieldURI(class Microsoft.Crm.Asynchronous.EmailConnector.PathToExtendedFieldType value)
0x3e5bd  ldloc.s  9
0x3e5bf  ldloca.s 3
0x3e5c1  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x3e5c6  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType::set_Item(object value)
0x3e5cb  ldloc.1
0x3e5cc  ldloc.s  9
0x3e5ce  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType>::Add(var<u1>)
0x3e5d3  br       loc_3E69D
0x3e5d8  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType::.ctor()
0x3e5dd  stloc.s  0xA
0x3e5df  ldloc.s  0xA
0x3e5e1  ldarg.0
0x3e5e2  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3e5e7  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.PathToExtendedFieldType Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::GetRegardingExtendedFieldTypePath()
0x3e5ec  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType::set_ExtendedFieldURI(class Microsoft.Crm.Asynchronous.EmailConnector.PathToExtendedFieldType value)
0x3e5f1  ldloc.s  0xA
0x3e5f3  ldloca.s 3
0x3e5f5  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x3e5fa  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType::set_Item(object value)
0x3e5ff  ldloc.1
0x3e600  ldloc.s  0xA
0x3e602  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType>::Add(var<u1>)
0x3e607  br       loc_3E69D
0x3e60c  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType::.ctor()
0x3e611  stloc.s  0xB
0x3e613  ldloc.s  0xB
0x3e615  ldarg.0
0x3e616  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3e61b  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.PathToExtendedFieldType Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::GetLinkStateTrackerExtendedFieldTypePath()
0x3e620  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType::set_ExtendedFieldURI(class Microsoft.Crm.Asynchronous.EmailConnector.PathToExtendedFieldType value)
0x3e625  ldloc.s  0xB
0x3e627  ldloca.s 3
0x3e629  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x3e62e  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType::set_Item(object value)
0x3e633  ldloc.1
0x3e634  ldloc.s  0xB
0x3e636  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType>::Add(var<u1>)
0x3e63b  br.s     loc_3E69D
0x3e63d  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType::.ctor()
0x3e642  stloc.s  0xC
0x3e644  ldloc.s  0xC
0x3e646  ldarg.0
0x3e647  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3e64c  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.PathToExtendedFieldType Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::GetIsFollowedExtendedFieldTypePath()
0x3e651  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType::set_ExtendedFieldURI(class Microsoft.Crm.Asynchronous.EmailConnector.PathToExtendedFieldType value)
0x3e656  ldloc.s  0xC
0x3e658  ldloca.s 3
0x3e65a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x3e65f  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType::set_Item(object value)
0x3e664  ldloc.1
0x3e665  ldloc.s  0xC
0x3e667  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType>::Add(var<u1>)
0x3e66c  br.s     loc_3E69D
0x3e66e  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType::.ctor()
0x3e673  stloc.s  0xD
0x3e675  ldloc.s  0xD
0x3e677  ldarg.0
0x3e678  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3e67d  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.PathToExtendedFieldType Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::GetCategoryTrackerExtendedFieldTypePath()
0x3e682  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType::set_ExtendedFieldURI(class Microsoft.Crm.Asynchronous.EmailConnector.PathToExtendedFieldType value)
0x3e687  ldloc.s  0xD
0x3e689  ldloca.s 3
0x3e68b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x3e690  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType::set_Item(object value)
0x3e695  ldloc.1
0x3e696  ldloc.s  0xD
0x3e698  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType>::Add(var<u1>)
0x3e69d  ldarg.1
0x3e69e  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_CustomProperties()
0x3e6a3  ldloca.s 3
0x3e6a5  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x3e6aa  ldloca.s 3
0x3e6ac  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x3e6b1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x3e6b6  ldloca.s 2
0x3e6b8  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>::MoveNext()
0x3e6bd  brtrue   loc_3E3BB
0x3e6c2  leave.s  loc_3E6D2
0x3e6c4  ldloca.s 2
0x3e6c6  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>
0x3e6cc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3e6d1  endfinally
0x3e6d2  ldloc.1
0x3e6d3  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType>::ToArray()
0x3e6d8  ret
```
