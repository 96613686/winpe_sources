# Microsoft.Crm.Ribbon.DiffProcessing::ExecuteCustomAction

- ea: `0x9140`
- end: `0x9563`
- name: `Microsoft.Crm.Ribbon.DiffProcessing::ExecuteCustomAction`
- size: `1059`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x8ec0`

## callees

- `0x9140`
- `0x9ac0`
- `0x9e80`

## string_xrefs

- `0x9225`: `ExecuteCustomAction: CustomActionType='{0}' Id='{1}' completed.`
- `0x941a`: `ExecuteCustomAction: CustomActionType='{0}' Id='{1}' completed.`
- `0x94e9`: `ExecuteCustomAction: CustomActionType='{0}' Id='{1}' completed.`
- `0x9546`: `ExecuteCustomAction: CustomActionType='{0}' Id='{1}' completed.`
- `0x9276`: `CommandUIDefinition`
- `0x92a7`: `ExecuteCustomAction: CustomActionType='{0}' Id='{1}' skipped. Ribbon custom action Id='{2}' does not contain a required child CommandUIDefinition element.`
- `0x92ed`: `ExecuteCustomAction: CustomActionType='{0}' Id='{1}' skipped. Ribbon custom action Id='{2}' CommandUIDefinition element does not contain a required child ribbon element.`
- `0x93db`: `ExecuteCustomAction: CustomActionType='{0}' Id='{1}' skipped. Ribbon could not overwrite. Location node does not have a parent node.`

## pseudocode

```c

