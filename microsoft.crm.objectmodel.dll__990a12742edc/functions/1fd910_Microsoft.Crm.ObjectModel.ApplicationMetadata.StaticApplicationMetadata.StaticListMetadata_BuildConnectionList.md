# Microsoft.Crm.ObjectModel.ApplicationMetadata.StaticApplicationMetadata.StaticListMetadata::BuildConnectionListViewModelTemplate_0

- ea: `0x1fd910`
- end: `0x1fdc90`
- name: `Microsoft.Crm.ObjectModel.ApplicationMetadata.StaticApplicationMetadata.StaticListMetadata::BuildConnectionListViewModelTemplate_0`
- size: `896`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0xab4c0`
- `0x1fd900`

## callees

- `0xbd0a0`
- `0x1fd7d0`
- `0x1fd910`

## string_xrefs

- `0x1fd965`: `FetchXml`
- `0x1fdbac`: `ComboBox`
- `0x1fda62`: `ListItemDescriptor`
- `0x1fd938`: `ListItemViewModelDescriptor`
- `0x1fd9d3`: `CreateFormType`
- `0x1fd99d`: `CreateFormDefinitionId`
- `0x1fdc17`: `record2roleid_readonly`
- `0x1fdc6c`: `record2roleid_readonly`

## pseudocode

```c

