# Microsoft.Crm.Web.BusinessManagement.RoleDetailPage::RenderCustomEntityPrivilegeRows

- ea: `0x35070`
- end: `0x354fc`
- name: `Microsoft.Crm.Web.BusinessManagement.RoleDetailPage::RenderCustomEntityPrivilegeRows`
- size: `1164`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x35050`

## callees

- `0x35070`
- `0x35570`
- `0x10a640`

## string_xrefs

- `0x3525a`: `Web.Biz.Roles.edit_role.aspx_create`
- `0x3528d`: `Web.Biz.Roles.edit_role.aspx_read`
- `0x352c0`: `Web.Biz.Roles.edit_role.aspx_write`
- `0x352f3`: `Web.Biz.Roles.edit_role.aspx_delete`
- `0x3512b`: `Web.Biz.Roles.ColumnSize.Create`
- `0x35142`: `Web.Biz.Roles.ColumnSize.Read`
- `0x35159`: `Web.Biz.Roles.ColumnSize.Write`
- `0x35170`: `Web.Biz.Roles.ColumnSize.Delete`
- `0x35216`: `<td CLASS="RoleDetailPage_RenderCustomEntityPrivilegeRows_td"  title="">`
- `0x35249`: `<td class="h" id="tab7_col_create" onclick="ToggleColumn(this)"><a onclick="return false" href="#"><span class='ms-crm-StatusLabel'>`
- `0x3527c`: `<td class="h" id="tab7_col_read" onclick="ToggleColumn(this)"><a onclick="return false" href="#"><span class='ms-crm-StatusLabel'>`
- `0x352af`: `<td class="h" id="tab7_col_write" onclick="ToggleColumn(this)"><a onclick="return false" href="#"><span class='ms-crm-StatusLabel'>`
- `0x352e2`: `<td class="h" id="tab7_col_delete" onclick="ToggleColumn(this)"><a onclick="return false" href="#"><span class='ms-crm-StatusLabel'>`

## pseudocode

```c

