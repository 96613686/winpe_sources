# Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::.ctor

- ea: `0x7680`
- end: `0x76d1`
- name: `Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::.ctor`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x3910`

## string_xrefs

- `0x7687`: `tpsService`
- `0x7692`: `keyVaultService`
- `0x769d`: `localConfigStoreServices`

## pseudocode

```c

```

## disassembly

```asm
0x7680  ldarg.0
0x7681  call     instance void [mscorlib]System.Object::.ctor()
0x7686  ldarg.1
0x7687  ldstr    aTpsservice// "tpsService"
0x768c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x7691  ldarg.2
0x7692  ldstr    aKeyvaultservic_3// "keyVaultService"
0x7697  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x769c  ldarg.3
0x769d  ldstr    aLocalconfigsto// "localConfigStoreServices"
0x76a2  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x76a7  ldarg.s  4
0x76a9  ldstr    aTransactedmess// "transactedMessageContextFactory"
0x76ae  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x76b3  ldarg.0
0x76b4  ldarg.1
0x76b5  stfld    class Microsoft.Crm.Sandbox.Service.ITPSService Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::_tpsService
0x76ba  ldarg.0
0x76bb  ldarg.2
0x76bc  stfld    class Microsoft.Crm.Sandbox.Service.IKeyVaultService Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::_keyVaultService
0x76c1  ldarg.0
0x76c2  ldarg.3
0x76c3  stfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ILocalConfigStoreServices Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::_localConfigStoreServices
0x76c8  ldarg.0
0x76c9  ldarg.s  4
0x76cb  stfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.ITransactedMessageContextFactory Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::_transactedMessageContextFactory
0x76d0  ret
```
