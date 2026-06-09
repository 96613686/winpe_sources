# Microsoft.Crm.Application.WebServices.ConvertRuleDefaultPropertiesProvider::GetDefaultProperties

- ea: `0xa20`
- end: `0xa77`
- name: `Microsoft.Crm.Application.WebServices.ConvertRuleDefaultPropertiesProvider::GetDefaultProperties`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0xa20`
- `0xa80`
- `0xad0`
- `0xb90`

## pseudocode

```c

```

## disassembly

```asm
0xa20  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0xa25  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0xa2a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_AnyChanelToAnyEntityRecordCreation()
0xa2f  ldarg.3
0xa30  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0xa35  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache::Instance()
0xa3a  ldarg.3
0xa3b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0xa40  ldarg.3
0xa41  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.BasicCrmCache`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.VersionCacheData>::LookupEntry(void, var<u1>)
0xa46  callvirt instance class [mscorlib]System.Version [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.VersionCacheData::get_CrmVersion()
0xa4b  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::IsEnabled(valuetype [mscorlib]System.Guid, class [mscorlib]System.Version)
0xa50  brfalse.s loc_A5B
0xa52  ldarg.0
0xa53  ldarg.1
0xa54  call     instance bool Microsoft.Crm.Application.WebServices.ConvertRuleDefaultPropertiesProvider::IsPrimaryCreateStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep createStep)
0xa59  brtrue.s loc_A62
0xa5b  ldc.i4.0
0xa5c  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification>::.ctor(int32)
0xa61  ret
0xa62  newobj   instance void Microsoft.Crm.Application.WebServices.ConvertRuleDefaultPropertiesProviderFactory::.ctor()
0xa67  ldarg.1
0xa68  ldarg.2
0xa69  call     instance class [Microsoft.Crm.Service.ObjectModel]Microsoft.Crm.Service.ObjectModel.IDefaultPropertiesProvider Microsoft.Crm.Application.WebServices.ConvertRuleDefaultPropertiesProviderFactory::GetDefaultPropertiesProvider(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep createStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0xa6e  ldarg.1
0xa6f  ldarg.2
0xa70  ldarg.3
0xa71  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification> [Microsoft.Crm.Service.ObjectModel]Microsoft.Crm.Service.ObjectModel.IDefaultPropertiesProvider::GetDefaultProperties(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa76  ret
```
