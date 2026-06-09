# Microsoft.Crm.Asynchronous.ServerOrganizationConfiguration::.ctor

- ea: `0xba90`
- end: `0xbab7`
- name: `Microsoft.Crm.Asynchronous.ServerOrganizationConfiguration::.ctor`
- size: `39`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xbd10`
- `0xcb80`

## string_xrefs

- `0xba97`: `locatorService`

## pseudocode

```c

```

## disassembly

```asm
0xba90  ldarg.0
0xba91  call     instance void [mscorlib]System.Object::.ctor()
0xba96  ldarg.3
0xba97  ldstr    aLocatorservice// "locatorService"
0xba9c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xbaa1  ldarg.0
0xbaa2  ldarg.1
0xbaa3  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ServerOrganizationConfiguration::_organizationId
0xbaa8  ldarg.0
0xbaa9  ldarg.2
0xbaaa  stfld    valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState Microsoft.Crm.Asynchronous.ServerOrganizationConfiguration::_organizationState
0xbaaf  ldarg.0
0xbab0  ldarg.3
0xbab1  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.ILocatorService Microsoft.Crm.Asynchronous.ServerOrganizationConfiguration::_locatorService
0xbab6  ret
```
