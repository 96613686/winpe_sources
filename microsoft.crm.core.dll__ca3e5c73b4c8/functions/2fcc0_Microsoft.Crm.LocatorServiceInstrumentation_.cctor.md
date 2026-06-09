# Microsoft.Crm.LocatorServiceInstrumentation::.cctor

- ea: `0x2fcc0`
- end: `0x2fd0b`
- name: `Microsoft.Crm.LocatorServiceInstrumentation::.cctor`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x2ed20`
- `0x2fcc0`
- `0x2fd30`
- `0x33840`
- `0x34780`

## string_xrefs

- `0x2fcc0`: `LocatorServiceInstrumentationEnabled`
- `0x2fcf4`: `LocatorServiceInstrumentation.config`
- `0x2fcf9`: `LocatorServicePlayback.xml`

## pseudocode

```c

```

## disassembly

```asm
0x2fcc0  ldstr    aLocatorservice_4// "LocatorServiceInstrumentationEnabled"
0x2fcc5  ldc.i4.0
0x2fcc6  box      [mscorlib]System.Int32
0x2fccb  call     object Microsoft.Crm.RegistryCache::GetValue(string key, object defaultValue)
0x2fcd0  unbox.any [mscorlib]System.Int32
0x2fcd5  ldc.i4.1
0x2fcd6  bne.un.s loc_2FD04
0x2fcd8  call     bool Microsoft.Crm.RegControl::IsInServerContext()
0x2fcdd  brfalse.s loc_2FD04
0x2fcdf  ldc.i4.1
0x2fce0  stsfld   bool Microsoft.Crm.LocatorServiceInstrumentation::Enabled
0x2fce5  newobj   instance void Microsoft.Crm.LocatorServiceInstrumentation::.ctor()
0x2fcea  stsfld   class Microsoft.Crm.LocatorServiceInstrumentation Microsoft.Crm.LocatorServiceInstrumentation::_instance
0x2fcef  ldsfld   class Microsoft.Crm.LocatorServiceInstrumentation Microsoft.Crm.LocatorServiceInstrumentation::_instance
0x2fcf4  ldstr    aLocatorservice_5// "LocatorServiceInstrumentation.config"
0x2fcf9  ldstr    aLocatorservice_6// "LocatorServicePlayback.xml"
0x2fcfe  callvirt instance void Microsoft.Crm.ConfigDBInstrumentation::LoadSettings(string configFileName, string playbackFileName)
0x2fd03  ret
0x2fd04  ldc.i4.0
0x2fd05  stsfld   bool Microsoft.Crm.LocatorServiceInstrumentation::Enabled
0x2fd0a  ret
```
