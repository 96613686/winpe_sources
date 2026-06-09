# Microsoft.Crm.Application.Controls.GridUIProvider::Render

- ea: `0x54a20`
- end: `0x551ec`
- name: `Microsoft.Crm.Application.Controls.GridUIProvider::Render`
- size: `1996`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x54930`
- `0x549e0`
- `0x54a00`
- `0x54a20`
- `0x551f0`
- `0x55b10`
- `0xcd890`

## string_xrefs

- `0x54d6b`: `SharePointSiteNotConfiguredError`
- `0x55064`: `folderpath`
- `0x55095`: `folderRenamed`

## pseudocode

```c

```

## disassembly

```asm
0x54a20  ldsfld   string [mscorlib]System.String::Empty
0x54a25  stloc.0
0x54a26  ldnull
0x54a27  stloc.1
0x54a28  ldnull
0x54a29  stloc.2
0x54a2a  ldnull
0x54a2b  stloc.3
0x54a2c  ldnull
0x54a2d  stloc.s  4
0x54a2f  newobj   instance void [System]System.Diagnostics.Stopwatch::.ctor()
0x54a34  stloc.s  5
0x54a36  ldloc.s  5
0x54a38  callvirt instance void [System]System.Diagnostics.Stopwatch::Reset()
0x54a3d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x54a42  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x54a47  ldc.i4.0
0x54a48  ldstr    a0_1// "{0}"
0x54a4d  ldc.i4.1
0x54a4e  newarr   [mscorlib]System.Object
0x54a53  dup
0x54a54  ldc.i4.0
0x54a55  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x54a5a  ldstr    aGriduiprovider// "GridUIProvider.Render entered at {0}:{1"...
0x54a5f  ldc.i4.3
0x54a60  newarr   [mscorlib]System.Object
0x54a65  dup
0x54a66  ldc.i4.0
0x54a67  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x54a6c  stloc.s  8
0x54a6e  ldloca.s 8
0x54a70  call     instance int32 [mscorlib]System.DateTime::get_Minute()
0x54a75  box      [mscorlib]System.Int32
0x54a7a  stelem.ref
0x54a7b  dup
0x54a7c  ldc.i4.1
0x54a7d  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x54a82  stloc.s  8
0x54a84  ldloca.s 8
0x54a86  call     instance int32 [mscorlib]System.DateTime::get_Second()
0x54a8b  box      [mscorlib]System.Int32
0x54a90  stelem.ref
0x54a91  dup
0x54a92  ldc.i4.2
0x54a93  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x54a98  stloc.s  8
0x54a9a  ldloca.s 8
0x54a9c  call     instance int32 [mscorlib]System.DateTime::get_Millisecond()
0x54aa1  box      [mscorlib]System.Int32
0x54aa6  stelem.ref
0x54aa7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x54aac  stelem.ref
0x54aad  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x54ab2  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridData::.ctor()
0x54ab7  stloc.s  6
0x54ab9  ldloc.s  5
0x54abb  callvirt instance void [System]System.Diagnostics.Stopwatch::Start()
0x54ac0  ldarg.0
0x54ac1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProvider Microsoft.Crm.Application.Controls.GridUIProvider::get_DataSource()
0x54ac6  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridData [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProvider::PrepareData()
0x54acb  stloc.s  6
0x54acd  ldarg.0
0x54ace  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProvider Microsoft.Crm.Application.Controls.GridUIProvider::get_DataSource()
0x54ad3  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridProvider::get_Parameters()
0x54ad8  ldstr    aEmptyview// "EmptyView"
0x54add  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x54ae2  brfalse.s loc_54B2E
0x54ae4  ldarg.0
0x54ae5  ldarg.0
0x54ae6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProvider Microsoft.Crm.Application.Controls.GridUIProvider::get_DataSource()
0x54aeb  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridProvider::get_Parameters()
0x54af0  ldstr    aEmptyviewmessa// "EmptyViewMessage"
0x54af5  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x54afa  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x54aff  stfld    string Microsoft.Crm.Application.Controls.GridUIProvider::_errorMessageHtml
0x54b04  ldarg.0
0x54b05  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProvider Microsoft.Crm.Application.Controls.GridUIProvider::get_DataSource()
0x54b0a  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridProvider::get_Parameters()
0x54b0f  ldstr    aEmptyview// "EmptyView"
0x54b14  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x54b19  ldarg.0
0x54b1a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProvider Microsoft.Crm.Application.Controls.GridUIProvider::get_DataSource()
0x54b1f  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridProvider::get_Parameters()
0x54b24  ldstr    aEmptyviewmessa// "EmptyViewMessage"
0x54b29  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x54b2e  ldarg.0
0x54b2f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProvider Microsoft.Crm.Application.Controls.GridUIProvider::get_DataSource()
0x54b34  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridProvider::get_Parameters()
0x54b39  ldstr    aLoadondemand// "LoadOnDemand"
0x54b3e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x54b43  ldstr    a1_0// "1"
0x54b48  call     bool [mscorlib]System.String::op_Equality(string, string)
0x54b4d  brfalse.s loc_54BA0
0x54b4f  ldarg.0
0x54b50  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProvider Microsoft.Crm.Application.Controls.GridUIProvider::get_DataSource()
0x54b55  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridProvider::get_Parameters()
0x54b5a  ldstr    aRenderasync// "RenderAsync"
0x54b5f  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x54b64  ldstr    a1_0// "1"
0x54b69  call     bool [mscorlib]System.String::op_Equality(string, string)
0x54b6e  brfalse.s loc_54BA0
0x54b70  ldarg.0
0x54b71  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x54b76  ldstr    aGridloaddata// "GridLoadData"
0x54b7b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x54b80  stfld    string Microsoft.Crm.Application.Controls.GridUIProvider::_loadOnDemandGridEmptyMessage
0x54b85  ldarg.0
0x54b86  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProvider Microsoft.Crm.Application.Controls.GridUIProvider::get_DataSource()
0x54b8b  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridProvider::get_Parameters()
0x54b90  ldstr    aLoadondemandGr// "LoadOnDemand_GridEmptyMessage"
0x54b95  ldarg.0
0x54b96  ldfld    string Microsoft.Crm.Application.Controls.GridUIProvider::_loadOnDemandGridEmptyMessage
0x54b9b  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x54ba0  ldarg.0
0x54ba1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProvider Microsoft.Crm.Application.Controls.GridUIProvider::get_DataSource()
0x54ba6  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridProvider::get_Parameters()
0x54bab  ldstr    aLoadondemand// "LoadOnDemand"
0x54bb0  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x54bb5  ldstr    a1_0// "1"
0x54bba  call     bool [mscorlib]System.String::op_Equality(string, string)
0x54bbf  brfalse.s loc_54BDC
0x54bc1  ldarg.0
0x54bc2  ldarg.0
0x54bc3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProvider Microsoft.Crm.Application.Controls.GridUIProvider::get_DataSource()
0x54bc8  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridProvider::get_Parameters()
0x54bcd  ldstr    aLoadondemandGr// "LoadOnDemand_GridEmptyMessage"
0x54bd2  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x54bd7  stfld    string Microsoft.Crm.Application.Controls.GridUIProvider::_loadOnDemandGridEmptyMessage
0x54bdc  ldloc.s  6
0x54bde  callvirt instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridData::get_DataType()
0x54be3  ldc.i4.2
0x54be4  bne.un.s loc_54C0F
0x54be6  ldarg.0
0x54be7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProvider Microsoft.Crm.Application.Controls.GridUIProvider::get_DataSource()
0x54bec  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridProvider::get_Parameters()
0x54bf1  ldstr    aOtn// "otn"
0x54bf6  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x54bfb  ldstr    aOfficegraphdoc// "officegraphdocument"
0x54c00  call     bool [mscorlib]System.String::op_Equality(string, string)
0x54c05  brfalse.s loc_54C0F
0x54c07  ldloc.s  6
0x54c09  ldc.i4.3
0x54c0a  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridData::set_DataType(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataType)
0x54c0f  leave    loc_54F75
0x54c14  stloc.s  9
0x54c16  ldloc.s  9
0x54c18  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x54c1d  ldc.i4   0x80040220
0x54c22  bne.un.s loc_54C5C
0x54c24  ldloc.s  6
0x54c26  ldc.i4.1
0x54c27  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridData::set_DataType(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataType)
0x54c2c  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorLookup::.ctor()
0x54c31  ldc.i4   0x80040220
0x54c36  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x54c3b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorData [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorLookup::GetError(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x54c40  stloc.s  0xA
0x54c42  ldarg.0
0x54c43  ldloc.s  0xA
0x54c45  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorData::get_MessageHtml()
0x54c4a  stfld    string Microsoft.Crm.Application.Controls.GridUIProvider::_errorMessageHtml
0x54c4f  ldloc.s  0xA
0x54c51  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorData::get_Message()
0x54c56  stloc.0
0x54c57  br       loc_54F73
0x54c5c  ldloc.s  9
0x54c5e  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x54c63  ldc.i4   0x80044181
0x54c68  bne.un   loc_54D01
0x54c6d  ldarg.0
0x54c6e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProvider Microsoft.Crm.Application.Controls.GridUIProvider::get_DataSource()
0x54c73  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridProvider::get_Parameters()
0x54c78  ldstr    aOtn// "otn"
0x54c7d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x54c82  ldstr    aOfficegraphdoc// "officegraphdocument"
0x54c87  call     bool [mscorlib]System.String::op_Equality(string, string)
0x54c8c  brfalse.s loc_54CC9
0x54c8e  ldloc.s  6
0x54c90  ldc.i4.1
0x54c91  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridData::set_DataType(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataType)
0x54c96  ldloc.s  6
0x54c98  callvirt instance class [System.Data]System.Data.DataTable [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridData::get_Data()
0x54c9d  callvirt instance class [System.Data]System.Data.PropertyCollection [System.Data]System.Data.DataTable::get_ExtendedProperties()
0x54ca2  ldstr    aErrorcode// "ErrorCode"
0x54ca7  ldc.i4   0x80044258
0x54cac  box      [mscorlib]System.Int32
0x54cb1  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x54cb6  ldarg.0
0x54cb7  ldloc.s  6
0x54cb9  call     instance class Microsoft.Crm.Application.Controls.Grid.UI.LayoutProvider Microsoft.Crm.Application.Controls.GridUIProvider::CreateLayoutProvider(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridData gridData)
0x54cbe  ldarg.1
0x54cbf  callvirt instance void Microsoft.Crm.Application.Controls.Grid.UI.LayoutProvider::Render(class [System.Web]System.Web.UI.HtmlTextWriter output)
0x54cc4  br       loc_54F73
0x54cc9  ldloc.s  6
0x54ccb  ldc.i4.1
0x54ccc  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridData::set_DataType(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataType)
0x54cd1  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorLookup::.ctor()
0x54cd6  ldc.i4   0x8063110F
0x54cdb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x54ce0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorData [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorLookup::GetError(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x54ce5  stloc.s  0xB
0x54ce7  ldarg.0
0x54ce8  ldloc.s  0xB
0x54cea  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorData::get_MessageHtml()
0x54cef  stfld    string Microsoft.Crm.Application.Controls.GridUIProvider::_errorMessageHtml
0x54cf4  ldloc.s  0xB
0x54cf6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorData::get_Message()
0x54cfb  stloc.0
0x54cfc  br       loc_54F73
0x54d01  ldloc.s  9
0x54d03  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x54d08  ldc.i4   0x8006071B
0x54d0d  bne.un.s loc_54D4F
0x54d0f  ldloc.s  6
0x54d11  ldc.i4.1
0x54d12  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridData::set_DataType(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataType)
0x54d17  ldarg.0
0x54d18  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x54d1d  ldstr    aSharepointfold// "SharePointFolderNotFoundError"
0x54d22  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x54d27  dup
0x54d28  stloc.s  0xC
0x54d2a  stfld    string Microsoft.Crm.Application.Controls.GridUIProvider::_errorMessageHtml
0x54d2f  ldloc.s  0xC
0x54d31  stloc.0
0x54d32  ldloc.s  9
0x54d34  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<object, object> [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_CrmExceptionData()
0x54d39  ldc.i4.0
0x54d3a  box      [mscorlib]System.Int32
0x54d3f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<object, object>::get_Item(void)
0x54d44  callvirt instance string [mscorlib]System.Object::ToString()
0x54d49  stloc.1
0x54d4a  br       loc_54F73
0x54d4f  ldloc.s  9
0x54d51  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x54d56  ldc.i4   0x8006071A
0x54d5b  bne.un.s loc_54D87
0x54d5d  ldloc.s  6
0x54d5f  ldc.i4.1
0x54d60  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridData::set_DataType(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataType)
0x54d65  ldarg.0
0x54d66  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x54d6b  ldstr    aSharepointsite_0// "SharePointSiteNotConfiguredError"
0x54d70  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x54d75  dup
0x54d76  stloc.s  0xC
0x54d78  stfld    string Microsoft.Crm.Application.Controls.GridUIProvider::_errorMessageHtml
0x54d7d  ldloc.s  0xC
0x54d7f  dup
0x54d80  stloc.3
0x54d81  stloc.0
0x54d82  br       loc_54F73
0x54d87  ldloc.s  9
0x54d89  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x54d8e  ldc.i4   0x8006071C
0x54d93  bne.un.s loc_54DBF
0x54d95  ldloc.s  6
0x54d97  ldc.i4.1
0x54d98  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridData::set_DataType(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataType)
0x54d9d  ldarg.0
0x54d9e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x54da3  ldstr    aNoactivedocume// "NoActiveDocumentLocation"
0x54da8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x54dad  dup
0x54dae  stloc.s  0xC
0x54db0  stfld    string Microsoft.Crm.Application.Controls.GridUIProvider::_errorMessageHtml
0x54db5  ldloc.s  0xC
0x54db7  dup
0x54db8  stloc.0
0x54db9  stloc.2
0x54dba  br       loc_54F73
0x54dbf  ldloc.s  9
0x54dc1  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x54dc6  ldc.i4   0x80060720
0x54dcb  bne.un.s loc_54DF7
0x54dcd  ldloc.s  6
0x54dcf  ldc.i4.1
0x54dd0  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridData::set_DataType(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataType)
0x54dd5  ldarg.0
0x54dd6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x54ddb  ldstr    aCurrentdocumen// "CurrentDocumentLocationDeactive"
0x54de0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x54de5  dup
0x54de6  stloc.s  0xC
0x54de8  stfld    string Microsoft.Crm.Application.Controls.GridUIProvider::_errorMessageHtml
0x54ded  ldloc.s  0xC
0x54def  dup
0x54df0  stloc.0
0x54df1  stloc.2
0x54df2  br       loc_54F73
0x54df7  ldloc.s  9
0x54df9  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x54dfe  ldc.i4   0x80060729
0x54e03  bne.un.s loc_54E30
0x54e05  ldloc.s  6
0x54e07  ldc.i4.1
0x54e08  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridData::set_DataType(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataType)
0x54e0d  ldarg.0
0x54e0e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x54e13  ldstr    aErrorMessage0x_2// "Error_Message_0x80060729"
  ... truncated ...
```
