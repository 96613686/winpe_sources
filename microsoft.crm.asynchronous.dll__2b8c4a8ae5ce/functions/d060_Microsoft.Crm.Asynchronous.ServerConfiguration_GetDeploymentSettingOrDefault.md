# Microsoft.Crm.Asynchronous.ServerConfiguration::GetDeploymentSettingOrDefault

- ea: `0xd060`
- end: `0xd093`
- name: `Microsoft.Crm.Asynchronous.ServerConfiguration::GetDeploymentSettingOrDefault`
- size: `51`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x2a50`
- `0x4d70`
- `0x7310`
- `0x9d70`

## callees

- `0xd060`

## string_xrefs

- `0xd068`: `LocatorService.Instance is null`

## pseudocode

```c

```

## disassembly

```asm
0xd060  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0xd065  ldnull
0xd066  cgt.un
0xd068  ldstr    aLocatorservice_0// "LocatorService.Instance is null"
0xd06d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0xd072  ldarg.1
0xd073  stloc.0
0xd074  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0xd079  ldarg.0
0xd07a  callvirt T0x2B00001A
0xd07f  stloc.1
0xd080  ldloca.s 1
0xd082  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xd087  brfalse.s loc_D091
0xd089  ldloca.s 1
0xd08b  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0xd090  stloc.0
0xd091  ldloc.0
0xd092  ret
```
