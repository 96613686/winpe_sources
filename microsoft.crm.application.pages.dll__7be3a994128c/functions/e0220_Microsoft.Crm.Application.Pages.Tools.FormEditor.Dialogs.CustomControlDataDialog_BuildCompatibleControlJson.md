# Microsoft.Crm.Application.Pages.Tools.FormEditor.Dialogs.CustomControlDataDialog::BuildCompatibleControlJson

- ea: `0xe0220`
- end: `0xe0a98`
- name: `Microsoft.Crm.Application.Pages.Tools.FormEditor.Dialogs.CustomControlDataDialog::BuildCompatibleControlJson`
- size: `2168`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0xe0100`

## callees

- `0xe0220`
- `0xe0aa0`
- `0xe0f20`
- `0xe1350`
- `0xe1390`
- `0xe13d0`
- `0xe1430`
- `0xe1a80`
- `0x105330`
- `0x105410`

## string_xrefs

- `0xe025e`: `/manifest/control/resources/resx`
- `0xe0283`: `/manifest/control`
- `0xe03c1`: `/manifest/control`
- `0xe064d`: `/manifest/control`
- `0xe02b5`: `/manifest/control/resources/resx[contains(@path,`
- `0xe049a`: `CustomControlPreviewImagePath`
- `0xe04cd`: `ReadMode`
- `0xe0620`: `/manifest/control/data-set | /manifest/control/groups/group/data-set`
- `0xe0633`: `/manifest/control/data-set | /manifest/control/groups/group/data-set`
- `0xe0863`: `/manifest/control/groups[@name='`

## pseudocode

```c

```

## disassembly

```asm
0xe0220  ldarg.1
0xe0221  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xe0226  brtrue.s loc_E024F
0xe0228  ldarg.2
0xe0229  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xe022e  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xe0233  brtrue.s loc_E024F
0xe0235  ldarg.3
0xe0236  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xe023b  brtrue.s loc_E024F
0xe023d  ldarg.s  4
0xe023f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xe0244  brtrue.s loc_E024F
0xe0246  ldarg.s  5
0xe0248  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xe024d  brfalse.s loc_E0255
0xe024f  ldsfld   string [mscorlib]System.String::Empty
0xe0254  ret
0xe0255  ldarg.s  5
0xe0257  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0xe025c  stloc.0
0xe025d  ldloc.0
0xe025e  ldstr    aManifestContro// "/manifest/control/resources/resx"
0xe0263  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0xe0268  stloc.1
0xe0269  ldloc.1
0xe026a  brfalse  loc_E0386
0xe026f  ldloc.1
0xe0270  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0xe0275  ldc.i4.0
0xe0276  ble      loc_E0386
0xe027b  ldsfld   string [mscorlib]System.String::Empty
0xe0280  stloc.s  6
0xe0282  ldloc.0
0xe0283  ldstr    aManifestContro_0// "/manifest/control"
0xe0288  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xe028d  stloc.s  7
0xe028f  ldarg.0
0xe0290  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [System.Xml]System.Xml.XmlDocument>::.ctor()
0xe0295  stfld    class [mscorlib]System.Collections.Generic.List`1<class [System.Xml]System.Xml.XmlDocument> Microsoft.Crm.Application.Pages.Tools.FormEditor.Dialogs.CustomControlDataDialog::resxXmlDocuments
0xe029a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xe029f  callvirt instance class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserCulture()
0xe02a4  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0xe02a9  stloc.s  0xC
0xe02ab  ldloca.s 0xC
0xe02ad  call     instance string [mscorlib]System.Int32::ToString()
0xe02b2  stloc.s  8
0xe02b4  ldloc.0
0xe02b5  ldstr    aManifestContro_1// "/manifest/control/resources/resx[contai"...
0xe02ba  ldloc.s  8
0xe02bc  ldstr    asc_1E8056// ")]"
0xe02c1  call     string [mscorlib]System.String::Concat(string, string, string)
0xe02c6  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xe02cb  stloc.s  9
0xe02cd  ldloc.s  9
0xe02cf  brtrue.s loc_E034B
0xe02d1  ldloc.1
0xe02d2  ldc.i4.0
0xe02d3  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0xe02d8  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xe02dd  ldstr    aPath// "path"
0xe02e2  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xe02e7  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xe02ec  stloc.s  0xD
0xe02ee  ldloc.s  0xD
0xe02f0  ldc.i4.0
0xe02f1  ldloc.s  0xD
0xe02f3  ldstr    aResx// ".resx"
0xe02f8  callvirt instance int32 [mscorlib]System.String::LastIndexOf(string)
0xe02fd  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xe0302  stloc.s  0xE
0xe0304  ldloc.s  0xE
0xe0306  ldc.i4.s 0x2E
0xe0308  callvirt instance int32 [mscorlib]System.String::LastIndexOf(char)
0xe030d  ldc.i4.m1
0xe030e  bgt.s    loc_E0325
0xe0310  ldloc.s  0xE
0xe0312  ldstr    asc_11B5DE// "."
0xe0317  ldloc.s  8
0xe0319  ldstr    aResx// ".resx"
0xe031e  call     string [mscorlib]System.String::Concat(string, string, string, string)
0xe0323  br.s     loc_E0347
0xe0325  ldloc.s  0xE
0xe0327  ldc.i4.0
0xe0328  ldloc.s  0xE
0xe032a  ldc.i4.s 0x2E
0xe032c  callvirt instance int32 [mscorlib]System.String::LastIndexOf(char)
0xe0331  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xe0336  ldstr    asc_11B5DE// "."
0xe033b  ldloc.s  8
0xe033d  ldstr    aResx// ".resx"
0xe0342  call     string [mscorlib]System.String::Concat(string, string, string, string)
0xe0347  stloc.s  6
0xe0349  br.s     loc_E0363
0xe034b  ldloc.s  9
0xe034d  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xe0352  ldstr    aPath// "path"
0xe0357  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xe035c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xe0361  stloc.s  6
0xe0363  ldloc.s  6
0xe0365  ldloc.s  7
0xe0367  call     string Microsoft.Crm.Application.Pages.Utility.ResxUtility::RetrieveResxFromManifest(string resxFileNamePath, class [System.Xml]System.Xml.XmlNode manifestControlNode)
0xe036c  stloc.s  0xA
0xe036e  ldarg.s  7
0xe0370  ldloc.s  0xA
0xe0372  call     class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Application.Pages.Utility.ResxUtility::RetrieveResxXmlWebResourceByName(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, string resxFileName)
0xe0377  stloc.s  0xB
0xe0379  ldarg.0
0xe037a  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [System.Xml]System.Xml.XmlDocument> Microsoft.Crm.Application.Pages.Tools.FormEditor.Dialogs.CustomControlDataDialog::resxXmlDocuments
0xe037f  ldloc.s  0xB
0xe0381  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System.Xml]System.Xml.XmlDocument>::Add(var<u1>)
0xe0386  ldarg.0
0xe0387  ldarg.1
0xe0388  ldloc.0
0xe0389  call     instance bool Microsoft.Crm.Application.Pages.Tools.FormEditor.Dialogs.CustomControlDataDialog::IsDataTypeCompatibleWithTheCustomControl(string dataType, class [System.Xml]System.Xml.XmlDocument controlManifest)
0xe038e  brtrue.s loc_E0396
0xe0390  ldsfld   string [mscorlib]System.String::Empty
0xe0395  ret
0xe0396  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0xe039b  stloc.2
0xe039c  ldloc.2
0xe039d  ldstr    aCustomcontroli_0// "CustomControlId"
0xe03a2  ldarga.s 2
0xe03a4  constrained. [mscorlib]System.Guid
0xe03aa  callvirt instance string [mscorlib]System.Object::ToString()
0xe03af  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xe03b4  ldc.i4.1
0xe03b5  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::GetJsonPair(string, string, bool)
0xe03ba  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xe03bf  pop
0xe03c0  ldloc.0
0xe03c1  ldstr    aManifestContro_0// "/manifest/control"
0xe03c6  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xe03cb  stloc.3
0xe03cc  ldloc.2
0xe03cd  ldstr    aCustomcontrolf// "CustomControlFullName"
0xe03d2  ldarg.3
0xe03d3  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xe03d8  ldc.i4.1
0xe03d9  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::GetJsonPair(string, string, bool)
0xe03de  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xe03e3  pop
0xe03e4  ldloc.2
0xe03e5  ldstr    aCustomcontroln// "CustomControlName"
0xe03ea  ldarg.0
0xe03eb  ldloc.3
0xe03ec  ldstr    aDisplayNameKey// "display-name-key"
0xe03f1  call     instance string Microsoft.Crm.Application.Pages.Tools.FormEditor.Dialogs.CustomControlDataDialog::RetrieveNodeAttributeValueFromName(class [System.Xml]System.Xml.XmlNode node, string attributeName)
0xe03f6  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xe03fb  ldc.i4.1
0xe03fc  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::GetJsonPair(string, string, bool)
0xe0401  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xe0406  pop
0xe0407  ldloc.2
0xe0408  ldstr    aControldescrip_1// "ControlDescription"
0xe040d  ldarg.0
0xe040e  ldloc.3
0xe040f  ldstr    aDescriptionKey// "description-key"
0xe0414  call     instance string Microsoft.Crm.Application.Pages.Tools.FormEditor.Dialogs.CustomControlDataDialog::RetrieveNodeAttributeValueFromName(class [System.Xml]System.Xml.XmlNode node, string attributeName)
0xe0419  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xe041e  ldc.i4.1
0xe041f  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::GetJsonPair(string, string, bool)
0xe0424  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xe0429  pop
0xe042a  ldloc.2
0xe042b  ldstr    aCustomcontrolv// "CustomControlVersion"
0xe0430  ldarg.s  4
0xe0432  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xe0437  ldc.i4.1
0xe0438  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::GetJsonPair(string, string, bool)
0xe043d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xe0442  pop
0xe0443  ldarg.s  6
0xe0445  callvirt instance string [mscorlib]System.String::Trim()
0xe044a  ldsfld   string [mscorlib]System.String::Empty
0xe044f  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe0454  brtrue.s loc_E0459
0xe0456  ldc.i4.0
0xe0457  br.s     loc_E045A
0xe0459  ldc.i4.1
0xe045a  stloc.s  4
0xe045c  ldloc.2
0xe045d  ldstr    aIshidden_1// "IsHidden"
0xe0462  ldloca.s 4
0xe0464  call     instance string [mscorlib]System.Boolean::ToString()
0xe0469  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xe046e  ldc.i4.0
0xe046f  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::GetJsonPair(string, string, bool)
0xe0474  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xe0479  pop
0xe047a  ldarg.0
0xe047b  ldarg.2
0xe047c  ldloc.0
0xe047d  call     instance string Microsoft.Crm.Application.Pages.Tools.FormEditor.Dialogs.CustomControlDataDialog::RetrieveControlDescriptorPreviewImagePath(valuetype [mscorlib]System.Guid customControlId, class [System.Xml]System.Xml.XmlDocument controlManifestDoc)
0xe0482  stloc.s  5
0xe0484  ldloc.s  5
0xe0486  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xe048b  brtrue.s loc_E04B2
0xe048d  ldloc.2
0xe048e  ldstr    asc_12EE00// ","
0xe0493  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xe0498  pop
0xe0499  ldloc.2
0xe049a  ldstr    aCustomcontrolp// "CustomControlPreviewImagePath"
0xe049f  ldloc.s  5
0xe04a1  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xe04a6  ldc.i4.0
0xe04a7  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::GetJsonPair(string, string, bool)
0xe04ac  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xe04b1  pop
0xe04b2  ldarg.0
0xe04b3  ldloc.0
0xe04b4  ldstr    aRead// "read"
0xe04b9  call     instance bool Microsoft.Crm.Application.Pages.Tools.FormEditor.Dialogs.CustomControlDataDialog::IsModeEnabled(class [System.Xml]System.Xml.XmlDocument controlXmlManifest, string mode)
0xe04be  brfalse.s loc_E04E8
0xe04c0  ldloc.2
0xe04c1  ldstr    asc_12EE00// ","
0xe04c6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xe04cb  pop
0xe04cc  ldloc.2
0xe04cd  ldstr    aReadmode// "ReadMode"
0xe04d2  ldstr    aTrue_0// "true"
0xe04d7  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xe04dc  ldc.i4.0
0xe04dd  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::GetJsonPair(string, string, bool)
0xe04e2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xe04e7  pop
0xe04e8  ldarg.0
0xe04e9  ldloc.0
0xe04ea  ldstr    aEdit_0// "edit"
0xe04ef  call     instance bool Microsoft.Crm.Application.Pages.Tools.FormEditor.Dialogs.CustomControlDataDialog::IsModeEnabled(class [System.Xml]System.Xml.XmlDocument controlXmlManifest, string mode)
0xe04f4  brfalse.s loc_E051E
0xe04f6  ldloc.2
0xe04f7  ldstr    asc_12EE00// ","
0xe04fc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xe0501  pop
0xe0502  ldloc.2
0xe0503  ldstr    aEditmode// "EditMode"
0xe0508  ldstr    aTrue_0// "true"
0xe050d  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xe0512  ldc.i4.0
0xe0513  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::GetJsonPair(string, string, bool)
0xe0518  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xe051d  pop
0xe051e  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0xe0523  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0xe0528  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_CustomControlSolutionExport()
0xe052d  ldarg.0
0xe052e  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Application.Pages.Tools.FormEditor.Dialogs.CustomControlDataDialog::_context
0xe0533  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xe0538  brfalse  loc_E0617
0xe053d  ldarg.0
0xe053e  ldloc.0
0xe053f  ldstr    aWeb_0// "web"
0xe0544  call     instance bool Microsoft.Crm.Application.Pages.Tools.FormEditor.Dialogs.CustomControlDataDialog::IsAvailableOn(class [System.Xml]System.Xml.XmlDocument controlXmlManifest, string formFactor)
0xe0549  brfalse.s loc_E0573
0xe054b  ldloc.2
0xe054c  ldstr    asc_12EE00// ","
0xe0551  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xe0556  pop
0xe0557  ldloc.2
0xe0558  ldstr    aWeb// "Web"
0xe055d  ldstr    aTrue_0// "true"
0xe0562  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xe0567  ldc.i4.0
0xe0568  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::GetJsonPair(string, string, bool)
0xe056d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xe0572  pop
0xe0573  ldarg.0
0xe0574  ldloc.0
0xe0575  ldstr    aPhone// "phone"
0xe057a  call     instance bool Microsoft.Crm.Application.Pages.Tools.FormEditor.Dialogs.CustomControlDataDialog::IsAvailableOn(class [System.Xml]System.Xml.XmlDocument controlXmlManifest, string formFactor)
0xe057f  brfalse.s loc_E05A9
0xe0581  ldloc.2
0xe0582  ldstr    asc_12EE00// ","
0xe0587  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xe058c  pop
0xe058d  ldloc.2
0xe058e  ldstr    aPhone_0// "Phone"
0xe0593  ldstr    aTrue_0// "true"
0xe0598  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xe059d  ldc.i4.0
0xe059e  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::GetJsonPair(string, string, bool)
0xe05a3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xe05a8  pop
0xe05a9  ldarg.0
0xe05aa  ldloc.0
0xe05ab  ldstr    aTablet// "tablet"
0xe05b0  call     instance bool Microsoft.Crm.Application.Pages.Tools.FormEditor.Dialogs.CustomControlDataDialog::IsAvailableOn(class [System.Xml]System.Xml.XmlDocument controlXmlManifest, string formFactor)
0xe05b5  brfalse.s loc_E05DF
0xe05b7  ldloc.2
0xe05b8  ldstr    asc_12EE00// ","
0xe05bd  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xe05c2  pop
0xe05c3  ldloc.2
0xe05c4  ldstr    aTablet_0// "Tablet"
0xe05c9  ldstr    aTrue_0// "true"
0xe05ce  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xe05d3  ldc.i4.0
  ... truncated ...
```
