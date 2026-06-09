# Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignRecordPageHandler::ChangeState

- ea: `0x17f0`
- end: `0x18fb`
- name: `Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignRecordPageHandler::ChangeState`
- size: `267`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x17f0`

## pseudocode

```c

```

## disassembly

```asm
0x17f0  ldarg.2
0x17f1  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs::get_Entity()
0x17f6  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_HasData()
0x17fb  brfalse.s loc_1808
0x17fd  ldarg.0
0x17fe  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0x1803  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Update()
0x1808  ldarg.0
0x1809  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0x180e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_EntityName()
0x1813  stloc.0
0x1814  ldloca.s 1
0x1816  ldarg.0
0x1817  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0x181c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x1821  call     instance void [mscorlib]System.Guid::.ctor(string)
0x1826  ldc.i4.m1
0x1827  stloc.3
0x1828  ldarg.0
0x1829  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentForm()
0x182e  callvirt instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_EventId()
0x1833  stloc.s  4
0x1835  ldloc.s  4
0x1837  ldc.i4.5
0x1838  beq.s    loc_1841
0x183a  ldloc.s  4
0x183c  ldc.i4.6
0x183d  beq.s    loc_18A8
0x183f  br.s     loc_18BB
0x1841  ldloc.1
0x1842  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1847  call     void [Microsoft.Crm.Marketing.Application.Platform]Microsoft.Crm.Marketing.Application.Platform.Campaign::CheckForOpenCampaignActivities(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x184c  ldarg.0
0x184d  call     instance class [System.Web]System.Web.HttpRequest [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_Request()
0x1852  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x1857  ldstr    aNewstatecode// "newStateCode"
0x185c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1861  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1866  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x186b  stloc.s  5
0x186d  ldloc.0
0x186e  ldloc.s  5
0x1870  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::ConvertStateCodeToString(string, int32)
0x1875  stloc.2
0x1876  ldarg.0
0x1877  call     instance class [System.Web]System.Web.HttpRequest [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_Request()
0x187c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x1881  ldstr    aNewstatuscode// "newStatusCode"
0x1886  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x188b  stloc.s  6
0x188d  ldloc.s  6
0x188f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1894  brtrue.s loc_18A4
0x1896  ldloc.s  6
0x1898  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x189d  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x18a2  br.s     loc_18A5
0x18a4  ldc.i4.m1
0x18a5  stloc.3
0x18a6  br.s     loc_18DB
0x18a8  ldc.i4.0
0x18a9  stloc.s  7
0x18ab  ldloca.s 7
0x18ad  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.CampaignState
0x18b3  callvirt instance string [mscorlib]System.Object::ToString()
0x18b8  stloc.2
0x18b9  br.s     loc_18DB
0x18bb  ldstr    aInvalidStateCh// "Invalid state change: "
0x18c0  ldarg.0
0x18c1  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentForm()
0x18c6  callvirt instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_EventId()
0x18cb  box      [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId
0x18d0  call     string [mscorlib]System.String::Concat(object, object)
0x18d5  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x18da  throw
0x18db  ldloc.0
0x18dc  ldloc.1
0x18dd  ldloc.2
0x18de  ldloc.3
0x18df  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x18e4  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::SetState(string, valuetype [mscorlib]System.Guid, string, int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x18e9  ldarg.0
0x18ea  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0x18ef  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Retrieve()
0x18f4  ldarg.0
0x18f5  call     instance void [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::RenderGridRefreshScriptBlock()
0x18fa  ret
```
