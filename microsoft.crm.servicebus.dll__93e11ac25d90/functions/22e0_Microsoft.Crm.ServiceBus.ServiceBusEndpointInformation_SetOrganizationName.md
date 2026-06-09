# Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::SetOrganizationName

- ea: `0x22e0`
- end: `0x231d`
- name: `Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::SetOrganizationName`
- size: `61`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x19d0`

## callees

- `0x1b60`
- `0x22e0`

## pseudocode

```c

```

## disassembly

```asm
0x22e0  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationMetadataProvider::get_Instance()
0x22e5  ldarg.1
0x22e6  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider::GetOrganizationUrlName(valuetype [mscorlib]System.Guid)
0x22eb  stloc.0
0x22ec  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x22f1  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x22f6  ldc.i4.2
0x22f7  bne.un.s loc_2315
0x22f9  ldstr    a01_0// "{0}.{1}"
0x22fe  ldloc.0
0x22ff  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x2304  ldstr    aRootdomain// "RootDomain"
0x2309  ldc.i4.0
0x230a  callvirt T0x2B000001
0x230f  call     string [mscorlib]System.String::Format(string, object, object)
0x2314  stloc.0
0x2315  ldarg.0
0x2316  ldloc.0
0x2317  call     instance void Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::set_OrganizationName(string value)
0x231c  ret
```
