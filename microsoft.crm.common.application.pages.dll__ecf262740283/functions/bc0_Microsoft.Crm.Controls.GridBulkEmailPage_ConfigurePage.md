# Microsoft.Crm.Controls.GridBulkEmailPage::ConfigurePage

- ea: `0xbc0`
- end: `0xf85`
- name: `Microsoft.Crm.Controls.GridBulkEmailPage::ConfigurePage`
- size: `965`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xbc0`

## string_xrefs

- `0xecc`: `template`
- `0xeeb`: `template`

## pseudocode

```c

```

## disassembly

```asm
0xbc0  ldarg.0
0xbc1  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xbc6  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0xbcb  stloc.0
0xbcc  ldloc.0
0xbcd  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0xbd2  ldc.i4.0
0xbd3  conv.i8
0xbd4  ble      loc_F7C
0xbd9  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderQueryBuilder::.ctor()
0xbde  stloc.1
0xbdf  ldarg.0
0xbe0  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xbe5  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xbea  ldstr    aMultipage// "multiPage"
0xbef  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xbf4  ldstr    aFalse// "false"
0xbf9  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbfe  stloc.2
0xbff  ldc.i4   0x40F
0xc04  stloc.3
0xc05  ldsfld   string [mscorlib]System.String::Empty
0xc0a  stloc.s  4
0xc0c  ldc.i4.0
0xc0d  stloc.s  5
0xc0f  newobj   instance void [System]System.Collections.Specialized.NameValueCollection::.ctor()
0xc14  stloc.s  6
0xc16  ldloc.0
0xc17  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [mscorlib]System.IO.Stream)
0xc1c  stloc.s  7
0xc1e  br       loc_DDF
0xc23  ldloc.s  7
0xc25  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xc2a  ldc.i4.1
0xc2b  bne.un   loc_DDF
0xc30  ldloc.s  7
0xc32  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0xc37  brtrue   loc_DDF
0xc3c  ldloc.s  7
0xc3e  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xc43  stloc.s  0xC
0xc45  ldloc.s  0xC
0xc47  ldstr    aPagenum// "pageNum"
0xc4c  call     bool [mscorlib]System.String::op_Equality(string, string)
0xc51  brtrue.s loc_C88
0xc53  ldloc.s  0xC
0xc55  ldstr    aRecsperpage// "recsPerPage"
0xc5a  call     bool [mscorlib]System.String::op_Equality(string, string)
0xc5f  brtrue.s loc_CBB
0xc61  ldloc.s  0xC
0xc63  ldstr    aSortcolumns// "sortColumns"
0xc68  call     bool [mscorlib]System.String::op_Equality(string, string)
0xc6d  brtrue   loc_CF2
0xc72  ldloc.s  0xC
0xc74  ldstr    aParameters// "parameters"
0xc79  call     bool [mscorlib]System.String::op_Equality(string, string)
0xc7e  brtrue   loc_DD3
0xc83  br       loc_DDF
0xc88  ldloc.2
0xc89  brfalse.s loc_CAF
0xc8b  ldloc.s  7
0xc8d  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0xc92  pop
0xc93  ldloc.1
0xc94  ldloc.s  7
0xc96  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Value()
0xc9b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xca0  call     unsigned int32 [mscorlib]System.UInt32::Parse(string, class [mscorlib]System.IFormatProvider)
0xca5  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::set_PageNumber(unsigned int32)
0xcaa  br       loc_DDF
0xcaf  ldloc.1
0xcb0  ldc.i4.1
0xcb1  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::set_PageNumber(unsigned int32)
0xcb6  br       loc_DDF
0xcbb  ldloc.2
0xcbc  brfalse.s loc_CE2
0xcbe  ldloc.s  7
0xcc0  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0xcc5  pop
0xcc6  ldloc.1
0xcc7  ldloc.s  7
0xcc9  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Value()
0xcce  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xcd3  call     unsigned int32 [mscorlib]System.UInt32::Parse(string, class [mscorlib]System.IFormatProvider)
0xcd8  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::set_RecordsPerPage(unsigned int32)
0xcdd  br       loc_DDF
0xce2  ldloc.1
0xce3  ldc.i4   0x1F4
0xce8  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::set_RecordsPerPage(unsigned int32)
0xced  br       loc_DDF
0xcf2  ldloc.s  7
0xcf4  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0xcf9  pop
0xcfa  ldloc.1
0xcfb  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.GridSortColumnCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_SortColumns()
0xd00  ldloc.s  7
0xd02  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Value()
0xd07  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.GridSortColumnCollection::DeserializeFromGridParameter(string)
0xd0c  br       loc_DDF
0xd11  ldloc.s  7
0xd13  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xd18  ldc.i4.1
0xd19  bne.un   loc_DAB
0xd1e  ldloc.s  7
0xd20  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0xd25  brtrue   loc_DAB
0xd2a  ldloc.s  7
0xd2c  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xd31  stloc.s  0xD
0xd33  ldloc.s  7
0xd35  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0xd3a  pop
0xd3b  ldloc.s  7
0xd3d  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Value()
0xd42  stloc.s  0xE
0xd44  ldloc.s  6
0xd46  ldloc.s  0xD
0xd48  ldloc.s  0xE
0xd4a  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0xd4f  ldloc.s  0xD
0xd51  ldstr    aViewid// "viewid"
0xd56  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd5b  brtrue.s loc_D7B
0xd5d  ldloc.s  0xD
0xd5f  ldstr    aViewtype// "viewtype"
0xd64  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd69  brtrue.s loc_D81
0xd6b  ldloc.s  0xD
0xd6d  ldstr    aOtc// "otc"
0xd72  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd77  brtrue.s loc_D9B
0xd79  br.s     loc_DD3
0xd7b  ldloc.s  0xE
0xd7d  stloc.s  4
0xd7f  br.s     loc_DD3
0xd81  ldloc.3
0xd82  box      [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewType
0xd87  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xd8c  ldloc.s  0xE
0xd8e  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0xd93  unbox.any [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewType
0xd98  stloc.3
0xd99  br.s     loc_DD3
0xd9b  ldloc.s  0xE
0xd9d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xda2  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0xda7  stloc.s  5
0xda9  br.s     loc_DD3
0xdab  ldloc.s  7
0xdad  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xdb2  ldc.i4.s 0xF
0xdb4  bne.un.s loc_DD3
0xdb6  ldloc.s  7
0xdb8  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xdbd  ldstr    aParameters// "parameters"
0xdc2  call     bool [mscorlib]System.String::op_Equality(string, string)
0xdc7  brfalse.s loc_DD3
0xdc9  ldloc.1
0xdca  ldloc.s  6
0xdcc  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::AddParameters(class [System]System.Collections.Specialized.NameValueCollection)
0xdd1  br.s     loc_DDF
0xdd3  ldloc.s  7
0xdd5  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0xdda  brtrue   loc_D11
0xddf  ldloc.s  7
0xde1  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0xde6  brtrue   loc_C23
0xdeb  ldloc.s  7
0xded  callvirt instance void [System.Xml]System.Xml.XmlReader::Close()
0xdf2  ldloc.s  4
0xdf4  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xdf9  ldloc.3
0xdfa  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.View [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Caching.ViewLoader::GetView(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewType)
0xdff  stloc.s  8
0xe01  ldloc.s  8
0xe03  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.View::get_IdColumnName()
0xe08  stloc.s  9
0xe0a  ldarg.0
0xe0b  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0xe10  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0xe15  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0xe1a  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xe1f  ldloc.s  8
0xe21  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.View::get_ObjectType()
0xe26  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe2b  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0xe30  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0xe35  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xe3a  stloc.s  0xA
0xe3c  ldloc.1
0xe3d  ldloc.s  9
0xe3f  ldloc.s  0xA
0xe41  ldstr    asc_1F1DE// ""
0xe46  ldc.i4.0
0xe47  ldc.i4.0
0xe48  ldc.i4.0
0xe49  ldc.i4.0
0xe4a  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::AddColumn(string, string, string, unsigned int32, bool, bool, bool)
0xe4f  ldc.i4   0x200
0xe54  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor(int32)
0xe59  stloc.s  0xB
0xe5b  ldloc.1
0xe5c  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::Execute()
0xe61  br.s     loc_E84
0xe63  ldloc.s  0xB
0xe65  ldloc.1
0xe66  callvirt instance class [System.Data]System.Data.DataRow [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Current()
0xe6b  ldstr    aRowid// "RowId"
0xe70  callvirt instance object [System.Data]System.Data.DataRow::get_Item(string)
0xe75  castclass [mscorlib]System.String
0xe7a  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xe7f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0xe84  ldloc.1
0xe85  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::MoveNext()
0xe8a  brtrue.s loc_E63
0xe8c  ldloc.1
0xe8d  dup
0xe8e  callvirt instance unsigned int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_PageNumber()
0xe93  stloc.s  0xF
0xe95  ldloc.s  0xF
0xe97  ldc.i4.1
0xe98  add
0xe99  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::set_PageNumber(unsigned int32)
0xe9e  ldloc.1
0xe9f  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::Reset()
0xea4  ldloc.1
0xea5  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridData [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Results()
0xeaa  callvirt instance class [System.Data]System.Data.DataTable [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridData::get_Data()
0xeaf  callvirt instance void [System.Data]System.Data.DataTable::Clear()
0xeb4  ldloc.1
0xeb5  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_MoreRecords()
0xeba  brfalse.s loc_EBF
0xebc  ldloc.2
0xebd  brfalse.s loc_E5B
0xebf  ldloc.s  0xB
0xec1  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0xec6  ldc.i4.0
0xec7  ble      loc_F56
0xecc  ldstr    aTemplate// "template"
0xed1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xed6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xedb  newobj   instance void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.Template::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0xee0  ldarg.0
0xee1  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xee6  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xeeb  ldstr    aTemplate// "template"
0xef0  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xef5  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xefa  stloc.s  0x11
0xefc  ldloca.s 0x11
0xefe  ldstr    aB// "B"
0xf03  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf08  call     instance string [mscorlib]System.Guid::ToString(string, class [mscorlib]System.IFormatProvider)
0xf0d  stloc.s  0x10
0xf0f  ldloc.s  0x10
0xf11  ldarg.0
0xf12  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xf17  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xf1c  ldstr    aFromid// "fromId"
0xf21  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xf26  ldarg.0
0xf27  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xf2c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xf31  ldstr    aFromtype// "fromType"
0xf36  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xf3b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf40  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0xf45  ldloc.s  5
0xf47  ldloc.s  0xB
0xf49  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::ToArray()
0xf4e  ldloc.s  5
0xf50  ldnull
0xf51  callvirt instance void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.Template::Send(string, string, int32, int32, valuetype [mscorlib]System.Guid[], int32, string)
0xf56  ldarg.0
0xf57  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0xf5c  callvirt instance void [System.Web]System.Web.HttpResponse::Clear()
0xf61  ldarg.0
0xf62  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0xf67  ldstr    aOk// "<ok/>"
0xf6c  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0xf71  ldarg.0
0xf72  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0xf77  callvirt instance void [System.Web]System.Web.HttpResponse::End()
0xf7c  leave.s  loc_F84
0xf7e  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0xf83  throw
0xf84  ret
```
