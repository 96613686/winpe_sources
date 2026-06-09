# Microsoft.Crm.ObjectModel.InteractionCentricTabConverter::CreateReferencePanelViewModelDescriptors

- ea: `0xa4f40`
- end: `0xa55c5`
- name: `Microsoft.Crm.ObjectModel.InteractionCentricTabConverter::CreateReferencePanelViewModelDescriptors`
- size: `1669`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callees

- `0xa4f40`
- `0xa7070`
- `0xb36a0`
- `0xb3a90`
- `0xb57e0`
- `0xb58c0`
- `0xb58d0`
- `0xb5910`
- `0xb5920`
- `0xb5950`
- `0xb5990`
- `0xb59d0`
- `0xb5a20`
- `0xb5a40`
- `0xb9d00`

## string_xrefs

- `0xa538a`: `FetchXml`
- `0xa553d`: `FetchXml`
- `0xa5353`: `SelectListItemCommandName`
- `0xa5506`: `SelectListItemCommandName`
- `0xa4f40`: `<fetch version="1.0" output-format="xml-platform" mapping="logical" distinct="false"><entity name="incident"><order attribute="statecode" descending="true" /><order attribute="prioritycode" descending="false" /><filter type="and"><condition attribute="createdon" operator="last-x-months" value="12" /></filter><attribute name="statecode" /><attribute name="createdon" /><attribute name="prioritycode" /><attribute name="title" /><attribute name="incidentid" /><attribute name="caseorigincode" /><attr`
- `0xa4f4c`: `<grid name="resultset" object="112" jump="title" select="1" preview="1" icon="1"><row name="result" id="incidentid"><cell name="title" width="150" /><cell name="ticketnumber" width="150" /><cell name="prioritycode" width="100" /><cell name="caseorigincode" width="100" /><cell name="customerid" width="150" /><cell name="ownerid" width="150" /><cell name="statecode" width="100" /><cell name="statuscode" width="150" /><cell name="createdon" width="100" /></row></grid>`
- `0xa50b9`: `ListItemDescriptor`
- `0xa50f7`: `ListItemDescriptor`
- `0xa52b4`: `ListItemViewModelDescriptor`
- `0xa5452`: `ListItemViewModelDescriptor`

## pseudocode

```c

```

## disassembly

