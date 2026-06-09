# Microsoft.Crm.LanguageUtility::get_PreferredLanguageMapping

- ea: `0x20c50`
- end: `0x20d02`
- name: `Microsoft.Crm.LanguageUtility::get_PreferredLanguageMapping`
- size: `178`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x20a10`

## callees

- `0x20c50`

## string_xrefs

- `0x20c60`: `MSOnlinePreferredLanguageMappingXml`

## pseudocode

```c

```

## disassembly

```asm
0x20c50  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x20c55  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x20c5a  stloc.0
0x20c5b  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x20c60  ldstr    aMsonlineprefer// "MSOnlinePreferredLanguageMappingXml"
0x20c65  ldc.i4.0
0x20c66  callvirt T0x2B000001
0x20c6b  stloc.1
0x20c6c  ldloc.1
0x20c6d  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x20c72  brtrue   loc_20D00
0x20c77  ldloc.1
0x20c78  call     class [System.Xml.Linq]System.Xml.Linq.XDocument [System.Xml.Linq]System.Xml.Linq.XDocument::Parse(string)
0x20c7d  ldstr    aPreferredlangu_0// "PreferredLanguage"
0x20c82  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x20c87  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement> [System.Xml.Linq]System.Xml.Linq.XContainer::Descendants(class [System.Xml.Linq]System.Xml.Linq.XName)
0x20c8c  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement>::GetEnumerator()
0x20c91  stloc.2
0x20c92  br.s     loc_20CEC
0x20c94  ldloc.2
0x20c95  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Xml.Linq]System.Xml.Linq.XElement>::get_Current()
0x20c9a  dup
0x20c9b  ldstr    aMsonlinevalue// "MsOnlineValue"
0x20ca0  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x20ca5  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement> [System.Xml.Linq]System.Xml.Linq.XContainer::Descendants(class [System.Xml.Linq]System.Xml.Linq.XName)
0x20caa  call     T0x2B00000D
0x20caf  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XElement::get_Value()
0x20cb4  stloc.3
0x20cb5  ldstr    aCrmbaselanguag// "CrmBaseLanguageCode"
0x20cba  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x20cbf  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement> [System.Xml.Linq]System.Xml.Linq.XContainer::Descendants(class [System.Xml.Linq]System.Xml.Linq.XName)
0x20cc4  call     T0x2B00000D
0x20cc9  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XElement::get_Value()
0x20cce  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x20cd3  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x20cd8  stloc.s  4
0x20cda  ldloc.0
0x20cdb  ldloc.3
0x20cdc  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::ContainsKey(var<u1>)
0x20ce1  brtrue.s loc_20CEC
0x20ce3  ldloc.0
0x20ce4  ldloc.3
0x20ce5  ldloc.s  4
0x20ce7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x20cec  ldloc.2
0x20ced  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x20cf2  brtrue.s loc_20C94
0x20cf4  leave.s  loc_20D00
0x20cf6  ldloc.2
0x20cf7  brfalse.s loc_20CFF
0x20cf9  ldloc.2
0x20cfa  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20cff  endfinally
0x20d00  ldloc.0
0x20d01  ret
```
