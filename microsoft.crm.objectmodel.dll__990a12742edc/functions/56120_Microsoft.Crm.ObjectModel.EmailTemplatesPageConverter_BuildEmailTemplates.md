# Microsoft.Crm.ObjectModel.EmailTemplatesPageConverter::BuildEmailTemplates

- ea: `0x56120`
- end: `0x561d6`
- name: `Microsoft.Crm.ObjectModel.EmailTemplatesPageConverter::BuildEmailTemplates`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x560c0`

## callees

- `0x19b90`
- `0x561e0`
- `0xb1600`
- `0xb9cc0`

## string_xrefs

- `0x56120`: `<fetch version="1.0" output-format="xml - platform" mapping="logical">\n	<entity name="template">\n		<order attribute="title" descending="false" />\n		<attribute name="title" /><attribute name="templatetypecode" />\n		<attribute name="ispersonal" /><attribute name="languagecode" />\n		<attribute name="templateid" />\n		<filter type="and">\n			<condition attribute="languagecode" operator="eq-userlanguage" />\n			<condition attribute="templatetypecode" operator="eq" value="{0}" />\n		</filter>\n	<`
- `0x56135`: `<fetch version="1.0" output-format="xml - platform" mapping="logical">\n	<entity name="template">\n		<order attribute="title" descending="false" />\n		<attribute name="title" /><attribute name="templatetypecode" />\n		<attribute name="ispersonal" /><attribute name="languagecode" />\n		<attribute name="templateid" />\n		<filter type="and">\n			<condition attribute="languagecode" operator="eq-userlanguage" />\n			<condition attribute="templatetypecode" operator="eq" value="{0}" />\n		</filter>\n	<`
- `0x5614a`: `MoCA_OWA_Global_Templates_Header`
- `0x5618b`: `emailTemplatesPaneCssClass`
- `0x561a2`: `globalEmailTemplatesList`
- `0x561ba`: `FilteredEmailTemplatesList`
- `0x561c0`: `FetchXmlWithPlaceholders`
- `0x561c5`: `Filtered Templates`

## pseudocode

```c

```

## disassembly

```asm
0x56120  ldstr    aFetchVersion10// "<fetch version=\"1.0\" output-format=\""...
0x56125  ldstr    a0_0// "{0}"
0x5612a  ldstr    a8// "8"
0x5612f  call     instance string [mscorlib]System.String::Replace(string, string)
0x56134  stloc.0
0x56135  ldstr    aFetchVersion10// "<fetch version=\"1.0\" output-format=\""...
0x5613a  ldstr    a0_0// "{0}"
0x5613f  ldstr    aEntitytypecode// "{EntityTypeCode}"
0x56144  call     instance string [mscorlib]System.String::Replace(string, string)
0x56149  stloc.1
0x5614a  ldstr    aMocaOwaGlobalT// "MoCA_OWA_Global_Templates_Header"
0x5614f  ldarg.0
0x56150  call     instance int32 Microsoft.Crm.ObjectModel.ConverterBase::get_UserLanguageCode()
0x56155  newobj   instance void [mscorlib]System.Globalization.CultureInfo::.ctor(int32)
0x5615a  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [mscorlib]System.Globalization.CultureInfo culture)
0x5615f  stloc.2
0x56160  ldstr    aPanoramaitem// "PanoramaItem"
0x56165  ldstr    aPanoramaitem// "PanoramaItem"
0x5616a  ldarg.1
0x5616b  callvirt instance string Microsoft.Crm.ObjectModel.RelationshipMetadata::get_TargetEntityTypeName()
0x56170  ldstr    aPane// "Pane"
0x56175  call     string [mscorlib]System.String::Concat(string, string)
0x5617a  ldnull
0x5617b  ldc.i4.2
0x5617c  newarr   [mscorlib]System.Object
0x56181  dup
0x56182  ldc.i4.0
0x56183  ldstr    aCssclass// "CssClass"
0x56188  stelem.ref
0x56189  dup
0x5618a  ldc.i4.1
0x5618b  ldstr    aEmailtemplates// "emailTemplatesPaneCssClass"
0x56190  stelem.ref
0x56191  newobj   instance void [Microsoft.Crm.Client.Shared]System.Dictionary::.ctor(object[])
0x56196  ldc.i4.2
0x56197  newarr   [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor
0x5619c  dup
0x5619d  ldc.i4.0
0x5619e  ldarg.0
0x5619f  ldarg.1
0x561a0  ldc.i4.s 0x64
0x561a2  ldstr    aGlobalemailtem// "globalEmailTemplatesList"
0x561a7  ldloc.0
0x561a8  ldstr    asc_24F76C// ""
0x561ad  ldloc.2
0x561ae  call     instance class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor Microsoft.Crm.ObjectModel.EmailTemplatesPageConverter::BuildListViewModel(class Microsoft.Crm.ObjectModel.RelationshipMetadata relationshipMetadata, int32 pageSize, string name, string queryXml, [opt] string queryName, [opt] string label)
0x561b3  stelem.ref
0x561b4  dup
0x561b5  ldc.i4.1
0x561b6  ldarg.0
0x561b7  ldarg.1
0x561b8  ldc.i4.s 0x64
0x561ba  ldstr    aFilteredemailt// "FilteredEmailTemplatesList"
0x561bf  ldloc.1
0x561c0  ldstr    aFetchxmlwithpl// "FetchXmlWithPlaceholders"
0x561c5  ldstr    aFilteredTempla// "Filtered Templates"
0x561ca  call     instance class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor Microsoft.Crm.ObjectModel.EmailTemplatesPageConverter::BuildListViewModel(class Microsoft.Crm.ObjectModel.RelationshipMetadata relationshipMetadata, int32 pageSize, string name, string queryXml, [opt] string queryName, [opt] string label)
0x561cf  stelem.ref
0x561d0  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor::.ctor(string, string, string, class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor[], class [Microsoft.Crm.Client.Shared]System.Dictionary, class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ViewModelDescriptor[])
0x561d5  ret
```
