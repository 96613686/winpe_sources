# Microsoft.Crm.Sandbox.SandboxCommon.CrmSandboxDiagnosticsEventSource::SandboxExecutionDiagnostics

- ea: `0xaa80`
- end: `0xabf9`
- name: `Microsoft.Crm.Sandbox.SandboxCommon.CrmSandboxDiagnosticsEventSource::SandboxExecutionDiagnostics`
- size: `377`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xaa80`

## pseudocode

```c

```

## disassembly

```asm
0xaa80  ldarg.0
0xaa81  call     instance bool [Microsoft.Diagnostics.Tracing.EventSource]Microsoft.Diagnostics.Tracing.EventSource::IsEnabled()
0xaa86  brfalse  loc_ABF8
0xaa8b  ldarg.s  7
0xaa8d  callvirt instance int32 [mscorlib]System.String::get_Length()
0xaa92  ldc.i4   0x3A98
0xaa97  ble.s    loc_AAA8
0xaa99  ldarg.s  7
0xaa9b  ldc.i4.0
0xaa9c  ldc.i4   0x3A98
0xaaa1  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xaaa6  starg.s  7
0xaaa8  ldarg.s  8
0xaaaa  callvirt instance int32 [mscorlib]System.String::get_Length()
0xaaaf  ldc.i4   0x3A98
0xaab4  ble.s    loc_AAC5
0xaab6  ldarg.s  8
0xaab8  ldc.i4.0
0xaab9  ldc.i4   0x3A98
0xaabe  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xaac3  starg.s  8
0xaac5  ldarg.0
0xaac6  ldfld    string Microsoft.Crm.Sandbox.SandboxCommon.CrmSandboxDiagnosticsEventSource::_fileVersion
0xaacb  starg.s  0x20
0xaacd  ldarg.0
0xaace  ldc.i4.1
0xaacf  ldc.i4.s 0x20
0xaad1  newarr   [mscorlib]System.Object
0xaad6  dup
0xaad7  ldc.i4.0
0xaad8  ldarg.1
0xaad9  box      [mscorlib]System.Guid
0xaade  stelem.ref
0xaadf  dup
0xaae0  ldc.i4.1
0xaae1  ldarg.2
0xaae2  stelem.ref
0xaae3  dup
0xaae4  ldc.i4.2
0xaae5  ldarg.3
0xaae6  box      [mscorlib]System.Boolean
0xaaeb  stelem.ref
0xaaec  dup
0xaaed  ldc.i4.3
0xaaee  ldarg.s  4
0xaaf0  box      [mscorlib]System.Guid
0xaaf5  stelem.ref
0xaaf6  dup
0xaaf7  ldc.i4.4
0xaaf8  ldarg.s  5
0xaafa  box      [mscorlib]System.Guid
0xaaff  stelem.ref
0xab00  dup
0xab01  ldc.i4.5
0xab02  ldarg.s  6
0xab04  stelem.ref
0xab05  dup
0xab06  ldc.i4.6
0xab07  ldarg.s  7
0xab09  stelem.ref
0xab0a  dup
0xab0b  ldc.i4.7
0xab0c  ldarg.s  8
0xab0e  stelem.ref
0xab0f  dup
0xab10  ldc.i4.8
0xab11  ldarg.s  9
0xab13  stelem.ref
0xab14  dup
0xab15  ldc.i4.s 9
0xab17  ldarg.s  0xA
0xab19  box      [mscorlib]System.Double
0xab1e  stelem.ref
0xab1f  dup
0xab20  ldc.i4.s 0xA
0xab22  ldarg.s  0xB
0xab24  box      [mscorlib]System.Int32
0xab29  stelem.ref
0xab2a  dup
0xab2b  ldc.i4.s 0xB
0xab2d  ldarg.s  0xC
0xab2f  stelem.ref
0xab30  dup
0xab31  ldc.i4.s 0xC
0xab33  ldarg.s  0xD
0xab35  stelem.ref
0xab36  dup
0xab37  ldc.i4.s 0xD
0xab39  ldarg.s  0xE
0xab3b  stelem.ref
0xab3c  dup
0xab3d  ldc.i4.s 0xE
0xab3f  ldarg.s  0xF
0xab41  box      [mscorlib]System.Guid
0xab46  stelem.ref
0xab47  dup
0xab48  ldc.i4.s 0xF
0xab4a  ldarg.s  0x10
0xab4c  box      [mscorlib]System.Int32
0xab51  stelem.ref
0xab52  dup
0xab53  ldc.i4.s 0x10
0xab55  ldarg.s  0x11
0xab57  box      [mscorlib]System.Guid
0xab5c  stelem.ref
0xab5d  dup
0xab5e  ldc.i4.s 0x11
0xab60  ldarg.s  0x12
0xab62  box      [mscorlib]System.Guid
0xab67  stelem.ref
0xab68  dup
0xab69  ldc.i4.s 0x12
0xab6b  ldarg.s  0x13
0xab6d  stelem.ref
0xab6e  dup
0xab6f  ldc.i4.s 0x13
0xab71  ldarg.s  0x14
0xab73  box      [mscorlib]System.Boolean
0xab78  stelem.ref
0xab79  dup
0xab7a  ldc.i4.s 0x14
0xab7c  ldarg.s  0x15
0xab7e  box      [mscorlib]System.Int32
0xab83  stelem.ref
0xab84  dup
0xab85  ldc.i4.s 0x15
0xab87  ldarg.s  0x16
0xab89  box      [mscorlib]System.Int32
0xab8e  stelem.ref
0xab8f  dup
0xab90  ldc.i4.s 0x16
0xab92  ldarg.s  0x17
0xab94  box      [mscorlib]System.Int32
0xab99  stelem.ref
0xab9a  dup
0xab9b  ldc.i4.s 0x17
0xab9d  ldarg.s  0x18
0xab9f  box      [mscorlib]System.Int32
0xaba4  stelem.ref
0xaba5  dup
0xaba6  ldc.i4.s 0x18
0xaba8  ldarg.s  0x19
0xabaa  box      [mscorlib]System.Int32
0xabaf  stelem.ref
0xabb0  dup
0xabb1  ldc.i4.s 0x19
0xabb3  ldarg.s  0x1A
0xabb5  box      [mscorlib]System.Int32
0xabba  stelem.ref
0xabbb  dup
0xabbc  ldc.i4.s 0x1A
0xabbe  ldarg.s  0x1B
0xabc0  box      [mscorlib]System.Int32
0xabc5  stelem.ref
0xabc6  dup
0xabc7  ldc.i4.s 0x1B
0xabc9  ldarg.s  0x1C
0xabcb  box      [mscorlib]System.Int32
0xabd0  stelem.ref
0xabd1  dup
0xabd2  ldc.i4.s 0x1C
0xabd4  ldarg.s  0x1D
0xabd6  box      [mscorlib]System.Int32
0xabdb  stelem.ref
0xabdc  dup
0xabdd  ldc.i4.s 0x1D
0xabdf  ldarg.s  0x1E
0xabe1  box      [mscorlib]System.Int32
0xabe6  stelem.ref
0xabe7  dup
0xabe8  ldc.i4.s 0x1E
0xabea  ldarg.s  0x1F
0xabec  stelem.ref
0xabed  dup
0xabee  ldc.i4.s 0x1F
0xabf0  ldarg.s  0x20
0xabf2  stelem.ref
0xabf3  call     instance void [Microsoft.Diagnostics.Tracing.EventSource]Microsoft.Diagnostics.Tracing.EventSource::WriteEvent(int32, object[])
0xabf8  ret
```
