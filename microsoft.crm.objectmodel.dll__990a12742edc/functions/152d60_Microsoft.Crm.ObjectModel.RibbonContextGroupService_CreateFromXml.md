# Microsoft.Crm.ObjectModel.RibbonContextGroupService::CreateFromXml

- ea: `0x152d60`
- end: `0x1530c2`
- name: `Microsoft.Crm.ObjectModel.RibbonContextGroupService::CreateFromXml`
- size: `866`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x154f20`

## callees

- `0x152d60`
- `0x154d10`
- `0x154f20`
- `0x155dc0`
- `0x155de0`
- `0x155e60`

## string_xrefs

- `0x152e7b`: `contextgroupxml`
- `0x152eed`: `contextgroupxml`
- `0x152f52`: `contextgroupxml`
- `0x152f72`: `contextgroupxml`
- `0x152f91`: `contextgroupxml`
- `0x152d8b`: `CommandUIDefinition`
- `0x152dbd`: `CommandUIDefinition`
- `0x153069`: `CommandUIDefinition`
- `0x152d80`: `Expecting xml element to be node of type 'CustomAction'.`

## pseudocode

```c

```

## disassembly

```asm
0x152d60  ldarg.1
0x152d61  ldstr    aCustomactionno// "customActionNode"
0x152d66  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x152d6b  ldarg.1
0x152d6c  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XElement::get_Name()
0x152d71  ldstr    aCustomaction// "CustomAction"
0x152d76  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x152d7b  call     bool [System.Xml.Linq]System.Xml.Linq.XName::op_Equality(class [System.Xml.Linq]System.Xml.Linq.XName, class [System.Xml.Linq]System.Xml.Linq.XName)
0x152d80  ldstr    aExpectingXmlEl_0// "Expecting xml element to be node of typ"...
0x152d85  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x152d8a  ldarg.1
0x152d8b  ldstr    aCommanduidefin// "CommandUIDefinition"
0x152d90  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x152d95  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x152d9a  ldstr    aContextualgrou// "ContextualGroup"
0x152d9f  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x152da4  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x152da9  stloc.0
0x152daa  ldloc.0
0x152dab  ldstr    aContextualgrou_0// "contextualGroupNode"
0x152db0  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x152db5  ldarg.1
0x152db6  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XElement::.ctor(class [System.Xml.Linq]System.Xml.Linq.XElement)
0x152dbb  stloc.1
0x152dbc  ldloc.1
0x152dbd  ldstr    aCommanduidefin// "CommandUIDefinition"
0x152dc2  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x152dc7  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x152dcc  ldstr    aContextualgrou// "ContextualGroup"
0x152dd1  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x152dd6  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x152ddb  callvirt instance void [System.Xml.Linq]System.Xml.Linq.XContainer::RemoveNodes()
0x152de0  ldloc.0
0x152de1  ldstr    aId_0// "Id"
0x152de6  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x152deb  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0x152df0  call     string [System.Xml.Linq]System.Xml.Linq.XAttribute::op_Explicit(class [System.Xml.Linq]System.Xml.Linq.XAttribute)
0x152df5  stloc.2
0x152df6  ldstr    aRibboncontextg// "RibbonContextGroup"
0x152dfb  ldarg.s  6
0x152dfd  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x152e02  stloc.3
0x152e03  ldloc.3
0x152e04  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x152e09  ldstr    aRibboncustomiz_0// "ribboncustomizationid"
0x152e0e  ldc.i4.0
0x152e0f  ldarg.2
0x152e10  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x152e15  box      [mscorlib]System.Guid
0x152e1a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x152e1f  pop
0x152e20  ldloc.3
0x152e21  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x152e26  ldstr    aContextgroupid// "contextgroupid"
0x152e2b  ldc.i4.0
0x152e2c  ldloc.2
0x152e2d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x152e32  pop
0x152e33  ldarg.s  4
0x152e35  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x152e3a  brfalse.s loc_152E51
0x152e3c  ldloc.3
0x152e3d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x152e42  ldstr    aEntity_0// "entity"
0x152e47  ldc.i4.s 0xC
0x152e49  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0x152e4e  pop
0x152e4f  br.s     loc_152E65
0x152e51  ldloc.3
0x152e52  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x152e57  ldstr    aEntity_0// "entity"
0x152e5c  ldc.i4.0
0x152e5d  ldarg.s  4
0x152e5f  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x152e64  pop
0x152e65  ldloc.3
0x152e66  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x152e6b  ldc.i4.2
0x152e6c  newarr   [mscorlib]System.String
0x152e71  dup
0x152e72  ldc.i4.0
0x152e73  ldstr    aRibboncontextg_0// "ribboncontextgroupid"
0x152e78  stelem.ref
0x152e79  dup
0x152e7a  ldc.i4.1
0x152e7b  ldstr    aContextgroupxm// "contextgroupxml"
0x152e80  stelem.ref
0x152e81  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x152e86  ldarg.0
0x152e87  ldloc.3
0x152e88  ldarg.s  6
0x152e8a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x152e8f  stloc.s  4
0x152e91  ldloc.s  4
0x152e93  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x152e98  ldc.i4.1
0x152e99  cgt
0x152e9b  ldc.i4.0
0x152e9c  ceq
0x152e9e  ldstr    aFoundMoreThanO_0// "Found more than one RibbonContextGroup "...
0x152ea3  ldc.i4.3
0x152ea4  newarr   [mscorlib]System.Object
0x152ea9  dup
0x152eaa  ldc.i4.0
0x152eab  ldloc.2
0x152eac  stelem.ref
0x152ead  dup
0x152eae  ldc.i4.1
0x152eaf  ldarg.s  4
0x152eb1  stelem.ref
0x152eb2  dup
0x152eb3  ldc.i4.2
0x152eb4  ldarg.2
0x152eb5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x152eba  box      [mscorlib]System.Guid
0x152ebf  stelem.ref
0x152ec0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string, object[])
0x152ec5  newobj   instance void Microsoft.Crm.ObjectModel.RibbonImportResult::.ctor()
0x152eca  stloc.s  5
0x152ecc  ldloc.s  4
0x152ece  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x152ed3  brtrue.s loc_152F3E
0x152ed5  ldarg.s  6
0x152ed7  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.RibbonContextGroup::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x152edc  stloc.s  8
0x152ede  ldloc.s  8
0x152ee0  ldstr    aContextgroupid// "contextgroupid"
0x152ee5  ldloc.2
0x152ee6  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x152eeb  ldloc.s  8
0x152eed  ldstr    aContextgroupxm// "contextgroupxml"
0x152ef2  ldloc.1
0x152ef3  ldc.i4.1
0x152ef4  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XNode::ToString(valuetype [System.Xml.Linq]System.Xml.Linq.SaveOptions)
0x152ef9  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x152efe  ldloc.s  8
0x152f00  ldstr    aEntity_0// "entity"
0x152f05  ldarg.s  4
0x152f07  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x152f0c  ldloc.s  8
0x152f0e  ldstr    aRibboncustomiz_0// "ribboncustomizationid"
0x152f13  ldarg.2
0x152f14  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x152f19  box      [mscorlib]System.Guid
0x152f1e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x152f23  ldloc.s  5
0x152f25  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker> Microsoft.Crm.ObjectModel.RibbonImportResult::get_Monikers()
0x152f2a  ldarg.0
0x152f2b  ldloc.s  8
0x152f2d  ldarg.s  6
0x152f2f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x152f34  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker>::Add(var<u1>)
0x152f39  br       loc_152FEC
0x152f3e  ldloc.s  4
0x152f40  ldc.i4.0
0x152f41  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x152f46  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.RibbonContextGroup
0x152f4b  stloc.s  9
0x152f4d  ldarg.3
0x152f4e  brtrue.s loc_152F8F
0x152f50  ldloc.s  9
0x152f52  ldstr    aContextgroupxm// "contextgroupxml"
0x152f57  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x152f5c  castclass [mscorlib]System.String
0x152f61  ldloc.1
0x152f62  ldc.i4.1
0x152f63  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XNode::ToString(valuetype [System.Xml.Linq]System.Xml.Linq.SaveOptions)
0x152f68  ldc.i4.5
0x152f69  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x152f6e  brtrue.s loc_152FC3
0x152f70  ldloc.s  9
0x152f72  ldstr    aContextgroupxm// "contextgroupxml"
0x152f77  ldloc.1
0x152f78  ldc.i4.1
0x152f79  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XNode::ToString(valuetype [System.Xml.Linq]System.Xml.Linq.SaveOptions)
0x152f7e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x152f83  ldarg.0
0x152f84  ldloc.s  9
0x152f86  ldarg.s  6
0x152f88  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x152f8d  br.s     loc_152FC3
0x152f8f  ldloc.s  9
0x152f91  ldstr    aContextgroupxm// "contextgroupxml"
0x152f96  ldloc.1
0x152f97  ldc.i4.1
0x152f98  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XNode::ToString(valuetype [System.Xml.Linq]System.Xml.Linq.SaveOptions)
0x152f9d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x152fa2  ldloc.s  9
0x152fa4  ldstr    aRibboncustomiz_0// "ribboncustomizationid"
0x152fa9  ldarg.3
0x152faa  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x152faf  box      [mscorlib]System.Guid
0x152fb4  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x152fb9  ldarg.0
0x152fba  ldloc.s  9
0x152fbc  ldarg.s  6
0x152fbe  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x152fc3  ldloc.s  5
0x152fc5  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker> Microsoft.Crm.ObjectModel.RibbonImportResult::get_Monikers()
0x152fca  ldloc.s  9
0x152fcc  ldstr    aRibboncontextg_0// "ribboncontextgroupid"
0x152fd1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x152fd6  unbox.any [mscorlib]System.Guid
0x152fdb  ldstr    aRibboncontextg// "RibbonContextGroup"
0x152fe0  ldarg.s  6
0x152fe2  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x152fe7  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker>::Add(var<u1>)
0x152fec  ldc.i4.0
0x152fed  stloc.s  6
0x152fef  newobj   instance void Microsoft.Crm.ObjectModel.RibbonDiffService::.ctor()
0x152ff4  stloc.s  7
0x152ff6  ldloc.0
0x152ff7  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement> [System.Xml.Linq]System.Xml.Linq.XContainer::Elements()
0x152ffc  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement>::GetEnumerator()
0x153001  stloc.s  0xA
0x153003  br       loc_1530A5
0x153008  ldloc.s  0xA
0x15300a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Xml.Linq]System.Xml.Linq.XElement>::get_Current()
0x15300f  stloc.s  0xB
0x153011  ldstr    aCustomaction// "CustomAction"
0x153016  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x15301b  ldc.i4.3
0x15301c  newarr   [mscorlib]System.Object
0x153021  dup
0x153022  ldc.i4.0
0x153023  ldstr    aId_0// "Id"
0x153028  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x15302d  ldloc.2
0x15302e  ldstr    asc_258298// "_"
0x153033  ldloca.s 6
0x153035  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15303a  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x15303f  call     string [mscorlib]System.String::Concat(string, string, string)
0x153044  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XAttribute::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x153049  stelem.ref
0x15304a  dup
0x15304b  ldc.i4.1
0x15304c  ldstr    aLocation_0// "Location"
0x153051  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x153056  ldloc.2
0x153057  ldstr    aChildren// "._children"
0x15305c  call     string [mscorlib]System.String::Concat(string, string)
0x153061  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XAttribute::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x153066  stelem.ref
0x153067  dup
0x153068  ldc.i4.2
0x153069  ldstr    aCommanduidefin// "CommandUIDefinition"
0x15306e  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x153073  ldloc.s  0xB
0x153075  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XElement::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x15307a  stelem.ref
0x15307b  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XElement::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object[])
0x153080  stloc.s  0xC
0x153082  ldloc.s  7
0x153084  ldloc.s  0xC
0x153086  ldarg.2
0x153087  ldarg.3
0x153088  ldarg.s  4
0x15308a  ldarg.s  5
0x15308c  ldc.i4.0
0x15308d  ldarg.s  6
0x15308f  callvirt instance class Microsoft.Crm.ObjectModel.RibbonImportResult Microsoft.Crm.ObjectModel.RibbonDiffService::CreateCustomActionFromXml(class [System.Xml.Linq]System.Xml.Linq.XElement customActionNode, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker parentRibbonCustomization, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker newRibbonCustomization, string entityLogicalName, class Microsoft.Crm.ObjectModel.ControlMapping controlMapping, bool ignoreMissingParentTab, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x153094  stloc.s  0xD
0x153096  ldloc.s  6
0x153098  ldc.i4.1
0x153099  add
0x15309a  stloc.s  6
0x15309c  ldloc.s  5
0x15309e  ldloc.s  0xD
0x1530a0  call     void Microsoft.Crm.ObjectModel.RibbonImportResult::AddToBaseResult(class Microsoft.Crm.ObjectModel.RibbonImportResult baseResult, class Microsoft.Crm.ObjectModel.RibbonImportResult newResult)
0x1530a5  ldloc.s  0xA
0x1530a7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1530ac  brtrue   loc_153008
0x1530b1  leave.s  loc_1530BF
0x1530b3  ldloc.s  0xA
0x1530b5  brfalse.s loc_1530BE
0x1530b7  ldloc.s  0xA
0x1530b9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1530be  endfinally
0x1530bf  ldloc.s  5
0x1530c1  ret
```
