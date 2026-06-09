# Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignActivityRecordPageHandler::ChangeState

- ea: `0x20e0`
- end: `0x2271`
- name: `Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignActivityRecordPageHandler::ChangeState`
- size: `401`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x20e0`

## pseudocode

```c

```

## disassembly

```asm
0x20e0  ldarg.2
0x20e1  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs::get_Entity()
0x20e6  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_HasData()
0x20eb  brfalse.s loc_20F8
0x20ed  ldarg.0
0x20ee  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0x20f3  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Update()
0x20f8  ldstr    aCampaignactivi// "campaignactivity"
0x20fd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2102  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2107  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x210c  stloc.0
0x210d  ldarg.0
0x210e  call     instance class [System.Web]System.Web.HttpRequest [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_Request()
0x2113  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x2118  ldstr    aAcstartdate// "acStartDate"
0x211d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2122  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2127  brfalse.s loc_215E
0x2129  ldarg.0
0x212a  call     instance class [System.Web]System.Web.HttpRequest [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_Request()
0x212f  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x2134  ldstr    aAcstartdate// "acStartDate"
0x2139  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x213e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2143  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Parse(string, class [mscorlib]System.IFormatProvider)
0x2148  stloc.s  5
0x214a  ldloc.0
0x214b  ldstr    aActualstart// "actualstart"
0x2150  ldloc.s  5
0x2152  box      [mscorlib]System.DateTime
0x2157  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x215c  br.s     loc_216A
0x215e  ldloc.0
0x215f  ldstr    aActualstart// "actualstart"
0x2164  ldnull
0x2165  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x216a  ldarg.0
0x216b  call     instance class [System.Web]System.Web.HttpRequest [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_Request()
0x2170  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x2175  ldstr    aAcenddate// "acEndDate"
0x217a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x217f  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2184  brfalse.s loc_21BB
0x2186  ldarg.0
0x2187  call     instance class [System.Web]System.Web.HttpRequest [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_Request()
0x218c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x2191  ldstr    aAcenddate// "acEndDate"
0x2196  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x219b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x21a0  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Parse(string, class [mscorlib]System.IFormatProvider)
0x21a5  stloc.s  6
0x21a7  ldloc.0
0x21a8  ldstr    aActualend// "actualend"
0x21ad  ldloc.s  6
0x21af  box      [mscorlib]System.DateTime
0x21b4  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x21b9  br.s     loc_21C7
0x21bb  ldloc.0
0x21bc  ldstr    aActualend// "actualend"
0x21c1  ldnull
0x21c2  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x21c7  ldloc.0
0x21c8  ldstr    aActivityid// "activityid"
0x21cd  ldarg.0
0x21ce  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentForm()
0x21d3  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_EntityId()
0x21d8  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x21dd  box      [mscorlib]System.Guid
0x21e2  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x21e7  ldloc.0
0x21e8  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Update()
0x21ed  ldloc.0
0x21ee  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_EntityName()
0x21f3  stloc.1
0x21f4  ldarg.0
0x21f5  call     instance class [System.Web]System.Web.HttpRequest [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_Request()
0x21fa  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x21ff  ldstr    aNewstatecode// "newStateCode"
0x2204  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2209  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x220e  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x2213  stloc.2
0x2214  ldloc.1
0x2215  ldloc.2
0x2216  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::ConvertStateCodeToString(string, int32)
0x221b  stloc.3
0x221c  ldloca.s 4
0x221e  ldarg.0
0x221f  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentForm()
0x2224  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_EntityId()
0x2229  call     instance void [mscorlib]System.Guid::.ctor(string)
0x222e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2233  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x2238  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x223d  ldstr    aCallingCaSetst// "Calling CA:SetState with state = {0}"
0x2242  ldc.i4.1
0x2243  newarr   [mscorlib]System.Object
0x2248  dup
0x2249  ldc.i4.0
0x224a  ldloc.3
0x224b  stelem.ref
0x224c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2251  ldloc.1
0x2252  ldloc.s  4
0x2254  ldloc.3
0x2255  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x225a  call     void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.ActivityBase::SetState(string, valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x225f  ldarg.0
0x2260  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0x2265  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Retrieve()
0x226a  ldarg.0
0x226b  call     instance void [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::RenderGridRefreshScriptBlock()
0x2270  ret
```
