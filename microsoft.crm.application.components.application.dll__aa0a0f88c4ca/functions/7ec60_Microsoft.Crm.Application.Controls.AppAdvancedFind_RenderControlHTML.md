# Microsoft.Crm.Application.Controls.AppAdvancedFind::RenderControlHTML

- ea: `0x7ec60`
- end: `0x7f5ce`
- name: `Microsoft.Crm.Application.Controls.AppAdvancedFind::RenderControlHTML`
- size: `2414`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x7f5d0`

## callees

- `0x7e1b0`
- `0x7e1d0`
- `0x7e1f0`
- `0x7e230`
- `0x7e2c0`
- `0x7e560`
- `0x7eb70`
- `0x7ec60`

## string_xrefs

- `0x7ecbd`: `<div style="position:{0};top:0px;bottom:0px;left:0px;right:0px;" ReadOnlyMode="{1}"`
- `0x7edb8`: ` CanWriteUserQuery=`
- `0x7ede1`: ` CanCreateUserQuery=`
- `0x7f419`: `<div id="AdvFindDetailed" class="ms-crm-AdvFindDetailed-Container" style="top:{0}px !important; overflow-y:auto;{1}" ReadOnlyMode="{2}"><span id="spnInlineMsg" class="ms-crm-AdvFind-Message"></span><span id="spnDetailed" class="`

## pseudocode

```c

```

## disassembly

