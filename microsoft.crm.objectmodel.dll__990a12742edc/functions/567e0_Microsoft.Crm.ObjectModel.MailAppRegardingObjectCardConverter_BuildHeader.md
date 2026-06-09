# Microsoft.Crm.ObjectModel.MailAppRegardingObjectCardConverter::BuildHeader

- ea: `0x567e0`
- end: `0x56a86`
- name: `Microsoft.Crm.ObjectModel.MailAppRegardingObjectCardConverter::BuildHeader`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x56690`

## callees

- `0x19b90`
- `0x56600`
- `0x567e0`
- `0x56b10`
- `0xb1320`
- `0xb9cc0`
- `0xb9d60`

## string_xrefs

- `0x567f3`: `PopOutLinkLabelViewModel`
- `0x567f8`: `PopOutLinkLabel`
- `0x5682c`: `PopOutLinkLabelCommandName`
- `0x56834`: `OpenInBrowserCommand`
- `0x5690c`: `ExternalProtocolLinkLabelViewModel`
- `0x56913`: `ExternalProtocolLinkLabel`
- `0x5698d`: `Protocol`
- `0x569ba`: `Protocol`

## pseudocode

```c

```

## disassembly

```asm
0x567e0  ldarg.0
0x567e1  call     instance int32 Microsoft.Crm.ObjectModel.ConverterBase::get_UserLanguageCode()
0x567e6  newobj   instance void [mscorlib]System.Globalization.CultureInfo::.ctor(int32)
0x567eb  stloc.0
0x567ec  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor>::.ctor()
0x567f1  stloc.2
0x567f2  ldloc.2
0x567f3  ldstr    aPopoutlinklabe// "PopOutLinkLabelViewModel"
0x567f8  ldstr    aPopoutlinklabe_0// "PopOutLinkLabel"
0x567fd  ldstr    aPrimaryfieldla// "PrimaryFieldLabel"
0x56802  ldarg.0
0x56803  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.ObjectModel.MailAppRegardingObjectCardConverter::_entityMetadata
0x56808  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryField()
0x5680d  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Name()
0x56812  ldnull
0x56813  ldnull
0x56814  ldc.i4.8
0x56815  newarr   [mscorlib]System.Object
0x5681a  dup
0x5681b  ldc.i4.0
0x5681c  ldstr    aLabelcssclass// "LabelCssClass"
0x56821  stelem.ref
0x56822  dup
0x56823  ldc.i4.1
0x56824  ldstr    aCardHeaderPrim// "card_header_primaryfield"
0x56829  stelem.ref
0x5682a  dup
0x5682b  ldc.i4.2
0x5682c  ldstr    aPopoutlinklabe_1// "PopOutLinkLabelCommandName"
0x56831  stelem.ref
0x56832  dup
0x56833  ldc.i4.3
0x56834  ldstr    aOpeninbrowserc// "OpenInBrowserCommand"
0x56839  stelem.ref
0x5683a  dup
0x5683b  ldc.i4.4
0x5683c  ldstr    aTitle// "Title"
0x56841  stelem.ref
0x56842  dup
0x56843  ldc.i4.5
0x56844  ldarg.0
0x56845  ldarg.0
0x56846  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.ObjectModel.MailAppRegardingObjectCardConverter::_entityMetadata
0x5684b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryField()
0x56850  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Name()
0x56855  call     instance string Microsoft.Crm.ObjectModel.MailAppRegardingObjectCardConverter::GetAttributeDisplayName(string attributeName)
0x5685a  stelem.ref
0x5685b  dup
0x5685c  ldc.i4.6
0x5685d  ldstr    aIsprimaryfield// "IsPrimaryFieldSection"
0x56862  stelem.ref
0x56863  dup
0x56864  ldc.i4.7
0x56865  ldc.i4.1
0x56866  box      [mscorlib]System.Boolean
0x5686b  stelem.ref
0x5686c  newobj   instance void [Microsoft.Crm.Client.Shared]System.Dictionary::.ctor(object[])
0x56871  ldnull
0x56872  call     class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.DescriptorBuilder::CreateControlViewModelDescriptor(string, string, string, string, string, class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor[], class [Microsoft.Crm.Client.Shared]System.Dictionary, string)
0x56877  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor>::Add(var<u1>)
0x5687c  ldloc.2
0x5687d  stloc.1
0x5687e  ldarg.0
0x5687f  call     instance class [System.Core]System.Collections.Generic.HashSet`1<string> Microsoft.Crm.ObjectModel.MailAppRegardingObjectCardConverter::GetFieldNames()
0x56884  callvirt instance valuetype [System.Core]System.Collections.Generic.HashSet`1/Enumerator<var<u1>> class [System.Core]System.Collections.Generic.HashSet`1<string>::GetEnumerator()
0x56889  stloc.3
0x5688a  br       loc_569D2
0x5688f  ldloca.s 3
0x56891  call     instance var<u1> valuetype [System.Core]System.Collections.Generic.HashSet`1/Enumerator<string>::get_Current()
0x56896  stloc.s  4
0x56898  ldloc.s  4
0x5689a  ldarg.0
0x5689b  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.ObjectModel.MailAppRegardingObjectCardConverter::_entityMetadata
0x568a0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryField()
0x568a5  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Name()
0x568aa  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x568af  brfalse  loc_569D2
0x568b4  ldloc.s  4
0x568b6  stloc.s  5
0x568b8  ldarg.0
0x568b9  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.ObjectModel.MailAppRegardingObjectCardConverter::_entityMetadata
0x568be  ldloc.s  4
0x568c0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x568c5  stloc.s  6
0x568c7  ldloc.s  6
0x568c9  brfalse.s loc_568D6
0x568cb  ldloc.s  4
0x568cd  ldloc.s  6
0x568cf  call     string Microsoft.Crm.ObjectModel.AttributeMetadataHelper::GetReadOnlyBindingPath(string bindingPath, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attributeMetadata)
0x568d4  stloc.s  5
0x568d6  ldstr    aLabel_0// "Label"
0x568db  stloc.s  7
0x568dd  ldstr    aLabel// "label"
0x568e2  stloc.s  8
0x568e4  ldloc.s  6
0x568e6  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Format()
0x568eb  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StringAttributeFormats::get_Phone()
0x568f0  ldc.i4.5
0x568f1  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x568f6  brfalse.s loc_5690C
0x568f8  ldloc.s  6
0x568fa  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Format()
0x568ff  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StringAttributeFormats::get_Email()
0x56904  ldc.i4.5
0x56905  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x5690a  brtrue.s loc_5691A
0x5690c  ldstr    aExternalprotoc// "ExternalProtocolLinkLabelViewModel"
0x56911  stloc.s  7
0x56913  ldstr    aExternalprotoc_0// "ExternalProtocolLinkLabel"
0x56918  stloc.s  8
0x5691a  ldloc.s  7
0x5691c  ldloc.s  8
0x5691e  ldloc.s  4
0x56920  ldloc.s  5
0x56922  ldnull
0x56923  ldc.i4.1
0x56924  newarr   [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor
0x56929  dup
0x5692a  ldc.i4.0
0x5692b  ldstr    aLabel_0// "Label"
0x56930  ldarg.0
0x56931  ldloc.s  4
0x56933  call     instance string Microsoft.Crm.ObjectModel.MailAppRegardingObjectCardConverter::GetAttributeDisplayName(string attributeName)
0x56938  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0x5693d  stelem.ref
0x5693e  ldc.i4.4
0x5693f  newarr   [mscorlib]System.Object
0x56944  dup
0x56945  ldc.i4.0
0x56946  ldstr    aLabelcssclass// "LabelCssClass"
0x5694b  stelem.ref
0x5694c  dup
0x5694d  ldc.i4.1
0x5694e  ldstr    aCardFieldValue// "card_field_value"
0x56953  stelem.ref
0x56954  dup
0x56955  ldc.i4.2
0x56956  ldstr    aShowlabel// "ShowLabel"
0x5695b  stelem.ref
0x5695c  dup
0x5695d  ldc.i4.3
0x5695e  ldc.i4.1
0x5695f  box      [mscorlib]System.Boolean
0x56964  stelem.ref
0x56965  newobj   instance void [Microsoft.Crm.Client.Shared]System.Dictionary::.ctor(object[])
0x5696a  ldnull
0x5696b  call     class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.DescriptorBuilder::CreateControlViewModelDescriptor(string, string, string, string, string, class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor[], class [Microsoft.Crm.Client.Shared]System.Dictionary, string)
0x56970  stloc.s  9
0x56972  ldloc.s  6
0x56974  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Format()
0x56979  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StringAttributeFormats::get_Phone()
0x5697e  ldc.i4.5
0x5697f  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x56984  brtrue.s loc_5699F
0x56986  ldloc.s  9
0x56988  ldfld    class [Microsoft.Crm.Client.Shared]System.Dictionary [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor::ControlProperties
0x5698d  ldstr    aProtocol// "Protocol"
0x56992  ldc.i4.1
0x56993  box      Microsoft.Crm.ObjectModel.ExternalProtocol
0x56998  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x5699d  br.s     loc_569CA
0x5699f  ldloc.s  6
0x569a1  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Format()
0x569a6  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StringAttributeFormats::get_Email()
0x569ab  ldc.i4.5
0x569ac  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x569b1  brtrue.s loc_569CA
0x569b3  ldloc.s  9
0x569b5  ldfld    class [Microsoft.Crm.Client.Shared]System.Dictionary [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor::ControlProperties
0x569ba  ldstr    aProtocol// "Protocol"
0x569bf  ldc.i4.0
0x569c0  box      Microsoft.Crm.ObjectModel.ExternalProtocol
0x569c5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x569ca  ldloc.1
0x569cb  ldloc.s  9
0x569cd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor>::Add(var<u1>)
0x569d2  ldloca.s 3
0x569d4  call     instance bool valuetype [System.Core]System.Collections.Generic.HashSet`1/Enumerator<string>::MoveNext()
0x569d9  brtrue   loc_5688F
0x569de  leave.s  loc_569EE
0x569e0  ldloca.s 3
0x569e2  constrained. valuetype [System.Core]System.Collections.Generic.HashSet`1/Enumerator<string>
0x569e8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x569ed  endfinally
0x569ee  ldstr    aSection// "Section"
0x569f3  ldstr    aSection// "Section"
0x569f8  ldstr    aCardFields// "card_fields"
0x569fd  ldc.i4.2
0x569fe  newarr   [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor
0x56a03  dup
0x56a04  ldc.i4.0
0x56a05  ldstr    aShowlabel// "ShowLabel"
0x56a0a  ldc.i4.1
0x56a0b  box      [mscorlib]System.Boolean
0x56a10  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0x56a15  stelem.ref
0x56a16  dup
0x56a17  ldc.i4.1
0x56a18  ldstr    aLabel_0// "Label"
0x56a1d  ldstr    aMocaOwaRegardi// "MoCA_OWA_RegardingObject_Card_Title"
0x56a22  ldloc.0
0x56a23  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [mscorlib]System.Globalization.CultureInfo culture)
0x56a28  ldarg.0
0x56a29  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.ObjectModel.MailAppRegardingObjectCardConverter::_entityMetadata
0x56a2e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedName()
0x56a33  ldarg.0
0x56a34  call     instance int32 Microsoft.Crm.ObjectModel.ConverterBase::get_UserLanguageCode()
0x56a39  ldarg.0
0x56a3a  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.ConverterBase::get_Context()
0x56a3f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::TryGetDescription(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x56a44  call     string [mscorlib]System.String::Format(string, object)
0x56a49  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0x56a4e  stelem.ref
0x56a4f  ldc.i4.2
0x56a50  newarr   [mscorlib]System.Object
0x56a55  dup
0x56a56  ldc.i4.0
0x56a57  ldstr    aBodycssclass// "BodyCssClass"
0x56a5c  stelem.ref
0x56a5d  dup
0x56a5e  ldc.i4.1
0x56a5f  ldstr    aRecordCardCont// "record_card_content "
0x56a64  ldarg.0
0x56a65  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.ObjectModel.MailAppRegardingObjectCardConverter::_entityMetadata
0x56a6a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x56a6f  call     string [mscorlib]System.String::Concat(string, string)
0x56a74  stelem.ref
0x56a75  newobj   instance void [Microsoft.Crm.Client.Shared]System.Dictionary::.ctor(object[])
0x56a7a  ldloc.1
0x56a7b  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor>::ToArray()
0x56a80  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor::.ctor(string, string, string, class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor[], class [Microsoft.Crm.Client.Shared]System.Dictionary, class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor[])
0x56a85  ret
```
