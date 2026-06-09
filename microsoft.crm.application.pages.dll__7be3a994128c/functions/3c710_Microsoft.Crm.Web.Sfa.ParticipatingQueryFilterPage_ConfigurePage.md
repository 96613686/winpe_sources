# Microsoft.Crm.Web.Sfa.ParticipatingQueryFilterPage::ConfigurePage

- ea: `0x3c710`
- end: `0x3c852`
- name: `Microsoft.Crm.Web.Sfa.ParticipatingQueryFilterPage::ConfigurePage`
- size: `322`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3c710`
- `0x3c860`

## string_xrefs

- `0x3c7b7`: `fetchXml`
- `0x3c72b`: `readonlymode`
- `0x3c748`: `readonlymode`
- `0x3c7fa`: `fetchxml`
- `0x3c80d`: `fetchxml`

## pseudocode

```c

```

## disassembly

```asm
0x3c710  ldarg.0
0x3c711  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3c716  ldstr    aStaticEntities_3// "/_static/entities/goalmanagement.js"
0x3c71b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x3c720  ldarg.0
0x3c721  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x3c726  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x3c72b  ldstr    aReadonlymode// "readonlymode"
0x3c730  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x3c735  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3c73a  brtrue.s loc_3C761
0x3c73c  ldarg.0
0x3c73d  ldarg.0
0x3c73e  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x3c743  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x3c748  ldstr    aReadonlymode// "readonlymode"
0x3c74d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x3c752  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3c757  call     bool [mscorlib]System.Convert::ToBoolean(string, class [mscorlib]System.IFormatProvider)
0x3c75c  stfld    bool Microsoft.Crm.Web.Sfa.ParticipatingQueryFilterPage::_readOnly
0x3c761  ldarg.0
0x3c762  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x3c767  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x3c76c  ldstr    aEntitytypecode// "entitytypecode"
0x3c771  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x3c776  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3c77b  brtrue.s loc_3C7A4
0x3c77d  ldarg.0
0x3c77e  ldarg.0
0x3c77f  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x3c784  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x3c789  ldstr    aEntitytypecode// "entitytypecode"
0x3c78e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x3c793  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3c798  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x3c79d  stfld    int32 Microsoft.Crm.Web.Sfa.ParticipatingQueryFilterPage::_entityTypeCode
0x3c7a2  br.s     loc_3C7AB
0x3c7a4  ldarg.0
0x3c7a5  ldc.i4.1
0x3c7a6  stfld    int32 Microsoft.Crm.Web.Sfa.ParticipatingQueryFilterPage::_entityTypeCode
0x3c7ab  ldarg.0
0x3c7ac  ldarg.0
0x3c7ad  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x3c7b2  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x3c7b7  ldstr    aFetchxml// "fetchXml"
0x3c7bc  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x3c7c1  stfld    string Microsoft.Crm.Web.Sfa.ParticipatingQueryFilterPage::fetchXml
0x3c7c6  ldarg.0
0x3c7c7  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x3c7cc  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x3c7d1  ldstr    aGoalrollupquer// "goalrollupqueryid"
0x3c7d6  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x3c7db  stloc.0
0x3c7dc  ldloc.0
0x3c7dd  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3c7e2  brtrue.s loc_3C821
0x3c7e4  ldloca.s 1
0x3c7e6  ldloc.0
0x3c7e7  call     instance void [mscorlib]System.Guid::.ctor(string)
0x3c7ec  ldstr    aGoalrollupquer_0// "goalrollupquery"
0x3c7f1  ldloc.1
0x3c7f2  ldc.i4.1
0x3c7f3  newarr   [mscorlib]System.String
0x3c7f8  dup
0x3c7f9  ldc.i4.0
0x3c7fa  ldstr    aFetchxml_2// "fetchxml"
0x3c7ff  stelem.ref
0x3c800  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3c805  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3c80a  stloc.2
0x3c80b  ldarg.0
0x3c80c  ldloc.2
0x3c80d  ldstr    aFetchxml_2// "fetchxml"
0x3c812  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x3c817  castclass [mscorlib]System.String
0x3c81c  stfld    string Microsoft.Crm.Web.Sfa.ParticipatingQueryFilterPage::fetchXml
0x3c821  ldarg.0
0x3c822  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3c827  ldstr    aLocidAfExecuti// "LOCID_AF_EXECUTINGSEARCH"
0x3c82c  ldarg.0
0x3c82d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3c832  ldstr    aAfMessageExecu// "AF_Message_ExecutingSearch"
0x3c837  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3c83c  ldc.i4.0
0x3c83d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x3c842  ldarg.0
0x3c843  ldfld    int32 Microsoft.Crm.Web.Sfa.ParticipatingQueryFilterPage::_entityTypeCode
0x3c848  ldc.i4.m1
0x3c849  beq.s    loc_3C851
0x3c84b  ldarg.0
0x3c84c  call     instance void Microsoft.Crm.Web.Sfa.ParticipatingQueryFilterPage::ConfigureAdvancedFindControl()
0x3c851  ret
```
