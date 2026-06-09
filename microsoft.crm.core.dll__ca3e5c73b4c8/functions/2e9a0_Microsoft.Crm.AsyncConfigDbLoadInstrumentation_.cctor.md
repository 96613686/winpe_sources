# Microsoft.Crm.AsyncConfigDbLoadInstrumentation::.cctor

- ea: `0x2e9a0`
- end: `0x2e9eb`
- name: `Microsoft.Crm.AsyncConfigDbLoadInstrumentation::.cctor`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x2e9a0`
- `0x2ea10`
- `0x2ed20`
- `0x33f20`
- `0x34780`

## string_xrefs

- `0x2e9a0`: `AsyncConfigDbLoadInstrumentationEnabled`
- `0x2e9d4`: `AsyncConfigDbLoadInstrumentation.config`
- `0x2e9d9`: `AsyncConfigDbLoadPlayback.txt`

## pseudocode

```c

```

## disassembly

```asm
0x2e9a0  ldstr    aAsyncconfigdbl// "AsyncConfigDbLoadInstrumentationEnabled"
0x2e9a5  ldc.i4.0
0x2e9a6  box      [mscorlib]System.Int32
0x2e9ab  call     object Microsoft.Crm.RegistryCache::GetValue(string key, object defaultValue)
0x2e9b0  unbox.any [mscorlib]System.Int32
0x2e9b5  ldc.i4.1
0x2e9b6  bne.un.s loc_2E9E4
0x2e9b8  call     bool Microsoft.Crm.RegControl::IsInAsyncServiceContext()
0x2e9bd  brfalse.s loc_2E9E4
0x2e9bf  ldc.i4.1
0x2e9c0  stsfld   bool Microsoft.Crm.AsyncConfigDbLoadInstrumentation::Enabled
0x2e9c5  newobj   instance void Microsoft.Crm.AsyncConfigDbLoadInstrumentation::.ctor()
0x2e9ca  stsfld   class Microsoft.Crm.AsyncConfigDbLoadInstrumentation Microsoft.Crm.AsyncConfigDbLoadInstrumentation::_instance
0x2e9cf  ldsfld   class Microsoft.Crm.AsyncConfigDbLoadInstrumentation Microsoft.Crm.AsyncConfigDbLoadInstrumentation::_instance
0x2e9d4  ldstr    aAsyncconfigdbl_0// "AsyncConfigDbLoadInstrumentation.config"
0x2e9d9  ldstr    aAsyncconfigdbl_1// "AsyncConfigDbLoadPlayback.txt"
0x2e9de  callvirt instance void Microsoft.Crm.ConfigDBInstrumentation::LoadSettings(string configFileName, string playbackFileName)
0x2e9e3  ret
0x2e9e4  ldc.i4.0
0x2e9e5  stsfld   bool Microsoft.Crm.AsyncConfigDbLoadInstrumentation::Enabled
0x2e9ea  ret
```
