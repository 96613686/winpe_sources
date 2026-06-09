# Microsoft.Crm.Application.Utility.AppPortalUtility::RetrieveCachedOrgInfo

- ea: `0x393d0`
- end: `0x3941d`
- name: `Microsoft.Crm.Application.Utility.AppPortalUtility::RetrieveCachedOrgInfo`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x39240`

## string_xrefs

- `0x39401`: `ConfigurationStatusCode`
- `0x3940d`: `RetrieveCachedOrgInfo`

## pseudocode

```c

```

## disassembly

```asm
0x393d0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x393d5  stloc.0
0x393d6  ldloc.0
0x393d7  ldstr    aCrmorganizatio// "CrmOrganizationId"
0x393dc  ldarg.0
0x393dd  box      [mscorlib]System.Guid
0x393e2  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x393e7  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x393ec  ldstr    aOrganizationli// "OrganizationLifecycle"
0x393f1  ldc.i4.2
0x393f2  newarr   [mscorlib]System.String
0x393f7  dup
0x393f8  ldc.i4.0
0x393f9  ldstr    aCrmorganizatio// "CrmOrganizationId"
0x393fe  stelem.ref
0x393ff  dup
0x39400  ldc.i4.1
0x39401  ldstr    aConfigurations// "ConfigurationStatusCode"
0x39406  stelem.ref
0x39407  ldloc.0
0x39408  ldc.i4   0xAB
0x3940d  ldstr    aRetrievecached// "RetrieveCachedOrgInfo"
0x39412  ldstr    aDDbsShDccm2110_1// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\2"...
0x39417  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::RetrieveSingleRow(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x3941c  ret
```
