# Microsoft.Crm.Asynchronous.ServerConfiguration::get_IsRunningInSafeMode

- ea: `0xd030`
- end: `0xd054`
- name: `Microsoft.Crm.Asynchronous.ServerConfiguration::get_IsRunningInSafeMode`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xc960`
- `0xd030`
- `0xd370`

## string_xrefs

- `0xd042`: `RunAsyncServiceInSafeMode`

## pseudocode

```c

```

## disassembly

```asm
0xd030  ldarg.0
0xd031  ldfld    class Microsoft.Crm.Asynchronous.IOrganizationRetriever Microsoft.Crm.Asynchronous.ServerConfiguration::retriever
0xd036  callvirt instance bool Microsoft.Crm.Asynchronous.IOrganizationRetriever::get_ReliabilitySettingsRetrieved()
0xd03b  brfalse.s loc_D052
0xd03d  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0xd042  ldstr    aRunasyncservic// "RunAsyncServiceInSafeMode"
0xd047  call     object Microsoft.Crm.Asynchronous.ServerConfiguration::ReadServerSetting(class [Microsoft.Crm.Core]Microsoft.Crm.ILocatorService locatorService, string settingName)
0xd04c  unbox.any [mscorlib]System.Boolean
0xd051  ret
0xd052  ldc.i4.0
0xd053  ret
```
