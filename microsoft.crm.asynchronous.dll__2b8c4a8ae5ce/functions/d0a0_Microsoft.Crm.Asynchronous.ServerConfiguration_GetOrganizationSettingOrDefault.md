# Microsoft.Crm.Asynchronous.ServerConfiguration::GetOrganizationSettingOrDefault

- ea: `0xd0a0`
- end: `0xd0e4`
- name: `Microsoft.Crm.Asynchronous.ServerConfiguration::GetOrganizationSettingOrDefault`
- size: `68`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x2a30`
- `0x7320`
- `0xac60`
- `0xb920`

## callees

- `0xd0a0`

## string_xrefs

- `0xd0c5`: `d:\dbs\sh\dccm2\1101_190851\cmd\13\src\Core\ObjectModel\Async\Shared\Configuration.cs`
- `0xd0a8`: `LocatorService.Instance is null`

## pseudocode

```c

```

## disassembly

```asm
0xd0a0  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0xd0a5  ldnull
0xd0a6  cgt.un
0xd0a8  ldstr    aLocatorservice_0// "LocatorService.Instance is null"
0xd0ad  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0xd0b2  ldarg.2
0xd0b3  stloc.0
0xd0b4  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0xd0b9  ldarg.0
0xd0ba  ldarg.1
0xd0bb  ldc.i4   0x3E3
0xd0c0  ldstr    aGetorganizatio// "GetOrganizationSettingOrDefault"
0xd0c5  ldstr    aDDbsShDccm2110// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\1"...
0xd0ca  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider::GetOrganizationSetting(valuetype [mscorlib]System.Guid, string, int32, string, string)
0xd0cf  stloc.1
0xd0d0  ldloc.1
0xd0d1  brfalse.s loc_D0E2
0xd0d3  ldloc.1
0xd0d4  isinst   [mscorlib]System.Int32
0xd0d9  brfalse.s loc_D0E2
0xd0db  ldloc.1
0xd0dc  unbox.any [mscorlib]System.Int32
0xd0e1  stloc.0
0xd0e2  ldloc.0
0xd0e3  ret
```
