# Microsoft.Crm.Common.Application.Components.PageHandlers.QueueItemEntityPageHandler::ConfigurePageHandler

- ea: `0x12cc0`
- end: `0x13103`
- name: `Microsoft.Crm.Common.Application.Components.PageHandlers.QueueItemEntityPageHandler::ConfigurePageHandler`
- size: `1091`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x12cc0`

## string_xrefs

- `0x12ce4`: `this.GridControlBar is null - not valid outside of Outlook context`

## pseudocode

```c

```

## disassembly

```asm
0x12cc0  ldarg.0
0x12cc1  call     instance void [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::ConfigurePageHandler()
0x12cc6  ldarg.0
0x12cc7  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.GridControlBar [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_GridControlBar()
0x12ccc  brtrue.s loc_12CEF
0x12cce  ldarg.0
0x12ccf  call     instance class [System.Web]System.Web.HttpRequest [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_Request()
0x12cd4  callvirt instance string [System.Web]System.Web.HttpRequest::get_Path()
0x12cd9  ldstr    aGridOutlookrib// "/_grid/OutlookRibbonContextGrid.aspx"
0x12cde  ldc.i4.5
0x12cdf  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x12ce4  ldstr    aThisGridcontro// "this.GridControlBar is null - not valid"...
0x12ce9  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x12cee  ret
0x12cef  ldc.i4.0
0x12cf0  stloc.1
0x12cf1  br.s     loc_12D32
0x12cf3  ldarg.0
0x12cf4  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.GridControlBar [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_GridControlBar()
0x12cf9  ldloc.1
0x12cfa  callvirt instance float64 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.GridControlBar::GetControlBarComponentSize(int32)
0x12cff  stloc.2
0x12d00  ldloc.2
0x12d01  ldc.r8   0.0
0x12d0a  blt.un.s loc_12D2E
0x12d0c  ldarg.0
0x12d0d  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.GridControlBar [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_GridControlBar()
0x12d12  ldloc.2
0x12d13  ldc.r8   121.0
0x12d1c  div
0x12d1d  ldc.r8   100.0
0x12d26  mul
0x12d27  ldloc.1
0x12d28  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.GridControlBar::ResizeGridControlBarComponent(float64, int32)
0x12d2d  pop
0x12d2e  ldloc.1
0x12d2f  ldc.i4.1
0x12d30  add
0x12d31  stloc.1
0x12d32  ldarg.0
0x12d33  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.GridControlBar [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_GridControlBar()
0x12d38  ldloc.1
0x12d39  callvirt instance class [System.Web]System.Web.UI.Control [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.GridControlBar::GetControlBarComponent(int32)
0x12d3e  brtrue.s loc_12CF3
0x12d40  ldarg.0
0x12d41  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.GridControlBar [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_GridControlBar()
0x12d46  ldc.r8   30.0
0x12d4f  ldstr    aCrmquickfind// "crmQuickFind"
0x12d54  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.GridControlBar::ResizeGridControlBarComponent(float64, string)
0x12d59  pop
0x12d5a  ldarg.0
0x12d5b  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.GridControlBar [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_GridControlBar()
0x12d60  ldc.r8   70.0
0x12d69  ldstr    aCrmgridSavedne// "crmGrid_SavedNewQuerySelector"
0x12d6e  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.GridControlBar::ResizeGridControlBarComponent(float64, string)
0x12d73  pop
0x12d74  newobj   instance void [System.Web]System.Web.UI.WebControls.Label::.ctor()
0x12d79  stloc.3
0x12d7a  ldloc.3
0x12d7b  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.WebControls.WebControl::get_Attributes()
0x12d80  ldstr    aFor// "for"
0x12d85  ldstr    aCrmqueueselect// "crmQueueSelector"
0x12d8a  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x12d8f  ldloc.3
0x12d90  ldstr    aMsCrmBoldHeade// "ms-crm-Bold-Header"
0x12d95  callvirt instance void [System.Web]System.Web.UI.WebControls.WebControl::set_CssClass(string)
0x12d9a  ldloc.3
0x12d9b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x12da0  ldstr    aWorkplaceQueue// "Workplace_Queue_Selector_Label"
0x12da5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12daa  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x12daf  callvirt instance void [System.Web]System.Web.UI.WebControls.Label::set_Text(string)
0x12db4  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x12db9  stloc.s  4
0x12dbb  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AttributeProperty::.ctor()
0x12dc0  stloc.s  5
0x12dc2  ldloc.s  5
0x12dc4  ldstr    aNowrap// "nowrap"
0x12dc9  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AttributeProperty::set_AttributeName(string)
0x12dce  ldloc.s  4
0x12dd0  ldloc.s  5
0x12dd2  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x12dd7  pop
0x12dd8  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AttributeProperty::.ctor()
0x12ddd  stloc.s  5
0x12ddf  ldloc.s  5
0x12de1  ldstr    aClass// "class"
0x12de6  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AttributeProperty::set_AttributeName(string)
0x12deb  ldloc.s  5
0x12ded  ldstr    aHomeCasesTdLab// "home_cases_td_Label"
0x12df2  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AttributeProperty::set_AttributeValue(string)
0x12df7  ldloc.s  4
0x12df9  ldloc.s  5
0x12dfb  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x12e00  pop
0x12e01  ldarg.0
0x12e02  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.GridControlBar [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_GridControlBar()
0x12e07  ldloc.3
0x12e08  ldsfld   string [mscorlib]System.String::Empty
0x12e0d  ldc.r8   2.0
0x12e16  ldc.i4.1
0x12e17  ldloc.s  4
0x12e19  ldc.i4.1
0x12e1a  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.GridControlBar::AddUserDefinedControl(class [System.Web]System.Web.UI.Control, string, float64, int32, class [mscorlib]System.Collections.ArrayList, bool)
0x12e1f  pop
0x12e20  leave.s  loc_12E2C
0x12e22  ldloc.3
0x12e23  brfalse.s loc_12E2B
0x12e25  ldloc.3
0x12e26  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12e2b  endfinally
0x12e2c  ldarg.0
0x12e2d  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.GridControlBar [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_GridControlBar()
0x12e32  ldnull
0x12e33  ldc.r8   3.5
0x12e3c  ldc.i4.1
0x12e3d  ldc.i4.1
0x12e3e  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.GridControlBar::AddFixedSizeSpace(string, float64, int32, bool)
0x12e43  pop
0x12e44  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::.ctor()
0x12e49  stloc.s  6
0x12e4b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x12e50  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserId()
0x12e55  ldc.i4.1
0x12e56  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x12e5b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::UserQueues(valuetype [mscorlib]System.Guid, bool, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x12e60  stloc.s  7
0x12e62  ldc.i4.0
0x12e63  stloc.s  9
0x12e65  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::.ctor()
0x12e6a  stloc.s  0xB
0x12e6c  ldloc.s  7
0x12e6e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::GetEnumerator()
0x12e73  stloc.s  0xC
0x12e75  br.s     loc_12EF1
0x12e77  ldloc.s  0xC
0x12e79  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Current()
0x12e7e  dup
0x12e7f  ldstr    aQueueid// "queueid"
0x12e84  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x12e89  unbox.any [mscorlib]System.Guid
0x12e8e  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GuidToString(valuetype [mscorlib]System.Guid)
0x12e93  stloc.s  8
0x12e95  ldstr    aName// "name"
0x12e9a  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x12e9f  castclass [mscorlib]System.String
0x12ea4  ldloc.s  8
0x12ea6  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Option::.ctor(string, string)
0x12eab  stloc.s  0xD
0x12ead  ldarg.0
0x12eae  ldfld    string Microsoft.Crm.Common.Application.Components.PageHandlers.QueueItemEntityPageHandler::QueueIdSelected
0x12eb3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x12eb8  brtrue.s loc_12ED4
0x12eba  ldloc.s  8
0x12ebc  ldarg.0
0x12ebd  ldfld    string Microsoft.Crm.Common.Application.Components.PageHandlers.QueueItemEntityPageHandler::QueueIdSelected
0x12ec2  call     bool [mscorlib]System.String::Equals(string, string)
0x12ec7  brfalse.s loc_12ED4
0x12ec9  ldloc.s  0xD
0x12ecb  ldc.i4.1
0x12ecc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Option::set_IsDefault(bool)
0x12ed1  ldc.i4.1
0x12ed2  stloc.s  9
0x12ed4  ldloc.s  0xB
0x12ed6  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::get_Options()
0x12edb  ldloc.s  0xD
0x12edd  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x12ee2  pop
0x12ee3  leave.s  loc_12EF1
0x12ee5  ldloc.s  0xD
0x12ee7  brfalse.s loc_12EF0
0x12ee9  ldloc.s  0xD
0x12eeb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12ef0  endfinally
0x12ef1  ldloc.s  0xC
0x12ef3  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x12ef8  brtrue   loc_12E77
0x12efd  leave.s  loc_12F0B
0x12eff  ldloc.s  0xC
0x12f01  brfalse.s loc_12F0A
0x12f03  ldloc.s  0xC
0x12f05  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12f0a  endfinally
0x12f0b  ldarg.0
0x12f0c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentResourceManager()
0x12f11  ldstr    aWorkplaceQueue_0// "Workplace_Queue_Selector_All"
0x12f16  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12f1b  ldarg.0
0x12f1c  ldfld    string Microsoft.Crm.Common.Application.Components.PageHandlers.QueueItemEntityPageHandler::uniqueIdForAllQueues
0x12f21  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Option::.ctor(string, string)
0x12f26  stloc.s  0xE
0x12f28  ldloc.s  0xB
0x12f2a  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::get_Options()
0x12f2f  ldloc.s  0xE
0x12f31  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x12f36  pop
0x12f37  leave.s  loc_12F45
0x12f39  ldloc.s  0xE
0x12f3b  brfalse.s loc_12F44
0x12f3d  ldloc.s  0xE
0x12f3f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12f44  endfinally
0x12f45  ldarg.0
0x12f46  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentResourceManager()
0x12f4b  ldstr    aWorkplaceQueue_1// "Workplace_Queue_Selector_Public"
0x12f50  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12f55  ldarg.0
0x12f56  ldfld    string Microsoft.Crm.Common.Application.Components.PageHandlers.QueueItemEntityPageHandler::publicQueuesUniqueId
0x12f5b  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Option::.ctor(string, string)
0x12f60  stloc.s  0xF
0x12f62  ldloc.s  0xB
0x12f64  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::get_Options()
0x12f69  ldloc.s  0xF
0x12f6b  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x12f70  pop
0x12f71  leave.s  loc_12F7F
0x12f73  ldloc.s  0xF
0x12f75  brfalse.s loc_12F7E
0x12f77  ldloc.s  0xF
0x12f79  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12f7e  endfinally
0x12f7f  ldarg.0
0x12f80  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_CurrentResourceManager()
0x12f85  ldstr    aWorkplaceQueue_2// "Workplace_Queue_Selector_Private"
0x12f8a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12f8f  ldarg.0
0x12f90  ldfld    string Microsoft.Crm.Common.Application.Components.PageHandlers.QueueItemEntityPageHandler::privateQueuesUniqueId
0x12f95  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Option::.ctor(string, string)
0x12f9a  stloc.s  0x10
0x12f9c  ldloc.s  9
0x12f9e  brtrue.s loc_12FA8
0x12fa0  ldloc.s  0x10
0x12fa2  ldc.i4.1
0x12fa3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Option::set_IsDefault(bool)
0x12fa8  ldloc.s  0xB
0x12faa  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::get_Options()
0x12faf  ldloc.s  0x10
0x12fb1  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x12fb6  pop
0x12fb7  leave.s  loc_12FC5
0x12fb9  ldloc.s  0x10
0x12fbb  brfalse.s loc_12FC4
0x12fbd  ldloc.s  0x10
0x12fbf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12fc4  endfinally
0x12fc5  ldloc.s  6
0x12fc7  ldloc.s  0xB
0x12fc9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddOptionGroup(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup)
0x12fce  leave.s  loc_12FDC
0x12fd0  ldloc.s  0xB
0x12fd2  brfalse.s loc_12FDB
0x12fd4  ldloc.s  0xB
0x12fd6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12fdb  endfinally
0x12fdc  ldarg.0
0x12fdd  call     instance class [System.Web]System.Web.HttpRequest [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_Request()
0x12fe2  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x12fe7  ldstr    aQueueid_0// "queueId"
0x12fec  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x12ff1  stloc.0
0x12ff2  ldarg.0
0x12ff3  call     instance class [System.Web]System.Web.HttpRequest [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.EntityPageHandler::get_Request()
0x12ff8  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x12ffd  ldstr    aVisualizationi// "visualizationId"
0x13002  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x13007  stloc.s  0xA
0x13009  ldloc.s  0xA
0x1300b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x13010  brtrue.s loc_1302A
0x13012  ldloc.s  0xA
0x13014  ldstr    a475e6f0232ae40// "{475E6F02-32AE-4081-8CB8-E3E24A9FBC0F}"
0x13019  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1301e  brfalse.s loc_1302A
0x13020  ldloc.s  6
0x13022  ldloc.0
0x13023  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::set_Selected(string)
0x13028  br.s     loc_1306D
0x1302a  ldloc.0
0x1302b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x13030  brtrue.s loc_13044
0x13032  ldloc.0
0x13033  call     bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Utility.ViewSelectionUtility::IsQueueExists(string)
0x13038  brfalse.s loc_13044
0x1303a  ldloc.s  6
0x1303c  ldloc.0
0x1303d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::set_Selected(string)
0x13042  br.s     loc_1306D
0x13044  ldarg.0
0x13045  ldfld    string Microsoft.Crm.Common.Application.Components.PageHandlers.QueueItemEntityPageHandler::QueueIdSelected
0x1304a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1304f  brtrue.s loc_13060
0x13051  ldloc.s  6
0x13053  ldarg.0
0x13054  ldfld    string Microsoft.Crm.Common.Application.Components.PageHandlers.QueueItemEntityPageHandler::QueueIdSelected
0x13059  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::set_Selected(string)
0x1305e  br.s     loc_1306D
0x13060  ldloc.s  6
0x13062  ldarg.0
0x13063  ldfld    string Microsoft.Crm.Common.Application.Components.PageHandlers.QueueItemEntityPageHandler::privateQueuesUniqueId
0x13068  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::set_Selected(string)
  ... truncated ...
```