```asm
0x7ec60  ldarg.0
0x7ec61  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.AdvancedFindModes Microsoft.Crm.Application.Controls.AppAdvancedFind::_modes
0x7ec66  ldarg.0
0x7ec67  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.AdvancedFindStartupMode Microsoft.Crm.Application.Controls.AppAdvancedFind::_startupMode
0x7ec6c  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x7ec71  ldstr    aInvalidAdvance// "Invalid advanced find startup mode. The"...
0x7ec76  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x7ec7b  ldarg.1
0x7ec7c  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x7ec81  stloc.0
0x7ec82  ldarg.0
0x7ec83  callvirt instance bool [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x7ec88  brfalse.s loc_7ECB7
0x7ec8a  ldloc.0
0x7ec8b  ldstr    aSpanClassMsCrm_6// "<span class=\"ms-crm-AdvFind-MsgDisable"...
0x7ec90  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x7ec95  ldarg.0
0x7ec96  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AppAdvancedFind::_rm
0x7ec9b  ldstr    aAfMessageNoPri// "AF_Message_No_Priv_Any_Enitity"
0x7eca0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7eca5  ldloc.0
0x7eca6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string, class [mscorlib]System.IO.TextWriter)
0x7ecab  ldloc.0
0x7ecac  ldstr    aSpan// "</span>"
0x7ecb1  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x7ecb6  ret
0x7ecb7  ldloc.0
0x7ecb8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7ecbd  ldstr    aDivStylePositi_0// "<div style=\"position:{0};top:0px;botto"...
0x7ecc2  ldc.i4.2
0x7ecc3  newarr   [mscorlib]System.Object
0x7ecc8  dup
0x7ecc9  ldc.i4.0
0x7ecca  ldarg.0
0x7eccb  call     instance bool Microsoft.Crm.Application.Controls.AppAdvancedFind::get_ShowOnlyFilterControl()
0x7ecd0  brtrue.s loc_7ECD9
0x7ecd2  ldstr    aAbsolute// "absolute"
0x7ecd7  br.s     loc_7ECDE
0x7ecd9  ldstr    aRelative// "relative"
0x7ecde  stelem.ref
0x7ecdf  dup
0x7ece0  ldc.i4.1
0x7ece1  ldarg.0
0x7ece2  call     instance bool Microsoft.Crm.Application.Controls.AppAdvancedFind::get_IsReadOnly()
0x7ece7  brtrue.s loc_7ECF0
0x7ece9  ldstr    a0// "0"
0x7ecee  br.s     loc_7ECF5
0x7ecf0  ldstr    a1_0// "1"
0x7ecf5  stelem.ref
0x7ecf6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7ecfb  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x7ed00  ldstr    aId_1// "id"
0x7ed05  ldarg.0
0x7ed06  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x7ed0b  ldarg.1
0x7ed0c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x7ed11  ldloc.0
0x7ed12  ldstr    aClass_1// " class=\""
0x7ed17  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x7ed1c  ldarg.0
0x7ed1d  ldfld    bool Microsoft.Crm.Application.Controls.AppAdvancedFind::_expandable
0x7ed22  brfalse.s loc_7ED31
0x7ed24  ldloc.0
0x7ed25  ldstr    aMsCrmAdvfindco// "ms-crm-AdvFindControlEx"
0x7ed2a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x7ed2f  br.s     loc_7ED3C
0x7ed31  ldloc.0
0x7ed32  ldstr    aMsCrmAdvfindco_0// "ms-crm-AdvFindControl"
0x7ed37  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x7ed3c  ldloc.0
0x7ed3d  ldstr    aMode_0// "\" Mode="
0x7ed42  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x7ed47  ldloc.0
0x7ed48  ldarg.0
0x7ed49  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.AdvancedFindStartupMode Microsoft.Crm.Application.Controls.AppAdvancedFind::_startupMode
0x7ed4e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(unsigned int32)
0x7ed53  ldloc.0
0x7ed54  ldstr    aModes// " Modes="
0x7ed59  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x7ed5e  ldloc.0
0x7ed5f  ldarg.0
0x7ed60  call     instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.AdvancedFindModes Microsoft.Crm.Application.Controls.AppAdvancedFind::get_Modes()
0x7ed65  callvirt instance void [mscorlib]System.IO.TextWriter::Write(unsigned int32)
0x7ed6a  ldloc.0
0x7ed6b  ldstr    aButtons// " Buttons="
0x7ed70  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x7ed75  ldloc.0
0x7ed76  ldarg.0
0x7ed77  ldfld    valuetype Microsoft.Crm.Application.Controls.AdvancedFindButtons Microsoft.Crm.Application.Controls.AppAdvancedFind::_buttons
0x7ed7c  callvirt instance void [mscorlib]System.IO.TextWriter::Write(unsigned int32)
0x7ed81  ldloc.0
0x7ed82  ldstr    aFetchmode// " FetchMode="
0x7ed87  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x7ed8c  ldloc.0
0x7ed8d  ldarg.0
0x7ed8e  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.AdvancedFindFetchMode Microsoft.Crm.Application.Controls.AppAdvancedFind::_fetchMode
0x7ed93  callvirt instance void [mscorlib]System.IO.TextWriter::Write(unsigned int32)
0x7ed98  ldloc.0
0x7ed99  ldstr    aIncludeapiquer// " IncludeAPIQuery="
0x7ed9e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x7eda3  ldloc.0
0x7eda4  ldarg.0
0x7eda5  ldfld    bool Microsoft.Crm.Application.Controls.AppAdvancedFind::_includeApiQuery
0x7edaa  brtrue.s loc_7EDB0
0x7edac  ldc.i4.s 0x30
0x7edae  br.s     loc_7EDB2
0x7edb0  ldc.i4.s 0x31
0x7edb2  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x7edb7  ldloc.0
0x7edb8  ldstr    aCanwriteuserqu// " CanWriteUserQuery="
0x7edbd  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x7edc2  ldloc.0
0x7edc3  ldstr    aUserquery// "userquery"
0x7edc8  ldc.i4.2
0x7edc9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x7edce  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::HasPrivilege(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7edd3  brtrue.s loc_7EDD9
0x7edd5  ldc.i4.s 0x30
0x7edd7  br.s     loc_7EDDB
0x7edd9  ldc.i4.s 0x31
0x7eddb  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x7ede0  ldloc.0
0x7ede1  ldstr    aCancreateuserq// " CanCreateUserQuery="
0x7ede6  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x7edeb  ldloc.0
0x7edec  ldstr    aUserquery// "userquery"
0x7edf1  ldc.i4.s 0x20
0x7edf3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x7edf8  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::HasPrivilege(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7edfd  brtrue.s loc_7EE03
0x7edff  ldc.i4.s 0x30
0x7ee01  br.s     loc_7EE05
0x7ee03  ldc.i4.s 0x31
0x7ee05  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x7ee0a  ldloc.0
0x7ee0b  ldstr    aQuerylistvisib// " QueryListVisible="
0x7ee10  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x7ee15  ldloc.0
0x7ee16  ldarg.0
0x7ee17  ldfld    bool Microsoft.Crm.Application.Controls.AppAdvancedFind::_queryListVisible
0x7ee1c  brtrue.s loc_7EE22
0x7ee1e  ldc.i4.s 0x30
0x7ee20  br.s     loc_7EE24
0x7ee22  ldc.i4.s 0x31
0x7ee24  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x7ee29  ldloc.0
0x7ee2a  ldstr    aRelatedentitie// " RelatedEntitiesVisible="
0x7ee2f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x7ee34  ldloc.0
0x7ee35  ldarg.0
0x7ee36  ldfld    bool Microsoft.Crm.Application.Controls.AppAdvancedFind::_relatedEntitiesVisible
0x7ee3b  brtrue.s loc_7EE41
0x7ee3d  ldc.i4.s 0x30
0x7ee3f  br.s     loc_7EE43
0x7ee41  ldc.i4.s 0x31
0x7ee43  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x7ee48  ldloc.0
0x7ee49  ldstr    aEntitylistvisi// " EntityListVisible="
0x7ee4e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x7ee53  ldloc.0
0x7ee54  ldarg.0
0x7ee55  ldfld    bool Microsoft.Crm.Application.Controls.AppAdvancedFind::_entityListVisible
0x7ee5a  brtrue.s loc_7EE60
0x7ee5c  ldc.i4.s 0x30
0x7ee5e  br.s     loc_7EE62
0x7ee60  ldc.i4.s 0x31
0x7ee62  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x7ee67  ldloc.0
0x7ee68  ldstr    aTitlevisible// " TitleVisible="
0x7ee6d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x7ee72  ldloc.0
0x7ee73  ldarg.0
0x7ee74  ldfld    bool Microsoft.Crm.Application.Controls.AppAdvancedFind::_titleVisible
0x7ee79  brtrue.s loc_7EE7F
0x7ee7b  ldc.i4.s 0x30
0x7ee7d  br.s     loc_7EE81
0x7ee7f  ldc.i4.s 0x31
0x7ee81  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x7ee86  ldloc.0
0x7ee87  ldstr    aFiltercontrolv// " FilterControlVisible="
0x7ee8c  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x7ee91  ldloc.0
0x7ee92  ldarg.0
0x7ee93  ldfld    bool Microsoft.Crm.Application.Controls.AppAdvancedFind::_filterControlVisible
0x7ee98  brtrue.s loc_7EE9E
0x7ee9a  ldc.i4.s 0x30
0x7ee9c  br.s     loc_7EEA0
0x7ee9e  ldc.i4.s 0x31
0x7eea0  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x7eea5  ldloc.0
0x7eea6  ldstr    aValidquerytype// " ValidQueryType="
0x7eeab  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x7eeb0  ldloc.0
0x7eeb1  ldarg.0
0x7eeb2  ldflda   int32 Microsoft.Crm.Application.Controls.AppAdvancedFind::_validQueryType
0x7eeb7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7eebc  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x7eec1  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x7eec6  ldloc.0
0x7eec7  ldstr    aIncludesystemq// " IncludeSystemQuery="
0x7eecc  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x7eed1  ldloc.0
0x7eed2  ldarg.0
0x7eed3  ldfld    bool Microsoft.Crm.Application.Controls.AppAdvancedFind::_includeSystemQuery
0x7eed8  brtrue.s loc_7EEDE
0x7eeda  ldc.i4.s 0x30
0x7eedc  br.s     loc_7EEE0
0x7eede  ldc.i4.s 0x31
0x7eee0  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x7eee5  ldloc.0
0x7eee6  ldstr    aIncludeuserque// " IncludeUserQuery="
0x7eeeb  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x7eef0  ldloc.0
0x7eef1  ldarg.0
0x7eef2  ldfld    bool Microsoft.Crm.Application.Controls.AppAdvancedFind::_includeUserQuery
0x7eef7  brtrue.s loc_7EEFD
0x7eef9  ldc.i4.s 0x30
0x7eefb  br.s     loc_7EEFF
0x7eefd  ldc.i4.s 0x31
0x7eeff  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x7ef04  ldloc.0
0x7ef05  ldstr    aSavechangesale// " SaveChangesAlert="
0x7ef0a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x7ef0f  ldloc.0
0x7ef10  ldarg.0
0x7ef11  ldfld    bool Microsoft.Crm.Application.Controls.AppAdvancedFind::_saveChangesAlert
0x7ef16  brtrue.s loc_7EF1C
0x7ef18  ldc.i4.s 0x30
0x7ef1a  br.s     loc_7EF1E
0x7ef1c  ldc.i4.s 0x31
0x7ef1e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x7ef23  ldloc.0
0x7ef24  ldstr    aDistinctfetch// " DistinctFetch="
0x7ef29  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x7ef2e  ldloc.0
0x7ef2f  ldarg.0
0x7ef30  ldfld    bool Microsoft.Crm.Application.Controls.AppAdvancedFind::_distinctFetch
0x7ef35  brtrue.s loc_7EF3B
0x7ef37  ldc.i4.s 0x30
0x7ef39  br.s     loc_7EF3D
0x7ef3b  ldc.i4.s 0x31
0x7ef3d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x7ef42  ldloc.0
0x7ef43  ldstr    aShowonlyfilter// " ShowOnlyFilterControl="
0x7ef48  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x7ef4d  ldloc.0
0x7ef4e  ldarg.0
0x7ef4f  ldfld    bool Microsoft.Crm.Application.Controls.AppAdvancedFind::_ShowOnlyFilterControl
0x7ef54  brtrue.s loc_7EF5A
0x7ef56  ldc.i4.s 0x30
0x7ef58  br.s     loc_7EF5C
0x7ef5a  ldc.i4.s 0x31
0x7ef5c  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x7ef61  ldloc.0
0x7ef62  ldc.i4.s 0x20
0x7ef64  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x7ef69  ldloc.0
0x7ef6a  ldstr    aDisablevalueco// " DisableValueControlInSimpleMode="
0x7ef6f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x7ef74  ldloc.0
0x7ef75  ldarg.0
0x7ef76  ldfld    bool Microsoft.Crm.Application.Controls.AppAdvancedFind::_disableValueControlInSimpleMode
0x7ef7b  brtrue.s loc_7EF81
0x7ef7d  ldc.i4.s 0x30
0x7ef7f  br.s     loc_7EF83
0x7ef81  ldc.i4.s 0x31
0x7ef83  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x7ef88  ldloc.0
0x7ef89  ldstr    aShowchangegrou// " ShowChangeGroupMenu="
0x7ef8e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x7ef93  ldloc.0
0x7ef94  ldarg.0
0x7ef95  ldfld    bool Microsoft.Crm.Application.Controls.AppAdvancedFind::_showChangeGroupMenu
0x7ef9a  brtrue.s loc_7EFA0
0x7ef9c  ldc.i4.s 0x30
0x7ef9e  br.s     loc_7EFA2
0x7efa0  ldc.i4.s 0x31
0x7efa2  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x7efa7  ldarg.0
0x7efa8  ldfld    string Microsoft.Crm.Application.Controls.AppAdvancedFind::_entityName
0x7efad  brfalse.s loc_7EFFB
0x7efaf  ldarg.0
0x7efb0  ldfld    string Microsoft.Crm.Application.Controls.AppAdvancedFind::_entityName
0x7efb5  callvirt instance int32 [mscorlib]System.String::get_Length()
0x7efba  ldc.i4.0
0x7efbb  ble.s    loc_7EFFB
0x7efbd  ldstr    aEntityname_0// "EntityName"
0x7efc2  ldarg.0
0x7efc3  ldfld    string Microsoft.Crm.Application.Controls.AppAdvancedFind::_entityName
0x7efc8  ldarg.1
0x7efc9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x7efce  ldstr    aEntitytypecode_0// "EntityTypeCode"
0x7efd3  ldarg.0
0x7efd4  ldfld    string Microsoft.Crm.Application.Controls.AppAdvancedFind::_entityName
0x7efd9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x7efde  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7efe3  call     instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0x7efe8  stloc.2
0x7efe9  ldloca.s 2
0x7efeb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
  ... truncated ...
```
