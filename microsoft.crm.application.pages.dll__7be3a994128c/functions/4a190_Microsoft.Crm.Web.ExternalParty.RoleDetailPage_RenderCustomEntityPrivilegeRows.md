# Microsoft.Crm.Web.ExternalParty.RoleDetailPage::RenderCustomEntityPrivilegeRows

- ea: `0x4a190`
- end: `0x4a4b6`
- name: `Microsoft.Crm.Web.ExternalParty.RoleDetailPage::RenderCustomEntityPrivilegeRows`
- size: `806`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x4a170`

## callees

- `0x4a190`
- `0x4a570`
- `0x10af40`

## string_xrefs

- `0x4a307`: `Web.Biz.Roles.edit_role.aspx_create`
- `0x4a33a`: `Web.Biz.Roles.edit_role.aspx_read`
- `0x4a36d`: `Web.Biz.Roles.edit_role.aspx_write`
- `0x4a24b`: `Web.Biz.Roles.ColumnSize.Create`
- `0x4a262`: `Web.Biz.Roles.ColumnSize.Read`
- `0x4a279`: `Web.Biz.Roles.ColumnSize.Write`
- `0x4a2c3`: `<td CLASS="RoleDetailPage_RenderCustomEntityPrivilegeRows_td"  title="">`
- `0x4a2f6`: `<td class="h" id="tab7_col_create" onclick="ToggleColumn(this)"><a onclick="return false" href="#"><span class='ms-crm-StatusLabel'>`
- `0x4a329`: `<td class="h" id="tab7_col_read" onclick="ToggleColumn(this)"><a onclick="return false" href="#"><span class='ms-crm-StatusLabel'>`
- `0x4a35c`: `<td class="h" id="tab7_col_write" onclick="ToggleColumn(this)"><a onclick="return false" href="#"><span class='ms-crm-StatusLabel'>`

## pseudocode

```c

