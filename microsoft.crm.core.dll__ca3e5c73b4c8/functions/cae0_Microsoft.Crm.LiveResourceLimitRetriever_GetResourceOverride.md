# Microsoft.Crm.LiveResourceLimitRetriever::GetResourceOverride

- ea: `0xcae0`
- end: `0xcbc9`
- name: `Microsoft.Crm.LiveResourceLimitRetriever::GetResourceOverride`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xc600`

## callees

- `0x1010`
- `0x1470`
- `0xcae0`

## string_xrefs

- `0xcb12`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\ObjectModel\LiveResourceLimitRetriever.cs`
- `0xcb4a`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\ObjectModel\LiveResourceLimitRetriever.cs`
- `0xcb79`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\ObjectModel\LiveResourceLimitRetriever.cs`
- `0xcba8`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\ObjectModel\LiveResourceLimitRetriever.cs`

## pseudocode

```c

```

## disassembly

```asm
0xcae0  ldarg.1
0xcae1  ldc.i4.2
0xcae2  sub
0xcae3  switch   loc_CB35, loc_CAFD, loc_CB64, loc_CB93
0xcaf8  br       loc_CBC5
0xcafd  call     class Microsoft.Crm.IOrganizationSettingsProvider Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0xcb02  ldarg.0
0xcb03  ldstr    aStoragelicense// "StorageLicensesPurchaseLimitOverride"
0xcb08  ldc.i4   0xCA
0xcb0d  ldstr    aGetresourceove// "GetResourceOverride"
0xcb12  ldstr    aDA1SSrcPlatfor_2// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xcb17  callvirt instance object Microsoft.Crm.IOrganizationSettingsProvider::GetOrganizationSetting(valuetype [mscorlib]System.Guid organizationId, string settingName, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xcb1c  stloc.1
0xcb1d  ldloc.1
0xcb1e  brfalse.s loc_CB2E
0xcb20  ldloc.1
0xcb21  unbox.any [mscorlib]System.Int32
0xcb26  ldc.i4   0x400
0xcb2b  mul
0xcb2c  br.s     loc_CB2F
0xcb2e  ldc.i4.0
0xcb2f  stloc.0
0xcb30  br       loc_CBC7
0xcb35  call     class Microsoft.Crm.IOrganizationSettingsProvider Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0xcb3a  ldarg.0
0xcb3b  ldstr    aUserlicensespu// "UserLicensesPurchaseLimitOverride"
0xcb40  ldc.i4   0xCE
0xcb45  ldstr    aGetresourceove// "GetResourceOverride"
0xcb4a  ldstr    aDA1SSrcPlatfor_2// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xcb4f  callvirt instance object Microsoft.Crm.IOrganizationSettingsProvider::GetOrganizationSetting(valuetype [mscorlib]System.Guid organizationId, string settingName, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xcb54  stloc.2
0xcb55  ldloc.2
0xcb56  brfalse.s loc_CB60
0xcb58  ldloc.2
0xcb59  unbox.any [mscorlib]System.Int32
0xcb5e  br.s     loc_CB61
0xcb60  ldc.i4.0
0xcb61  stloc.0
0xcb62  br.s     loc_CBC7
0xcb64  call     class Microsoft.Crm.IOrganizationSettingsProvider Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0xcb69  ldarg.0
0xcb6a  ldstr    aCustomentityli// "CustomEntityLimitOverride"
0xcb6f  ldc.i4   0xD2
0xcb74  ldstr    aGetresourceove// "GetResourceOverride"
0xcb79  ldstr    aDA1SSrcPlatfor_2// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xcb7e  callvirt instance object Microsoft.Crm.IOrganizationSettingsProvider::GetOrganizationSetting(valuetype [mscorlib]System.Guid organizationId, string settingName, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xcb83  stloc.3
0xcb84  ldloc.3
0xcb85  brfalse.s loc_CB8F
0xcb87  ldloc.3
0xcb88  unbox.any [mscorlib]System.Int32
0xcb8d  br.s     loc_CB90
0xcb8f  ldc.i4.0
0xcb90  stloc.0
0xcb91  br.s     loc_CBC7
0xcb93  call     class Microsoft.Crm.IOrganizationSettingsProvider Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0xcb98  ldarg.0
0xcb99  ldstr    aPubworkflowsli// "PubWorkflowsLimitOverride"
0xcb9e  ldc.i4   0xD6
0xcba3  ldstr    aGetresourceove// "GetResourceOverride"
0xcba8  ldstr    aDA1SSrcPlatfor_2// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xcbad  callvirt instance object Microsoft.Crm.IOrganizationSettingsProvider::GetOrganizationSetting(valuetype [mscorlib]System.Guid organizationId, string settingName, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xcbb2  stloc.s  4
0xcbb4  ldloc.s  4
0xcbb6  brfalse.s loc_CBC1
0xcbb8  ldloc.s  4
0xcbba  unbox.any [mscorlib]System.Int32
0xcbbf  br.s     loc_CBC2
0xcbc1  ldc.i4.0
0xcbc2  stloc.0
0xcbc3  br.s     loc_CBC7
0xcbc5  ldc.i4.0
0xcbc6  stloc.0
0xcbc7  ldloc.0
0xcbc8  ret
```