```

## disassembly

```asm
0x9140  ldarg.2
0x9141  brtrue.s loc_9146
0x9143  ldnull
0x9144  br.s     loc_9162
0x9146  ldarg.2
0x9147  ldstr    aId_0// "Id"
0x914c  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x9151  call     instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0x9156  dup
0x9157  brtrue.s loc_915D
0x9159  pop
0x915a  ldnull
0x915b  br.s     loc_9162
0x915d  call     instance string [System.Xml.Linq]System.Xml.Linq.XAttribute::get_Value()
0x9162  stloc.0
0x9163  ldarg.s  6
0x9165  brtrue.s loc_916E
0x9167  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x916c  br.s     loc_9175
0x916e  ldarg.s  6
0x9170  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x9175  ldc.i4.s 0x14
0x9177  ldstr    aExecutecustoma// "ExecuteCustomAction: CustomActionType='"...
0x917c  ldarg.0
0x917d  box      CustomActionType
0x9182  ldloc.0
0x9183  call     string [mscorlib]System.String::Format(string, object, object)
0x9188  ldc.i4.0
0x9189  newarr   [mscorlib]System.Object
0x918e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x9193  ldarg.1
0x9194  brtrue.s loc_91C7
0x9196  ldarg.s  6
0x9198  brtrue.s loc_91A1
0x919a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x919f  br.s     loc_91A8
0x91a1  ldarg.s  6
0x91a3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x91a8  ldc.i4.s 0x14
0x91aa  ldstr    aExecutecustoma_0// "ExecuteCustomAction: CustomActionType='"...
0x91af  ldarg.0
0x91b0  box      CustomActionType
0x91b5  ldloc.0
0x91b6  call     string [mscorlib]System.String::Format(string, object, object)
0x91bb  ldc.i4.0
0x91bc  newarr   [mscorlib]System.Object
0x91c1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x91c6  ret
0x91c7  ldarg.0
0x91c8  ldc.i4.1
0x91c9  bne.un.s loc_9242
0x91cb  ldarg.1
0x91cc  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x91d1  brtrue.s loc_9204
0x91d3  ldarg.s  6
0x91d5  brtrue.s loc_91DE
0x91d7  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x91dc  br.s     loc_91E5
0x91de  ldarg.s  6
0x91e0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x91e5  ldc.i4.s 0x14
0x91e7  ldstr    aExecutecustoma_1// "ExecuteCustomAction: CustomActionType='"...
0x91ec  ldarg.0
0x91ed  box      CustomActionType
0x91f2  ldloc.0
0x91f3  call     string [mscorlib]System.String::Format(string, object, object)
0x91f8  ldc.i4.0
0x91f9  newarr   [mscorlib]System.Object
0x91fe  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x9203  ret
0x9204  ldarg.1
0x9205  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x920a  ldarg.1
0x920b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x9210  pop
0x9211  ldarg.s  6
0x9213  brtrue.s loc_921C
0x9215  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x921a  br.s     loc_9223
0x921c  ldarg.s  6
0x921e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x9223  ldc.i4.s 0x14
0x9225  ldstr    aExecutecustoma_2// "ExecuteCustomAction: CustomActionType='"...
0x922a  ldarg.0
0x922b  box      CustomActionType
0x9230  ldloc.0
0x9231  call     string [mscorlib]System.String::Format(string, object, object)
0x9236  ldc.i4.0
0x9237  newarr   [mscorlib]System.Object
0x923c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x9241  ret
0x9242  ldarg.2
0x9243  brtrue.s loc_9275
0x9245  ldarg.s  6
0x9247  brtrue.s loc_9250
0x9249  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x924e  br.s     loc_9257
0x9250  ldarg.s  6
0x9252  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x9257  ldc.i4.s 0x14
0x9259  ldstr    aExecutecustoma_3// "ExecuteCustomAction: CustomActionType='"...
0x925e  ldarg.0
0x925f  box      CustomActionType
0x9264  call     string [mscorlib]System.String::Format(string, object)
0x9269  ldc.i4.0
0x926a  newarr   [mscorlib]System.Object
0x926f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x9274  ret
0x9275  ldarg.2
0x9276  ldstr    aCommanduidefin// "CommandUIDefinition"
0x927b  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x9280  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement> [System.Xml.Linq]System.Xml.Linq.XContainer::Descendants(class [System.Xml.Linq]System.Xml.Linq.XName)
0x9285  call     T0x2B00000C
0x928a  stloc.1
0x928b  ldloc.1
0x928c  call     T0x2B00000D
0x9291  brtrue.s loc_92C5
0x9293  ldarg.s  6
0x9295  brtrue.s loc_929E
0x9297  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x929c  br.s     loc_92A5
0x929e  ldarg.s  6
0x92a0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x92a5  ldc.i4.s 0x14
0x92a7  ldstr    aExecutecustoma_4// "ExecuteCustomAction: CustomActionType='"...
0x92ac  ldarg.0
0x92ad  box      CustomActionType
0x92b2  ldloc.0
0x92b3  ldloc.0
0x92b4  call     string [mscorlib]System.String::Format(string, object, object, object)
0x92b9  ldc.i4.0
0x92ba  newarr   [mscorlib]System.Object
0x92bf  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x92c4  ret
0x92c5  ldloc.1
0x92c6  call     T0x2B00000E
0x92cb  call     T0x2B00000C
0x92d0  stloc.2
0x92d1  ldloc.2
0x92d2  call     T0x2B00000D
0x92d7  brtrue.s loc_9314
0x92d9  ldarg.s  6
0x92db  brtrue.s loc_92E4
0x92dd  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x92e2  br.s     loc_92EB
0x92e4  ldarg.s  6
0x92e6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x92eb  ldc.i4.s 0x14
0x92ed  ldstr    aExecutecustoma_5// "ExecuteCustomAction: CustomActionType='"...
0x92f2  ldarg.0
0x92f3  box      CustomActionType
0x92f8  ldloc.0
0x92f9  ldloc.0
0x92fa  dup
0x92fb  brtrue.s loc_9303
0x92fd  pop
0x92fe  ldstr    aUnknown// "unknown"
0x9303  call     string [mscorlib]System.String::Format(string, object, object, object)
0x9308  ldc.i4.0
0x9309  newarr   [mscorlib]System.Object
0x930e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x9313  ret
0x9314  ldloc.2
0x9315  call     T0x2B00000F
0x931a  ldc.i4.1
0x931b  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XNode::ToString(valuetype [System.Xml.Linq]System.Xml.Linq.SaveOptions)
0x9320  ldarg.1
0x9321  callvirt instance class [System.Xml]System.Xml.XmlDocument [System.Xml]System.Xml.XmlNode::get_OwnerDocument()
0x9326  call     class [System.Xml]System.Xml.XmlElement Microsoft.Crm.Ribbon.RibbonPlatformXml::CreateXmlElement(string xml, class [System.Xml]System.Xml.XmlDocument document)
0x932b  stloc.3
0x932c  ldloc.3
0x932d  ldstr    aId_0// "Id"
0x9332  callvirt instance bool [System.Xml]System.Xml.XmlElement::HasAttribute(string)
0x9337  brtrue.s loc_933C
0x9339  ldnull
0x933a  br.s     loc_9347
0x933c  ldloc.3
0x933d  ldstr    aId_0// "Id"
0x9342  callvirt instance string [System.Xml]System.Xml.XmlElement::GetAttribute(string)
0x9347  stloc.s  4
0x9349  ldarg.3
0x934a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x934f  brtrue.s loc_938A
0x9351  ldloc.3
0x9352  brfalse.s loc_938A
0x9354  ldloc.3
0x9355  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x935a  ldstr    aTab// "Tab"
0x935f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9364  brfalse.s loc_938A
0x9366  ldloc.s  4
0x9368  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x936d  brtrue.s loc_938A
0x936f  ldloc.s  4
0x9371  ldarg.3
0x9372  ldarg.s  4
0x9374  ldarg.s  5
0x9376  call     string Microsoft.Crm.Ribbon.RibbonPlatformXml::MarkEntityTabId(string originalTabId, string entityLogicalName, valuetype [Microsoft.Crm]Microsoft.Crm.RibbonRuleRelationshipType relationshipType, string entityContext)
0x937b  stloc.s  5
0x937d  ldloc.3
0x937e  ldstr    aId_0// "Id"
0x9383  ldloc.s  5
0x9385  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x938a  ldarg.0
0x938b  ldc.i4.2
0x938c  bne.un.s loc_93BB
0x938e  ldarg.1
0x938f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9394  ldstr    aId0// "./*[@Id='{0}']"
0x9399  ldc.i4.1
0x939a  newarr   [mscorlib]System.Object
0x939f  dup
0x93a0  ldc.i4.0
0x93a1  ldloc.s  4
0x93a3  stelem.ref
0x93a4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x93a9  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x93ae  stloc.s  6
0x93b0  ldloc.s  6
0x93b2  brfalse.s loc_93BB
0x93b4  ldloc.s  6
0x93b6  starg.s  1
0x93b8  ldc.i4.3
0x93b9  starg.s  0
0x93bb  ldarg.0
0x93bc  ldc.i4.3
0x93bd  bne.un.s loc_9437
0x93bf  ldarg.1
0x93c0  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x93c5  brtrue.s loc_93F8
0x93c7  ldarg.s  6
0x93c9  brtrue.s loc_93D2
0x93cb  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x93d0  br.s     loc_93D9
0x93d2  ldarg.s  6
0x93d4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x93d9  ldc.i4.s 0x14
0x93db  ldstr    aExecutecustoma_6// "ExecuteCustomAction: CustomActionType='"...
0x93e0  ldarg.0
0x93e1  box      CustomActionType
0x93e6  ldloc.0
0x93e7  call     string [mscorlib]System.String::Format(string, object, object)
0x93ec  ldc.i4.0
0x93ed  newarr   [mscorlib]System.Object
0x93f2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x93f7  ret
0x93f8  ldarg.1
0x93f9  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x93fe  ldloc.3
0x93ff  ldarg.1
0x9400  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::ReplaceChild(class [System.Xml]System.Xml.XmlNode, class [System.Xml]System.Xml.XmlNode)
0x9405  pop
0x9406  ldarg.s  6
0x9408  brtrue.s loc_9411
0x940a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x940f  br.s     loc_9418
0x9411  ldarg.s  6
0x9413  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x9418  ldc.i4.s 0x14
0x941a  ldstr    aExecutecustoma_2// "ExecuteCustomAction: CustomActionType='"...
0x941f  ldarg.0
0x9420  box      CustomActionType
0x9425  ldloc.0
0x9426  call     string [mscorlib]System.String::Format(string, object, object)
0x942b  ldc.i4.0
0x942c  newarr   [mscorlib]System.Object
0x9431  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x9436  ret
0x9437  ldarg.0
0x9438  ldc.i4.2
0x9439  bne.un   loc_9562
0x943e  ldloc.3
0x943f  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x9444  ldstr    aSequence// "Sequence"
0x9449  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x944e  stloc.s  7
0x9450  ldloc.s  7
0x9452  brfalse  loc_952A
0x9457  ldloc.s  7
0x9459  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x945e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9463  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x9468  stloc.s  8
0x946a  ldarg.1
0x946b  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x9470  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x9475  stloc.s  9
0x9477  br       loc_9507
0x947c  ldloc.s  9
0x947e  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x9483  castclass [System.Xml]System.Xml.XmlNode
0x9488  stloc.s  0xA
0x948a  ldloc.s  0xA
0x948c  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlNode::get_NodeType()
0x9491  ldc.i4.1
0x9492  bne.un.s loc_9507
0x9494  ldloc.s  0xA
0x9496  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x949b  dup
0x949c  brtrue.s loc_94A2
  ... truncated ...
```
