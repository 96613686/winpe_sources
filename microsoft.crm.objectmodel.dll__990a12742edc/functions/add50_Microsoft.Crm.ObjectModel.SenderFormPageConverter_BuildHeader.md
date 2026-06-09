# Microsoft.Crm.ObjectModel.SenderFormPageConverter::BuildHeader

- ea: `0xadd50`
- end: `0xae21b`
- name: `Microsoft.Crm.ObjectModel.SenderFormPageConverter::BuildHeader`
- size: `1227`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0xadbd0`

## callees

- `0x19ba0`
- `0xadac0`
- `0xadd50`
- `0xae220`
- `0xb9cc0`
- `0xb9d60`

## string_xrefs

- `0xadd6d`: `PopOutLinkLabelViewModel`
- `0xadd72`: `PopOutLinkLabel`
- `0xadda6`: `PopOutLinkLabelCommandName`
- `0xaddae`: `OpenInBrowserCommand`
- `0xadf64`: `ExternalProtocolLinkLabel`
- `0xadffd`: `ExternalProtocolLinkLabel`
- `0xae06b`: `ExternalProtocolLinkLabel`
- `0xadfa3`: `Protocol`
- `0xae026`: `Protocol`
- `0xae09a`: `Protocol`
- `0xadeb8`: `companyname`
- `0xadee4`: `companyname`
- `0xaddd4`: `MoCA_OWA_PopoutLink_Label_Tooltip`
- `0xadefb`: `CompanyLabel`
- `0xadf14`: `form_header_company`
- `0xadf5f`: `RecipientExternalProtocolLinkViewModel`
- `0xadff8`: `RecipientExternalProtocolLinkViewModel`
- `0xae066`: `RecipientExternalProtocolLinkViewModel`

## pseudocode

```c

