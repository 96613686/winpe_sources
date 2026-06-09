# Microsoft.Crm.ViewDetails::AddProcessIdAndProcessTimestampToFetchXml

- ea: `0x5360`
- end: `0x551b`
- name: `Microsoft.Crm.ViewDetails::AddProcessIdAndProcessTimestampToFetchXml`
- size: `443`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x15cf0`

## callees

- `0x5360`
- `0x98730`

## string_xrefs

- `0x5368`: `fetch/entity/link-entity`
- `0x538e`: `processidworkflowworkflowid`
- `0x5461`: `processidworkflowworkflowid`
- `0x53dc`: `processid`
- `0x5426`: `processid`
- `0x54a6`: `processid`
- `0x5445`: `link-entity`
- `0x54b3`: `link-type`

## pseudocode

```c

```

## disassembly

```asm
0x5360  ldarg.1
0x5361  call     class [System.Xml.Linq]System.Xml.Linq.XDocument [System.Xml.Linq]System.Xml.Linq.XDocument::Parse(string)
0x5366  stloc.0
0x5367  ldloc.0
0x5368  ldstr    aFetchEntityLin// "fetch/entity/link-entity"
0x536d  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement> [System.Xml.Linq]System.Xml.XPath.Extensions::XPathSelectElements(class [System.Xml.Linq]System.Xml.Linq.XNode, string)
0x5372  ldc.i4.0
0x5373  stloc.1
0x5374  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement>::GetEnumerator()
0x5379  stloc.s  4
0x537b  br.s     loc_539E
0x537d  ldloc.s  4
0x537f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Xml.Linq]System.Xml.Linq.XElement>::get_Current()
0x5384  ldstr    aAlias// "alias"
0x5389  call     string Microsoft.Crm.Application.Components.Platform.ProcessDefinition.XElementExtensions::GetStringAttribute(class [System.Xml.Linq]System.Xml.Linq.XElement element, string attributeName)
0x538e  ldstr    aProcessidworkf// "processidworkflowworkflowid"
0x5393  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5398  brfalse.s loc_539E
0x539a  ldc.i4.1
0x539b  stloc.1
0x539c  leave.s  loc_53B5
0x539e  ldloc.s  4
0x53a0  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x53a5  brtrue.s loc_537D
0x53a7  leave.s  loc_53B5
0x53a9  ldloc.s  4
0x53ab  brfalse.s loc_53B4
0x53ad  ldloc.s  4
0x53af  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x53b4  endfinally
0x53b5  ldloc.0
0x53b6  ldstr    aFetchEntityAtt// "fetch/entity/attribute"
0x53bb  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement> [System.Xml.Linq]System.Xml.XPath.Extensions::XPathSelectElements(class [System.Xml.Linq]System.Xml.Linq.XNode, string)
0x53c0  ldc.i4.0
0x53c1  stloc.2
0x53c2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement>::GetEnumerator()
0x53c7  stloc.s  4
0x53c9  br.s     loc_53EC
0x53cb  ldloc.s  4
0x53cd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Xml.Linq]System.Xml.Linq.XElement>::get_Current()
0x53d2  ldstr    aName// "name"
0x53d7  call     string Microsoft.Crm.Application.Components.Platform.ProcessDefinition.XElementExtensions::GetStringAttribute(class [System.Xml.Linq]System.Xml.Linq.XElement element, string attributeName)
0x53dc  ldstr    aProcessid// "processid"
0x53e1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x53e6  brfalse.s loc_53EC
0x53e8  ldc.i4.1
0x53e9  stloc.2
0x53ea  leave.s  loc_5403
0x53ec  ldloc.s  4
0x53ee  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x53f3  brtrue.s loc_53CB
0x53f5  leave.s  loc_5403
0x53f7  ldloc.s  4
0x53f9  brfalse.s loc_5402
0x53fb  ldloc.s  4
0x53fd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5402  endfinally
0x5403  ldloc.0
0x5404  ldstr    aFetchEntity// "fetch/entity"
0x5409  call     class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.XPath.Extensions::XPathSelectElement(class [System.Xml.Linq]System.Xml.Linq.XNode, string)
0x540e  stloc.3
0x540f  ldloc.2
0x5410  brtrue.s loc_543F
0x5412  ldstr    aAttribute// "attribute"
0x5417  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x541c  ldstr    aName// "name"
0x5421  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x5426  ldstr    aProcessid// "processid"
0x542b  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XAttribute::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x5430  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XElement::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x5435  stloc.s  5
0x5437  ldloc.3
0x5438  ldloc.s  5
0x543a  callvirt instance void [System.Xml.Linq]System.Xml.Linq.XContainer::Add(object)
0x543f  ldloc.1
0x5440  brtrue   loc_5514
0x5445  ldstr    aLinkEntity// "link-entity"
0x544a  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x544f  ldc.i4.7
0x5450  newarr   [mscorlib]System.Object
0x5455  dup
0x5456  ldc.i4.0
0x5457  ldstr    aAlias// "alias"
0x545c  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x5461  ldstr    aProcessidworkf// "processidworkflowworkflowid"
0x5466  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XAttribute::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x546b  stelem.ref
0x546c  dup
0x546d  ldc.i4.1
0x546e  ldstr    aName// "name"
0x5473  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x5478  ldstr    aWorkflow// "workflow"
0x547d  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XAttribute::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x5482  stelem.ref
0x5483  dup
0x5484  ldc.i4.2
0x5485  ldstr    aFrom// "from"
0x548a  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x548f  ldstr    aWorkflowid// "workflowid"
0x5494  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XAttribute::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x5499  stelem.ref
0x549a  dup
0x549b  ldc.i4.3
0x549c  ldstr    aTo// "to"
0x54a1  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x54a6  ldstr    aProcessid// "processid"
0x54ab  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XAttribute::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x54b0  stelem.ref
0x54b1  dup
0x54b2  ldc.i4.4
0x54b3  ldstr    aLinkType// "link-type"
0x54b8  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x54bd  ldstr    aOuter// "outer"
0x54c2  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XAttribute::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x54c7  stelem.ref
0x54c8  dup
0x54c9  ldc.i4.5
0x54ca  ldstr    aVisible// "visible"
0x54cf  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x54d4  ldstr    aFalse// "false"
0x54d9  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XAttribute::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x54de  stelem.ref
0x54df  dup
0x54e0  ldc.i4.6
0x54e1  ldstr    aAttribute// "attribute"
0x54e6  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x54eb  ldstr    aName// "name"
0x54f0  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x54f5  ldstr    aVersionnumber// "versionnumber"
0x54fa  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XAttribute::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x54ff  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XElement::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x5504  stelem.ref
0x5505  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XElement::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object[])
0x550a  stloc.s  6
0x550c  ldloc.3
0x550d  ldloc.s  6
0x550f  callvirt instance void [System.Xml.Linq]System.Xml.Linq.XContainer::Add(object)
0x5514  ldloc.0
0x5515  callvirt instance string [mscorlib]System.Object::ToString()
0x551a  ret
```
