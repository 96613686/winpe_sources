# Microsoft.Crm.Application.CellDescriptor::.ctor_1

- ea: `0x171d0`
- end: `0x174cb`
- name: `Microsoft.Crm.Application.CellDescriptor::.ctor_1`
- size: `763`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1b0e0`

## callees

- `0xbd0`
- `0x17130`
- `0x171d0`
- `0x174d0`
- `0x174f0`
- `0x17530`
- `0x17590`
- `0x18790`
- `0x187c0`
- `0x19080`
- `0x1c2e0`
- `0x1c2f0`
- `0x1f7c0`
- `0x1f7d0`
- `0x2fb90`
- `0x42990`
- `0x47280`
- `0x59e10`
- `0x5be20`
- `0x5be60`

## string_xrefs

- `0x1722c`: `classid`
- `0x1726e`: `classid`
- `0x17459`: `classid`
- `0x17306`: `customControl/parameters/msinternal.isvisibleinmocaonly`
- `0x17484`: `CellDescriptor: Exception while handling Appointment RTE: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x171d0  ldarg.0
0x171d1  ldarg.1
0x171d2  ldarg.3
0x171d3  callvirt instance bool Microsoft.Crm.Application.FormDescriptor::get_IsUserForm()
0x171d8  ldc.i4.0
0x171d9  ceq
0x171db  ldarg.3
0x171dc  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.FormDescriptor::get_Context()
0x171e1  ldarg.s  5
0x171e3  ldarg.s  6
0x171e5  ldarg.s  7
0x171e7  call     instance void Microsoft.Crm.Application.CellDescriptor::.ctor(class [System.Xml]System.Xml.XmlNode formNode, bool canHaveMultipleLabels, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, bool isInFirstColumn, bool isInLastColumn, [opt] bool insertLabel)
0x171ec  ldarg.0
0x171ed  ldarg.3
0x171ee  stfld    class Microsoft.Crm.Application.FormDescriptor Microsoft.Crm.Application.CellDescriptor::_formDescriptor
0x171f3  ldarg.0
0x171f4  ldarg.s  4
0x171f6  call     instance void Microsoft.Crm.Application.CellDescriptor::set_ContainerTab(class Microsoft.Crm.Application.TabDescriptor value)
0x171fb  ldarg.1
0x171fc  ldstr    aControl// "control"
0x17201  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x17206  stloc.0
0x17207  ldloc.0
0x17208  ldstr    aDatafieldname// "datafieldname"
0x1720d  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string)
0x17212  stloc.1
0x17213  ldloc.1
0x17214  brfalse.s loc_17254
0x17216  ldarg.2
0x17217  brfalse.s loc_17254
0x17219  ldarg.2
0x1721a  ldloc.1
0x1721b  ldc.i4.1
0x1721c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x17221  brtrue.s loc_17254
0x17223  ldloc.0
0x17224  brfalse.s loc_1724C
0x17226  ldloc.0
0x17227  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x1722c  ldstr    aClassid// "classid"
0x17231  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x17236  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x1723b  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x17240  ldstr    a00ad73daBd4d49// "{00AD73DA-BD4D-49C6-88A8-2F4F4CAD4A20}"
0x17245  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x1724a  brfalse.s loc_17254
0x1724c  ldarg.0
0x1724d  ldc.i4.0
0x1724e  call     instance void Microsoft.Crm.Application.FormPartWithLabelDescriptor::set_ShowLabel(bool value)
0x17253  ret
0x17254  ldloc.0
0x17255  brfalse  loc_174CA
0x1725a  ldarg.0
0x1725b  ldloc.0
0x1725c  call     instance bool Microsoft.Crm.Application.CellDescriptor::SkipControlDescriptorForControl(class [System.Xml]System.Xml.XmlNode controlNode)
0x17261  brtrue   loc_174CA
0x17266  ldloc.0
0x17267  stloc.2
0x17268  ldloc.0
0x17269  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x1726e  ldstr    aClassid// "classid"
0x17273  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x17278  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x1727d  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x17282  ldstr    aF9a8a302114e46// "{F9A8A302-114E-466A-B582-6771B2AE0D92}"
0x17287  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1728c  brfalse  loc_17360
0x17291  ldarg.0
0x17292  ldloc.0
0x17293  call     instance bool Microsoft.Crm.Application.CellDescriptor::IsUnboundControl(class [System.Xml]System.Xml.XmlNode controlNode)
0x17298  brfalse.s loc_172A5
0x1729a  ldarg.0
0x1729b  call     instance bool Microsoft.Crm.Application.CellDescriptor::IsMDDControl()
0x172a0  brfalse  loc_17360
0x172a5  ldarg.0
0x172a6  ldloc.0
0x172a7  ldarg.2
0x172a8  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Application.CellDescriptor::ProcessCustomControl(class [System.Xml]System.Xml.XmlNode controlNode, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata)
0x172ad  stloc.2
0x172ae  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x172b3  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x172b8  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_CustomControlSolutionExport()
0x172bd  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x172c2  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x172c7  brfalse  loc_174A2
0x172cc  ldloc.0
0x172cd  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x172d2  ldstr    aUniqueid// "uniqueid"
0x172d7  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x172dc  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x172e1  stloc.3
0x172e2  ldloc.0
0x172e3  callvirt instance class [System.Xml]System.Xml.XmlDocument [System.Xml]System.Xml.XmlNode::get_OwnerDocument()
0x172e8  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x172ed  ldstr    aControldescrip_0// "//controlDescription[@forControl='"
0x172f2  ldloc.3
0x172f3  ldstr    asc_B6994// "']"
0x172f8  call     string [mscorlib]System.String::Concat(string, string, string)
0x172fd  stloc.s  4
0x172ff  ldloc.s  4
0x17301  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x17306  ldstr    aCustomcontrolP// "customControl/parameters/msinternal.isv"...
0x1730b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x17310  stloc.s  5
0x17312  ldc.i4.0
0x17313  stloc.s  6
0x17315  ldloc.s  5
0x17317  brfalse.s loc_17333
0x17319  ldloc.s  5
0x1731b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x17320  brtrue.s loc_17325
0x17322  ldc.i4.0
0x17323  br.s     loc_17331
0x17325  ldloc.s  5
0x17327  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x1732c  call     bool [mscorlib]System.Boolean::Parse(string)
0x17331  stloc.s  6
0x17333  ldloc.s  6
0x17335  brfalse  loc_174A2
0x1733a  call     bool Microsoft.Crm.Application.Utility.Util::IsForOutlookClient()
0x1733f  brtrue   loc_174A2
0x17344  ldarg.3
0x17345  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.FormDescriptor::get_Context()
0x1734a  call     bool Microsoft.Crm.Application.Utility.Util::IsDashboardPage(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x1734f  brfalse  loc_174A2
0x17354  ldarg.0
0x17355  ldc.i4.0
0x17356  call     instance void Microsoft.Crm.Application.CellDescriptor::set_Visible(bool value)
0x1735b  br       loc_174A2
0x17360  ldloc.0
0x17361  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x17366  ldstr    aUniqueid// "uniqueid"
0x1736b  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x17370  brfalse.s loc_173B6
0x17372  ldloc.0
0x17373  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x17378  ldstr    aIsunbound// "isunbound"
0x1737d  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x17382  brfalse.s loc_173A5
0x17384  ldloc.0
0x17385  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x1738a  ldstr    aIsunbound// "isunbound"
0x1738f  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x17394  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x17399  ldstr    aTrue// "true"
0x1739e  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x173a3  brfalse.s loc_173B6
0x173a5  ldloc.0
0x173a6  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x173ab  ldstr    aUniqueid// "uniqueid"
0x173b0  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::RemoveNamedItem(string)
0x173b5  pop
0x173b6  nop
0x173b7  ldloc.1
0x173b8  brfalse  loc_17480
0x173bd  ldloc.1
0x173be  ldstr    aDescription_0// "description"
0x173c3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x173c8  brfalse  loc_17480
0x173cd  ldarg.2
0x173ce  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x173d3  ldstr    aAppointment// "appointment"
0x173d8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x173dd  brfalse  loc_17480
0x173e2  ldarg.3
0x173e3  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.FormDescriptor::get_Context()
0x173e8  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x173ed  ldstr    aOrganization// "organization"
0x173f2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string)
0x173f7  ldstr    aAppointmentric// "appointmentricheditorexperience"
0x173fc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0x17401  brfalse.s loc_17480
0x17403  ldstr    aOrganization// "organization"
0x17408  ldarg.3
0x17409  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.FormDescriptor::get_Context()
0x1740e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x17413  ldc.i4.1
0x17414  newarr   [mscorlib]System.String
0x17419  dup
0x1741a  ldc.i4.0
0x1741b  ldstr    aAppointmentric// "appointmentricheditorexperience"
0x17420  stelem.ref
0x17421  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSet::.ctor(string[])
0x17426  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1742b  call     class Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Platform.DataSource::Retrieve(string entityName, valuetype [mscorlib]System.Guid entityId, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase columnSet, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x17430  stloc.s  7
0x17432  ldloc.s  7
0x17434  ldstr    aAppointmentric// "appointmentricheditorexperience"
0x17439  callvirt instance bool Microsoft.Crm.Application.Platform.EntityBase::HasAttributeAndNotNull(string name)
0x1743e  brfalse.s loc_17480
0x17440  ldloc.s  7
0x17442  ldstr    aAppointmentric// "appointmentricheditorexperience"
0x17447  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x1744c  unbox.any [mscorlib]System.Boolean
0x17451  brfalse.s loc_17480
0x17453  ldloc.0
0x17454  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x17459  ldstr    aClassid// "classid"
0x1745e  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x17463  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.FormControlClassId::EmailBodyControl
0x17468  stloc.s  8
0x1746a  ldloca.s 8
0x1746c  ldstr    aB_0// "B"
0x17471  call     instance string [mscorlib]System.Guid::ToString(string)
0x17476  callvirt instance string [mscorlib]System.String::ToUpper()
0x1747b  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x17480  leave.s  loc_174A0
0x17482  stloc.s  9
0x17484  ldstr    aCelldescriptor// "CellDescriptor: Exception while handlin"...
0x17489  ldc.i4.1
0x1748a  newarr   [mscorlib]System.Object
0x1748f  dup
0x17490  ldc.i4.0
0x17491  ldloc.s  9
0x17493  callvirt instance string [mscorlib]System.Object::ToString()
0x17498  stelem.ref
0x17499  call     void Microsoft.Crm.Util::TraceInfo(string message, object[] args)
0x1749e  leave.s  loc_174A0
0x174a0  ldloc.0
0x174a1  stloc.2
0x174a2  ldarg.0
0x174a3  ldloc.2
0x174a4  ldarg.2
0x174a5  ldarg.3
0x174a6  ldarg.0
0x174a7  ldarg.3
0x174a8  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.FormDescriptor::get_Context()
0x174ad  ldarg.s  7
0x174af  newobj   instance void Microsoft.Crm.Application.ControlDescriptor::.ctor(class [System.Xml]System.Xml.XmlNode formNode, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata, class Microsoft.Crm.Application.FormDescriptor formDescriptor, class Microsoft.Crm.Application.CellDescriptor parentCellDescriptor, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, [opt] bool insertLabel)
0x174b4  stfld    class Microsoft.Crm.Application.ControlDescriptor Microsoft.Crm.Application.CellDescriptor::_control
0x174b9  ldarg.0
0x174ba  ldfld    class Microsoft.Crm.Application.ControlDescriptor Microsoft.Crm.Application.CellDescriptor::_control
0x174bf  ldarg.0
0x174c0  call     instance bool Microsoft.Crm.Application.FormPartWithLabelDescriptor::get_ShowLabel()
0x174c5  callvirt instance void Microsoft.Crm.Application.FormPartWithLabelDescriptor::set_ShowLabel(bool value)
0x174ca  ret
```
