# Microsoft.Crm.Sandbox.SandboxCommon.CrmSandboxDiagnosticsEventSource::SandboxHostUnhandledException

- ea: `0xaca0`
- end: `0xad1a`
- name: `Microsoft.Crm.Sandbox.SandboxCommon.CrmSandboxDiagnosticsEventSource::SandboxHostUnhandledException`
- size: `122`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xaca0`

## pseudocode

```c

```

## disassembly

```asm
0xaca0  ldarg.0
0xaca1  call     instance bool [Microsoft.Diagnostics.Tracing.EventSource]Microsoft.Diagnostics.Tracing.EventSource::IsEnabled()
0xaca6  brfalse.s loc_AD19
0xaca8  ldarg.2
0xaca9  callvirt instance int32 [mscorlib]System.String::get_Length()
0xacae  ldc.i4   0x3A98
0xacb3  ble.s    loc_ACC3
0xacb5  ldarg.2
0xacb6  ldc.i4.0
0xacb7  ldc.i4   0x3A98
0xacbc  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xacc1  starg.s  2
0xacc3  ldarg.3
0xacc4  callvirt instance int32 [mscorlib]System.String::get_Length()
0xacc9  ldc.i4   0x3A98
0xacce  ble.s    loc_ACDE
0xacd0  ldarg.3
0xacd1  ldc.i4.0
0xacd2  ldc.i4   0x3A98
0xacd7  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xacdc  starg.s  3
0xacde  ldarg.s  4
0xace0  callvirt instance int32 [mscorlib]System.String::get_Length()
0xace5  ldc.i4   0x3A98
0xacea  ble.s    loc_ACFB
0xacec  ldarg.s  4
0xacee  ldc.i4.0
0xacef  ldc.i4   0x3A98
0xacf4  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xacf9  starg.s  4
0xacfb  ldarg.0
0xacfc  ldc.i4.5
0xacfd  ldc.i4.4
0xacfe  newarr   [mscorlib]System.Object
0xad03  dup
0xad04  ldc.i4.0
0xad05  ldarg.1
0xad06  stelem.ref
0xad07  dup
0xad08  ldc.i4.1
0xad09  ldarg.2
0xad0a  stelem.ref
0xad0b  dup
0xad0c  ldc.i4.2
0xad0d  ldarg.3
0xad0e  stelem.ref
0xad0f  dup
0xad10  ldc.i4.3
0xad11  ldarg.s  4
0xad13  stelem.ref
0xad14  call     instance void [Microsoft.Diagnostics.Tracing.EventSource]Microsoft.Diagnostics.Tracing.EventSource::WriteEvent(int32, object[])
0xad19  ret
```
