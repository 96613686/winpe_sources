# Microsoft.Crm.Sandbox.SandboxCommon.CrmSandboxDiagnosticsEventSource::SandboxWorkerUnhandledException

- ea: `0xad20`
- end: `0xad9a`
- name: `Microsoft.Crm.Sandbox.SandboxCommon.CrmSandboxDiagnosticsEventSource::SandboxWorkerUnhandledException`
- size: `122`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xad20`

## pseudocode

```c

```

## disassembly

```asm
0xad20  ldarg.0
0xad21  call     instance bool [Microsoft.Diagnostics.Tracing.EventSource]Microsoft.Diagnostics.Tracing.EventSource::IsEnabled()
0xad26  brfalse.s loc_AD99
0xad28  ldarg.2
0xad29  callvirt instance int32 [mscorlib]System.String::get_Length()
0xad2e  ldc.i4   0x3A98
0xad33  ble.s    loc_AD43
0xad35  ldarg.2
0xad36  ldc.i4.0
0xad37  ldc.i4   0x3A98
0xad3c  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xad41  starg.s  2
0xad43  ldarg.3
0xad44  callvirt instance int32 [mscorlib]System.String::get_Length()
0xad49  ldc.i4   0x3A98
0xad4e  ble.s    loc_AD5E
0xad50  ldarg.3
0xad51  ldc.i4.0
0xad52  ldc.i4   0x3A98
0xad57  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xad5c  starg.s  3
0xad5e  ldarg.s  4
0xad60  callvirt instance int32 [mscorlib]System.String::get_Length()
0xad65  ldc.i4   0x3A98
0xad6a  ble.s    loc_AD7B
0xad6c  ldarg.s  4
0xad6e  ldc.i4.0
0xad6f  ldc.i4   0x3A98
0xad74  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xad79  starg.s  4
0xad7b  ldarg.0
0xad7c  ldc.i4.6
0xad7d  ldc.i4.4
0xad7e  newarr   [mscorlib]System.Object
0xad83  dup
0xad84  ldc.i4.0
0xad85  ldarg.1
0xad86  stelem.ref
0xad87  dup
0xad88  ldc.i4.1
0xad89  ldarg.2
0xad8a  stelem.ref
0xad8b  dup
0xad8c  ldc.i4.2
0xad8d  ldarg.3
0xad8e  stelem.ref
0xad8f  dup
0xad90  ldc.i4.3
0xad91  ldarg.s  4
0xad93  stelem.ref
0xad94  call     instance void [Microsoft.Diagnostics.Tracing.EventSource]Microsoft.Diagnostics.Tracing.EventSource::WriteEvent(int32, object[])
0xad99  ret
```
