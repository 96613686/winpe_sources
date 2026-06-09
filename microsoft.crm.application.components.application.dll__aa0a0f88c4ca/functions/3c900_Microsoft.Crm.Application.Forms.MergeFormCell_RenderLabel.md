# Microsoft.Crm.Application.Forms.MergeFormCell::RenderLabel

- ea: `0x3c900`
- end: `0x3cb89`
- name: `Microsoft.Crm.Application.Forms.MergeFormCell::RenderLabel`
- size: `649`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x3cb90`

## callees

- `0x3c900`

## string_xrefs

- `0x3c950`: `ms-crm-Field-Recommended`
- `0x3ca6a`: `Forms.Recommended.AltTag`
- `0x3ca94`: `/_imgs/frm_recommended.gif`

## pseudocode

```c

```

## disassembly

```asm
0x3c900  ldarg.1
0x3c901  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x3c906  stloc.0
0x3c907  ldloc.0
0x3c908  ldstr    aTdClassFieldna// "<td class=\"fieldname "
0x3c90d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x3c912  ldarg.2
0x3c913  brfalse.s loc_3C93E
0x3c915  ldc.i4.1
0x3c916  ldarg.2
0x3c917  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.IAttributeMetadataAwareControl::get_Metadata()
0x3c91c  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AttributeRequiredLevelId()
0x3c921  beq.s    loc_3C931
0x3c923  ldc.i4.2
0x3c924  ldarg.2
0x3c925  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.IAttributeMetadataAwareControl::get_Metadata()
0x3c92a  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AttributeRequiredLevelId()
0x3c92f  bne.un.s loc_3C93E
0x3c931  ldloc.0
0x3c932  ldstr    aMsCrmFieldRequ// "ms-crm-Field-Required"
0x3c937  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x3c93c  br.s     loc_3C967
0x3c93e  ldarg.2
0x3c93f  brfalse.s loc_3C95C
0x3c941  ldc.i4.3
0x3c942  ldarg.2
0x3c943  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.IAttributeMetadataAwareControl::get_Metadata()
0x3c948  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AttributeRequiredLevelId()
0x3c94d  bne.un.s loc_3C95C
0x3c94f  ldloc.0
0x3c950  ldstr    aMsCrmFieldReco// "ms-crm-Field-Recommended"
0x3c955  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x3c95a  br.s     loc_3C967
0x3c95c  ldloc.0
0x3c95d  ldstr    aMsCrmFieldNorm// "ms-crm-Field-Normal"
0x3c962  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x3c967  ldloc.0
0x3c968  ldc.i4.s 0x22
0x3c96a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x3c96f  ldarg.2
0x3c970  brfalse.s loc_3C999
0x3c972  ldstr    aNtext// "ntext"
0x3c977  ldarg.2
0x3c978  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.IAttributeMetadataAwareControl::get_Metadata()
0x3c97d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0x3c982  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Name()
0x3c987  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3c98c  brfalse.s loc_3C999
0x3c98e  ldloc.0
0x3c98f  ldstr    aStyleVerticalA// " style=\"vertical-align:top;\""
0x3c994  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x3c999  ldloc.0
0x3c99a  ldarg.3
0x3c99b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x3c9a0  ldloc.0
0x3c9a1  ldc.i4.s 0x3E
0x3c9a3  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x3c9a8  ldloc.0
0x3c9a9  ldstr    aNobr// "<nobr>"
0x3c9ae  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x3c9b3  ldarg.0
0x3c9b4  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.CellDescriptor Microsoft.Crm.Application.Forms.MergeFormCell::_descriptor
0x3c9b9  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.LabelDescriptor [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormPartWithLabelDescriptor::get_UserLabel()
0x3c9be  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.LabelDescriptor::get_Description()
0x3c9c3  ldarg.1
0x3c9c4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string, class [mscorlib]System.IO.TextWriter)
0x3c9c9  ldarg.2
0x3c9ca  brfalse.s loc_3CA44
0x3c9cc  ldc.i4.1
0x3c9cd  ldarg.2
0x3c9ce  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.IAttributeMetadataAwareControl::get_Metadata()
0x3c9d3  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AttributeRequiredLevelId()
0x3c9d8  beq.s    loc_3C9E8
0x3c9da  ldc.i4.2
0x3c9db  ldarg.2
0x3c9dc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.IAttributeMetadataAwareControl::get_Metadata()
0x3c9e1  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AttributeRequiredLevelId()
0x3c9e6  bne.un.s loc_3CA44
0x3c9e8  ldloc.0
0x3c9e9  ldstr    aImg// "<img "
0x3c9ee  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x3c9f3  ldstr    aAlt// "alt"
0x3c9f8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3c9fd  ldstr    aFormsRequiredA// "Forms.Required.AltTag"
0x3ca02  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3ca07  ldarg.1
0x3ca08  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x3ca0d  ldstr    aSrc// "src"
0x3ca12  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x3ca17  ldc.i4.1
0x3ca18  newarr   [mscorlib]System.Char
0x3ca1d  dup
0x3ca1e  ldc.i4.0
0x3ca1f  ldc.i4.s 0x2F
0x3ca21  stelem.i2
0x3ca22  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x3ca27  ldstr    aImgsFrmRequire// "/_imgs/frm_required.gif"
0x3ca2c  call     string [mscorlib]System.String::Concat(string, string)
0x3ca31  ldarg.1
0x3ca32  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x3ca37  ldloc.0
0x3ca38  ldstr    asc_111DE8// "/>"
0x3ca3d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x3ca42  br.s     loc_3CAAF
0x3ca44  ldarg.2
0x3ca45  brfalse.s loc_3CAAF
0x3ca47  ldc.i4.3
0x3ca48  ldarg.2
0x3ca49  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.IAttributeMetadataAwareControl::get_Metadata()
0x3ca4e  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AttributeRequiredLevelId()
0x3ca53  bne.un.s loc_3CAAF
0x3ca55  ldloc.0
0x3ca56  ldstr    aImg// "<img "
0x3ca5b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x3ca60  ldstr    aAlt// "alt"
0x3ca65  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3ca6a  ldstr    aFormsRecommend// "Forms.Recommended.AltTag"
0x3ca6f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3ca74  ldarg.1
0x3ca75  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x3ca7a  ldstr    aSrc// "src"
0x3ca7f  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x3ca84  ldc.i4.1
0x3ca85  newarr   [mscorlib]System.Char
0x3ca8a  dup
0x3ca8b  ldc.i4.0
0x3ca8c  ldc.i4.s 0x2F
0x3ca8e  stelem.i2
0x3ca8f  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x3ca94  ldstr    aImgsFrmRecomme// "/_imgs/frm_recommended.gif"
0x3ca99  call     string [mscorlib]System.String::Concat(string, string)
0x3ca9e  ldarg.1
0x3ca9f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x3caa4  ldloc.0
0x3caa5  ldstr    asc_111DE8// "/>"
0x3caaa  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x3caaf  ldarg.2
0x3cab0  brfalse  loc_3CB7D
0x3cab5  ldarg.2
0x3cab6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.IAttributeMetadataAwareControl::get_Metadata()
0x3cabb  brfalse  loc_3CB7D
0x3cac0  ldarg.2
0x3cac1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.IAttributeMetadataAwareControl::get_Metadata()
0x3cac6  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_IsSecured()
0x3cacb  brtrue.s loc_3CB13
0x3cacd  ldarg.2
0x3cace  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.IAttributeMetadataAwareControl::get_Metadata()
0x3cad3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_YomiOf()
0x3cad8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3cadd  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3cae2  brfalse  loc_3CB7D
0x3cae7  ldarg.2
0x3cae8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.IAttributeMetadataAwareControl::get_Metadata()
0x3caed  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0x3caf2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesById()
0x3caf7  ldarg.2
0x3caf8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.IAttributeMetadataAwareControl::get_Metadata()
0x3cafd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_YomiOf()
0x3cb02  box      [mscorlib]System.Guid
0x3cb07  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Item(!!T0)
0x3cb0c  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_IsSecured()
0x3cb11  brfalse.s loc_3CB7D
0x3cb13  ldloc.0
0x3cb14  ldstr    aImg// "<img "
0x3cb19  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x3cb1e  ldstr    aAlt// "alt"
0x3cb23  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3cb28  ldstr    aFormsSecuredAl// "Forms.Secured.AltTag"
0x3cb2d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3cb32  ldarg.1
0x3cb33  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x3cb38  ldstr    aSrc// "src"
0x3cb3d  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x3cb42  ldc.i4.1
0x3cb43  newarr   [mscorlib]System.Char
0x3cb48  dup
0x3cb49  ldc.i4.0
0x3cb4a  ldc.i4.s 0x2F
0x3cb4c  stelem.i2
0x3cb4d  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x3cb52  ldstr    aImgsPermission// "/_imgs/permission_key.png"
0x3cb57  call     string [mscorlib]System.String::Concat(string, string)
0x3cb5c  ldarg.1
0x3cb5d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x3cb62  ldstr    aStyle_0// "style"
0x3cb67  ldstr    aVerticalAlignB// "vertical-align: bottom;"
0x3cb6c  ldarg.1
0x3cb6d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x3cb72  ldloc.0
0x3cb73  ldstr    asc_111DE8// "/>"
0x3cb78  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x3cb7d  ldloc.0
0x3cb7e  ldstr    aNobrTd// "</nobr></td>"
0x3cb83  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x3cb88  ret
```
