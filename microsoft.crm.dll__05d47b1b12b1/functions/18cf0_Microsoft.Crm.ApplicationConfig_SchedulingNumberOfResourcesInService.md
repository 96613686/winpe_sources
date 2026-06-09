# Microsoft.Crm.ApplicationConfig::SchedulingNumberOfResourcesInService

- ea: `0x18cf0`
- end: `0x18d0b`
- name: `Microsoft.Crm.ApplicationConfig::SchedulingNumberOfResourcesInService`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18fb0`

## string_xrefs

- `0x18cf0`: `SchedulingNumOfResInService`

## pseudocode

```c

```

## disassembly

```asm
0x18cf0  ldstr    aSchedulingnumo_3// "SchedulingNumOfResInService"
0x18cf5  ldc.i4   0x2710
0x18cfa  box      [mscorlib]System.Int32
0x18cff  ldarg.0
0x18d00  call     object Microsoft.Crm.ApplicationConfig::Retrieve(string propertyName, object defaultValue, valuetype [mscorlib]System.Guid organizationId)
0x18d05  unbox.any [mscorlib]System.Int32
0x18d0a  ret
```
