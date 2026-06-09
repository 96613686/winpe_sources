# Microsoft.Crm.ObjectModel.InteractionCentricTabConverter::CreateFormCells_0

- ea: `0xa3ed0`
- end: `0xa4c5a`
- name: `Microsoft.Crm.ObjectModel.InteractionCentricTabConverter::CreateFormCells_0`
- size: `3466`
- prototype: ``
- caller_count: `3`
- callee_count: `30`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0xa2e40`
- `0xa2fc0`
- `0xa3e60`

## callees

- `0x9b2a0`
- `0x9c1a0`
- `0x9db70`
- `0xa3e80`
- `0xa3ed0`
- `0xa4c60`
- `0xa4dd0`
- `0xa4ef0`
- `0xa55e0`
- `0xa5600`
- `0xa7070`
- `0xa7090`
- `0xa70b0`
- `0xa70d0`
- `0xa7100`
- `0xa82f0`
- `0xa9b40`
- `0xb24d0`
- `0xb24f0`
- `0xb2570`
- `0xb2590`
- `0xb2620`
- `0xb2640`
- `0xb2660`
- `0xb2680`
- `0xb9cc0`
- `0xb9ce0`
- `0xb9d00`
- `0xb9f90`
- `0xb9ff0`

## string_xrefs

- `0xa3f41`: `classid`
- `0xa4aea`: `_readonly`
- `0xa4afa`: `_readonly`
- `0xa4b29`: `_readonly`
- `0xa40cd`: `ComponentSwitcherViewModel`
- `0xa4186`: `ComponentSwitcherViewModel`
- `0xa40d2`: `ComponentSwitcher`
- `0xa40d7`: `ComponentSwitcher`
- `0xa418b`: `ComponentSwitcher`
- `0xa4190`: `ComponentSwitcher`

## pseudocode

```c