```

## disassembly

```asm
0x35070  ldarg.0
0x35071  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Crm.Web.BusinessManagement.RoleDetailPage::_customPrivileges
0x35076  callvirt instance void [mscorlib]System.Collections.ArrayList::Clear()
0x3507b  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x35080  stloc.0
0x35081  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x35086  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3508b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_CustomEntities()
0x35090  stloc.1
0x35091  ldloc.1
0x35092  brfalse.s loc_3509C
0x35094  ldloc.1
0x35095  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x3509a  brtrue.s loc_350D5
0x3509c  ldloc.0
0x3509d  ldstr    aCenterClassMsC// "<center class='ms-crm-TabMargin' width="...
0x350a2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x350a7  pop
0x350a8  ldloc.0
0x350a9  ldarg.0
0x350aa  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x350af  ldstr    aRoleeditorMess// "RoleEditor_Message_NoCustomEntities"
0x350b4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x350b9  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x350be  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x350c3  pop
0x350c4  ldloc.0
0x350c5  ldstr    aCenter// "</center>"
0x350ca  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x350cf  pop
0x350d0  br       loc_354F5
0x350d5  ldc.i4.0
0x350d6  stloc.2
0x350d7  ldloc.0
0x350d8  ldstr    aTableClassMsCr_2// "<table class=\"ms-crm-TabMargin\" width"...
0x350dd  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x350e2  pop
0x350e3  ldloc.0
0x350e4  ldstr    aTr// "<tr>"
0x350e9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x350ee  pop
0x350ef  ldloc.0
0x350f0  ldstr    aTdValignTop_0// "<td valign=\"top\">"
0x350f5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x350fa  pop
0x350fb  ldloc.0
0x350fc  ldstr    aTableClassMsCr_3// "<table class=\"ms-crm-Form-Area\" cells"...
0x35101  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x35106  pop
0x35107  ldloc.0
0x35108  ldstr    aOnclickProcess// "onclick=\"ProcessClick(new Sys.UI.DomEv"...
0x3510d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x35112  pop
0x35113  ldloc.0
0x35114  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x35119  ldstr    aColColStyleWid_0// "<col /><col style=\"width:{0}px\"><col "...
0x3511e  ldc.i4.8
0x3511f  newarr   [mscorlib]System.Object
0x35124  dup
0x35125  ldc.i4.0
0x35126  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3512b  ldstr    aWebBizRolesCol_0// "Web.Biz.Roles.ColumnSize.Create"
0x35130  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x35135  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x3513a  stelem.ref
0x3513b  dup
0x3513c  ldc.i4.1
0x3513d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x35142  ldstr    aWebBizRolesCol_1// "Web.Biz.Roles.ColumnSize.Read"
0x35147  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3514c  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x35151  stelem.ref
0x35152  dup
0x35153  ldc.i4.2
0x35154  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x35159  ldstr    aWebBizRolesCol_2// "Web.Biz.Roles.ColumnSize.Write"
0x3515e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x35163  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x35168  stelem.ref
0x35169  dup
0x3516a  ldc.i4.3
0x3516b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x35170  ldstr    aWebBizRolesCol_3// "Web.Biz.Roles.ColumnSize.Delete"
0x35175  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3517a  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x3517f  stelem.ref
0x35180  dup
0x35181  ldc.i4.4
0x35182  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x35187  ldstr    aWebBizRolesCol_4// "Web.Biz.Roles.ColumnSize.Append"
0x3518c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x35191  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x35196  stelem.ref
0x35197  dup
0x35198  ldc.i4.5
0x35199  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3519e  ldstr    aWebBizRolesCol_5// "Web.Biz.Roles.ColumnSize.AppendTo"
0x351a3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x351a8  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x351ad  stelem.ref
0x351ae  dup
0x351af  ldc.i4.6
0x351b0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x351b5  ldstr    aWebBizRolesCol_6// "Web.Biz.Roles.ColumnSize.Assign"
0x351ba  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x351bf  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x351c4  stelem.ref
0x351c5  dup
0x351c6  ldc.i4.7
0x351c7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x351cc  ldstr    aWebBizRolesCol_7// "Web.Biz.Roles.ColumnSize.Share"
0x351d1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x351d6  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x351db  stelem.ref
0x351dc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x351e1  pop
0x351e2  ldloc.0
0x351e3  ldstr    aTrClassMsCrmTi_0// "<tr class='ms-crm-TitleRowBkgd ms-crm-S"...
0x351e8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x351ed  pop
0x351ee  ldloc.0
0x351ef  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x351f4  ldstr    aWebBizRolesEdi_19// "Web.Biz.Roles.edit_role.aspx_colTip"
0x351f9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x351fe  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x35203  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x35208  pop
0x35209  ldloc.0
0x3520a  ldstr    asc_1458D8// "\">"
0x3520f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x35214  pop
0x35215  ldloc.0
0x35216  ldstr    aTdClassRoledet// "<td CLASS=\"RoleDetailPage_RenderCustom"...
0x3521b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x35220  pop
0x35221  ldloc.0
0x35222  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x35227  ldstr    aWebBizRolesEdi_15// "Web.Biz.Roles.edit_role.aspx_recordtype"
0x3522c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x35231  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x35236  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3523b  pop
0x3523c  ldloc.0
0x3523d  ldstr    aTd// "</td>"
0x35242  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x35247  pop
0x35248  ldloc.0
0x35249  ldstr    aTdClassHIdTab7// "<td class=\"h\" id=\"tab7_col_create\" "...
0x3524e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x35253  pop
0x35254  ldloc.0
0x35255  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3525a  ldstr    aWebBizRolesEdi// "Web.Biz.Roles.edit_role.aspx_create"
0x3525f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x35264  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x35269  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3526e  pop
0x3526f  ldloc.0
0x35270  ldstr    aSpanATd// "</span></a></td>"
0x35275  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3527a  pop
0x3527b  ldloc.0
0x3527c  ldstr    aTdClassHIdTab7_0// "<td class=\"h\" id=\"tab7_col_read\" on"...
0x35281  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x35286  pop
0x35287  ldloc.0
0x35288  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3528d  ldstr    aWebBizRolesEdi_0// "Web.Biz.Roles.edit_role.aspx_read"
0x35292  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x35297  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x3529c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x352a1  pop
0x352a2  ldloc.0
0x352a3  ldstr    aSpanATd// "</span></a></td>"
0x352a8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x352ad  pop
0x352ae  ldloc.0
0x352af  ldstr    aTdClassHIdTab7_1// "<td class=\"h\" id=\"tab7_col_write\" o"...
0x352b4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x352b9  pop
0x352ba  ldloc.0
0x352bb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x352c0  ldstr    aWebBizRolesEdi_1// "Web.Biz.Roles.edit_role.aspx_write"
0x352c5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x352ca  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x352cf  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x352d4  pop
0x352d5  ldloc.0
0x352d6  ldstr    aSpanATd// "</span></a></td>"
0x352db  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x352e0  pop
0x352e1  ldloc.0
0x352e2  ldstr    aTdClassHIdTab7_2// "<td class=\"h\" id=\"tab7_col_delete\" "...
0x352e7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x352ec  pop
0x352ed  ldloc.0
0x352ee  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x352f3  ldstr    aWebBizRolesEdi_2// "Web.Biz.Roles.edit_role.aspx_delete"
0x352f8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x352fd  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x35302  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x35307  pop
0x35308  ldloc.0
0x35309  ldstr    aSpanATd// "</span></a></td>"
0x3530e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x35313  pop
0x35314  ldloc.0
0x35315  ldstr    aTdClassHIdTab7_3// "<td class=\"h\" id=\"tab7_col_append\" "...
0x3531a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3531f  pop
0x35320  ldloc.0
0x35321  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x35326  ldstr    aWebBizRolesEdi_3// "Web.Biz.Roles.edit_role.aspx_append"
0x3532b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x35330  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x35335  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3533a  pop
0x3533b  ldloc.0
0x3533c  ldstr    aSpanATd// "</span></a></td>"
0x35341  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x35346  pop
0x35347  ldloc.0
0x35348  ldstr    aTdClassHIdTab7_4// "<td class=\"h\" id=\"tab7_col_appendto"...
0x3534d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x35352  pop
0x35353  ldloc.0
0x35354  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x35359  ldstr    aWebBizRolesEdi_4// "Web.Biz.Roles.edit_role.aspx_appendto"
0x3535e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x35363  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x35368  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3536d  pop
0x3536e  ldloc.0
0x3536f  ldstr    aSpanATd// "</span></a></td>"
0x35374  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x35379  pop
0x3537a  ldloc.0
0x3537b  ldstr    aTdClassHIdTab7_5// "<td class=\"h\" id=\"tab7_col_assign\" "...
0x35380  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x35385  pop
0x35386  ldloc.0
0x35387  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3538c  ldstr    aWebBizRolesEdi_5// "Web.Biz.Roles.edit_role.aspx_assign"
0x35391  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x35396  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x3539b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x353a0  pop
0x353a1  ldloc.0
0x353a2  ldstr    aSpanATd// "</span></a></td>"
0x353a7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x353ac  pop
0x353ad  ldloc.0
0x353ae  ldstr    aTdClassHIdTab7_6// "<td class=\"h\" id=\"tab7_col_share\" o"...
0x353b3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x353b8  pop
0x353b9  ldloc.0
0x353ba  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x353bf  ldstr    aWebBizRolesEdi_6// "Web.Biz.Roles.edit_role.aspx_share"
0x353c4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x353c9  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x353ce  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x353d3  pop
0x353d4  ldloc.0
0x353d5  ldstr    aSpanATd// "</span></a></td>"
0x353da  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x353df  pop
0x353e0  ldloc.0
0x353e1  ldstr    aTdTd_0// "<td></td>"
0x353e6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x353eb  pop
0x353ec  ldloc.0
0x353ed  ldstr    aTr_0// "</tr>"
0x353f2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x353f7  pop
0x353f8  ldloc.1
0x353f9  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x353fe  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::.ctor(int32)
0x35403  stloc.3
0x35404  ldloc.1
0x35405  callvirt instance class [mscorlib]System.Collections.IDictionaryEnumerator [mscorlib]System.Collections.IDictionary::GetEnumerator()
0x3540a  stloc.s  4
0x3540c  br.s     loc_3544D
0x3540e  ldloc.s  4
0x35410  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x35415  unbox.any [mscorlib]System.Collections.DictionaryEntry
0x3541a  stloc.s  5
0x3541c  ldloca.s 5
0x3541e  call     instance object [mscorlib]System.Collections.DictionaryEntry::get_Value()
0x35423  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata
0x35428  stloc.s  6
0x3542a  ldloc.s  6
0x3542c  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsActivity()
0x35431  brtrue.s loc_3544D
0x35433  ldloc.s  6
0x35435  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsIntersect()
0x3543a  brtrue.s loc_3544D
0x3543c  ldloc.s  6
0x3543e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsBPFEntity()
0x35443  brtrue.s loc_3544D
0x35445  ldloc.3
  ... truncated ...
```
