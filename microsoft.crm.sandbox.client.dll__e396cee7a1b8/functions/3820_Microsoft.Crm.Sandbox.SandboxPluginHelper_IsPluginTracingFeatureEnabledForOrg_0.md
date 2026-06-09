# Microsoft.Crm.Sandbox.SandboxPluginHelper::IsPluginTracingFeatureEnabledForOrg_0

- ea: `0x3820`
- end: `0x3877`
- name: `Microsoft.Crm.Sandbox.SandboxPluginHelper::IsPluginTracingFeatureEnabledForOrg_0`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x37c0`
- `0x3810`

## callees

- `0x3820`

## string_xrefs

- `0x3861`: `SandboxPluginHelper, IsPluginTracingFeatureEnabledForOrg: Unable to retrieve FCB for PluginTraceLogging due to error {0}. Defaulting to false.`

## pseudocode

```c

```

## disassembly

```asm
0x3820  ldarg.0
0x3821  brtrue.s loc_3825
0x3823  ldc.i4.0
0x3824  ret
0x3825  nop
0x3826  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x382b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x3830  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_PluginTraceLogging()
0x3835  ldarg.0
0x3836  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x383b  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache::Instance()
0x3840  ldarg.0
0x3841  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x3846  ldarg.0
0x3847  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.BasicCrmCache`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.VersionCacheData>::LookupEntry(void, var<u1>)
0x384c  callvirt instance class [mscorlib]System.Version [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.VersionCacheData::get_CrmVersion()
0x3851  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::IsEnabled(valuetype [mscorlib]System.Guid, class [mscorlib]System.Version)
0x3856  stloc.0
0x3857  leave.s  loc_3875
0x3859  ldarg.0
0x385a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x385f  ldc.i4.s 0x21
0x3861  ldstr    aSandboxpluginh_3// "SandboxPluginHelper, IsPluginTracingFea"...
0x3866  ldc.i4.0
0x3867  newarr   [mscorlib]System.Object
0x386c  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3871  ldc.i4.0
0x3872  stloc.0
0x3873  leave.s  loc_3875
0x3875  ldloc.0
0x3876  ret
```
