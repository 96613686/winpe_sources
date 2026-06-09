# Microsoft.Crm.SearchParser::.ctor

- ea: `0x230d0`
- end: `0x2318f`
- name: `Microsoft.Crm.SearchParser::.ctor`
- size: `191`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x215c0`
- `0x215d0`
- `0x230d0`

## string_xrefs

- `0x23100`: `Search_Logical_OR_Command`
- `0x2311b`: `Search_Logical_AND_Command`

## pseudocode

```c

```

## disassembly

```asm
0x230d0  ldarg.0
0x230d1  call     instance void [mscorlib]System.Object::.ctor()
0x230d6  ldarg.1
0x230d7  ldstr    aCulture_0// "culture"
0x230dc  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x230e1  ldarg.2
0x230e2  ldstr    aNoisewordsload// "noiseWordsLoader"
0x230e7  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x230ec  ldarg.0
0x230ed  ldarg.1
0x230ee  stfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.SearchParser::_culture
0x230f3  ldarg.0
0x230f4  ldarg.2
0x230f5  stfld    class Microsoft.Crm.INoiseWordsLoader Microsoft.Crm.SearchParser::_noiseWordsLoader
0x230fa  ldarg.0
0x230fb  ldsfld   class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager Microsoft.Crm.SearchParser::_resourceManager
0x23100  ldstr    aSearchLogicalO// "Search_Logical_OR_Command"
0x23105  ldarg.0
0x23106  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.SearchParser::_culture
0x2310b  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x23110  stfld    string Microsoft.Crm.SearchParser::_logicalOrResourceString
0x23115  ldarg.0
0x23116  ldsfld   class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager Microsoft.Crm.SearchParser::_resourceManager
0x2311b  ldstr    aSearchLogicalA// "Search_Logical_AND_Command"
0x23120  ldarg.0
0x23121  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.SearchParser::_culture
0x23126  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x2312b  stfld    string Microsoft.Crm.SearchParser::_logicalAndResourceString
0x23130  ldarg.0
0x23131  ldfld    class Microsoft.Crm.INoiseWordsLoader Microsoft.Crm.SearchParser::_noiseWordsLoader
0x23136  ldarg.0
0x23137  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.SearchParser::_culture
0x2313c  callvirt instance string Microsoft.Crm.INoiseWordsLoader::GetLogicalOrResourceString(class [mscorlib]System.Globalization.CultureInfo culture)
0x23141  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x23146  brtrue.s loc_2315F
0x23148  ldarg.0
0x23149  ldarg.0
0x2314a  ldfld    class Microsoft.Crm.INoiseWordsLoader Microsoft.Crm.SearchParser::_noiseWordsLoader
0x2314f  ldarg.0
0x23150  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.SearchParser::_culture
0x23155  callvirt instance string Microsoft.Crm.INoiseWordsLoader::GetLogicalOrResourceString(class [mscorlib]System.Globalization.CultureInfo culture)
0x2315a  stfld    string Microsoft.Crm.SearchParser::_logicalOrResourceString
0x2315f  ldarg.0
0x23160  ldfld    class Microsoft.Crm.INoiseWordsLoader Microsoft.Crm.SearchParser::_noiseWordsLoader
0x23165  ldarg.0
0x23166  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.SearchParser::_culture
0x2316b  callvirt instance string Microsoft.Crm.INoiseWordsLoader::GetLogicalAndResourceString(class [mscorlib]System.Globalization.CultureInfo culture)
0x23170  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x23175  brtrue.s loc_2318E
0x23177  ldarg.0
0x23178  ldarg.0
0x23179  ldfld    class Microsoft.Crm.INoiseWordsLoader Microsoft.Crm.SearchParser::_noiseWordsLoader
0x2317e  ldarg.0
0x2317f  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.SearchParser::_culture
0x23184  callvirt instance string Microsoft.Crm.INoiseWordsLoader::GetLogicalAndResourceString(class [mscorlib]System.Globalization.CultureInfo culture)
0x23189  stfld    string Microsoft.Crm.SearchParser::_logicalAndResourceString
0x2318e  ret
```