```asm
0xa4f40  ldstr    aFetchVersion10_0// "<fetch version=\"1.0\" output-format=\""...
0xa4f45  stloc.0
0xa4f46  ldstr    aFetchVersion10_1// "<fetch version=\"1.0\" mapping=\"logica"...
0xa4f4b  stloc.1
0xa4f4c  ldstr    aGridNameResult// "<grid name=\"resultset\" object=\"112\""...
0xa4f51  stloc.2
0xa4f52  ldstr    aGridNameResult_0// "<grid name=\"resultset\" object=\"9930"...
0xa4f57  stloc.3
0xa4f58  ldnull
0xa4f59  ldc.i4   0x409
0xa4f5e  ldc.i4   0x409
0xa4f63  newobj   instance void Microsoft.Crm.ObjectModel.SavedQueryWrapper::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity savedQuery, int32 currentUserLanguageId, int32 orgLanguageId)
0xa4f68  dup
0xa4f69  ldstr    aEbd1d24aEea7E2// "ebd1d24a-eea7-e211-9fb6-00155dd0ea05"
0xa4f6e  callvirt instance void Microsoft.Crm.ObjectModel.ListQueryWrapper::set_QueryId(string value)
0xa4f73  dup
0xa4f74  ldc.i4.0
0xa4f75  callvirt instance void Microsoft.Crm.ObjectModel.ListQueryWrapper::set_IsDefault(bool value)
0xa4f7a  dup
0xa4f7b  ldc.i4.s 0x70
0xa4f7d  callvirt instance void Microsoft.Crm.ObjectModel.ListQueryWrapper::set_AssociatedEntityType(int32 value)
0xa4f82  dup
0xa4f83  ldstr    aRecentCases// "Recent Cases"
0xa4f88  callvirt instance void Microsoft.Crm.ObjectModel.ListQueryWrapper::set_ViewName(string value)
0xa4f8d  dup
0xa4f8e  ldloc.0
0xa4f8f  callvirt instance void Microsoft.Crm.ObjectModel.ListQueryWrapper::set_FetchXml(string value)
0xa4f94  dup
0xa4f95  ldloc.2
0xa4f96  callvirt instance void Microsoft.Crm.ObjectModel.ListQueryWrapper::set_LayoutXml(string value)
0xa4f9b  dup
0xa4f9c  ldc.i4.0
0xa4f9d  callvirt instance void Microsoft.Crm.ObjectModel.ListQueryWrapper::set_QueryType(int32 value)
0xa4fa2  stloc.s  4
0xa4fa4  ldnull
0xa4fa5  ldc.i4   0x409
0xa4faa  ldc.i4   0x409
0xa4faf  newobj   instance void Microsoft.Crm.ObjectModel.SavedQueryWrapper::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity savedQuery, int32 currentUserLanguageId, int32 orgLanguageId)
0xa4fb4  dup
0xa4fb5  ldstr    a9deaed8b13b545// "9deaed8b-13b5-457f-8ae2-dd00a7c53115"
0xa4fba  callvirt instance void Microsoft.Crm.ObjectModel.ListQueryWrapper::set_QueryId(string value)
0xa4fbf  dup
0xa4fc0  ldc.i4.0
0xa4fc1  callvirt instance void Microsoft.Crm.ObjectModel.ListQueryWrapper::set_IsDefault(bool value)
0xa4fc6  dup
0xa4fc7  ldc.i4   0x26CA
0xa4fcc  callvirt instance void Microsoft.Crm.ObjectModel.ListQueryWrapper::set_AssociatedEntityType(int32 value)
0xa4fd1  dup
0xa4fd2  ldstr    aAllKnowledgeBa// "All knowledge base (KB) articles"
0xa4fd7  callvirt instance void Microsoft.Crm.ObjectModel.ListQueryWrapper::set_ViewName(string value)
0xa4fdc  dup
0xa4fdd  ldloc.1
0xa4fde  callvirt instance void Microsoft.Crm.ObjectModel.ListQueryWrapper::set_FetchXml(string value)
0xa4fe3  dup
0xa4fe4  ldloc.3
0xa4fe5  callvirt instance void Microsoft.Crm.ObjectModel.ListQueryWrapper::set_LayoutXml(string value)
0xa4fea  dup
0xa4feb  ldc.i4.0
0xa4fec  callvirt instance void Microsoft.Crm.ObjectModel.ListQueryWrapper::set_QueryType(int32 value)
0xa4ff1  stloc.s  5
0xa4ff3  ldc.i4   0x409
0xa4ff8  newobj   instance void [mscorlib]System.Globalization.CultureInfo::.ctor(int32)
0xa4ffd  stloc.s  8
0xa4fff  ldloc.s  4
0xa5001  ldloc.s  8
0xa5003  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0xa5008  ldloc.s  4
0xa500a  callvirt instance string Microsoft.Crm.ObjectModel.ListQueryWrapper::get_ViewName()
0xa500f  ldloc.s  8
0xa5011  callvirt instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0xa5016  callvirt instance string [mscorlib]System.Globalization.TextInfo::ToTitleCase(string)
0xa501b  callvirt instance void Microsoft.Crm.ObjectModel.ListQueryWrapper::set_ViewName(string value)
0xa5020  ldloc.s  5
0xa5022  ldloc.s  8
0xa5024  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0xa5029  ldloc.s  5
0xa502b  callvirt instance string Microsoft.Crm.ObjectModel.ListQueryWrapper::get_ViewName()
0xa5030  ldloc.s  8
0xa5032  callvirt instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0xa5037  callvirt instance string [mscorlib]System.Globalization.TextInfo::ToTitleCase(string)
0xa503c  callvirt instance void Microsoft.Crm.ObjectModel.ListQueryWrapper::set_ViewName(string value)
0xa5041  ldarg.0
0xa5042  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.TabConverter::get_Context()
0xa5047  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_MetadataCache()
0xa504c  ldloc.s  4
0xa504e  callvirt instance int32 Microsoft.Crm.ObjectModel.ListQueryWrapper::get_AssociatedEntityType()
0xa5053  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(int32)
0xa5058  stloc.s  9
0xa505a  ldarg.0
0xa505b  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.TabConverter::get_Context()
0xa5060  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_MetadataCache()
0xa5065  ldloc.s  5
0xa5067  callvirt instance int32 Microsoft.Crm.ObjectModel.ListQueryWrapper::get_AssociatedEntityType()
0xa506c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(int32)
0xa5071  stloc.s  0xA
0xa5073  ldloc.s  9
0xa5075  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xa507a  ldstr    aActivitypointe_1// "activitypointer"
0xa507f  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa5084  stloc.s  0xB
0xa5086  ldloc.s  0xA
0xa5088  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xa508d  ldstr    aActivitypointe_1// "activitypointer"
0xa5092  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa5097  stloc.s  0xC
0xa5099  ldc.i4.0
0xa509a  newarr   [mscorlib]System.Object
0xa509f  newobj   instance void [Microsoft.Crm.Client.Shared]System.Dictionary::.ctor(object[])
0xa50a4  stloc.s  0xD
0xa50a6  ldloc.s  0xD
0xa50a8  ldstr    aScrolldirectio// "ScrollDirection"
0xa50ad  ldstr    aVertical// "Vertical"
0xa50b2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xa50b7  ldloc.s  0xD
0xa50b9  ldstr    aListitemdescri// "ListItemDescriptor"
0xa50be  ldloc.s  4
0xa50c0  ldarg.0
0xa50c1  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.TabConverter::get_Context()
0xa50c6  ldarg.0
0xa50c7  call     instance valuetype [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.FormFactor Microsoft.Crm.ObjectModel.ConverterBase::get_FormFactor()
0xa50cc  ldc.i4.0
0xa50cd  call     class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.View.ControlViewDescriptor Microsoft.Crm.ObjectModel.ListItemBuilder::BuildListItemView(class Microsoft.Crm.ObjectModel.ListQueryWrapper listQuery, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, valuetype [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.FormFactor formFactor, valuetype [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.MetadataType metaDataType)
0xa50d2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xa50d7  ldc.i4.0
0xa50d8  newarr   [mscorlib]System.Object
0xa50dd  newobj   instance void [Microsoft.Crm.Client.Shared]System.Dictionary::.ctor(object[])
0xa50e2  stloc.s  0xE
0xa50e4  ldloc.s  0xE
0xa50e6  ldstr    aScrolldirectio// "ScrollDirection"
0xa50eb  ldstr    aVertical// "Vertical"
0xa50f0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xa50f5  ldloc.s  0xE
0xa50f7  ldstr    aListitemdescri// "ListItemDescriptor"
0xa50fc  ldloc.s  5
0xa50fe  ldarg.0
0xa50ff  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.TabConverter::get_Context()
0xa5104  ldarg.0
0xa5105  call     instance valuetype [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.FormFactor Microsoft.Crm.ObjectModel.ConverterBase::get_FormFactor()
0xa510a  ldc.i4.0
0xa510b  call     class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.View.ControlViewDescriptor Microsoft.Crm.ObjectModel.ListItemBuilder::BuildListItemView(class Microsoft.Crm.ObjectModel.ListQueryWrapper listQuery, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, valuetype [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.FormFactor formFactor, valuetype [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.MetadataType metaDataType)
0xa5110  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xa5115  ldloc.s  4
0xa5117  ldarg.0
0xa5118  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.TabConverter::get_Context()
0xa511d  ldarg.0
0xa511e  call     instance valuetype [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.FormFactor Microsoft.Crm.ObjectModel.ConverterBase::get_FormFactor()
0xa5123  ldloca.s 6
0xa5125  ldc.i4.0
0xa5126  ldc.i4.0
0xa5127  call     class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor Microsoft.Crm.ObjectModel.ListItemBuilder::BuildListItemViewModel(class Microsoft.Crm.ObjectModel.ListQueryWrapper listQuery, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, valuetype [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.FormFactor formFactor, [out] string[]& renderedFields, valuetype [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.MetadataType metadataType, [opt] bool isIshFormAvailable)
0xa512c  stloc.s  0xF
0xa512e  ldstr    aReferencepanel_0// "ReferencePanelViewModel"
0xa5133  ldstr    aReferencepanel_1// "ReferencePanel"
0xa5138  ldstr    aReferencepanel_1// "ReferencePanel"
0xa513d  ldnull
0xa513e  ldnull
0xa513f  ldc.i4.2
0xa5140  newarr   [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor
0xa5145  dup
0xa5146  ldc.i4.0
0xa5147  ldstr    aMultisessionta// "MultiSessionTabContainerViewModel"
0xa514c  ldstr    aMultisessionta_0// "MultiSessionTabContainer"
0xa5151  ldstr    aStatictabs// "StaticTabs"
0xa5156  ldc.i4.4
0xa5157  newarr   [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor
0xa515c  dup
0xa515d  ldc.i4.0
0xa515e  ldstr    aTaborientation// "TabOrientation"
0xa5163  ldstr    aRight// "right"
0xa5168  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0xa516d  stelem.ref
0xa516e  dup
0xa516f  ldc.i4.1
0xa5170  ldstr    aActivechild// "ActiveChild"
0xa5175  ldstr    aSessiontabcont_1// "SessionTabContainer1"
0xa517a  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0xa517f  stelem.ref
0xa5180  dup
0xa5181  ldc.i4.2
0xa5182  ldstr    aActivatedtabco// "ActivatedTabColor"
0xa5187  ldstr    aWhite// "white"
0xa518c  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0xa5191  stelem.ref
0xa5192  dup
0xa5193  ldc.i4.3
0xa5194  ldstr    aDeactivatedtab// "DeactivatedTabColor"
0xa5199  ldstr    aE9e9e9// "#e9e9e9"
0xa519e  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0xa51a3  stelem.ref
0xa51a4  ldnull
0xa51a5  ldc.i4.3
0xa51a6  newarr   [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor
0xa51ab  dup
0xa51ac  ldc.i4.0
0xa51ad  ldstr    aMultisessionta// "MultiSessionTabContainerViewModel"
0xa51b2  ldstr    aSessiontabcont// "SessionTabContainer"
0xa51b7  ldstr    aSessiontabcont// "SessionTabContainer"
0xa51bc  ldc.i4.4
0xa51bd  newarr   [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor
0xa51c2  dup
0xa51c3  ldc.i4.0
0xa51c4  ldstr    aTaborientation// "TabOrientation"
0xa51c9  ldstr    aRight// "right"
0xa51ce  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0xa51d3  stelem.ref
0xa51d4  dup
0xa51d5  ldc.i4.1
0xa51d6  ldstr    aContentdatasou// "ContentDataSource"
0xa51db  ldc.i4.2
0xa51dc  box      [mscorlib]System.Int32
0xa51e1  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0xa51e6  stelem.ref
0xa51e7  dup
0xa51e8  ldc.i4.2
0xa51e9  ldstr    aIsclosebuttonv// "IsCloseButtonVisible"
0xa51ee  ldc.i4.0
0xa51ef  box      [mscorlib]System.Boolean
0xa51f4  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0xa51f9  stelem.ref
0xa51fa  dup
0xa51fb  ldc.i4.3
0xa51fc  ldstr    aFonticonname// "FontIconName"
0xa5201  ldstr    aSearchbutton// "SearchButton"
0xa5206  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0xa520b  stelem.ref
0xa520c  ldnull
0xa520d  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor::.ctor(string, string, string, class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor[], class [Microsoft.Crm.Client.Shared]System.Dictionary)
0xa5212  stelem.ref
0xa5213  dup
0xa5214  ldc.i4.1
0xa5215  ldstr    aMultisessionta// "MultiSessionTabContainerViewModel"
0xa521a  ldstr    aSessiontabcont// "SessionTabContainer"
0xa521f  ldstr    aSessiontabcont_1// "SessionTabContainer1"
0xa5224  ldc.i4.4
0xa5225  newarr   [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor
0xa522a  dup
0xa522b  ldc.i4.0
0xa522c  ldstr    aTaborientation// "TabOrientation"
0xa5231  ldstr    aRight// "right"
0xa5236  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0xa523b  stelem.ref
0xa523c  dup
0xa523d  ldc.i4.1
0xa523e  ldstr    aContentdatasou// "ContentDataSource"
0xa5243  ldc.i4.2
0xa5244  box      [mscorlib]System.Int32
0xa5249  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0xa524e  stelem.ref
0xa524f  dup
0xa5250  ldc.i4.2
0xa5251  ldstr    aIsclosebuttonv// "IsCloseButtonVisible"
0xa5256  ldc.i4.0
0xa5257  box      [mscorlib]System.Boolean
0xa525c  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0xa5261  stelem.ref
0xa5262  dup
0xa5263  ldc.i4.3
0xa5264  ldstr    aFonticonname// "FontIconName"
0xa5269  ldstr    aRecentcases// "RecentCases"
0xa526e  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0xa5273  stelem.ref
0xa5274  ldnull
0xa5275  ldc.i4.1
0xa5276  newarr   [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor
0xa527b  dup
0xa527c  ldc.i4.0
0xa527d  ldstr    aMultilinelist// "MultilineList"
0xa5282  ldstr    aMultilinelist// "MultilineList"
0xa5287  ldloc.s  4
0xa5289  callvirt instance string Microsoft.Crm.ObjectModel.ListQueryWrapper::get_ViewName()
0xa528e  ldstr    aMultilinelist_0// "-MultilineList"
0xa5293  call     string [mscorlib]System.String::Concat(string, string)
0xa5298  ldc.i4.s 0xB
0xa529a  newarr   [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor
0xa529f  dup
0xa52a0  ldc.i4.0
0xa52a1  ldstr    aPagesize// "PageSize"
0xa52a6  ldc.i4.5
0xa52a7  box      [mscorlib]System.Int32
0xa52ac  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0xa52b1  stelem.ref
0xa52b2  dup
0xa52b3  ldc.i4.1
0xa52b4  ldstr    aListitemviewmo// "ListItemViewModelDescriptor"
0xa52b9  ldloc.s  0xF
0xa52bb  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0xa52c0  stelem.ref
0xa52c1  dup
0xa52c2  ldc.i4.2
0xa52c3  ldstr    aColumnnames// "ColumnNames"
0xa52c8  ldloc.s  6
0xa52ca  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0xa52cf  stelem.ref
0xa52d0  dup
0xa52d1  ldc.i4.3
0xa52d2  ldstr    aGridenabled// "GridEnabled"
0xa52d7  ldc.i4.1
0xa52d8  box      [mscorlib]System.Boolean
0xa52dd  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ValuePropertyDescriptor::.ctor(string, object)
0xa52e2  stelem.ref
  ... truncated ...
```
