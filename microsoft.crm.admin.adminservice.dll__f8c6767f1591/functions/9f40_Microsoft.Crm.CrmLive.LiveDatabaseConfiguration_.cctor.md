# Microsoft.Crm.CrmLive.LiveDatabaseConfiguration::.cctor

- ea: `0x9f40`
- end: `0xa00d`
- name: `Microsoft.Crm.CrmLive.LiveDatabaseConfiguration::.cctor`
- size: `205`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x9f46`: `DataFilePath`
- `0x9f50`: `DataFilePath`
- `0x9f61`: `LogFilePath`
- `0x9f6b`: `LogFilePath`
- `0x9f7c`: `TransferPath`
- `0x9f86`: `TransferPath`

## pseudocode

```c

```

## disassembly

```asm
0x9f40  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x9f45  dup
0x9f46  ldstr    aDatafilepath// "DataFilePath"
0x9f4b  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x9f50  ldstr    aDatafilepath// "DataFilePath"
0x9f55  ldc.i4.0
0x9f56  callvirt T0x2B000001
0x9f5b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x9f60  dup
0x9f61  ldstr    aLogfilepath// "LogFilePath"
0x9f66  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x9f6b  ldstr    aLogfilepath// "LogFilePath"
0x9f70  ldc.i4.0
0x9f71  callvirt T0x2B000001
0x9f76  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x9f7b  dup
0x9f7c  ldstr    aTransferpath// "TransferPath"
0x9f81  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x9f86  ldstr    aTransferpath// "TransferPath"
0x9f8b  ldc.i4.0
0x9f8c  callvirt T0x2B000001
0x9f91  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x9f96  dup
0x9f97  ldstr    aTransfershare// "TransferShare"
0x9f9c  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x9fa1  ldstr    aTransfershare// "TransferShare"
0x9fa6  ldc.i4.0
0x9fa7  callvirt T0x2B000001
0x9fac  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x9fb1  dup
0x9fb2  ldstr    aEndpointname// "EndpointName"
0x9fb7  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x9fbc  ldstr    aEndpointname// "EndpointName"
0x9fc1  ldc.i4.0
0x9fc2  callvirt T0x2B000001
0x9fc7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x9fcc  dup
0x9fcd  ldstr    aMirroringport// "MirroringPort"
0x9fd2  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x9fd7  ldstr    aMirroringport// "MirroringPort"
0x9fdc  ldc.i4.0
0x9fdd  callvirt T0x2B000020
0x9fe2  box      [mscorlib]System.Int32
0x9fe7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x9fec  dup
0x9fed  ldstr    aMirroringdomai// "MirroringDomainName"
0x9ff2  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x9ff7  ldstr    aMirroringdomai// "MirroringDomainName"
0x9ffc  ldc.i4.0
0x9ffd  callvirt T0x2B000001
0xa002  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0xa007  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.CrmLive.LiveDatabaseConfiguration::_config
0xa00c  ret
```
