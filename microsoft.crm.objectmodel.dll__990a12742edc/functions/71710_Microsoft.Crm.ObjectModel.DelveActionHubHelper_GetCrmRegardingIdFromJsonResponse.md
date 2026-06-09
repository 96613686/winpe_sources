# Microsoft.Crm.ObjectModel.DelveActionHubHelper::GetCrmRegardingIdFromJsonResponse

- ea: `0x71710`
- end: `0x718be`
- name: `Microsoft.Crm.ObjectModel.DelveActionHubHelper::GetCrmRegardingIdFromJsonResponse`
- size: `430`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x72340`

## callees

- `0x71710`
- `0x728b0`
- `0x72930`
- `0x729d0`
- `0x72af0`
- `0x72b90`
- `0x731b0`
- `0x731c0`
- `0x73220`
- `0x1c98b0`
- `0x1c98c0`
- `0x1c9e30`
- `0x1c9e50`

## string_xrefs

- `0x717ad`: `GetCrmRegardingIdFromJsonResponse`
- `0x717b8`: `GetCrmRegardingIdFromJsonResponse`
- `0x71859`: `GetCrmRegardingIdFromJsonResponse`
- `0x71864`: `GetCrmRegardingIdFromJsonResponse`
- `0x7187a`: `GetCrmRegardingIdFromJsonResponse`
- `0x71885`: `GetCrmRegardingIdFromJsonResponse`
- `0x718a3`: `GetCrmRegardingIdFromJsonResponse`

## pseudocode

```c

