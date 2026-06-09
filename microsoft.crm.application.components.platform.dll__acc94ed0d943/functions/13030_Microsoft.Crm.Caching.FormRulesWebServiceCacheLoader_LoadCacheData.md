# Microsoft.Crm.Caching.FormRulesWebServiceCacheLoader::LoadCacheData

- ea: `0x13030`
- end: `0x132ee`
- name: `Microsoft.Crm.Caching.FormRulesWebServiceCacheLoader::LoadCacheData`
- size: `702`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x13030`
- `0x30e70`
- `0x59710`
- `0x59800`
- `0x5be20`
- `0x5be50`
- `0xa2b60`

## string_xrefs

- `0x1303e`: `formxml`
- `0x13064`: `formxml`
- `0x13046`: `componentstate`
- `0x1327f`: `componentstate`

## pseudocode

```c

```

## disassembly

```asm
0x13030  ldstr    aSystemform// "systemform"
0x13035  ldarg.1
0x13036  ldc.i4.4
0x13037  newarr   [mscorlib]System.String
0x1303c  dup
0x1303d  ldc.i4.0
0x1303e  ldstr    aFormxml// "formxml"
0x13043  stelem.ref
0x13044  dup
0x13045  ldc.i4.1
0x13046  ldstr    aComponentstate// "componentstate"
0x1304b  stelem.ref
0x1304c  dup
0x1304d  ldc.i4.2
0x1304e  ldstr    aSolutionid_0// "solutionid"
0x13053  stelem.ref
0x13054  dup
0x13055  ldc.i4.3
0x13056  ldstr    aPublishedon// "publishedon"
0x1305b  stelem.ref
0x1305c  ldarg.2
0x1305d  call     class Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Platform.DataSource::Retrieve(string entityName, valuetype [mscorlib]System.Guid entityId, string[] columns, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x13062  stloc.0
0x13063  ldloc.0
0x13064  ldstr    aFormxml// "formxml"
0x13069  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x1306e  castclass [mscorlib]System.String
0x13073  stloc.1
0x13074  ldnull
0x13075  stloc.2
0x13076  ldloc.1
0x13077  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1307c  brtrue   loc_1327E
0x13081  ldloc.1
0x13082  call     class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XElement::Parse(string)
0x13087  ldstr    aDisplayconditi// "DisplayConditions"
0x1308c  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x13091  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x13096  stloc.s  6
0x13098  ldloc.s  6
0x1309a  brfalse  loc_1327E
0x1309f  ldloc.s  6
0x130a1  ldc.i4.1
0x130a2  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XNode::ToString(valuetype [System.Xml.Linq]System.Xml.Linq.SaveOptions)
0x130a7  stloc.2
0x130a8  ldloc.s  6
0x130aa  ldstr    aRole// "Role"
0x130af  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x130b4  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement> [System.Xml.Linq]System.Xml.Linq.XContainer::Descendants(class [System.Xml.Linq]System.Xml.Linq.XName)
0x130b9  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x130be  stloc.s  7
0x130c0  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement>::GetEnumerator()
0x130c5  stloc.s  8
0x130c7  br.s     loc_13102
0x130c9  ldloc.s  8
0x130cb  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Xml.Linq]System.Xml.Linq.XElement>::get_Current()
0x130d0  stloc.s  9
0x130d2  ldloc.s  9
0x130d4  ldstr    aId_0// "Id"
0x130d9  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x130de  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0x130e3  brfalse.s loc_13102
0x130e5  ldloc.s  7
0x130e7  ldloc.s  9
0x130e9  ldstr    aId_0// "Id"
0x130ee  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x130f3  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0x130f8  call     valuetype [mscorlib]System.Guid [System.Xml.Linq]System.Xml.Linq.XAttribute::op_Explicit(class [System.Xml.Linq]System.Xml.Linq.XAttribute)
0x130fd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x13102  ldloc.s  8
0x13104  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x13109  brtrue.s loc_130C9
0x1310b  leave.s  loc_13119
0x1310d  ldloc.s  8
0x1310f  brfalse.s loc_13118
0x13111  ldloc.s  8
0x13113  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x13118  endfinally
0x13119  ldloc.s  7
0x1311b  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x13120  ldc.i4.0
0x13121  ble      loc_1327E
0x13126  ldstr    aRole_0// "role"
0x1312b  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor(string)
0x13130  dup
0x13131  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x13136  ldstr    aParentrootrole// "parentrootroleid"
0x1313b  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x13140  dup
0x13141  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x13146  ldstr    aRoleid// "roleid"
0x1314b  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x13150  dup
0x13151  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x13156  ldstr    aRoleid// "roleid"
0x1315b  ldc.i4.8
0x1315c  ldloc.s  7
0x1315e  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::ToArray()
0x13163  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x13168  ldarg.2
0x13169  call     class Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression query, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x1316e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.Entity>::GetEnumerator()
0x13173  stloc.s  0xA
0x13175  br       loc_1325B
0x1317a  ldloc.s  0xA
0x1317c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Application.Platform.Entity>::get_Current()
0x13181  stloc.s  0xB
0x13183  newobj   instance void <>c__DisplayClass0_0::.ctor()
0x13188  stloc.s  0xC
0x1318a  ldloc.s  0xC
0x1318c  ldloc.s  0xB
0x1318e  ldstr    aRoleid// "roleid"
0x13193  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x13198  isinst   Microsoft.Crm.Application.Types.LookupValue
0x1319d  stfld    class Microsoft.Crm.Application.Types.LookupValue <>c__DisplayClass0_0::roleIdAttribute
0x131a2  ldloc.s  0xC
0x131a4  ldfld    class Microsoft.Crm.Application.Types.LookupValue <>c__DisplayClass0_0::roleIdAttribute
0x131a9  brfalse  loc_1325B
0x131ae  ldloc.s  6
0x131b0  ldstr    aRole// "Role"
0x131b5  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x131ba  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement> [System.Xml.Linq]System.Xml.Linq.XContainer::Elements(class [System.Xml.Linq]System.Xml.Linq.XName)
0x131bf  ldsfld   class [mscorlib]System.Func`2<class [System.Xml.Linq]System.Xml.Linq.XElement, class <>f__AnonymousType0`2<class [System.Xml.Linq]System.Xml.Linq.XElement, valuetype [mscorlib]System.Guid>> <>c::<>9__0_0
0x131c4  dup
0x131c5  brtrue.s loc_131DE
0x131c7  pop
0x131c8  ldsfld   class <>c <>c::<>9
0x131cd  ldftn    instance class <>f__AnonymousType0`2<class [System.Xml.Linq]System.Xml.Linq.XElement, valuetype [mscorlib]System.Guid> <>c::<LoadCacheData>b__0_0(class [System.Xml.Linq]System.Xml.Linq.XElement el)
0x131d3  newobj   instance void class [mscorlib]System.Func`2<class [System.Xml.Linq]System.Xml.Linq.XElement, class <>f__AnonymousType0`2<class [System.Xml.Linq]System.Xml.Linq.XElement, valuetype [mscorlib]System.Guid>>::.ctor(object, native int)
0x131d8  dup
0x131d9  stsfld   class [mscorlib]System.Func`2<class [System.Xml.Linq]System.Xml.Linq.XElement, class <>f__AnonymousType0`2<class [System.Xml.Linq]System.Xml.Linq.XElement, valuetype [mscorlib]System.Guid>> <>c::<>9__0_0
0x131de  call     T0x2B000026
0x131e3  ldloc.s  0xC
0x131e5  ldftn    instance bool <>c__DisplayClass0_0::<LoadCacheData>b__1(class <>f__AnonymousType0`2<class [System.Xml.Linq]System.Xml.Linq.XElement, valuetype [mscorlib]System.Guid> <>h__TransparentIdentifier0)
0x131eb  newobj   instance void class [mscorlib]System.Func`2<class <>f__AnonymousType0`2<class [System.Xml.Linq]System.Xml.Linq.XElement, valuetype [mscorlib]System.Guid>, bool>::.ctor(object, native int)
0x131f0  call     T0x2B000027
0x131f5  ldsfld   class [mscorlib]System.Func`2<class <>f__AnonymousType0`2<class [System.Xml.Linq]System.Xml.Linq.XElement, valuetype [mscorlib]System.Guid>, class [System.Xml.Linq]System.Xml.Linq.XElement> <>c::<>9__0_2
0x131fa  dup
0x131fb  brtrue.s loc_13214
0x131fd  pop
0x131fe  ldsfld   class <>c <>c::<>9
0x13203  ldftn    instance class [System.Xml.Linq]System.Xml.Linq.XElement <>c::<LoadCacheData>b__0_2(class <>f__AnonymousType0`2<class [System.Xml.Linq]System.Xml.Linq.XElement, valuetype [mscorlib]System.Guid> <>h__TransparentIdentifier0)
0x13209  newobj   instance void class [mscorlib]System.Func`2<class <>f__AnonymousType0`2<class [System.Xml.Linq]System.Xml.Linq.XElement, valuetype [mscorlib]System.Guid>, class [System.Xml.Linq]System.Xml.Linq.XElement>::.ctor(object, native int)
0x1320e  dup
0x1320f  stsfld   class [mscorlib]System.Func`2<class <>f__AnonymousType0`2<class [System.Xml.Linq]System.Xml.Linq.XElement, valuetype [mscorlib]System.Guid>, class [System.Xml.Linq]System.Xml.Linq.XElement> <>c::<>9__0_2
0x13214  call     T0x2B000028
0x13219  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement>::GetEnumerator()
0x1321e  stloc.s  8
0x13220  br.s     loc_13244
0x13222  ldloc.s  8
0x13224  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Xml.Linq]System.Xml.Linq.XElement>::get_Current()
0x13229  ldstr    aParentrootrole_0// "ParentRootRoleId"
0x1322e  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x13233  ldloc.s  0xC
0x13235  ldfld    class Microsoft.Crm.Application.Types.LookupValue <>c__DisplayClass0_0::roleIdAttribute
0x1323a  callvirt instance string Microsoft.Crm.Application.Types.LookupValue::get_ID()
0x1323f  callvirt instance void [System.Xml.Linq]System.Xml.Linq.XElement::SetAttributeValue(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x13244  ldloc.s  8
0x13246  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1324b  brtrue.s loc_13222
0x1324d  leave.s  loc_1325B
0x1324f  ldloc.s  8
0x13251  brfalse.s loc_1325A
0x13253  ldloc.s  8
0x13255  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1325a  endfinally
0x1325b  ldloc.s  0xA
0x1325d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x13262  brtrue   loc_1317A
0x13267  leave.s  loc_13275
0x13269  ldloc.s  0xA
0x1326b  brfalse.s loc_13274
0x1326d  ldloc.s  0xA
0x1326f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x13274  endfinally
0x13275  ldloc.s  6
0x13277  ldc.i4.1
0x13278  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XNode::ToString(valuetype [System.Xml.Linq]System.Xml.Linq.SaveOptions)
0x1327d  stloc.2
0x1327e  ldloc.0
0x1327f  ldstr    aComponentstate// "componentstate"
0x13284  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x13289  unbox.any [mscorlib]System.Int32
0x1328e  stloc.3
0x1328f  ldloc.0
0x13290  ldstr    aSolutionid_0// "solutionid"
0x13295  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x1329a  unbox.any [mscorlib]System.Guid
0x1329f  stloc.s  4
0x132a1  ldloc.0
0x132a2  ldstr    aPublishedon// "publishedon"
0x132a7  callvirt instance bool Microsoft.Crm.Application.Platform.EntityBase::HasAttribute(string name)
0x132ac  brfalse.s loc_132BB
0x132ae  ldloc.0
0x132af  ldstr    aPublishedon// "publishedon"
0x132b4  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x132b9  brtrue.s loc_132C4
0x132bb  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x132c0  stloc.s  5
0x132c2  br.s     loc_132D6
0x132c4  ldloc.0
0x132c5  ldstr    aPublishedon// "publishedon"
0x132ca  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x132cf  unbox.any [mscorlib]System.DateTime
0x132d4  stloc.s  5
0x132d6  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FormRulesCacheValue::.ctor()
0x132db  dup
0x132dc  ldloc.2
0x132dd  ldloc.s  5
0x132df  ldloc.s  4
0x132e1  ldloc.3
0x132e2  ldarg.2
0x132e3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x132e8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FormRulesCacheValue::Initialize(string, valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState, valuetype [mscorlib]System.Guid)
0x132ed  ret
```