```

## disassembly

```asm
0x4a190  ldarg.0
0x4a191  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Crm.Web.ExternalParty.RoleDetailPage::_customPrivileges
0x4a196  callvirt instance void [mscorlib]System.Collections.ArrayList::Clear()
0x4a19b  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x4a1a0  stloc.0
0x4a1a1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4a1a6  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4a1ab  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_CustomEntities()
0x4a1b0  stloc.1
0x4a1b1  ldloc.1
0x4a1b2  brfalse.s loc_4A1BC
0x4a1b4  ldloc.1
0x4a1b5  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x4a1ba  brtrue.s loc_4A1F5
0x4a1bc  ldloc.0
0x4a1bd  ldstr    aCenterClassMsC// "<center class='ms-crm-TabMargin' width="...
0x4a1c2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4a1c7  pop
0x4a1c8  ldloc.0
0x4a1c9  ldarg.0
0x4a1ca  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x4a1cf  ldstr    aRoleeditorMess// "RoleEditor_Message_NoCustomEntities"
0x4a1d4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4a1d9  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x4a1de  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4a1e3  pop
0x4a1e4  ldloc.0
0x4a1e5  ldstr    aCenter// "</center>"
0x4a1ea  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4a1ef  pop
0x4a1f0  br       loc_4A4AF
0x4a1f5  ldc.i4.0
0x4a1f6  stloc.2
0x4a1f7  ldloc.0
0x4a1f8  ldstr    aTableClassMsCr_2// "<table class=\"ms-crm-TabMargin\" width"...
0x4a1fd  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4a202  pop
0x4a203  ldloc.0
0x4a204  ldstr    aTr// "<tr>"
0x4a209  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4a20e  pop
0x4a20f  ldloc.0
0x4a210  ldstr    aTdValignTop_0// "<td valign=\"top\">"
0x4a215  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4a21a  pop
0x4a21b  ldloc.0
0x4a21c  ldstr    aTableClassMsCr_3// "<table class=\"ms-crm-Form-Area\" cells"...
0x4a221  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4a226  pop
0x4a227  ldloc.0
0x4a228  ldstr    aOnclickProcess// "onclick=\"ProcessClick(new Sys.UI.DomEv"...
0x4a22d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4a232  pop
0x4a233  ldloc.0
0x4a234  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4a239  ldstr    aColColStyleWid_1// "<col /><col style=\"width:{0}px\"><col "...
0x4a23e  ldc.i4.3
0x4a23f  newarr   [mscorlib]System.Object
0x4a244  dup
0x4a245  ldc.i4.0
0x4a246  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4a24b  ldstr    aWebBizRolesCol_0// "Web.Biz.Roles.ColumnSize.Create"
0x4a250  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4a255  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x4a25a  stelem.ref
0x4a25b  dup
0x4a25c  ldc.i4.1
0x4a25d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4a262  ldstr    aWebBizRolesCol_1// "Web.Biz.Roles.ColumnSize.Read"
0x4a267  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4a26c  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x4a271  stelem.ref
0x4a272  dup
0x4a273  ldc.i4.2
0x4a274  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4a279  ldstr    aWebBizRolesCol_2// "Web.Biz.Roles.ColumnSize.Write"
0x4a27e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4a283  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x4a288  stelem.ref
0x4a289  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x4a28e  pop
0x4a28f  ldloc.0
0x4a290  ldstr    aTrClassMsCrmTi_0// "<tr class='ms-crm-TitleRowBkgd ms-crm-S"...
0x4a295  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4a29a  pop
0x4a29b  ldloc.0
0x4a29c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4a2a1  ldstr    aWebBizRolesEdi_19// "Web.Biz.Roles.edit_role.aspx_colTip"
0x4a2a6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4a2ab  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x4a2b0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4a2b5  pop
0x4a2b6  ldloc.0
0x4a2b7  ldstr    asc_1458D8// "\">"
0x4a2bc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4a2c1  pop
0x4a2c2  ldloc.0
0x4a2c3  ldstr    aTdClassRoledet// "<td CLASS=\"RoleDetailPage_RenderCustom"...
0x4a2c8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4a2cd  pop
0x4a2ce  ldloc.0
0x4a2cf  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4a2d4  ldstr    aWebBizRolesEdi_15// "Web.Biz.Roles.edit_role.aspx_recordtype"
0x4a2d9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4a2de  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x4a2e3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4a2e8  pop
0x4a2e9  ldloc.0
0x4a2ea  ldstr    aTd// "</td>"
0x4a2ef  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4a2f4  pop
0x4a2f5  ldloc.0
0x4a2f6  ldstr    aTdClassHIdTab7// "<td class=\"h\" id=\"tab7_col_create\" "...
0x4a2fb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4a300  pop
0x4a301  ldloc.0
0x4a302  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4a307  ldstr    aWebBizRolesEdi// "Web.Biz.Roles.edit_role.aspx_create"
0x4a30c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4a311  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x4a316  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4a31b  pop
0x4a31c  ldloc.0
0x4a31d  ldstr    aSpanATd// "</span></a></td>"
0x4a322  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4a327  pop
0x4a328  ldloc.0
0x4a329  ldstr    aTdClassHIdTab7_0// "<td class=\"h\" id=\"tab7_col_read\" on"...
0x4a32e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4a333  pop
0x4a334  ldloc.0
0x4a335  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4a33a  ldstr    aWebBizRolesEdi_0// "Web.Biz.Roles.edit_role.aspx_read"
0x4a33f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4a344  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x4a349  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4a34e  pop
0x4a34f  ldloc.0
0x4a350  ldstr    aSpanATd// "</span></a></td>"
0x4a355  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4a35a  pop
0x4a35b  ldloc.0
0x4a35c  ldstr    aTdClassHIdTab7_1// "<td class=\"h\" id=\"tab7_col_write\" o"...
0x4a361  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4a366  pop
0x4a367  ldloc.0
0x4a368  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4a36d  ldstr    aWebBizRolesEdi_1// "Web.Biz.Roles.edit_role.aspx_write"
0x4a372  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4a377  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x4a37c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4a381  pop
0x4a382  ldloc.0
0x4a383  ldstr    aSpanATd// "</span></a></td>"
0x4a388  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4a38d  pop
0x4a38e  ldloc.0
0x4a38f  ldstr    aSpanATd// "</span></a></td>"
0x4a394  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4a399  pop
0x4a39a  ldloc.0
0x4a39b  ldstr    aTdTd_0// "<td></td>"
0x4a3a0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4a3a5  pop
0x4a3a6  ldloc.0
0x4a3a7  ldstr    aTr_0// "</tr>"
0x4a3ac  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4a3b1  pop
0x4a3b2  ldloc.1
0x4a3b3  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x4a3b8  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::.ctor(int32)
0x4a3bd  stloc.3
0x4a3be  ldloc.1
0x4a3bf  callvirt instance class [mscorlib]System.Collections.IDictionaryEnumerator [mscorlib]System.Collections.IDictionary::GetEnumerator()
0x4a3c4  stloc.s  4
0x4a3c6  br.s     loc_4A407
0x4a3c8  ldloc.s  4
0x4a3ca  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x4a3cf  unbox.any [mscorlib]System.Collections.DictionaryEntry
0x4a3d4  stloc.s  5
0x4a3d6  ldloca.s 5
0x4a3d8  call     instance object [mscorlib]System.Collections.DictionaryEntry::get_Value()
0x4a3dd  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata
0x4a3e2  stloc.s  6
0x4a3e4  ldloc.s  6
0x4a3e6  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsActivity()
0x4a3eb  brtrue.s loc_4A407
0x4a3ed  ldloc.s  6
0x4a3ef  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsIntersect()
0x4a3f4  brtrue.s loc_4A407
0x4a3f6  ldloc.s  6
0x4a3f8  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsEnabledForExternalChannels()
0x4a3fd  brfalse.s loc_4A407
0x4a3ff  ldloc.3
0x4a400  ldloc.s  6
0x4a402  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::Add(var<u1>)
0x4a407  ldloc.s  4
0x4a409  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4a40e  brtrue.s loc_4A3C8
0x4a410  leave.s  loc_4A427
0x4a412  ldloc.s  4
0x4a414  isinst   [mscorlib]System.IDisposable
0x4a419  stloc.s  7
0x4a41b  ldloc.s  7
0x4a41d  brfalse.s loc_4A426
0x4a41f  ldloc.s  7
0x4a421  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4a426  endfinally
0x4a427  ldloc.3
0x4a428  newobj   instance void EntityMetadataNameComparer::.ctor()
0x4a42d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::Sort(class [mscorlib]System.Collections.Generic.IComparer`1<var<u1>>)
0x4a432  ldloc.3
0x4a433  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::GetEnumerator()
0x4a438  stloc.s  8
0x4a43a  br.s     loc_4A45A
0x4a43c  ldloca.s 8
0x4a43e  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::get_Current()
0x4a443  stloc.s  9
0x4a445  ldloc.0
0x4a446  ldarg.0
0x4a447  ldloc.s  9
0x4a449  ldloc.2
0x4a44a  call     instance string Microsoft.Crm.Web.ExternalParty.RoleDetailPage::RenderCustomEntityPrivileges(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entity, bool highlight)
0x4a44f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4a454  pop
0x4a455  ldloc.2
0x4a456  ldc.i4.0
0x4a457  ceq
0x4a459  stloc.2
0x4a45a  ldloca.s 8
0x4a45c  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::MoveNext()
0x4a461  brtrue.s loc_4A43C
0x4a463  leave.s  loc_4A473
0x4a465  ldloca.s 8
0x4a467  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>
0x4a46d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4a472  endfinally
0x4a473  ldloc.0
0x4a474  ldstr    aTable_1// "</table>"
0x4a479  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4a47e  pop
0x4a47f  ldloc.0
0x4a480  ldstr    aTd// "</td>"
0x4a485  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4a48a  pop
0x4a48b  ldloc.0
0x4a48c  ldstr    aTr_0// "</tr>"
0x4a491  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4a496  pop
0x4a497  ldloc.0
0x4a498  ldstr    aTrHeight100TdV// "<tr height=\"100%\"><td valign=\"top\">"...
0x4a49d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4a4a2  pop
0x4a4a3  ldloc.0
0x4a4a4  ldstr    aTable_1// "</table>"
0x4a4a9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4a4ae  pop
0x4a4af  ldloc.0
0x4a4b0  callvirt instance string [mscorlib]System.Object::ToString()
0x4a4b5  ret
```
