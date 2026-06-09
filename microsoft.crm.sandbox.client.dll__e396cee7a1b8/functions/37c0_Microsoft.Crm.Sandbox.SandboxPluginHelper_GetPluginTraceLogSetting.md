# Microsoft.Crm.Sandbox.SandboxPluginHelper::GetPluginTraceLogSetting

- ea: `0x37c0`
- end: `0x3808`
- name: `Microsoft.Crm.Sandbox.SandboxPluginHelper::GetPluginTraceLogSetting`
- size: `72`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x23d0`
- `0x2c40`

## callees

- `0x37c0`
- `0x3820`

## string_xrefs

- `0x37f2`: `SandboxPluginHelper.GetPluginTraceLogSetting: Unable to retrieve FCB for PluginTraceLogSetting due to error {0}. Defaulting to false.`

## pseudocode

```c

```

## disassembly

```asm
0x37c0  ldarg.0
0x37c1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x37c6  stloc.0
0x37c7  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x37cc  ldarg.0
0x37cd  ldloc.0
0x37ce  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x37d3  stloc.1
0x37d4  ldloc.0
0x37d5  call     bool Microsoft.Crm.Sandbox.SandboxPluginHelper::IsPluginTracingFeatureEnabledForOrg(class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext context)
0x37da  brfalse.s loc_37E8
0x37dc  ldloc.1
0x37dd  brfalse.s loc_37E8
0x37df  ldloc.1
0x37e0  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTraceLogSettingType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_PluginTraceLogSetting()
0x37e5  stloc.2
0x37e6  leave.s  loc_3806
0x37e8  leave.s  loc_3804
0x37ea  ldloc.0
0x37eb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x37f0  ldc.i4.s 0x21
0x37f2  ldstr    aSandboxpluginh_2// "SandboxPluginHelper.GetPluginTraceLogSe"...
0x37f7  ldc.i4.0
0x37f8  newarr   [mscorlib]System.Object
0x37fd  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3802  leave.s  loc_3804
0x3804  ldc.i4.0
0x3805  ret
0x3806  ldloc.2
0x3807  ret
```
