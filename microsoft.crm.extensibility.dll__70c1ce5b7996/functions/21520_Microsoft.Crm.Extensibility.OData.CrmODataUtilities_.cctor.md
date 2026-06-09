# Microsoft.Crm.Extensibility.OData.CrmODataUtilities::.cctor

- ea: `0x21520`
- end: `0x215a6`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataUtilities::.cctor`
- size: `134`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x21550`: `$skiptoken`
- `0x21558`: `$deltatoken`

## pseudocode

```c

```

## disassembly

```asm
0x21520  ldc.i4.2
0x21521  newarr   [mscorlib]System.String
0x21526  dup
0x21527  ldc.i4.0
0x21528  ldstr    aSearch// "$search"
0x2152d  stelem.ref
0x2152e  dup
0x2152f  ldc.i4.1
0x21530  ldstr    aLevels// "$levels"
0x21535  stelem.ref
0x21536  newobj   instance void class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0x2153b  stsfld   class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<string> Microsoft.Crm.Extensibility.OData.CrmODataUtilities::_unsupportedQueryOptions
0x21540  ldc.i4.3
0x21541  newarr   [mscorlib]System.String
0x21546  dup
0x21547  ldc.i4.0
0x21548  ldstr    aSelect// "$select"
0x2154d  stelem.ref
0x2154e  dup
0x2154f  ldc.i4.1
0x21550  ldstr    aSkiptoken// "$skiptoken"
0x21555  stelem.ref
0x21556  dup
0x21557  ldc.i4.2
0x21558  ldstr    aDeltatoken// "$deltatoken"
0x2155d  stelem.ref
0x2155e  newobj   instance void class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0x21563  stsfld   class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<string> Microsoft.Crm.Extensibility.OData.CrmODataUtilities::_supportedQueryOptionsForChangeTracking
0x21568  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OneToManyEntityRelationship>>::.ctor()
0x2156d  newobj   instance void class [mscorlib]System.Collections.ObjectModel.ReadOnlyDictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OneToManyEntityRelationship>>::.ctor(class [mscorlib]System.Collections.Generic.IDictionary`2<var<u1>, !!T0>)
0x21572  stsfld   class [mscorlib]System.Collections.ObjectModel.ReadOnlyDictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OneToManyEntityRelationship>> Microsoft.Crm.Extensibility.OData.CrmODataUtilities::emptyReadOnlyDictionary
0x21577  ldc.i4.1
0x21578  newarr   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ModelVisibility
0x2157d  stsfld   valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ModelVisibility[] Microsoft.Crm.Extensibility.OData.CrmODataUtilities::RuntimeModelVisibilities
0x21582  ldc.i4.2
0x21583  newarr   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ModelVisibility
0x21588  dup
0x21589  ldc.i4.0
0x2158a  ldc.i4.2
0x2158b  stelem.i4
0x2158c  dup
0x2158d  ldc.i4.1
0x2158e  ldc.i4.1
0x2158f  stelem.i4
0x21590  stsfld   valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ModelVisibility[] Microsoft.Crm.Extensibility.OData.CrmODataUtilities::PublicModelVisibilities
0x21595  ldstr    aSWSSS// "(\\s*(\\w+)\\s*=\\s*(([^'][^,]*)|('([^'"...
0x2159a  ldc.i4.8
0x2159b  call     class [System]System.Text.RegularExpressions.Regex [Microsoft.Crm.Core]Microsoft.Crm.CrmRegexCache::GetRegex(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x215a0  stsfld   class [System]System.Text.RegularExpressions.Regex Microsoft.Crm.Extensibility.OData.CrmODataUtilities::AlternateKeysRegex
0x215a5  ret
```