```

## disassembly

```asm
0xadd50  ldarg.0
0xadd51  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.ObjectModel.SenderFormPageConverter::_entityMetadata
0xadd56  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedName()
0xadd5b  ldarg.0
0xadd5c  call     instance int32 Microsoft.Crm.ObjectModel.ConverterBase::get_UserLanguageCode()
0xadd61  ldarg.0
0xadd62  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.ConverterBase::get_Context()
0xadd67  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::TryGetDescription(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xadd6c  stloc.0
0xadd6d  ldstr    aPopoutlinklabe// "PopOutLinkLabelViewModel"
0xadd72  ldstr    aPopoutlinklabe_0// "PopOutLinkLabel"
0xadd77  ldstr    aPrimaryfieldla// "PrimaryFieldLabel"
0xadd7c  ldarg.0
0xadd7d  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.ObjectModel.SenderFormPageConverter::_entityMetadata
0xadd82  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryField()
0xadd87  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Name()
0xadd8c  ldnull
0xadd8d  ldnull
0xadd8e  ldc.i4.8
0xadd8f  newarr   [mscorlib]System.Object
0xadd94  dup
0xadd95  ldc.i4.0
0xadd96  ldstr    aLabelcssclass// "LabelCssClass"
0xadd9b  stelem.ref
0xadd9c  dup
0xadd9d  ldc.i4.1
0xadd9e  ldstr    aFormHeaderPrim// "form_header_primaryfield"
0xadda3  stelem.ref
0xadda4  dup
0xadda5  ldc.i4.2
0xadda6  ldstr    aPopoutlinklabe_1// "PopOutLinkLabelCommandName"
0xaddab  stelem.ref
0xaddac  dup
0xaddad  ldc.i4.3
0xaddae  ldstr    aOpeninbrowserc// "OpenInBrowserCommand"
0xaddb3  stelem.ref
0xaddb4  dup
0xaddb5  ldc.i4.4
0xaddb6  ldstr    aSuffixtext// "SuffixText"
0xaddbb  stelem.ref
0xaddbc  dup
0xaddbd  ldc.i4.5
0xaddbe  ldstr    a0_4// "({0})"
0xaddc3  ldloc.0
0xaddc4  call     string [mscorlib]System.String::Format(string, object)
0xaddc9  stelem.ref
0xaddca  dup
0xaddcb  ldc.i4.6
0xaddcc  ldstr    aTitle// "Title"
0xaddd1  stelem.ref
0xaddd2  dup
0xaddd3  ldc.i4.7
0xaddd4  ldstr    aMocaOwaPopoutl// "MoCA_OWA_PopoutLink_Label_Tooltip"
0xaddd9  ldarg.0
0xaddda  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.ObjectModel.SenderFormPageConverter::userCultureInfo
0xadddf  ldc.i4.1
0xadde0  newarr   [mscorlib]System.Object
0xadde5  dup
0xadde6  ldc.i4.0
0xadde7  ldloc.0
0xadde8  stelem.ref
0xadde9  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [mscorlib]System.Globalization.CultureInfo culture, object[] args)
0xaddee  stelem.ref
0xaddef  newobj   instance void [Microsoft.Crm.Client.Shared]System.Dictionary::.ctor(object[])
0xaddf4  ldnull
0xaddf5  call     class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.DescriptorBuilder::CreateControlViewModelDescriptor(string, string, string, string, string, class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor[], class [Microsoft.Crm.Client.Shared]System.Dictionary, string)
0xaddfa  stloc.1
0xaddfb  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor>::.ctor()
0xade00  stloc.2
0xade01  ldarg.0
0xade02  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.ObjectModel.SenderFormPageConverter::_entityMetadata
0xade07  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xade0c  ldstr    aSystemuser// "systemuser"
0xade11  call     bool [mscorlib]System.String::op_Equality(string, string)
0xade16  brtrue.s loc_ADE1F
0xade18  ldstr    aJobtitle// "jobtitle"
0xade1d  br.s     loc_ADE24
0xade1f  ldstr    aTitle_0// "title"
0xade24  stloc.3
0xade25  ldloc.2
0xade26  ldstr    aLabel_0// "Label"
0xade2b  ldstr    aLabel// "label"
0xade30  ldstr    aJobtitlelabel// "JobTitleLabel"
0xade35  ldloc.3
0xade36  ldnull
0xade37  ldnull
0xade38  ldc.i4.6
0xade39  newarr   [mscorlib]System.Object
0xade3e  dup
0xade3f  ldc.i4.0
0xade40  ldstr    aLabelcssclass// "LabelCssClass"
0xade45  stelem.ref
0xade46  dup
0xade47  ldc.i4.1
0xade48  ldstr    aFormHeaderJobt// "form_header_jobtitle"
0xade4d  stelem.ref
0xade4e  dup
0xade4f  ldc.i4.2
0xade50  ldstr    aTitle// "Title"
0xade55  stelem.ref
0xade56  dup
0xade57  ldc.i4.3
0xade58  ldarg.0
0xade59  ldloc.3
0xade5a  call     instance string Microsoft.Crm.ObjectModel.SenderFormPageConverter::GetAttributeDisplayName(string attributeName)
0xade5f  stelem.ref
0xade60  dup
0xade61  ldc.i4.4
0xade62  ldstr    aTitleformat// "TitleFormat"
0xade67  stelem.ref
0xade68  dup
0xade69  ldc.i4.5
0xade6a  ldstr    a01_12// "{0}: {1}"
0xade6f  stelem.ref
0xade70  newobj   instance void [Microsoft.Crm.Client.Shared]System.Dictionary::.ctor(object[])
0xade75  ldnull
0xade76  call     class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.DescriptorBuilder::CreateControlViewModelDescriptor(string, string, string, string, string, class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor[], class [Microsoft.Crm.Client.Shared]System.Dictionary, string)
0xade7b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor>::Add(var<u1>)
0xade80  ldarg.0
0xade81  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.ObjectModel.SenderFormPageConverter::_entityMetadata
0xade86  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xade8b  ldstr    aSystemuser// "systemuser"
0xade90  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xade95  brfalse  loc_ADF47
0xade9a  ldarg.0
0xade9b  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.ObjectModel.SenderFormPageConverter::_entityMetadata
0xadea0  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xadea5  ldstr    aLead_0// "lead"
0xadeaa  call     bool [mscorlib]System.String::op_Equality(string, string)
0xadeaf  brtrue.s loc_ADEB8
0xadeb1  ldstr    aParentcustomer_0// "parentcustomerid!name"
0xadeb6  br.s     loc_ADEBD
0xadeb8  ldstr    aCompanyname// "companyname"
0xadebd  stloc.s  5
0xadebf  ldarg.0
0xadec0  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.ObjectModel.SenderFormPageConverter::_entityMetadata
0xadec5  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xadeca  ldstr    aLead_0// "lead"
0xadecf  call     bool [mscorlib]System.String::op_Equality(string, string)
0xaded4  brtrue.s loc_ADEE3
0xaded6  ldarg.0
0xaded7  ldstr    aParentcustomer// "parentcustomerid"
0xadedc  call     instance string Microsoft.Crm.ObjectModel.SenderFormPageConverter::GetAttributeDisplayName(string attributeName)
0xadee1  br.s     loc_ADEEE
0xadee3  ldarg.0
0xadee4  ldstr    aCompanyname// "companyname"
0xadee9  call     instance string Microsoft.Crm.ObjectModel.SenderFormPageConverter::GetAttributeDisplayName(string attributeName)
0xadeee  stloc.s  6
0xadef0  ldloc.2
0xadef1  ldstr    aLabel_0// "Label"
0xadef6  ldstr    aLabel// "label"
0xadefb  ldstr    aCompanylabel// "CompanyLabel"
0xadf00  ldloc.s  5
0xadf02  ldnull
0xadf03  ldnull
0xadf04  ldc.i4.6
0xadf05  newarr   [mscorlib]System.Object
0xadf0a  dup
0xadf0b  ldc.i4.0
0xadf0c  ldstr    aLabelcssclass// "LabelCssClass"
0xadf11  stelem.ref
0xadf12  dup
0xadf13  ldc.i4.1
0xadf14  ldstr    aFormHeaderComp// "form_header_company"
0xadf19  stelem.ref
0xadf1a  dup
0xadf1b  ldc.i4.2
0xadf1c  ldstr    aTitle// "Title"
0xadf21  stelem.ref
0xadf22  dup
0xadf23  ldc.i4.3
0xadf24  ldloc.s  6
0xadf26  stelem.ref
0xadf27  dup
0xadf28  ldc.i4.4
0xadf29  ldstr    aTitleformat// "TitleFormat"
0xadf2e  stelem.ref
0xadf2f  dup
0xadf30  ldc.i4.5
0xadf31  ldstr    a01_12// "{0}: {1}"
0xadf36  stelem.ref
0xadf37  newobj   instance void [Microsoft.Crm.Client.Shared]System.Dictionary::.ctor(object[])
0xadf3c  ldnull
0xadf3d  call     class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.DescriptorBuilder::CreateControlViewModelDescriptor(string, string, string, string, string, class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor[], class [Microsoft.Crm.Client.Shared]System.Dictionary, string)
0xadf42  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor>::Add(var<u1>)
0xadf47  ldarg.0
0xadf48  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.ObjectModel.SenderFormPageConverter::_entityMetadata
0xadf4d  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xadf52  ldstr    aSystemuser// "systemuser"
0xadf57  call     bool [mscorlib]System.String::op_Equality(string, string)
0xadf5c  brfalse.s loc_ADFD2
0xadf5e  ldloc.2
0xadf5f  ldstr    aRecipientexter// "RecipientExternalProtocolLinkViewModel"
0xadf64  ldstr    aExternalprotoc_0// "ExternalProtocolLinkLabel"
0xadf69  ldstr    aInternalemaila_0// "InternalEmailAddressLabel"
0xadf6e  ldstr    aInternalemaila// "internalemailaddress"
0xadf73  ldnull
0xadf74  ldnull
0xadf75  ldc.i4.8
0xadf76  newarr   [mscorlib]System.Object
0xadf7b  dup
0xadf7c  ldc.i4.0
0xadf7d  ldstr    aLabelcssclass// "LabelCssClass"
0xadf82  stelem.ref
0xadf83  dup
0xadf84  ldc.i4.1
0xadf85  ldstr    aFormHeaderInte// "form_header_internalemailaddress"
0xadf8a  stelem.ref
0xadf8b  dup
0xadf8c  ldc.i4.2
0xadf8d  ldstr    aTitle// "Title"
0xadf92  stelem.ref
0xadf93  dup
0xadf94  ldc.i4.3
0xadf95  ldarg.0
0xadf96  ldstr    aInternalemaila// "internalemailaddress"
0xadf9b  call     instance string Microsoft.Crm.ObjectModel.SenderFormPageConverter::GetAttributeDisplayName(string attributeName)
0xadfa0  stelem.ref
0xadfa1  dup
0xadfa2  ldc.i4.4
0xadfa3  ldstr    aProtocol// "Protocol"
0xadfa8  stelem.ref
0xadfa9  dup
0xadfaa  ldc.i4.5
0xadfab  ldc.i4.0
0xadfac  box      Microsoft.Crm.ObjectModel.ExternalProtocol
0xadfb1  stelem.ref
0xadfb2  dup
0xadfb3  ldc.i4.6
0xadfb4  ldstr    aTitleformat// "TitleFormat"
0xadfb9  stelem.ref
0xadfba  dup
0xadfbb  ldc.i4.7
0xadfbc  ldstr    a01_12// "{0}: {1}"
0xadfc1  stelem.ref
0xadfc2  newobj   instance void [Microsoft.Crm.Client.Shared]System.Dictionary::.ctor(object[])
0xadfc7  ldnull
0xadfc8  call     class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.DescriptorBuilder::CreateControlViewModelDescriptor(string, string, string, string, string, class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor[], class [Microsoft.Crm.Client.Shared]System.Dictionary, string)
0xadfcd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor>::Add(var<u1>)
0xadfd2  ldarg.0
0xadfd3  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.ObjectModel.SenderFormPageConverter::_entityMetadata
0xadfd8  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xadfdd  ldstr    aSystemuser// "systemuser"
0xadfe2  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xadfe7  brtrue.s loc_ADFF0
0xadfe9  ldstr    aAddress1Teleph// "address1_telephone1"
0xadfee  br.s     loc_ADFF5
0xadff0  ldstr    aTelephone1// "telephone1"
0xadff5  stloc.s  4
0xadff7  ldloc.2
0xadff8  ldstr    aRecipientexter// "RecipientExternalProtocolLinkViewModel"
0xadffd  ldstr    aExternalprotoc_0// "ExternalProtocolLinkLabel"
0xae002  ldstr    aBusinessphonel// "BusinessPhoneLabel"
0xae007  ldloc.s  4
0xae009  ldnull
0xae00a  ldnull
0xae00b  ldc.i4.8
0xae00c  newarr   [mscorlib]System.Object
0xae011  dup
0xae012  ldc.i4.0
0xae013  ldstr    aTitle// "Title"
0xae018  stelem.ref
0xae019  dup
0xae01a  ldc.i4.1
0xae01b  ldarg.0
0xae01c  ldloc.s  4
0xae01e  call     instance string Microsoft.Crm.ObjectModel.SenderFormPageConverter::GetAttributeDisplayName(string attributeName)
0xae023  stelem.ref
0xae024  dup
0xae025  ldc.i4.2
0xae026  ldstr    aProtocol// "Protocol"
0xae02b  stelem.ref
0xae02c  dup
0xae02d  ldc.i4.3
0xae02e  ldc.i4.1
0xae02f  box      Microsoft.Crm.ObjectModel.ExternalProtocol
0xae034  stelem.ref
0xae035  dup
0xae036  ldc.i4.4
0xae037  ldstr    aIconsymbolname// "IconSymbolName"
0xae03c  stelem.ref
0xae03d  dup
0xae03e  ldc.i4.5
0xae03f  ldstr    aBusinessphone// "BusinessPhone"
0xae044  stelem.ref
0xae045  dup
0xae046  ldc.i4.6
0xae047  ldstr    aTitleformat// "TitleFormat"
0xae04c  stelem.ref
0xae04d  dup
0xae04e  ldc.i4.7
0xae04f  ldstr    a01_12// "{0}: {1}"
0xae054  stelem.ref
0xae055  newobj   instance void [Microsoft.Crm.Client.Shared]System.Dictionary::.ctor(object[])
0xae05a  ldnull
0xae05b  call     class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.DescriptorBuilder::CreateControlViewModelDescriptor(string, string, string, string, string, class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor[], class [Microsoft.Crm.Client.Shared]System.Dictionary, string)
0xae060  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor>::Add(var<u1>)
0xae065  ldloc.2
0xae066  ldstr    aRecipientexter// "RecipientExternalProtocolLinkViewModel"
0xae06b  ldstr    aExternalprotoc_0// "ExternalProtocolLinkLabel"
  ... truncated ...
```
