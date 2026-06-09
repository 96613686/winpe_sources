# Microsoft.Crm.Extensibility.OData.CrmODataHeaders::.cctor

- ea: `0x1a160`
- end: `0x1a2d2`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataHeaders::.cctor`
- size: `370`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x1a24f`: `OData.Community.Display.V1.FormattedValue`
- `0x1a168`: `application/json`
- `0x1a25a`: `OData.Community.Display.V1.*`
- `0x1a265`: `OData.Community.Display.*`
- `0x1a270`: `OData.Community.*`
- `0x1a286`: `-OData.Community.Display.V1.FormattedValue`
- `0x1a291`: `-OData.Community.Display.V1.*`
- `0x1a29c`: `-OData.Community.Display.*`
- `0x1a2a7`: `-OData.Community.*`

## pseudocode

```c

```

## disassembly

```asm
0x1a160  ldc.i4.2
0x1a161  newarr   [mscorlib]System.String
0x1a166  dup
0x1a167  ldc.i4.0
0x1a168  ldstr    aApplicationJso// "application/json"
0x1a16d  stelem.ref
0x1a16e  dup
0x1a16f  ldc.i4.1
0x1a170  ldstr    aMultipartMixed// "multipart/mixed"
0x1a175  stelem.ref
0x1a176  stsfld   string[] Microsoft.Crm.Extensibility.OData.CrmODataHeaders::WhitelistContentTypes
0x1a17b  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x1a180  dup
0x1a181  ldstr    aReturnnotifica// "ReturnNotifications"
0x1a186  ldstr    aMscrmReturnnot// "MSCRM.ReturnNotifications"
0x1a18b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1a190  dup
0x1a191  ldstr    aSuppressduplic// "SuppressDuplicateDetection"
0x1a196  ldstr    aMscrmSuppressd// "MSCRM.SuppressDuplicateDetection"
0x1a19b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1a1a0  dup
0x1a1a1  ldstr    aMergelabels// "MergeLabels"
0x1a1a6  ldstr    aMscrmMergelabe// "MSCRM.MergeLabels"
0x1a1ab  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1a1b0  dup
0x1a1b1  ldstr    aSolutionunique// "SolutionUniqueName"
0x1a1b6  ldstr    aMscrmSolutionu// "MSCRM.SolutionUniqueName"
0x1a1bb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1a1c0  stsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Extensibility.OData.CrmODataHeaders::_crmOptionalParametersMapping
0x1a1c5  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x1a1ca  dup
0x1a1cb  ldstr    aMicrosoftDynam_6// "Microsoft.Dynamics.CRM.lookuplogicalnam"...
0x1a1d0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1a1d5  dup
0x1a1d6  ldstr    aMicrosoftDynam_7// "Microsoft.Dynamics.CRM.associatednaviga"...
0x1a1db  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1a1e0  dup
0x1a1e1  ldstr    aMicrosoftDynam_8// "Microsoft.Dynamics.CRM.*"
0x1a1e6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1a1eb  dup
0x1a1ec  ldstr    aMicrosoftDynam_9// "Microsoft.Dynamics.*"
0x1a1f1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1a1f6  dup
0x1a1f7  ldstr    aMicrosoft// "Microsoft.*"
0x1a1fc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1a201  dup
0x1a202  ldstr    asc_383DE// "*"
0x1a207  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1a20c  dup
0x1a20d  ldstr    asc_3F9C4// "-*"
0x1a212  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1a217  dup
0x1a218  ldstr    aMicrosoftDynam_10// "-Microsoft.Dynamics.CRM.*"
0x1a21d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1a222  dup
0x1a223  ldstr    aMicrosoftDynam_11// "-Microsoft.Dynamics.*"
0x1a228  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1a22d  dup
0x1a22e  ldstr    aMicrosoft_0// "-Microsoft.*"
0x1a233  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1a238  dup
0x1a239  ldstr    aMicrosoftDynam_12// "-Microsoft.Dynamics.CRM.lookuplogicalna"...
0x1a23e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1a243  dup
0x1a244  ldstr    aMicrosoftDynam_13// "-Microsoft.Dynamics.CRM.associatednavig"...
0x1a249  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1a24e  dup
0x1a24f  ldstr    aOdataCommunity// "OData.Community.Display.V1.FormattedVal"...
0x1a254  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1a259  dup
0x1a25a  ldstr    aOdataCommunity_2// "OData.Community.Display.V1.*"
0x1a25f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1a264  dup
0x1a265  ldstr    aOdataCommunity_3// "OData.Community.Display.*"
0x1a26a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1a26f  dup
0x1a270  ldstr    aOdataCommunity_4// "OData.Community.*"
0x1a275  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1a27a  dup
0x1a27b  ldstr    aOdata// "OData.*"
0x1a280  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1a285  dup
0x1a286  ldstr    aOdataCommunity_5// "-OData.Community.Display.V1.FormattedVa"...
0x1a28b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1a290  dup
0x1a291  ldstr    aOdataCommunity_6// "-OData.Community.Display.V1.*"
0x1a296  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1a29b  dup
0x1a29c  ldstr    aOdataCommunity_7// "-OData.Community.Display.*"
0x1a2a1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1a2a6  dup
0x1a2a7  ldstr    aOdataCommunity_8// "-OData.Community.*"
0x1a2ac  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1a2b1  dup
0x1a2b2  ldstr    aOdata_0// "-OData.*"
0x1a2b7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1a2bc  stsfld   class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.Crm.Extensibility.OData.CrmODataHeaders::_supportedAnnotationValuesForPreferIncludeHeader
0x1a2c1  ldstr    aS_0// ",\\s*(?=([^\"]*\"[^\"]*\")*[^\"]*$)"
0x1a2c6  ldc.i4.8
0x1a2c7  call     class [System]System.Text.RegularExpressions.Regex [Microsoft.Crm.Core]Microsoft.Crm.CrmRegexCache::GetRegex(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x1a2cc  stsfld   class [System]System.Text.RegularExpressions.Regex Microsoft.Crm.Extensibility.OData.CrmODataHeaders::PreferHeadersRegex
0x1a2d1  ret
```
