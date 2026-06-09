# Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::get_Instance

- ea: `0x10900`
- end: `0x1090b`
- name: `Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::get_Instance`
- size: `11`
- prototype: ``
- caller_count: `27`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x2950`
- `0x46b0`
- `0x50a0`
- `0x62e0`
- `0x69a0`
- `0x6ac0`
- `0x6c30`
- `0x7c50`
- `0x8040`
- `0x8770`
- `0x93d0`
- `0xa9d0`
- `0xad30`
- `0xae90`
- `0xaf50`
- `0xb0f0`
- `0xb1a0`
- `0xb280`
- `0xb9b0`
- `0xdde0`
- `0xe0d0`
- `0x11d70`
- `0x12780`
- `0x127c0`
- `0x13700`
- `0x137b0`
- `0x16b90`

## pseudocode

```c

```

## disassembly

```asm
0x10900  ldsfld   class [mscorlib]System.Lazy`1<class Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger> Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LazyInstance
0x10905  callvirt instance var<u1> class [mscorlib]System.Lazy`1<class Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger>::get_Value()
0x1090a  ret
```