```

## disassembly

```asm
0xa3ed0  newobj   instance void class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor>::.ctor()
0xa3ed5  stloc.0
0xa3ed6  ldc.i4.s 0x12
0xa3ed8  ldstr    aGridcell// "GridCell"
0xa3edd  ldstr    aGridcell// "GridCell"
0xa3ee2  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ClientApiDescriptor::.ctor(valuetype [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ClientApiControlType, string, string)
0xa3ee7  stloc.1
0xa3ee8  ldc.i4.0
0xa3ee9  stloc.2
0xa3eea  br       loc_A4C4B
0xa3eef  ldnull
0xa3ef0  stloc.3
0xa3ef1  ldarg.1
0xa3ef2  callvirt instance class Microsoft.Crm.ObjectModel.FormXmlNode[] Microsoft.Crm.ObjectModel.FormXmlNode::get_Children()
0xa3ef7  brfalse.s loc_A3F07
0xa3ef9  ldarg.1
0xa3efa  callvirt instance class Microsoft.Crm.ObjectModel.FormXmlNode[] Microsoft.Crm.ObjectModel.FormXmlNode::get_Children()
0xa3eff  ldloc.2
0xa3f00  ldelem.ref
0xa3f01  castclass Microsoft.Crm.ObjectModel.FormXmlLeafNode
0xa3f06  stloc.3
0xa3f07  ldloc.3
0xa3f08  brtrue.s loc_A3F11
0xa3f0a  ldarg.s  9
0xa3f0c  brfalse  loc_A4C47
0xa3f11  ldc.i4.s 0x3D
0xa3f13  stloc.s  4
0xa3f15  ldsfld   string [mscorlib]System.String::Empty
0xa3f1a  stloc.s  5
0xa3f1c  ldarg.s  4
0xa3f1e  ldloc.2
0xa3f1f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0xa3f24  ldstr    aControl// "control"
0xa3f29  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xa3f2e  stloc.s  6
0xa3f30  ldloc.s  6
0xa3f32  brfalse.s loc_A3F89
0xa3f34  ldarg.0
0xa3f35  call     instance class Microsoft.Crm.ObjectModel.ControlCreator Microsoft.Crm.ObjectModel.TabConverter::get_ControlCreatorInstance()
0xa3f3a  ldloc.s  6
0xa3f3c  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa3f41  ldstr    aClassid// "classid"
0xa3f46  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xa3f4b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xa3f50  callvirt instance valuetype Microsoft.Crm.ObjectModel.ControlType Microsoft.Crm.ObjectModel.ControlCreator::GetControlType(string classId)
0xa3f55  stloc.s  4
0xa3f57  ldloc.s  6
0xa3f59  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa3f5e  ldstr    aDatafieldname// "datafieldname"
0xa3f63  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xa3f68  brtrue.s loc_A3F71
0xa3f6a  ldsfld   string [mscorlib]System.String::Empty
0xa3f6f  br.s     loc_A3F87
0xa3f71  ldloc.s  6
0xa3f73  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa3f78  ldstr    aDatafieldname// "datafieldname"
0xa3f7d  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xa3f82  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xa3f87  stloc.s  5
0xa3f89  ldc.i4.0
0xa3f8a  stloc.s  7
0xa3f8c  ldloc.s  4
0xa3f8e  ldc.i4.s 0x2E
0xa3f90  bne.un.s loc_A3FA8
0xa3f92  ldloc.s  6
0xa3f94  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa3f99  ldstr    aIndicationofsu// "indicationOfSubgrid"
0xa3f9e  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xa3fa3  brfalse.s loc_A3FA8
0xa3fa5  ldc.i4.1
0xa3fa6  stloc.s  7
0xa3fa8  newobj   instance void class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor>::.ctor()
0xa3fad  stloc.s  8
0xa3faf  newobj   instance void class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor>::.ctor()
0xa3fb4  stloc.s  9
0xa3fb6  ldc.i4.0
0xa3fb7  newarr   [mscorlib]System.Object
0xa3fbc  newobj   instance void [Microsoft.Crm.Client.Shared]System.Dictionary::.ctor(object[])
0xa3fc1  stloc.s  0xA
0xa3fc3  ldloc.s  4
0xa3fc5  ldc.i4.s 0x14
0xa3fc7  bne.un   loc_A41CF
0xa3fcc  ldnull
0xa3fcd  stloc.s  0xB
0xa3fcf  ldloc.s  6
0xa3fd1  ldstr    aParametersDisp_3// "parameters/DisplayAsCustomer360Tile"
0xa3fd6  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xa3fdb  stloc.s  0xC
0xa3fdd  ldloc.s  0xC
0xa3fdf  brfalse  loc_A4106
0xa3fe4  ldloc.s  0xC
0xa3fe6  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0xa3feb  ldstr    aTrue// "true"
0xa3ff0  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa3ff5  brfalse  loc_A4106
0xa3ffa  ldarg.0
0xa3ffb  ldc.i4.1
0xa3ffc  stfld    bool Microsoft.Crm.ObjectModel.InteractionCentricTabConverter::isInteractionCentricCommunicationCardPresent
0xa4001  ldarg.0
0xa4002  ldc.i4.1
0xa4003  stfld    bool Microsoft.Crm.ObjectModel.InteractionCentricTabConverter::isInteractionCentricCommunicationCardRow
0xa4008  ldc.i4.6
0xa4009  stloc.s  0xD
0xa400b  ldc.i4.2
0xa400c  stloc.s  0xE
0xa400e  ldloc.s  0xE
0xa4010  ldc.i4.s 0x64
0xa4012  mul
0xa4013  ldarg.s  7
0xa4015  div
0xa4016  stloc.s  0xF
0xa4018  ldloc.s  0xD
0xa401a  ldc.i4.s 0x18
0xa401c  mul
0xa401d  stloc.s  0x10
0xa401f  ldloc.s  9
0xa4021  ldstr    aRowspan_0// "RowSpan"
0xa4026  ldloc.s  0xD
0xa4028  box      [mscorlib]System.Int32
0xa402d  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0xa4032  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor>::Add(var<u1>)
0xa4037  ldloc.s  9
0xa4039  ldstr    aColspan_0// "ColSpan"
0xa403e  ldloc.s  0xE
0xa4040  box      [mscorlib]System.Int32
0xa4045  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0xa404a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor>::Add(var<u1>)
0xa404f  ldloc.s  9
0xa4051  ldstr    aWidthpercent// "WidthPercent"
0xa4056  ldloc.s  0xF
0xa4058  box      [mscorlib]System.Int32
0xa405d  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0xa4062  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor>::Add(var<u1>)
0xa4067  ldloc.s  9
0xa4069  ldstr    aCellheight// "CellHeight"
0xa406e  ldloc.s  0x10
0xa4070  box      [mscorlib]System.Int32
0xa4075  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0xa407a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor>::Add(var<u1>)
0xa407f  ldloc.s  9
0xa4081  ldstr    aIsqueuecontain// "IsQueueContainer"
0xa4086  ldc.i4.1
0xa4087  box      [mscorlib]System.Boolean
0xa408c  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0xa4091  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor>::Add(var<u1>)
0xa4096  ldloc.s  6
0xa4098  call     class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`3<string, string, valuetype [mscorlib]System.Guid>> Microsoft.Crm.ObjectModel.InteractionCentricTabConverter::ExtractQuickFormIds(class [System.Xml]System.Xml.XmlNode controlNode)
0xa409d  stloc.s  0x11
0xa409f  ldloc.s  0x11
0xa40a1  ldc.i4.0
0xa40a2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`3<string, string, valuetype [mscorlib]System.Guid>>::get_Item(!!T0)
0xa40a7  callvirt instance var<u1> class [mscorlib]System.Tuple`3<string, string, valuetype [mscorlib]System.Guid>::get_Item1()
0xa40ac  stloc.s  0x12
0xa40ae  ldarg.s  5
0xa40b0  ldloc.s  0x12
0xa40b2  callvirt instance bool class [mscorlib]System.Collections.Generic.ICollection`1<string>::Contains(var<u1>)
0xa40b7  brtrue.s loc_A40C2
0xa40b9  ldarg.s  5
0xa40bb  ldloc.s  0x12
0xa40bd  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0xa40c2  ldarg.0
0xa40c3  ldloc.s  0x11
0xa40c5  ldarg.3
0xa40c6  call     instance class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor> Microsoft.Crm.ObjectModel.InteractionCentricTabConverter::GetCommunicationCardDescriptors(class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`3<string, string, valuetype [mscorlib]System.Guid>> formIdFieldNamePairs, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata)
0xa40cb  stloc.s  0x13
0xa40cd  ldstr    aComponentswitc// "ComponentSwitcherViewModel"
0xa40d2  ldstr    aComponentswitc_0// "ComponentSwitcher"
0xa40d7  ldstr    aComponentswitc_0// "ComponentSwitcher"
0xa40dc  ldc.i4.1
0xa40dd  newarr   [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor
0xa40e2  dup
0xa40e3  ldc.i4.0
0xa40e4  ldstr    aDatafield// "DataField"
0xa40e9  ldloc.s  0x12
0xa40eb  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ReferencePropertyDescriptor::.ctor(string, string)
0xa40f0  stelem.ref
0xa40f1  ldnull
0xa40f2  ldloc.s  0x13
0xa40f4  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor>::ToArray()
0xa40f9  ldnull
0xa40fa  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor::.ctor(string, string, string, class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor[], class [Microsoft.Crm.Client.Shared]System.Dictionary, class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor[], string)
0xa40ff  stloc.s  0xB
0xa4101  br       loc_A41BA
0xa4106  ldarg.0
0xa4107  call     instance int32 Microsoft.Crm.ObjectModel.ConverterBase::get_UserLanguageCode()
0xa410c  ldarg.0
0xa410d  call     instance int32 Microsoft.Crm.ObjectModel.ConverterBase::get_FallbackLanguageCode()
0xa4112  ldarg.0
0xa4113  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.ObjectModel.TabConverter::fieldNameOccurrenceMap
0xa4118  ldarg.0
0xa4119  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.TabConverter::get_Context()
0xa411e  ldarg.0
0xa411f  call     instance class Microsoft.Crm.ObjectModel.FormConversionContext Microsoft.Crm.ObjectModel.TabConverter::get_FormConversionContext()
0xa4124  ldarg.0
0xa4125  call     instance bool Microsoft.Crm.ObjectModel.TabConverter::get_IsRefreshForm()
0xa412a  ldarg.0
0xa412b  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string[]> Microsoft.Crm.ObjectModel.TabConverter::get_CompositeControlConstituentFields()
0xa4130  ldarg.0
0xa4131  call     instance valuetype [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.FormFactor Microsoft.Crm.ObjectModel.ConverterBase::get_FormFactor()
0xa4136  newobj   instance void Microsoft.Crm.ObjectModel.QuickViewFormConverter::.ctor(int32 currentUserLanguageId, int32 orgLanguageId, class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> occurrenceMap, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class Microsoft.Crm.ObjectModel.FormConversionContext formConversionContext, bool isRefreshForm, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string[]> compositeControlConstituentFields, valuetype [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.FormFactor formFactor)
0xa413b  dup
0xa413c  ldarg.0
0xa413d  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.Crm.ObjectModel.TabConverter::savedQueryIds
0xa4142  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.Crm.ObjectModel.TabConverter::savedQueryIds
0xa4147  ldloc.s  6
0xa4149  call     string Microsoft.Crm.ObjectModel.InteractionCentricTabConverter::ExtractDataFieldName(class [System.Xml]System.Xml.XmlNode controlNode)
0xa414e  stloc.s  0x14
0xa4150  ldarg.s  5
0xa4152  ldloc.s  0x14
0xa4154  callvirt instance bool class [mscorlib]System.Collections.Generic.ICollection`1<string>::Contains(var<u1>)
0xa4159  brtrue.s loc_A4164
0xa415b  ldarg.s  5
0xa415d  ldloc.s  0x14
0xa415f  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0xa4164  ldloc.s  9
0xa4166  ldstr    aIsquickviewfor// "IsQuickViewForm"
0xa416b  ldc.i4.1
0xa416c  box      [mscorlib]System.Boolean
0xa4171  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0xa4176  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor>::Add(var<u1>)
0xa417b  ldloc.s  6
0xa417d  ldarg.s  0xA
0xa417f  callvirt instance class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor> Microsoft.Crm.ObjectModel.QuickViewFormConverter::createFormQuickForm(class [System.Xml]System.Xml.XmlNode ctrl, string parentTabName)
0xa4184  stloc.s  0x15
0xa4186  ldstr    aComponentswitc// "ComponentSwitcherViewModel"
0xa418b  ldstr    aComponentswitc_0// "ComponentSwitcher"
0xa4190  ldstr    aComponentswitc_0// "ComponentSwitcher"
0xa4195  ldc.i4.1
0xa4196  newarr   [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor
0xa419b  dup
0xa419c  ldc.i4.0
0xa419d  ldstr    aDatafield// "DataField"
0xa41a2  ldloc.s  0x14
0xa41a4  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ReferencePropertyDescriptor::.ctor(string, string)
0xa41a9  stelem.ref
0xa41aa  ldnull
0xa41ab  ldloc.s  0x15
0xa41ad  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor>::ToArray()
0xa41b2  ldnull
0xa41b3  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor::.ctor(string, string, string, class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor[], class [Microsoft.Crm.Client.Shared]System.Dictionary, class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor[], string)
0xa41b8  stloc.s  0xB
0xa41ba  ldloc.s  0xB
0xa41bc  brfalse  loc_A47C0
0xa41c1  ldloc.s  8
0xa41c3  ldloc.s  0xB
0xa41c5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor>::Add(var<u1>)
0xa41ca  br       loc_A47C0
0xa41cf  ldloc.s  4
0xa41d1  ldc.i4.s 0x2F
0xa41d3  bne.un   loc_A42AC
0xa41d8  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor>::.ctor()
0xa41dd  stloc.s  0x16
0xa41df  newobj   instance void Microsoft.Crm.ObjectModel.InteractionWallControlConverter::.ctor()
0xa41e4  ldstr    aInteractionwal_3// "InteractionWallViewModel"
0xa41e9  ldstr    aInteractionwal_2// "InteractionWallControl"
0xa41ee  ldstr    aInteractionwal_4// "InteractionWall"
0xa41f3  ldloc.s  0x16
0xa41f5  ldarg.3
0xa41f6  ldarg.0
0xa41f7  call     instance int32 Microsoft.Crm.ObjectModel.ConverterBase::get_UserLanguageCode()
0xa41fc  ldarg.0
0xa41fd  call     instance int32 Microsoft.Crm.ObjectModel.ConverterBase::get_FallbackLanguageCode()
0xa4202  ldarg.0
0xa4203  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.TabConverter::get_Context()
0xa4208  callvirt instance class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor Microsoft.Crm.ObjectModel.ControlConverterBase::GetViewModelDescriptor(string editViewModelName, string editName, string id, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor> parameters, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata, int32 userLanguageCode, int32 fallbackLanguageCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xa420d  stloc.s  0x17
0xa420f  ldc.i4.s 0x19
0xa4211  stloc.s  0x18
0xa4213  ldc.i4.2
0xa4214  stloc.s  0x19
0xa4216  ldloc.s  0x19
0xa4218  ldc.i4.s 0x64
0xa421a  mul
0xa421b  ldarg.s  7
0xa421d  div
0xa421e  stloc.s  0x1A
0xa4220  ldloc.s  0x18
0xa4222  ldc.i4.s 0x18
0xa4224  mul
0xa4225  stloc.s  0x1B
0xa4227  ldloc.s  9
0xa4229  ldstr    aRowspan_0// "RowSpan"
0xa422e  ldloc.s  0x18
0xa4230  box      [mscorlib]System.Int32
0xa4235  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0xa423a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor>::Add(var<u1>)
0xa423f  ldloc.s  9
0xa4241  ldstr    aColspan_0// "ColSpan"
0xa4246  ldloc.s  0x19
0xa4248  box      [mscorlib]System.Int32
0xa424d  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0xa4252  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor>::Add(var<u1>)
0xa4257  ldloc.s  9
0xa4259  ldstr    aWidthpercent// "WidthPercent"
0xa425e  ldloc.s  0x1A
0xa4260  box      [mscorlib]System.Int32
0xa4265  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0xa426a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor>::Add(var<u1>)
0xa426f  ldloc.s  9
0xa4271  ldstr    aCellheight// "CellHeight"
  ... truncated ...
```
