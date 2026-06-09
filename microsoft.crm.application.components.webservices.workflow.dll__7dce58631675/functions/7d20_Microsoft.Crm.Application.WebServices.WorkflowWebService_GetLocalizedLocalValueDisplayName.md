# Microsoft.Crm.Application.WebServices.WorkflowWebService::GetLocalizedLocalValueDisplayName

- ea: `0x7d20`
- end: `0x7e64`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::GetLocalizedLocalValueDisplayName`
- size: `324`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ab0`
- `0x7d20`

## pseudocode

```c

```

## disassembly

```asm
0x7d20  ldarg.1
0x7d21  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7d26  brfalse.s loc_7D33
0x7d28  ldsfld   string [mscorlib]System.String::Empty
0x7d2d  stloc.3
0x7d2e  leave    loc_7E62
0x7d33  ldarg.1
0x7d34  ldc.i4.1
0x7d35  newarr   [mscorlib]System.Char
0x7d3a  dup
0x7d3b  ldc.i4.0
0x7d3c  ldc.i4.s 0x23
0x7d3e  stelem.i2
0x7d3f  ldc.i4.1
0x7d40  callvirt instance string[] [mscorlib]System.String::Split(char[], valuetype [mscorlib]System.StringSplitOptions)
0x7d45  stloc.0
0x7d46  ldloc.0
0x7d47  ldc.i4.3
0x7d48  ldelem.ref
0x7d49  stloc.1
0x7d4a  ldarg.0
0x7d4b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x7d50  ldloc.0
0x7d51  ldc.i4.2
0x7d52  ldelem.ref
0x7d53  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x7d58  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x7d5d  stloc.2
0x7d5e  ldloc.2
0x7d5f  ldloc.1
0x7d60  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x7d65  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x7d6a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x7d6f  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_AnyChanelToAnyEntityRecordCreation()
0x7d74  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x7d79  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x7d7e  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache::Instance()
0x7d83  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x7d88  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x7d8d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x7d92  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x7d97  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x7d9c  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.BasicCrmCache`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.VersionCacheData>::LookupEntry(void, var<u1>)
0x7da1  callvirt instance class [mscorlib]System.Version [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.VersionCacheData::get_CrmVersion()
0x7da6  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::IsEnabled(valuetype [mscorlib]System.Guid, class [mscorlib]System.Version)
0x7dab  brfalse.s loc_7DF8
0x7dad  ldloc.2
0x7dae  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PublicationParameters()
0x7db3  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::get_WorkflowRendererObjectTypeCode()
0x7db8  brfalse.s loc_7DF8
0x7dba  ldloc.2
0x7dbb  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PublicationParameters()
0x7dc0  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::get_WorkflowRendererObjectTypeCode()
0x7dc5  ldstr    aConvertruleite// "ConvertRuleItem"
0x7dca  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7dcf  call     instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0x7dd4  callvirt instance bool [mscorlib]System.String::Equals(string)
0x7dd9  brfalse.s loc_7DF8
0x7ddb  ldloc.2
0x7ddc  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IMetadataProvider [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_MetadataProvider()
0x7de1  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.ApplicationMetadataProvider
0x7de6  stloc.s  4
0x7de8  ldloc.s  4
0x7dea  brfalse.s loc_7DF8
0x7dec  ldloc.s  4
0x7dee  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.ConvertRuleAppResourceManager::.ctor()
0x7df3  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.ApplicationMetadataProvider::set_ResourceManager(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager)
0x7df8  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.DataSourceCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_DataSources()
0x7dfd  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IDataSource> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.DataSourceCollection::GetEnumerator()
0x7e02  stloc.s  5
0x7e04  br.s     loc_7E38
0x7e06  ldloc.s  5
0x7e08  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IDataSource>::get_Current()
0x7e0d  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ValuesCreatedByStep
0x7e12  stloc.s  6
0x7e14  ldloc.s  6
0x7e16  brfalse.s loc_7E38
0x7e18  ldarg.1
0x7e19  ldloc.s  6
0x7e1b  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ValuesCreatedByStep::get_Key()
0x7e20  ldc.i4.4
0x7e21  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x7e26  ldc.i4.0
0x7e27  ble.s    loc_7E38
0x7e29  ldloc.s  6
0x7e2b  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x7e30  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ValuesCreatedByStep::GetLocalizedName(class [mscorlib]System.Globalization.CultureInfo)
0x7e35  stloc.3
0x7e36  leave.s  loc_7E62
0x7e38  ldloc.s  5
0x7e3a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x7e3f  brtrue.s loc_7E06
0x7e41  leave.s  loc_7E4F
0x7e43  ldloc.s  5
0x7e45  brfalse.s loc_7E4E
0x7e47  ldloc.s  5
0x7e49  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7e4e  endfinally
0x7e4f  ldsfld   string [mscorlib]System.String::Empty
0x7e54  stloc.3
0x7e55  leave.s  loc_7E62
0x7e57  stloc.s  7
0x7e59  ldarg.0
0x7e5a  ldloc.s  7
0x7e5c  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x7e61  throw
0x7e62  ldloc.3
0x7e63  ret
```
