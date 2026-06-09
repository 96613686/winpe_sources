# Microsoft.Xrm.Sdk.Utility.ConfigurationProvider::CheckOrganizationState

- ea: `0x2e0`
- end: `0x322`
- name: `Microsoft.Xrm.Sdk.Utility.ConfigurationProvider::CheckOrganizationState`
- size: `66`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x190`
- `0x330`

## callees

- `0x260`
- `0x2e0`

## pseudocode

```c

```

## disassembly

```asm
0x2e0  ldarg.2
0x2e1  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::GetContextInstance(valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext)
0x2e6  ldarg.1
0x2e7  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::GetOrganization(valuetype [mscorlib]System.Guid)
0x2ec  stloc.0
0x2ed  ldloc.0
0x2ee  ldstr    aState// "State"
0x2f3  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x2f8  unbox.any [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState
0x2fd  stloc.1
0x2fe  ldloc.1
0x2ff  ldc.i4.1
0x300  bne.un.s loc_30E
0x302  ldarg.0
0x303  ldarg.1
0x304  ldloc.0
0x305  callvirt instance bool Microsoft.Xrm.Sdk.Utility.ConfigurationProvider::IsOrgValidForCurrentSkuAndAuth(valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag orgData)
0x30a  brfalse.s loc_30E
0x30c  ldc.i4.0
0x30d  ret
0x30e  ldloc.1
0x30f  ldc.i4.1
0x310  beq.s    loc_314
0x312  ldc.i4.2
0x313  ret
0x314  ldarg.0
0x315  ldarg.1
0x316  ldloc.0
0x317  callvirt instance bool Microsoft.Xrm.Sdk.Utility.ConfigurationProvider::IsOrgValidForCurrentSkuAndAuth(valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag orgData)
0x31c  brtrue.s loc_320
0x31e  ldc.i4.1
0x31f  ret
0x320  ldc.i4.2
0x321  ret
```
