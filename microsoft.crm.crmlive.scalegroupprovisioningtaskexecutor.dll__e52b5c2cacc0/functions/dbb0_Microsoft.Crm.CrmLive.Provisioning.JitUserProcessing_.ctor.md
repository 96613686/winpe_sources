# Microsoft.Crm.CrmLive.Provisioning.JitUserProcessing::.ctor

- ea: `0xdbb0`
- end: `0xdc14`
- name: `Microsoft.Crm.CrmLive.Provisioning.JitUserProcessing::.ctor`
- size: `100`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xdbb0`

## string_xrefs

- `0xdbb6`: `MaximumNumberOfJitCreateRequestsPerHour`
- `0xdbca`: `MaximumNumberOfJitCreateRequestsPerHour`

## pseudocode

```c

```

## disassembly

```asm
0xdbb0  ldarg.0
0xdbb1  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0xdbb6  ldstr    aMaximumnumbero// "MaximumNumberOfJitCreateRequestsPerHour"
0xdbbb  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::GetServerSetting(string)
0xdbc0  brtrue.s loc_DBC5
0xdbc2  ldc.i4.3
0xdbc3  br.s     loc_DBD9
0xdbc5  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0xdbca  ldstr    aMaximumnumbero// "MaximumNumberOfJitCreateRequestsPerHour"
0xdbcf  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::GetServerSetting(string)
0xdbd4  unbox.any [mscorlib]System.Int32
0xdbd9  stfld    int32 Microsoft.Crm.CrmLive.Provisioning.JitUserProcessing::_maximumNumberOfJitRequestAllowedPerHour
0xdbde  ldarg.0
0xdbdf  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0xdbe4  ldstr    aJitcounterpers// "JitCounterPersistanceTimeInMinutes"
0xdbe9  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::GetServerSetting(string)
0xdbee  brtrue.s loc_DBF4
0xdbf0  ldc.i4.s 0x3C
0xdbf2  br.s     loc_DC08
0xdbf4  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0xdbf9  ldstr    aJitcounterpers// "JitCounterPersistanceTimeInMinutes"
0xdbfe  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::GetServerSetting(string)
0xdc03  unbox.any [mscorlib]System.Int32
0xdc08  stfld    int32 Microsoft.Crm.CrmLive.Provisioning.JitUserProcessing::_jitCookiePersistanceTimeInMinutes
0xdc0d  ldarg.0
0xdc0e  call     instance void [mscorlib]System.Object::.ctor()
0xdc13  ret
```
