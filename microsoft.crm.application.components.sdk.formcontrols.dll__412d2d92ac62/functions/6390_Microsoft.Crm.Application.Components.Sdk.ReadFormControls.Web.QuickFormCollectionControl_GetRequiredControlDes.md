# Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormCollectionControl::GetRequiredControlDescriptors

- ea: `0x6390`
- end: `0x6666`
- name: `Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormCollectionControl::GetRequiredControlDescriptors`
- size: `726`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1450`
- `0x6140`
- `0x6180`
- `0x6390`
- `0x6670`

## pseudocode

```c

```

## disassembly

```asm
0x6390  ldarg.0
0x6391  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor> Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormCollectionControl::_controlDescriptors
0x6396  brtrue   loc_665F
0x639b  ldarg.0
0x639c  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor>::.ctor()
0x63a1  stfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor> Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormCollectionControl::_controlDescriptors
0x63a6  ldarg.0
0x63a7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x63ac  brfalse.s loc_6404
0x63ae  ldarg.0
0x63af  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x63b4  ldstr    aLookupField// "_lookup_field"
0x63b9  call     string [mscorlib]System.String::Concat(string, string)
0x63be  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.FormControlClassId::HiddenInputControl
0x63c3  stloc.1
0x63c4  ldloca.s 1
0x63c6  constrained. [mscorlib]System.Guid
0x63cc  callvirt instance string [mscorlib]System.Object::ToString()
0x63d1  ldarg.0
0x63d2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x63d7  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x63dc  ldarg.0
0x63dd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x63e2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0x63e7  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x63ec  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x63f1  ldnull
0x63f2  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor::.ctor(string, string, string, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ParameterDescriptor>)
0x63f7  stloc.0
0x63f8  ldarg.0
0x63f9  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor> Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormCollectionControl::_controlDescriptors
0x63fe  ldloc.0
0x63ff  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor>::Add(var<u1>)
0x6404  ldarg.0
0x6405  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormCollectionControl::get_QuickForms()
0x640a  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x640f  ldstr    aQuickformidsQu// "/QuickFormIds/QuickFormId"
0x6414  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x6419  stloc.2
0x641a  ldc.i4.1
0x641b  stloc.3
0x641c  ldloc.2
0x641d  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x6422  stloc.s  4
0x6424  br       loc_6632
0x6429  ldloc.s  4
0x642b  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x6430  castclass [System.Xml]System.Xml.XmlNode
0x6435  stloc.s  5
0x6437  ldloc.s  5
0x6439  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x643e  ldstr    aEntityname// "entityname"
0x6443  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x6448  ldnull
0x6449  cgt.un
0x644b  ldstr    aEntityNameAttr// "entity name attribute must be present"
0x6450  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x6455  ldarg.0
0x6456  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x645b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6460  ldc.i4.0
0x6461  ceq
0x6463  ldstr    aIdMustNotBeAnE// "ID must not be an empty"
0x6468  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x646d  ldloc.s  5
0x646f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x6474  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6479  ldc.i4.0
0x647a  ceq
0x647c  ldstr    aFormidMustBePr// "FormId must be present"
0x6481  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x6486  ldc.i4.6
0x6487  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor(int32)
0x648c  stloc.s  6
0x648e  ldloc.s  6
0x6490  ldstr    aFormid// "FormId"
0x6495  ldloc.s  5
0x6497  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x649c  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Parse(string)
0x64a1  stloc.1
0x64a2  ldloca.s 1
0x64a4  constrained. [mscorlib]System.Guid
0x64aa  callvirt instance string [mscorlib]System.Object::ToString()
0x64af  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ParameterDescriptor::.ctor(string, string)
0x64b4  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x64b9  pop
0x64ba  ldloc.s  6
0x64bc  ldstr    aControlmode// "ControlMode"
0x64c1  ldarg.0
0x64c2  call     instance valuetype Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControlMode Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormCollectionControl::get_ControlMode()
0x64c7  stloc.s  8
0x64c9  ldloca.s 8
0x64cb  constrained. Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControlMode
0x64d1  callvirt instance string [mscorlib]System.Object::ToString()
0x64d6  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ParameterDescriptor::.ctor(string, string)
0x64db  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x64e0  pop
0x64e1  ldloc.s  6
0x64e3  ldstr    aUniqueid// "UniqueId"
0x64e8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x64ed  ldstr    a0Quickform1// "{0}_quickForm_{1}"
0x64f2  ldc.i4.2
0x64f3  newarr   [mscorlib]System.Object
0x64f8  dup
0x64f9  ldc.i4.0
0x64fa  ldarg.0
0x64fb  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x6500  stelem.ref
0x6501  dup
0x6502  ldc.i4.1
0x6503  ldloc.s  5
0x6505  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x650a  ldstr    aEntityname// "entityname"
0x650f  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x6514  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x6519  stelem.ref
0x651a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x651f  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ParameterDescriptor::.ctor(string, string)
0x6524  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x6529  pop
0x652a  ldarg.0
0x652b  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x6530  brfalse.s loc_658B
0x6532  ldarg.0
0x6533  ldarg.1
0x6534  ldarg.0
0x6535  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x653a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x653f  ldloc.s  5
0x6541  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x6546  ldstr    aEntityname// "entityname"
0x654b  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x6550  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x6555  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormCollectionControl::GetRelationshipName(int32 parentEntityObjectCode, string referencingAttributeId, string childEntity)
0x655a  stloc.s  9
0x655c  ldloc.s  9
0x655e  brfalse.s loc_658B
0x6560  ldloc.s  6
0x6562  ldstr    aQuickformrelat// "QuickFormRelationshipName"
0x6567  ldloc.s  9
0x6569  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ParameterDescriptor::.ctor(string, string)
0x656e  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x6573  pop
0x6574  ldloc.s  6
0x6576  ldstr    aQuickformrelat_0// "QuickFormRelationshipRoleOrdinal"
0x657b  ldstr    a1_0// "1"
0x6580  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ParameterDescriptor::.ctor(string, string)
0x6585  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x658a  pop
0x658b  ldloc.s  6
0x658d  ldstr    aDefaultvisibil// "DefaultVisibility"
0x6592  ldloc.3
0x6593  brtrue.s loc_659C
0x6595  ldstr    a0// "0"
0x659a  br.s     loc_65A1
0x659c  ldstr    a1_0// "1"
0x65a1  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ParameterDescriptor::.ctor(string, string)
0x65a6  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x65ab  pop
0x65ac  ldarg.0
0x65ad  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x65b2  ldstr    asc_359D6// "_"
0x65b7  ldloc.s  5
0x65b9  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x65be  ldstr    aEntityname// "entityname"
0x65c3  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x65c8  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x65cd  call     string [mscorlib]System.String::Concat(string, string, string)
0x65d2  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.FormControlClassId::QuickFormControl
0x65d7  stloc.1
0x65d8  ldloca.s 1
0x65da  constrained. [mscorlib]System.Guid
0x65e0  callvirt instance string [mscorlib]System.Object::ToString()
0x65e5  ldnull
0x65e6  ldarg.0
0x65e7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x65ec  brtrue.s loc_65F1
0x65ee  ldnull
0x65ef  br.s     loc_6601
0x65f1  ldarg.0
0x65f2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x65f7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0x65fc  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x6601  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6606  ldloc.s  6
0x6608  ldtoken  [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ParameterDescriptor
0x660d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6612  callvirt instance class [mscorlib]System.Array [mscorlib]System.Collections.ArrayList::ToArray(class [mscorlib]System.Type)
0x6617  castclass class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ParameterDescriptor[]
0x661c  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor::.ctor(string, string, string, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ParameterDescriptor>)
0x6621  stloc.s  7
0x6623  ldarg.0
0x6624  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor> Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormCollectionControl::_controlDescriptors
0x6629  ldloc.s  7
0x662b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor>::Add(var<u1>)
0x6630  ldc.i4.0
0x6631  stloc.3
0x6632  ldloc.s  4
0x6634  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6639  brtrue   loc_6429
0x663e  leave.s  loc_665F
0x6640  ldloc.s  4
0x6642  isinst   [mscorlib]System.IDisposable
0x6647  stloc.s  0xA
0x6649  ldloc.s  0xA
0x664b  brfalse.s loc_6654
0x664d  ldloc.s  0xA
0x664f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6654  endfinally
0x6655  ldloc.2
0x6656  brfalse.s loc_665E
0x6658  ldloc.2
0x6659  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x665e  endfinally
0x665f  ldarg.0
0x6660  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor> Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormCollectionControl::_controlDescriptors
0x6665  ret
```
