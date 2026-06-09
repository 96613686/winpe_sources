# Microsoft.Crm.Caching.RibbonCacheUtility::RetrieveContextualTabs

- ea: `0x13d00`
- end: `0x13de5`
- name: `Microsoft.Crm.Caching.RibbonCacheUtility::RetrieveContextualTabs`
- size: `229`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x138a0`

## callees

- `0x13d00`

## string_xrefs

- `0x13d36`: `contextgroupxml`
- `0x13d91`: `CommandUIDefinition`

## pseudocode

```c

```

## disassembly

```asm
0x13d00  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x13d05  stloc.0
0x13d06  newobj   instance void [System.Xml]System.Xml.XmlWriterSettings::.ctor()
0x13d0b  stloc.1
0x13d0c  ldloc.1
0x13d0d  ldc.i4.1
0x13d0e  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_ConformanceLevel(valuetype [System.Xml]System.Xml.ConformanceLevel)
0x13d13  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonContextGroupCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonContextGroupCache::get_Instance()
0x13d18  ldarg.1
0x13d19  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonContextGroupCacheValue> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonContextGroupCache::GetAllRibbonContextGroups(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x13d1e  stloc.2
0x13d1f  ldloc.0
0x13d20  ldloc.1
0x13d21  call     class [System.Xml]System.Xml.XmlWriter [System.Xml]System.Xml.XmlWriter::Create(class [mscorlib]System.Text.StringBuilder, class [System.Xml]System.Xml.XmlWriterSettings)
0x13d26  stloc.3
0x13d27  ldstr    aRibboncontextg// "ribboncontextgroup"
0x13d2c  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor(string)
0x13d31  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x13d36  ldstr    aContextgroupxm// "contextgroupxml"
0x13d3b  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x13d40  ldarg.0
0x13d41  brtrue.s loc_13D69
0x13d43  ldloc.2
0x13d44  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonContextGroupCacheValue, bool> <>c::<>9__11_0
0x13d49  dup
0x13d4a  brtrue.s loc_13D63
0x13d4c  pop
0x13d4d  ldsfld   class <>c <>c::<>9
0x13d52  ldftn    instance bool <>c::<RetrieveContextualTabs>b__11_0(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonContextGroupCacheValue rcg)
0x13d58  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonContextGroupCacheValue, bool>::.ctor(object, native int)
0x13d5d  dup
0x13d5e  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonContextGroupCacheValue, bool> <>c::<>9__11_0
0x13d63  call     T0x2B00002E
0x13d68  stloc.2
0x13d69  ldloc.2
0x13d6a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonContextGroupCacheValue>::GetEnumerator()
0x13d6f  stloc.s  4
0x13d71  br.s     loc_13DBD
0x13d73  ldloc.s  4
0x13d75  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonContextGroupCacheValue>::get_Current()
0x13d7a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.RibbonContextGroupCacheValue::get_ContextGroupXml()
0x13d7f  stloc.s  5
0x13d81  ldloc.s  5
0x13d83  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x13d88  brtrue.s loc_13DBD
0x13d8a  ldloc.s  5
0x13d8c  call     class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XElement::Parse(string)
0x13d91  ldstr    aCommanduidefin// "CommandUIDefinition"
0x13d96  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x13d9b  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x13da0  ldstr    aContextualgrou// "ContextualGroup"
0x13da5  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x13daa  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x13daf  stloc.s  6
0x13db1  ldloc.s  6
0x13db3  brfalse.s loc_13DBD
0x13db5  ldloc.s  6
0x13db7  ldloc.3
0x13db8  callvirt instance void [System.Xml.Linq]System.Xml.Linq.XNode::WriteTo(class [System.Xml]System.Xml.XmlWriter)
0x13dbd  ldloc.s  4
0x13dbf  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x13dc4  brtrue.s loc_13D73
0x13dc6  leave.s  loc_13DDE
0x13dc8  ldloc.s  4
0x13dca  brfalse.s loc_13DD3
0x13dcc  ldloc.s  4
0x13dce  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x13dd3  endfinally
0x13dd4  ldloc.3
0x13dd5  brfalse.s loc_13DDD
0x13dd7  ldloc.3
0x13dd8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x13ddd  endfinally
0x13dde  ldloc.0
0x13ddf  callvirt instance string [mscorlib]System.Object::ToString()
0x13de4  ret
```