```

## disassembly

```asm
0x71710  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x71715  stloc.0
0x71716  ldarg.1
0x71717  newobj   instance void Microsoft.Crm.ObjectModel.AddressManager::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x7171c  stloc.2
0x7171d  ldarg.0
0x7171e  call     T0x2B000120
0x71723  stloc.3
0x71724  ldloc.3
0x71725  brfalse  loc_71894
0x7172a  ldloc.3
0x7172b  callvirt instance class Microsoft.Crm.ObjectModel.Recipients Microsoft.Crm.ObjectModel.Message::get_From()
0x71730  brfalse.s loc_71798
0x71732  ldloc.3
0x71733  callvirt instance class Microsoft.Crm.ObjectModel.Recipients Microsoft.Crm.ObjectModel.Message::get_From()
0x71738  callvirt instance class Microsoft.Crm.ObjectModel.EmailAddress Microsoft.Crm.ObjectModel.Recipients::get_EmailAddress()
0x7173d  brfalse.s loc_71798
0x7173f  ldloc.3
0x71740  callvirt instance class Microsoft.Crm.ObjectModel.Recipients Microsoft.Crm.ObjectModel.Message::get_From()
0x71745  callvirt instance class Microsoft.Crm.ObjectModel.EmailAddress Microsoft.Crm.ObjectModel.Recipients::get_EmailAddress()
0x7174a  callvirt instance string Microsoft.Crm.ObjectModel.EmailAddress::get_Address()
0x7174f  brfalse.s loc_71798
0x71751  ldloc.2
0x71752  ldloc.3
0x71753  callvirt instance class Microsoft.Crm.ObjectModel.Recipients Microsoft.Crm.ObjectModel.Message::get_From()
0x71758  callvirt instance class Microsoft.Crm.ObjectModel.EmailAddress Microsoft.Crm.ObjectModel.Recipients::get_EmailAddress()
0x7175d  callvirt instance string Microsoft.Crm.ObjectModel.EmailAddress::get_Address()
0x71762  ldc.i4.0
0x71763  callvirt instance class Microsoft.Crm.ObjectModel.AddressEntry[] Microsoft.Crm.ObjectModel.AddressManager::ParseEmailAddresses(string rawInput, valuetype Microsoft.Crm.ObjectModel.AddressCategory addressCategory)
0x71768  stloc.1
0x71769  ldloc.1
0x7176a  ldc.i4.0
0x7176b  ldelem.ref
0x7176c  ldloc.1
0x7176d  ldc.i4.0
0x7176e  ldelem.ref
0x7176f  callvirt instance string Microsoft.Crm.ObjectModel.AddressEntry::get_EmailAddress()
0x71774  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x71779  callvirt instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0x7177e  callvirt instance void Microsoft.Crm.ObjectModel.AddressEntry::set_EmailAddress(string value)
0x71783  ldloc.0
0x71784  ldstr    aSenderemailadd// "SenderEmailAddress"
0x71789  ldloc.1
0x7178a  ldc.i4.0
0x7178b  ldelem.ref
0x7178c  callvirt instance string Microsoft.Crm.ObjectModel.AddressEntry::get_EmailAddress()
0x71791  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x71796  br.s     loc_717C7
0x71798  ldloc.0
0x71799  ldstr    aSenderemailadd// "SenderEmailAddress"
0x7179e  ldsfld   string [mscorlib]System.String::Empty
0x717a3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x717a8  call     class Microsoft.Crm.ObjectModel.DelveActionHubEventSource Microsoft.Crm.ObjectModel.DelveActionHubEventSource::get_Instance()
0x717ad  ldstr    aGetcrmregardin// "GetCrmRegardingIdFromJsonResponse"
0x717b2  ldarg.1
0x717b3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x717b8  ldstr    aGetcrmregardin// "GetCrmRegardingIdFromJsonResponse"
0x717bd  ldstr    aSendersEmailAd// "Senders email address is null or not po"...
0x717c2  callvirt instance void Microsoft.Crm.ObjectModel.DelveActionHubEventSource::LogInformation(string EventName, valuetype [mscorlib]System.Guid OrganizationId, string CallingMethod, string EventDetails)
0x717c7  ldloc.3
0x717c8  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ObjectModel.SingleValueExtendedProperty> Microsoft.Crm.ObjectModel.Message::get_SingleValueExtendedProperties()
0x717cd  brfalse  loc_71875
0x717d2  ldloc.3
0x717d3  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ObjectModel.SingleValueExtendedProperty> Microsoft.Crm.ObjectModel.Message::get_SingleValueExtendedProperties()
0x717d8  dup
0x717d9  ldsfld   class [mscorlib]System.Predicate`1<class Microsoft.Crm.ObjectModel.SingleValueExtendedProperty> <>c::<>9__38_0
0x717de  dup
0x717df  brtrue.s loc_717F8
0x717e1  pop
0x717e2  ldsfld   class <>c <>c::<>9
0x717e7  ldftn    instance bool <>c::<GetCrmRegardingIdFromJsonResponse>b__38_0(class Microsoft.Crm.ObjectModel.SingleValueExtendedProperty x)
0x717ed  newobj   instance void class [mscorlib]System.Predicate`1<class Microsoft.Crm.ObjectModel.SingleValueExtendedProperty>::.ctor(object, native int)
0x717f2  dup
0x717f3  stsfld   class [mscorlib]System.Predicate`1<class Microsoft.Crm.ObjectModel.SingleValueExtendedProperty> <>c::<>9__38_0
0x717f8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ObjectModel.SingleValueExtendedProperty>::Find(!!T0)
0x717fd  stloc.s  4
0x717ff  ldsfld   class [mscorlib]System.Predicate`1<class Microsoft.Crm.ObjectModel.SingleValueExtendedProperty> <>c::<>9__38_1
0x71804  dup
0x71805  brtrue.s loc_7181E
0x71807  pop
0x71808  ldsfld   class <>c <>c::<>9
0x7180d  ldftn    instance bool <>c::<GetCrmRegardingIdFromJsonResponse>b__38_1(class Microsoft.Crm.ObjectModel.SingleValueExtendedProperty x)
0x71813  newobj   instance void class [mscorlib]System.Predicate`1<class Microsoft.Crm.ObjectModel.SingleValueExtendedProperty>::.ctor(object, native int)
0x71818  dup
0x71819  stsfld   class [mscorlib]System.Predicate`1<class Microsoft.Crm.ObjectModel.SingleValueExtendedProperty> <>c::<>9__38_1
0x7181e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ObjectModel.SingleValueExtendedProperty>::Find(!!T0)
0x71823  stloc.s  5
0x71825  ldloc.s  4
0x71827  brfalse.s loc_71854
0x71829  ldloc.s  4
0x7182b  callvirt instance string Microsoft.Crm.ObjectModel.SingleValueExtendedProperty::get_Value()
0x71830  ldstr    a3// "3"
0x71835  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7183a  brfalse.s loc_71854
0x7183c  ldloc.s  5
0x7183e  brfalse.s loc_71854
0x71840  ldloc.0
0x71841  ldstr    aCrmregardingid// "crmRegardingId"
0x71846  ldloc.s  5
0x71848  callvirt instance string Microsoft.Crm.ObjectModel.SingleValueExtendedProperty::get_Value()
0x7184d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x71852  br.s     loc_71894
0x71854  call     class Microsoft.Crm.ObjectModel.DelveActionHubEventSource Microsoft.Crm.ObjectModel.DelveActionHubEventSource::get_Instance()
0x71859  ldstr    aGetcrmregardin// "GetCrmRegardingIdFromJsonResponse"
0x7185e  ldarg.1
0x7185f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x71864  ldstr    aGetcrmregardin// "GetCrmRegardingIdFromJsonResponse"
0x71869  ldstr    aEitherCrmregar// "Either crmRegardingObjectType or crmReg"...
0x7186e  callvirt instance void Microsoft.Crm.ObjectModel.DelveActionHubEventSource::LogInformation(string EventName, valuetype [mscorlib]System.Guid OrganizationId, string CallingMethod, string EventDetails)
0x71873  br.s     loc_71894
0x71875  call     class Microsoft.Crm.ObjectModel.DelveActionHubEventSource Microsoft.Crm.ObjectModel.DelveActionHubEventSource::get_Instance()
0x7187a  ldstr    aGetcrmregardin// "GetCrmRegardingIdFromJsonResponse"
0x7187f  ldarg.1
0x71880  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x71885  ldstr    aGetcrmregardin// "GetCrmRegardingIdFromJsonResponse"
0x7188a  ldstr    aInvalidExchang// "Invalid Exchange Response: actionItem.S"...
0x7188f  callvirt instance void Microsoft.Crm.ObjectModel.DelveActionHubEventSource::LogInformation(string EventName, valuetype [mscorlib]System.Guid OrganizationId, string CallingMethod, string EventDetails)
0x71894  leave.s  loc_718BC
0x71896  stloc.s  6
0x71898  call     class Microsoft.Crm.ObjectModel.DelveActionHubEventSource Microsoft.Crm.ObjectModel.DelveActionHubEventSource::get_Instance()
0x7189d  ldarg.1
0x7189e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x718a3  ldstr    aGetcrmregardin// "GetCrmRegardingIdFromJsonResponse"
0x718a8  ldc.i4.0
0x718a9  ldsfld   string [mscorlib]System.String::Empty
0x718ae  ldloc.s  6
0x718b0  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x718b5  callvirt instance void Microsoft.Crm.ObjectModel.DelveActionHubEventSource::LogError(valuetype [mscorlib]System.Guid OrganizationId, string CallingMethod, int32 CrmErrorCode, string MessageId, string ErrorDetails)
0x718ba  leave.s  loc_718BC
0x718bc  ldloc.0
0x718bd  ret
```
