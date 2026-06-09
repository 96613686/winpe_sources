# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemFinder::GetItemChangeInfo

- ea: `0x5c940`
- end: `0x5cab4`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemFinder::GetItemChangeInfo`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x5cb00`

## callees

- `0xac40`
- `0x5c940`
- `0x5e150`
- `0x5e610`
- `0x5eae0`
- `0x5eaf0`
- `0x5eb00`
- `0x5eb10`
- `0x5eb50`
- `0x5eb60`
- `0x5eb70`
- `0x5ebe0`

## string_xrefs

- `0x5ca57`: `The item with exchange id '{0}', crm id '{1}' and link state '{2}' will be added to id mapping.`
- `0x5ca8b`: `The item with exchange id '{0}' and link state '{1}' will not be processed by RebuildIdMappingStep as it is not a valid item.`

## pseudocode

```c

```

## disassembly

```asm
0x5c940  ldc.i4.1
0x5c941  stloc.0
0x5c942  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::.ctor()
0x5c947  stloc.1
0x5c948  ldloc.1
0x5c949  ldarg.1
0x5c94a  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ItemId [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::get_Id()
0x5c94f  callvirt instance string [mscorlib]System.Object::ToString()
0x5c954  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::set_ExchangeEntryId(string value)
0x5c959  ldloc.1
0x5c95a  ldarg.2
0x5c95b  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::set_ItemObjectType(valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType value)
0x5c960  ldloc.1
0x5c961  ldarg.1
0x5c962  call     valuetype Microsoft.Crm.Asynchronous.EmailConnector.LinkState Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemFinder::GetLinkState(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item item)
0x5c967  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::set_ItemLinkState(valuetype Microsoft.Crm.Asynchronous.EmailConnector.LinkState value)
0x5c96c  ldloc.1
0x5c96d  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.LinkState Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_ItemLinkState()
0x5c972  ldc.i4.2
0x5c973  bne.un.s loc_5C977
0x5c975  ldc.i4.0
0x5c976  stloc.0
0x5c977  ldarg.1
0x5c978  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyCollection [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::get_ExtendedProperties()
0x5c97d  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ComplexPropertyCollection`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedProperty>::GetEnumerator()
0x5c982  stloc.2
0x5c983  br       loc_5CA3B
0x5c988  ldloc.2
0x5c989  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedProperty>::get_Current()
0x5c98e  stloc.3
0x5c98f  ldloc.3
0x5c990  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedProperty::get_PropertyDefinition()
0x5c995  callvirt instance string [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::get_Name()
0x5c99a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5c99f  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0x5c9a4  ldstr    aCrmid_1// "CRMID"
0x5c9a9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5c9ae  brfalse.s loc_5C9E3
0x5c9b0  ldloc.3
0x5c9b1  callvirt instance object [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedProperty::get_Value()
0x5c9b6  brfalse.s loc_5C9DF
0x5c9b8  ldloc.3
0x5c9b9  callvirt instance object [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedProperty::get_Value()
0x5c9be  callvirt instance string [mscorlib]System.Object::ToString()
0x5c9c3  call     bool Microsoft.Crm.Asynchronous.EmailConnector.CrmHelper::IsValidCrmId(string crmIdString)
0x5c9c8  brfalse.s loc_5C9DF
0x5c9ca  ldloc.1
0x5c9cb  ldloc.3
0x5c9cc  callvirt instance object [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedProperty::get_Value()
0x5c9d1  callvirt instance string [mscorlib]System.Object::ToString()
0x5c9d6  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::set_CrmId(string value)
0x5c9db  ldc.i4.1
0x5c9dc  stloc.0
0x5c9dd  br.s     loc_5CA3B
0x5c9df  ldc.i4.0
0x5c9e0  stloc.0
0x5c9e1  br.s     loc_5CA3B
0x5c9e3  ldloc.3
0x5c9e4  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedProperty::get_PropertyDefinition()
0x5c9e9  callvirt instance string [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::get_Name()
0x5c9ee  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5c9f3  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0x5c9f8  ldstr    aCrmobjecttypec_0// "CRMOBJECTTYPECODE"
0x5c9fd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5ca02  brfalse.s loc_5CA3B
0x5ca04  ldloc.3
0x5ca05  callvirt instance object [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedProperty::get_Value()
0x5ca0a  brfalse.s loc_5CA3B
0x5ca0c  ldloc.3
0x5ca0d  callvirt instance object [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedProperty::get_Value()
0x5ca12  callvirt instance string [mscorlib]System.Object::ToString()
0x5ca17  callvirt instance int32 [mscorlib]System.String::get_Length()
0x5ca1c  ldc.i4.0
0x5ca1d  ble.s    loc_5CA3B
0x5ca1f  ldloc.3
0x5ca20  callvirt instance object [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedProperty::get_Value()
0x5ca25  callvirt instance string [mscorlib]System.Object::ToString()
0x5ca2a  ldloca.s 4
0x5ca2c  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0x5ca31  brfalse.s loc_5CA3B
0x5ca33  ldloc.1
0x5ca34  ldloc.s  4
0x5ca36  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::set_ItemObjectType(valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType value)
0x5ca3b  ldloc.2
0x5ca3c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5ca41  brtrue   loc_5C988
0x5ca46  leave.s  loc_5CA52
0x5ca48  ldloc.2
0x5ca49  brfalse.s loc_5CA51
0x5ca4b  ldloc.2
0x5ca4c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5ca51  endfinally
0x5ca52  ldloc.0
0x5ca53  brfalse.s loc_5CA89
0x5ca55  ldarg.0
0x5ca56  ldc.i4.4
0x5ca57  ldstr    aTheItemWithExc// "The item with exchange id '{0}', crm id"...
0x5ca5c  ldc.i4.3
0x5ca5d  newarr   [mscorlib]System.Object
0x5ca62  dup
0x5ca63  ldc.i4.0
0x5ca64  ldloc.1
0x5ca65  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_ExchangeEntryId()
0x5ca6a  stelem.ref
0x5ca6b  dup
0x5ca6c  ldc.i4.1
0x5ca6d  ldloc.1
0x5ca6e  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_CrmId()
0x5ca73  stelem.ref
0x5ca74  dup
0x5ca75  ldc.i4.2
0x5ca76  ldloc.1
0x5ca77  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.LinkState Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_ItemLinkState()
0x5ca7c  box      Microsoft.Crm.Asynchronous.EmailConnector.LinkState
0x5ca81  stelem.ref
0x5ca82  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x5ca87  ldloc.1
0x5ca88  ret
0x5ca89  ldarg.0
0x5ca8a  ldc.i4.4
0x5ca8b  ldstr    aTheItemWithExc_0// "The item with exchange id '{0}' and lin"...
0x5ca90  ldc.i4.2
0x5ca91  newarr   [mscorlib]System.Object
0x5ca96  dup
0x5ca97  ldc.i4.0
0x5ca98  ldloc.1
0x5ca99  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_ExchangeEntryId()
0x5ca9e  stelem.ref
0x5ca9f  dup
0x5caa0  ldc.i4.1
0x5caa1  ldloc.1
0x5caa2  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.LinkState Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_ItemLinkState()
0x5caa7  box      Microsoft.Crm.Asynchronous.EmailConnector.LinkState
0x5caac  stelem.ref
0x5caad  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x5cab2  ldnull
0x5cab3  ret
```
