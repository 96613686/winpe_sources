# Microsoft.Crm.Reporting.ReportPublisher::UploadReports

- ea: `0x3a90`
- end: `0x3e8c`
- name: `Microsoft.Crm.Reporting.ReportPublisher::UploadReports`
- size: `1020`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x3800`

## callees

- `0x180`
- `0x3a60`
- `0x3a90`
- `0x3e90`
- `0x3eb0`
- `0x3f90`
- `0x4030`
- `0x40a0`
- `0x4110`
- `0x4760`

## string_xrefs

- `0x3a9c`: `publish.config`
- `0x3d74`: `Publishing report {0} (attempt {1})`
- `0x3e21`: `Failed to publish report {0} (attempt {1}): {2}`

## pseudocode

```c

```

## disassembly

```asm
0x3a90  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x3a95  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor(class [mscorlib]System.Collections.IEqualityComparer)
0x3a9a  stloc.0
0x3a9b  ldarg.2
0x3a9c  ldstr    aPublishConfig// "publish.config"
0x3aa1  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x3aa6  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::LoadXmlDocumentFromFile(string)
0x3aab  dup
0x3aac  ldstr    aPublish// "/publish"
0x3ab1  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x3ab6  dup
0x3ab7  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x3abc  ldstr    aSignaturemajor// "signaturemajorversion"
0x3ac1  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x3ac6  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3acb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3ad0  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x3ad5  stloc.1
0x3ad6  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x3adb  ldstr    aSignatureminor// "signatureminorversion"
0x3ae0  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x3ae5  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3aea  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3aef  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x3af4  stloc.2
0x3af5  ldloc.1
0x3af6  ldloc.2
0x3af7  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32)
0x3afc  stloc.3
0x3afd  ldstr    aReport// "report"
0x3b02  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlDocument::GetElementsByTagName(string)
0x3b07  stloc.s  4
0x3b09  ldloc.s  4
0x3b0b  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x3b10  stloc.s  5
0x3b12  ldc.i4.0
0x3b13  stloc.s  6
0x3b15  ldstr    aMicrosoftCrmRe// "Microsoft.Crm.Reporting.Strings"
0x3b1a  ldtoken  Microsoft.Crm.Reporting.ReportServer
0x3b1f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3b24  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x3b29  newobj   instance void [mscorlib]System.Resources.ResourceManager::.ctor(string, class [mscorlib]System.Reflection.Assembly)
0x3b2e  stloc.s  7
0x3b30  ldarg.3
0x3b31  newobj   instance void [mscorlib]System.Globalization.CultureInfo::.ctor(int32)
0x3b36  stloc.s  8
0x3b38  ldloc.s  4
0x3b3a  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x3b3f  stloc.s  9
0x3b41  br       loc_3E5C
0x3b46  ldloc.s  9
0x3b48  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x3b4d  castclass [System.Xml]System.Xml.XmlNode
0x3b52  stloc.s  0xA
0x3b54  ldloc.s  0xA
0x3b56  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x3b5b  ldstr    aName_0// "name"
0x3b60  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x3b65  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3b6a  stloc.s  0xB
0x3b6c  ldloc.s  0xA
0x3b6e  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x3b73  ldstr    aFilename// "filename"
0x3b78  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x3b7d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3b82  stloc.s  0xC
0x3b84  ldloc.s  0xA
0x3b86  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x3b8b  ldstr    aDescription// "description"
0x3b90  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x3b95  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3b9a  stloc.s  0xD
0x3b9c  ldloca.s 0xE
0x3b9e  ldloc.s  0xA
0x3ba0  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x3ba5  ldstr    aSignatureid// "signatureid"
0x3baa  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x3baf  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3bb4  call     instance void [mscorlib]System.Guid::.ctor(string)
0x3bb9  ldarga.s 3
0x3bbb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3bc0  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x3bc5  ldloc.s  0xA
0x3bc7  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x3bcc  ldstr    aReportnameonsr// "reportnameonsrs"
0x3bd1  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x3bd6  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3bdb  call     string [mscorlib]System.String::Concat(string, string)
0x3be0  stloc.s  0xF
0x3be2  ldloc.s  0xA
0x3be4  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x3be9  ldsfld   string [mscorlib]System.String::Empty
0x3bee  stloc.s  0x10
0x3bf0  ldsfld   string [mscorlib]System.String::Empty
0x3bf5  stloc.s  0x11
0x3bf7  ldsfld   string [mscorlib]System.String::Empty
0x3bfc  stloc.s  0x12
0x3bfe  dup
0x3bff  ldstr    aShowin// "showin"
0x3c04  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x3c09  stloc.s  0x13
0x3c0b  ldloc.s  0x13
0x3c0d  brfalse.s loc_3C18
0x3c0f  ldloc.s  0x13
0x3c11  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3c16  stloc.s  0x10
0x3c18  dup
0x3c19  ldstr    aRelatedentity// "relatedentity"
0x3c1e  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x3c23  stloc.s  0x14
0x3c25  ldloc.s  0x14
0x3c27  brfalse.s loc_3C32
0x3c29  ldloc.s  0x14
0x3c2b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3c30  stloc.s  0x11
0x3c32  dup
0x3c33  ldstr    aCategory// "category"
0x3c38  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x3c3d  stloc.s  0x15
0x3c3f  ldloc.s  0x15
0x3c41  brfalse.s loc_3C4C
0x3c43  ldloc.s  0x15
0x3c45  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3c4a  stloc.s  0x12
0x3c4c  ldnull
0x3c4d  stloc.s  0x16
0x3c4f  ldstr    aParent// "parent"
0x3c54  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x3c59  stloc.s  0x17
0x3c5b  ldloc.s  0x17
0x3c5d  brfalse.s loc_3C6E
0x3c5f  ldloc.0
0x3c60  ldloc.s  0x17
0x3c62  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3c67  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x3c6c  stloc.s  0x16
0x3c6e  ldarg.0
0x3c6f  ldloc.s  0x11
0x3c71  ldarg.1
0x3c72  call     instance int32[] Microsoft.Crm.Reporting.ReportPublisher::BuildRelatedEntitiesValue(string relatedEntities, valuetype [mscorlib]System.Guid organizationId)
0x3c77  stloc.s  0x18
0x3c79  ldarg.0
0x3c7a  ldloc.s  0x12
0x3c7c  call     instance class [mscorlib]System.Collections.ArrayList Microsoft.Crm.Reporting.ReportPublisher::BuildCategoriesValue(string categories)
0x3c81  stloc.s  0x19
0x3c83  ldarg.0
0x3c84  ldloc.s  0x10
0x3c86  call     instance class [mscorlib]System.Collections.ArrayList Microsoft.Crm.Reporting.ReportPublisher::BuildVisibilitiesValue(string visibilities)
0x3c8b  stloc.s  0x1A
0x3c8d  ldarg.s  4
0x3c8f  brfalse.s loc_3CD8
0x3c91  ldarg.0
0x3c92  ldloc.s  0xE
0x3c94  ldloc.s  0xB
0x3c96  ldarg.s  4
0x3c98  ldarg.1
0x3c99  callvirt instance bool Microsoft.Crm.Reporting.ReportPublisher::CheckForMatchingReport(valuetype [mscorlib]System.Guid signatureId, string reportName, int32 matchCategoryNumber, valuetype [mscorlib]System.Guid organizationId)
0x3c9e  brfalse.s loc_3CD8
0x3ca0  ldloc.s  0x1A
0x3ca2  ldc.i4.2
0x3ca3  box      [mscorlib]System.Int32
0x3ca8  callvirt instance bool [mscorlib]System.Collections.ArrayList::Contains(object)
0x3cad  brfalse.s loc_3CBC
0x3caf  ldloc.s  0x1A
0x3cb1  ldc.i4.2
0x3cb2  box      [mscorlib]System.Int32
0x3cb7  callvirt instance void [mscorlib]System.Collections.ArrayList::Remove(object)
0x3cbc  ldloc.s  0x1A
0x3cbe  ldc.i4.3
0x3cbf  box      [mscorlib]System.Int32
0x3cc4  callvirt instance bool [mscorlib]System.Collections.ArrayList::Contains(object)
0x3cc9  brfalse.s loc_3CD8
0x3ccb  ldloc.s  0x1A
0x3ccd  ldc.i4.3
0x3cce  box      [mscorlib]System.Int32
0x3cd3  callvirt instance void [mscorlib]System.Collections.ArrayList::Remove(object)
0x3cd8  ldarg.s  5
0x3cda  brfalse.s loc_3CFB
0x3cdc  ldloc.s  0x19
0x3cde  ldarg.s  5
0x3ce0  box      [mscorlib]System.Int32
0x3ce5  callvirt instance bool [mscorlib]System.Collections.ArrayList::Contains(object)
0x3cea  brtrue.s loc_3CFB
0x3cec  ldloc.s  0x19
0x3cee  ldarg.s  5
0x3cf0  box      [mscorlib]System.Int32
0x3cf5  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x3cfa  pop
0x3cfb  ldloc.s  0x19
0x3cfd  ldtoken  [mscorlib]System.Int32
0x3d02  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d07  callvirt instance class [mscorlib]System.Array [mscorlib]System.Collections.ArrayList::ToArray(class [mscorlib]System.Type)
0x3d0c  castclass int32[]
0x3d11  stloc.s  0x1B
0x3d13  ldloc.s  0x1A
0x3d15  ldtoken  [mscorlib]System.Int32
0x3d1a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d1f  callvirt instance class [mscorlib]System.Array [mscorlib]System.Collections.ArrayList::ToArray(class [mscorlib]System.Type)
0x3d24  castclass int32[]
0x3d29  stloc.s  0x1C
0x3d2b  ldloc.s  6
0x3d2d  ldc.i4.1
0x3d2e  add
0x3d2f  stloc.s  6
0x3d31  ldarg.s  6
0x3d33  brfalse.s loc_3D5E
0x3d35  ldarg.s  6
0x3d37  ldloc.s  7
0x3d39  ldstr    aSrsPublisingre// "SRS.PublisingReport"
0x3d3e  ldloc.s  8
0x3d40  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3d45  ldstr    asc_B3EC// " "
0x3d4a  ldloc.s  0xB
0x3d4c  call     string [mscorlib]System.String::Concat(string, string, string)
0x3d51  ldloc.s  6
0x3d53  ldc.i4.s 0x64
0x3d55  mul
0x3d56  ldloc.s  5
0x3d58  div
0x3d59  callvirt instance void Microsoft.Crm.Reporting.IProgressEventSource::RaiseProgressChanged(string text, int32 value)
0x3d5e  ldc.i4.0
0x3d5f  stloc.s  0x1D
0x3d61  br       loc_3E54
0x3d66  nop
0x3d67  ldarg.0
0x3d68  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Reporting.ReportPublisher::get_Context()
0x3d6d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x3d72  ldc.i4.s 0x20
0x3d74  ldstr    aPublishingRepo// "Publishing report {0} (attempt {1})"
0x3d79  ldc.i4.2
0x3d7a  newarr   [mscorlib]System.Object
0x3d7f  dup
0x3d80  ldc.i4.0
0x3d81  ldloc.s  0xB
0x3d83  stelem.ref
0x3d84  dup
0x3d85  ldc.i4.1
0x3d86  ldloc.s  0x1D
0x3d88  box      [mscorlib]System.Int32
0x3d8d  stelem.ref
0x3d8e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3d93  ldarg.0
0x3d94  ldarg.2
0x3d95  ldloc.s  0xB
0x3d97  ldloc.s  0xC
0x3d99  ldloc.s  0xD
0x3d9b  ldarg.3
0x3d9c  ldloc.s  0x1B
0x3d9e  ldloc.s  0x18
0x3da0  ldloc.s  0x1C
0x3da2  ldloc.s  0x16
0x3da4  ldloc.s  0xE
0x3da6  ldloc.3
0x3da7  ldarg.1
0x3da8  ldloc.0
0x3da9  ldloc.s  0xF
0x3dab  ldarg.s  7
0x3dad  call     instance void Microsoft.Crm.Reporting.ReportPublisher::UploadReport(string reportFolder, string reportName, string fileName, string description, int32 languageCode, int32[] categoriesArray, int32[] relatedEntitiesArray, int32[] visibilitiesArray, object parentId, valuetype [mscorlib]System.Guid signatureId, class [mscorlib]System.Version version, valuetype [mscorlib]System.Guid organizationId, class [mscorlib]System.Collections.Hashtable reportsPublished, string reportNameOnSrs, bool isProvisioning)
0x3db2  ldarg.0
0x3db3  ldloc.s  7
0x3db5  ldstr    aSrsInfoPublish// "SRS.Info.PublishedReport"
0x3dba  ldloc.s  8
0x3dbc  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3dc1  ldc.i4.1
0x3dc2  newarr   [mscorlib]System.Object
0x3dc7  dup
0x3dc8  ldc.i4.0
0x3dc9  ldloc.s  0xB
0x3dcb  stelem.ref
0x3dcc  callvirt instance void Microsoft.Crm.Reporting.ReportPublisher::LogInfoFormat(string format, object[] args)
0x3dd1  leave    loc_3E5C
0x3dd6  stloc.s  0x1E
0x3dd8  ldloc.s  0x1D
0x3dda  ldc.i4.1
0x3ddb  blt.s    loc_3E14
0x3ddd  ldarg.0
0x3dde  ldloc.s  0x1E
0x3de0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3de5  ldloc.s  7
0x3de7  ldstr    aSrsWarningPubl// "SRS.Warning.PublishFailure"
0x3dec  ldloc.s  8
0x3dee  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3df3  ldc.i4.2
0x3df4  newarr   [mscorlib]System.Object
0x3df9  dup
0x3dfa  ldc.i4.0
0x3dfb  ldloc.s  0xB
0x3dfd  stelem.ref
0x3dfe  dup
0x3dff  ldc.i4.1
0x3e00  ldloc.s  0x1E
0x3e02  callvirt instance string [mscorlib]System.Exception::get_Message()
0x3e07  stelem.ref
0x3e08  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3e0d  callvirt instance void Microsoft.Crm.Reporting.ReportPublisher::OnPublishFail(class [mscorlib]System.Exception exception, string message)
0x3e12  br.s     loc_3E4C
0x3e14  ldarg.0
0x3e15  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Reporting.ReportPublisher::get_Context()
0x3e1a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x3e1f  ldc.i4.s 0x20
  ... truncated ...
```