```

## disassembly

```asm
0x1fd910  ldstr    aMultilinelist// "MultilineList"
0x1fd915  ldstr    aMultilinelist// "MultilineList"
0x1fd91a  ldarg.0
0x1fd91b  ldc.i4.s 0xD
0x1fd91d  newarr   [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor
0x1fd922  dup
0x1fd923  ldc.i4.0
0x1fd924  ldstr    aPagesize// "PageSize"
0x1fd929  ldc.i4.s 0x19
0x1fd92b  box      [mscorlib]System.Int32
0x1fd930  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0x1fd935  stelem.ref
0x1fd936  dup
0x1fd937  ldc.i4.1
0x1fd938  ldstr    aListitemviewmo// "ListItemViewModelDescriptor"
0x1fd93d  ldarg.3
0x1fd93e  ldloca.s 0
0x1fd940  call     class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor Microsoft.Crm.ObjectModel.ApplicationMetadata.StaticApplicationMetadata.StaticListMetadata::BuildConnectionListItemViewModelTemplate(string roleFilter, [out] string[]& renderedFields)
0x1fd945  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0x1fd94a  stelem.ref
0x1fd94b  dup
0x1fd94c  ldc.i4.2
0x1fd94d  ldstr    aColumnnames// "ColumnNames"
0x1fd952  ldloc.0
0x1fd953  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0x1fd958  stelem.ref
0x1fd959  dup
0x1fd95a  ldc.i4.3
0x1fd95b  ldstr    aActionprovider// "ActionProvider"
0x1fd960  ldstr    aActionprovider// "ActionProvider"
0x1fd965  ldstr    aFetchxml_0// "FetchXml"
0x1fd96a  ldarg.1
0x1fd96b  ldstr    aConnection_0// "Connection"
0x1fd970  ldc.i4.1
0x1fd971  ldarg.s  6
0x1fd973  call     class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Storage.Common.ObjectModel.DescriptorData> Microsoft.Crm.ObjectModel.ConverterUtilities::CreateDescriptorDataFromFetchXml(string fetchXml, string entityName, bool generateSql, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1fd978  ldc.i4.1
0x1fd979  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.QueryDescriptor::.ctor(string, object, bool)
0x1fd97e  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ActionProviderPropertyDescriptor::.ctor(string, string, object)
0x1fd983  stelem.ref
0x1fd984  dup
0x1fd985  ldc.i4.4
0x1fd986  ldstr    aContextfilter// "ContextFilter"
0x1fd98b  ldarg.2
0x1fd98c  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0x1fd991  stelem.ref
0x1fd992  dup
0x1fd993  ldc.i4.5
0x1fd994  ldarg.s  4
0x1fd996  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1fd99b  brtrue.s loc_1FD9AB
0x1fd99d  ldstr    aCreateformdefi// "CreateFormDefinitionId"
0x1fd9a2  ldarg.s  4
0x1fd9a4  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0x1fd9a9  br.s     loc_1FD9AC
0x1fd9ab  ldnull
0x1fd9ac  stelem.ref
0x1fd9ad  dup
0x1fd9ae  ldc.i4.6
0x1fd9af  ldstr    aTargetreferenc// "TargetReference"
0x1fd9b4  ldstr    aRecord2id// "record2id"
0x1fd9b9  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0x1fd9be  stelem.ref
0x1fd9bf  dup
0x1fd9c0  ldc.i4.7
0x1fd9c1  ldstr    aHeadertitlefie// "HeaderTitleField"
0x1fd9c6  ldstr    aName// "name"
0x1fd9cb  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0x1fd9d0  stelem.ref
0x1fd9d1  dup
0x1fd9d2  ldc.i4.8
0x1fd9d3  ldstr    aCreateformtype// "CreateFormType"
0x1fd9d8  ldc.i4.s 0xE
0x1fd9da  box      [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.MetadataType
0x1fd9df  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0x1fd9e4  stelem.ref
0x1fd9e5  dup
0x1fd9e6  ldc.i4.s 9
0x1fd9e8  ldarg.s  4
0x1fd9ea  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1fd9ef  brtrue.s loc_1FD9FF
0x1fd9f1  ldstr    aDefinitionid// "DefinitionId"
0x1fd9f6  ldarg.s  4
0x1fd9f8  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0x1fd9fd  br.s     loc_1FDA00
0x1fd9ff  ldnull
0x1fda00  stelem.ref
0x1fda01  dup
0x1fda02  ldc.i4.s 0xA
0x1fda04  ldarg.s  4
0x1fda06  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1fda0b  brtrue.s loc_1FDA1B
0x1fda0d  ldstr    aSourceid_0// "SourceId"
0x1fda12  ldarg.s  4
0x1fda14  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0x1fda19  br.s     loc_1FDA1C
0x1fda1b  ldnull
0x1fda1c  stelem.ref
0x1fda1d  dup
0x1fda1e  ldc.i4.s 0xB
0x1fda20  ldstr    aCanaddoffline// "CanAddOffline"
0x1fda25  ldc.i4.0
0x1fda26  box      [mscorlib]System.Boolean
0x1fda2b  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0x1fda30  stelem.ref
0x1fda31  dup
0x1fda32  ldc.i4.s 0xC
0x1fda34  ldstr    aDisableheaderl// "DisableHeaderLongPress"
0x1fda39  ldarg.s  5
0x1fda3b  ldc.i4.2
0x1fda3c  ceq
0x1fda3e  box      [mscorlib]System.Boolean
0x1fda43  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0x1fda48  stelem.ref
0x1fda49  ldnull
0x1fda4a  ldnull
0x1fda4b  ldstr    aConnection// "connection"
0x1fda50  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor::.ctor(string, string, string, class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor[], class [Microsoft.Crm.Client.Shared]System.Dictionary, class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor[], string)
0x1fda55  stloc.1
0x1fda56  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.View.ControlViewDescriptor::.ctor()
0x1fda5b  stloc.2
0x1fda5c  ldloc.1
0x1fda5d  ldfld    class [Microsoft.Crm.Client.Shared]System.Dictionary [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor::ControlProperties
0x1fda62  ldstr    aListitemdescri// "ListItemDescriptor"
0x1fda67  ldloc.2
0x1fda68  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1fda6d  ldloc.1
0x1fda6e  ldfld    class [Microsoft.Crm.Client.Shared]System.Dictionary [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor::ControlProperties
0x1fda73  ldstr    aCssclass// "CssClass"
0x1fda78  ldstr    aListpanoramait// "listPanoramaItem"
0x1fda7d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1fda82  ldloc.2
0x1fda83  ldstr    aListitem// "ListItem"
0x1fda88  stfld    string [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.View.ViewDescriptor::TypeName
0x1fda8d  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.View.ControlViewDescriptor::.ctor()
0x1fda92  stloc.3
0x1fda93  ldloc.3
0x1fda94  ldstr    aConnectioncard// "ConnectionCard"
0x1fda99  stfld    string [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.View.ControlViewDescriptor::BindingPath
0x1fda9e  ldloc.3
0x1fda9f  ldstr    aEditmodesectio_0// "EditModeSection"
0x1fdaa4  stfld    string [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.View.ViewDescriptor::TypeName
0x1fdaa9  ldloc.3
0x1fdaaa  ldc.i4.0
0x1fdaab  newarr   [mscorlib]System.Object
0x1fdab0  newobj   instance void [Microsoft.Crm.Client.Shared]System.Dictionary::.ctor(object[])
0x1fdab5  stfld    class [Microsoft.Crm.Client.Shared]System.Dictionary [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.View.ViewDescriptor::ChildControlViewDescriptors
0x1fdaba  ldloc.2
0x1fdabb  ldc.i4.0
0x1fdabc  newarr   [mscorlib]System.Object
0x1fdac1  newobj   instance void [Microsoft.Crm.Client.Shared]System.Dictionary::.ctor(object[])
0x1fdac6  stfld    class [Microsoft.Crm.Client.Shared]System.Dictionary [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.View.ViewDescriptor::ChildControlViewDescriptors
0x1fdacb  ldloc.2
0x1fdacc  ldfld    class [Microsoft.Crm.Client.Shared]System.Dictionary [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.View.ViewDescriptor::ChildControlViewDescriptors
0x1fdad1  ldstr    aSection1// "Section1"
0x1fdad6  ldloc.3
0x1fdad7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1fdadc  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Form.SectionDescriptor::.ctor()
0x1fdae1  stloc.s  4
0x1fdae3  ldloc.s  4
0x1fdae5  ldstr    aConnectioncard// "ConnectionCard"
0x1fdaea  stfld    string [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Form.SectionDescriptor::Name
0x1fdaef  ldloc.s  4
0x1fdaf1  ldstr    aListitemSectio_0// "listItem_section image_enabled"
0x1fdaf6  stfld    string [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Form.SectionDescriptor::BodyCssClass
0x1fdafb  ldloc.s  4
0x1fdafd  ldstr    aFontListSectio// "font_list_sectionlabel"
0x1fdb02  stfld    string [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Form.SectionDescriptor::SectionLabelCssClass
0x1fdb07  ldloc.s  4
0x1fdb09  ldc.i4.0
0x1fdb0a  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Form.LabelAlignmentType>::.ctor(var<u1>)
0x1fdb0f  stfld    valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Form.LabelAlignmentType> [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Form.SectionDescriptor::CellLabelAlignment
0x1fdb14  ldloc.s  4
0x1fdb16  ldc.i4.3
0x1fdb17  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Form.LabelPositionType>::.ctor(var<u1>)
0x1fdb1c  stfld    valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Form.LabelPositionType> [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Form.SectionDescriptor::CellLabelPosition
0x1fdb21  ldloc.3
0x1fdb22  ldloc.s  4
0x1fdb24  call     class [Microsoft.Crm.Client.Shared]System.Dictionary [Microsoft.Crm.Client.Shared]System.Dictionary::GetDictionary(object)
0x1fdb29  stfld    class [Microsoft.Crm.Client.Shared]System.Dictionary [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.View.ViewDescriptor::Properties
0x1fdb2e  call     class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.View.ControlViewDescriptor [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.DescriptorBuilder::CreateUnboundImageControlView()
0x1fdb33  stloc.s  5
0x1fdb35  ldloc.s  5
0x1fdb37  ldfld    class [Microsoft.Crm.Client.Shared]System.Dictionary [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.View.ViewDescriptor::Properties
0x1fdb3c  ldstr    aWidth_0// "Width"
0x1fdb41  ldstr    a67// "67"
0x1fdb46  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1fdb4b  ldloc.3
0x1fdb4c  ldfld    class [Microsoft.Crm.Client.Shared]System.Dictionary [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.View.ViewDescriptor::ChildControlViewDescriptors
0x1fdb51  ldstr    aImage// "image"
0x1fdb56  ldloc.s  5
0x1fdb58  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1fdb5d  ldstr    aLabel// "label"
0x1fdb62  ldstr    aRecord2id// "record2id"
0x1fdb67  call     class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.View.ControlViewDescriptor [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.DescriptorBuilder::CreateControlViewDescriptor(string, string)
0x1fdb6c  stloc.s  6
0x1fdb6e  ldloc.s  6
0x1fdb70  ldfld    class [Microsoft.Crm.Client.Shared]System.Dictionary [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.View.ViewDescriptor::Properties
0x1fdb75  ldstr    aCellvaluecsscl// "CellValueCssClass"
0x1fdb7a  ldstr    aListitemPrimar// "listItem_primary_field"
0x1fdb7f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1fdb84  ldloc.s  6
0x1fdb86  ldfld    class [Microsoft.Crm.Client.Shared]System.Dictionary [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.View.ViewDescriptor::Properties
0x1fdb8b  ldstr    aWidth_0// "Width"
0x1fdb90  ldstr    a196// "196"
0x1fdb95  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1fdb9a  ldloc.3
0x1fdb9b  ldfld    class [Microsoft.Crm.Client.Shared]System.Dictionary [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.View.ViewDescriptor::ChildControlViewDescriptors
0x1fdba0  ldstr    aTitle_0// "title"
0x1fdba5  ldloc.s  6
0x1fdba7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1fdbac  ldstr    aCombobox// "ComboBox"
0x1fdbb1  ldstr    aRecord2roleidE// "record2roleid_edit"
0x1fdbb6  call     class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.View.ControlViewDescriptor [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.DescriptorBuilder::CreateControlViewDescriptor(string, string)
0x1fdbbb  stloc.s  7
0x1fdbbd  ldloc.s  7
0x1fdbbf  ldfld    class [Microsoft.Crm.Client.Shared]System.Dictionary [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.View.ViewDescriptor::Properties
0x1fdbc4  ldstr    aCellvaluecsscl// "CellValueCssClass"
0x1fdbc9  ldstr    aListitemConnec// "listItem_connection_role"
0x1fdbce  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1fdbd3  ldloc.s  7
0x1fdbd5  ldfld    class [Microsoft.Crm.Client.Shared]System.Dictionary [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.View.ViewDescriptor::Properties
0x1fdbda  ldstr    aWidth_0// "Width"
0x1fdbdf  ldstr    a196// "196"
0x1fdbe4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1fdbe9  ldloc.s  7
0x1fdbeb  ldfld    class [Microsoft.Crm.Client.Shared]System.Dictionary [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.View.ViewDescriptor::Properties
0x1fdbf0  ldstr    aIsinlistcontex// "IsInListContext"
0x1fdbf5  ldc.i4.1
0x1fdbf6  box      [mscorlib]System.Boolean
0x1fdbfb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1fdc00  ldloc.3
0x1fdc01  ldfld    class [Microsoft.Crm.Client.Shared]System.Dictionary [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.View.ViewDescriptor::ChildControlViewDescriptors
0x1fdc06  ldstr    aRecord2roleidE// "record2roleid_edit"
0x1fdc0b  ldloc.s  7
0x1fdc0d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1fdc12  ldstr    aLabel// "label"
0x1fdc17  ldstr    aRecord2roleidR// "record2roleid_readonly"
0x1fdc1c  call     class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.View.ControlViewDescriptor [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.DescriptorBuilder::CreateControlViewDescriptor(string, string)
0x1fdc21  stloc.s  8
0x1fdc23  ldloc.s  8
0x1fdc25  ldfld    class [Microsoft.Crm.Client.Shared]System.Dictionary [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.View.ViewDescriptor::Properties
0x1fdc2a  ldstr    aCellvaluecsscl// "CellValueCssClass"
0x1fdc2f  ldstr    aListitemConnec// "listItem_connection_role"
0x1fdc34  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1fdc39  ldloc.s  8
0x1fdc3b  ldfld    class [Microsoft.Crm.Client.Shared]System.Dictionary [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.View.ViewDescriptor::Properties
0x1fdc40  ldstr    aWidth_0// "Width"
0x1fdc45  ldstr    a196// "196"
0x1fdc4a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1fdc4f  ldloc.s  8
0x1fdc51  ldfld    class [Microsoft.Crm.Client.Shared]System.Dictionary [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.View.ViewDescriptor::Properties
0x1fdc56  ldstr    aIsinlistcontex// "IsInListContext"
0x1fdc5b  ldc.i4.1
0x1fdc5c  box      [mscorlib]System.Boolean
0x1fdc61  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1fdc66  ldloc.3
0x1fdc67  ldfld    class [Microsoft.Crm.Client.Shared]System.Dictionary [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.View.ViewDescriptor::ChildControlViewDescriptors
0x1fdc6c  ldstr    aRecord2roleidR// "record2roleid_readonly"
0x1fdc71  ldloc.s  8
0x1fdc73  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1fdc78  ldloc.s  8
0x1fdc7a  ldfld    class [Microsoft.Crm.Client.Shared]System.Dictionary [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.View.ViewDescriptor::Properties
0x1fdc7f  ldstr    aBodycssclass// "BodyCssClass"
0x1fdc84  ldstr    aListitemConnec_0// "listitem_connection_role_control"
0x1fdc89  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1fdc8e  ldloc.1
0x1fdc8f  ret
```
