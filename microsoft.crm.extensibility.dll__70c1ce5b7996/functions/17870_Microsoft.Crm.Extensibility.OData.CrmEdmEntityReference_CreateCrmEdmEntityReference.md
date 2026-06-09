# Microsoft.Crm.Extensibility.OData.CrmEdmEntityReference::CreateCrmEdmEntityReference

- ea: `0x17870`
- end: `0x179b1`
- name: `Microsoft.Crm.Extensibility.OData.CrmEdmEntityReference::CreateCrmEdmEntityReference`
- size: `321`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x12c70`
- `0x26890`
- `0x271e0`

## callees

- `0x17820`
- `0x17870`
- `0x24e20`

## string_xrefs

- `0x17877`: `link cannot be null`
- `0x17890`: `AbsoluteUri parsing cannot be done without context.`
- `0x178e5`: `linkPath should have 2 segments`

## pseudocode

```c

```

## disassembly

```asm
0x17870  ldarg.0
0x17871  ldnull
0x17872  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x17877  ldstr    aLinkCannotBeNu// "link cannot be null"
0x1787c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x17881  ldarg.0
0x17882  callvirt instance bool [System]System.Uri::get_IsAbsoluteUri()
0x17887  brfalse.s loc_1788F
0x17889  ldarg.2
0x1788a  ldnull
0x1788b  cgt.un
0x1788d  br.s     loc_17890
0x1788f  ldc.i4.1
0x17890  ldstr    aAbsoluteuriPar// "AbsoluteUri parsing cannot be done with"...
0x17895  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x1789a  ldarg.0
0x1789b  callvirt instance bool [System]System.Uri::get_IsAbsoluteUri()
0x178a0  brfalse.s loc_178C3
0x178a2  ldarg.1
0x178a3  ldarg.2
0x178a4  callvirt instance class [System]System.Uri Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_ServiceRootUri()
0x178a9  ldarg.0
0x178aa  newobj   instance void [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataUriParser::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel, class [System]System.Uri, class [System]System.Uri)
0x178af  dup
0x178b0  ldarg.1
0x178b1  newobj   instance void [Microsoft.OData.Core]Microsoft.OData.UriParser.AlternateKeysODataUriResolver::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel)
0x178b6  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataUriParser::set_Resolver(class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataUriResolver)
0x178bb  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPath [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataUriParser::ParsePath()
0x178c0  stloc.0
0x178c1  br.s     loc_178DC
0x178c3  ldarg.1
0x178c4  ldarg.0
0x178c5  newobj   instance void [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataUriParser::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel, class [System]System.Uri)
0x178ca  dup
0x178cb  ldarg.1
0x178cc  newobj   instance void [Microsoft.OData.Core]Microsoft.OData.UriParser.AlternateKeysODataUriResolver::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel)
0x178d1  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataUriParser::set_Resolver(class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataUriResolver)
0x178d6  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPath [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataUriParser::ParsePath()
0x178db  stloc.0
0x178dc  ldloc.0
0x178dd  callvirt instance int32 [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPath::get_Count()
0x178e2  ldc.i4.2
0x178e3  ceq
0x178e5  ldstr    aLinkpathShould// "linkPath should have 2 segments"
0x178ea  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x178ef  ldloc.0
0x178f0  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPath::get_FirstSegment()
0x178f5  isinst   [Microsoft.OData.Core]Microsoft.OData.UriParser.EntitySetSegment
0x178fa  ldnull
0x178fb  cgt.un
0x178fd  ldstr    aFirstsegmentSh// "FirstSegment should have be EntitySetSe"...
0x17902  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x17907  ldloc.0
0x17908  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPath::get_LastSegment()
0x1790d  isinst   [Microsoft.OData.Core]Microsoft.OData.UriParser.KeySegment
0x17912  ldnull
0x17913  cgt.un
0x17915  ldstr    aLastsegmentSho// "LastSegment should have be KeySegment"
0x1791a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x1791f  ldloc.0
0x17920  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPath::get_FirstSegment()
0x17925  castclass [Microsoft.OData.Core]Microsoft.OData.UriParser.EntitySetSegment
0x1792a  stloc.1
0x1792b  ldloc.0
0x1792c  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPath::get_LastSegment()
0x17931  castclass [Microsoft.OData.Core]Microsoft.OData.UriParser.KeySegment
0x17936  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>> [Microsoft.OData.Core]Microsoft.OData.UriParser.KeySegment::get_Keys()
0x1793b  call     T0x2B00008F
0x17940  stloc.s  4
0x17942  ldloca.s 4
0x17944  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Value()
0x17949  callvirt instance string [mscorlib]System.Object::ToString()
0x1794e  stloc.2
0x1794f  ldloc.2
0x17950  ldloca.s 3
0x17952  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x17957  brtrue.s loc_17994
0x17959  ldarg.0
0x1795a  callvirt instance string [System]System.Uri::get_OriginalString()
0x1795f  ldstr    asc_3B90E// "("
0x17964  ldc.i4.4
0x17965  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x1796a  ldc.i4.1
0x1796b  add
0x1796c  stloc.s  5
0x1796e  ldarg.0
0x1796f  callvirt instance string [System]System.Uri::get_OriginalString()
0x17974  ldstr    asc_36900// ")"
0x17979  ldc.i4.4
0x1797a  callvirt instance int32 [mscorlib]System.String::LastIndexOf(string, valuetype [mscorlib]System.StringComparison)
0x1797f  ldloc.s  5
0x17981  sub
0x17982  stloc.s  6
0x17984  ldarg.0
0x17985  callvirt instance string [System]System.Uri::get_OriginalString()
0x1798a  ldloc.s  5
0x1798c  ldloc.s  6
0x1798e  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x17993  stloc.2
0x17994  ldloc.1
0x17995  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEntitySet [Microsoft.OData.Core]Microsoft.OData.UriParser.EntitySetSegment::get_EntitySet()
0x1799a  castclass [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEntitySet
0x1799f  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEntityType [Microsoft.OData.Edm]Microsoft.OData.Edm.ExtensionMethods::EntityType(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationSource)
0x179a4  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNamedElement::get_Name()
0x179a9  ldloc.2
0x179aa  ldarg.0
0x179ab  newobj   instance void Microsoft.Crm.Extensibility.OData.CrmEdmEntityReference::.ctor(string edmEntityCollectionName, string edmEntityKey, class [System]System.Uri link)
0x179b0  ret
```
