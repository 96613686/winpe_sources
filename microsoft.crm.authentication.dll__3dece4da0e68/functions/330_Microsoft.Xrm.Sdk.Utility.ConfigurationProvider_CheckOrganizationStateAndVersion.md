# Microsoft.Xrm.Sdk.Utility.ConfigurationProvider::CheckOrganizationStateAndVersion

- ea: `0x330`
- end: `0x37f`
- name: `Microsoft.Xrm.Sdk.Utility.ConfigurationProvider::CheckOrganizationStateAndVersion`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1f0`

## callees

- `0x2e0`
- `0x330`
- `0x380`
- `0x140c0`
- `0x140d0`

## pseudocode

```c

```

## disassembly

```asm
0x330  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.WebServices.EndpointVersion, class VersionRange> Microsoft.Xrm.Sdk.Utility.ConfigurationProvider::_versionToVersionRange
0x335  ldarg.2
0x336  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Core]Microsoft.Crm.WebServices.EndpointVersion, class VersionRange>::get_Item(void)
0x33b  stloc.0
0x33c  ldarg.0
0x33d  ldarg.1
0x33e  ldarg.3
0x33f  call     instance class [mscorlib]System.Version Microsoft.Xrm.Sdk.Utility.ConfigurationProvider::RetrieveOrganizationVersion(valuetype [mscorlib]System.Guid organizationId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext locatorServiceContext)
0x344  stloc.1
0x345  ldarg.0
0x346  ldarg.1
0x347  ldarg.3
0x348  call     instance valuetype OrgState Microsoft.Xrm.Sdk.Utility.ConfigurationProvider::CheckOrganizationState(valuetype [mscorlib]System.Guid organizationId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext locatorServiceContext)
0x34d  stloc.2
0x34e  ldloc.2
0x34f  brfalse.s loc_353
0x351  ldloc.2
0x352  ret
0x353  ldloc.2
0x354  brtrue.s loc_37D
0x356  ldloc.1
0x357  ldnull
0x358  call     bool [mscorlib]System.Version::op_Equality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x35d  brtrue.s loc_37B
0x35f  ldloc.1
0x360  ldloc.0
0x361  callvirt instance class [mscorlib]System.Version VersionRange::get_Min()
0x366  call     bool [mscorlib]System.Version::op_GreaterThanOrEqual(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x36b  brfalse.s loc_37D
0x36d  ldloc.1
0x36e  ldloc.0
0x36f  callvirt instance class [mscorlib]System.Version VersionRange::get_Max()
0x374  call     bool [mscorlib]System.Version::op_LessThan(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x379  brfalse.s loc_37D
0x37b  ldc.i4.0
0x37c  ret
0x37d  ldc.i4.2
0x37e  ret
```
