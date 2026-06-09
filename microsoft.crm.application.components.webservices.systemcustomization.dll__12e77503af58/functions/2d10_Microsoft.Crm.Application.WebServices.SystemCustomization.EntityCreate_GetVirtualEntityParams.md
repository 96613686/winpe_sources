# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetVirtualEntityParams

- ea: `0x2d10`
- end: `0x2d77`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetVirtualEntityParams`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x26f0`

## callees

- `0x190`
- `0x330`
- `0x2d10`

## pseudocode

```c

```

## disassembly

```asm
0x2d10  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x2d15  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x2d1a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_VirtualEntity()
0x2d1f  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0x2d24  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2d29  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2d2e  brfalse.s loc_2D76
0x2d30  ldarg.1
0x2d31  ldstr    aDataproviderid// "dataproviderid"
0x2d36  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x2d3b  brfalse.s loc_2D53
0x2d3d  ldarg.0
0x2d3e  ldarg.1
0x2d3f  ldstr    aDataproviderid// "dataproviderid"
0x2d44  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.WebServices.ParameterBag::GetGuid(string name)
0x2d49  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x2d4e  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_DataProviderId(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>)
0x2d53  ldarg.1
0x2d54  ldstr    aDatasourceid// "datasourceid"
0x2d59  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x2d5e  brfalse.s loc_2D76
0x2d60  ldarg.0
0x2d61  ldarg.1
0x2d62  ldstr    aDatasourceid// "datasourceid"
0x2d67  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.WebServices.ParameterBag::GetGuid(string name)
0x2d6c  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x2d71  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityCreateInfo::set_DataSourceId(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>)
0x2d76  ret
```
