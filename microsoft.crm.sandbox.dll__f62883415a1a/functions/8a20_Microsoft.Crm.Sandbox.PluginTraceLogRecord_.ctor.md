# Microsoft.Crm.Sandbox.PluginTraceLogRecord::.ctor

- ea: `0x8a20`
- end: `0x8ad9`
- name: `Microsoft.Crm.Sandbox.PluginTraceLogRecord::.ctor`
- size: `185`
- prototype: ``
- caller_count: `0`
- callee_count: `22`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x8710`
- `0x8730`
- `0x8750`
- `0x8770`
- `0x8790`
- `0x87b0`
- `0x87d0`
- `0x87f0`
- `0x8810`
- `0x8830`
- `0x8850`
- `0x8870`
- `0x8890`
- `0x88b0`
- `0x88d0`
- `0x88f0`
- `0x8910`
- `0x8930`
- `0x8950`
- `0x8970`
- `0x8990`
- `0x89b0`

## pseudocode

```c

```

## disassembly

```asm
0x8a20  ldarg.0
0x8a21  call     instance void [mscorlib]System.Object::.ctor()
0x8a26  ldarg.0
0x8a27  ldarg.1
0x8a28  call     instance void Microsoft.Crm.Sandbox.PluginTraceLogRecord::set_OrganizationId(valuetype [mscorlib]System.Guid value)
0x8a2d  ldarg.0
0x8a2e  ldarg.2
0x8a2f  call     instance void Microsoft.Crm.Sandbox.PluginTraceLogRecord::set_PluginTraceLogId(valuetype [mscorlib]System.Guid value)
0x8a34  ldarg.0
0x8a35  ldarg.3
0x8a36  call     instance void Microsoft.Crm.Sandbox.PluginTraceLogRecord::set_Configuration(string value)
0x8a3b  ldarg.0
0x8a3c  ldarg.s  4
0x8a3e  call     instance void Microsoft.Crm.Sandbox.PluginTraceLogRecord::set_MessageName(string value)
0x8a43  ldarg.0
0x8a44  ldarg.s  5
0x8a46  call     instance void Microsoft.Crm.Sandbox.PluginTraceLogRecord::set_Depth(int32 value)
0x8a4b  ldarg.0
0x8a4c  ldarg.s  6
0x8a4e  call     instance void Microsoft.Crm.Sandbox.PluginTraceLogRecord::set_Mode(int32 value)
0x8a53  ldarg.0
0x8a54  ldarg.s  7
0x8a56  call     instance void Microsoft.Crm.Sandbox.PluginTraceLogRecord::set_OperationType(int32 value)
0x8a5b  ldarg.0
0x8a5c  ldarg.s  8
0x8a5e  call     instance void Microsoft.Crm.Sandbox.PluginTraceLogRecord::set_PerformanceConstructorDuration(int32 value)
0x8a63  ldarg.0
0x8a64  ldarg.s  9
0x8a66  call     instance void Microsoft.Crm.Sandbox.PluginTraceLogRecord::set_PerformanceConstructorStartTime(valuetype [mscorlib]System.DateTime value)
0x8a6b  ldarg.0
0x8a6c  ldarg.s  0xA
0x8a6e  call     instance void Microsoft.Crm.Sandbox.PluginTraceLogRecord::set_PerformanceExecutionDuration(int32 value)
0x8a73  ldarg.0
0x8a74  ldarg.s  0xB
0x8a76  call     instance void Microsoft.Crm.Sandbox.PluginTraceLogRecord::set_PerformanceExecutionStartTime(valuetype [mscorlib]System.DateTime value)
0x8a7b  ldarg.0
0x8a7c  ldarg.s  0xC
0x8a7e  call     instance void Microsoft.Crm.Sandbox.PluginTraceLogRecord::set_PersistenceKey(valuetype [mscorlib]System.Guid value)
0x8a83  ldarg.0
0x8a84  ldarg.s  0xD
0x8a86  call     instance void Microsoft.Crm.Sandbox.PluginTraceLogRecord::set_PrimaryEntity(string value)
0x8a8b  ldarg.0
0x8a8c  ldarg.s  0xE
0x8a8e  call     instance void Microsoft.Crm.Sandbox.PluginTraceLogRecord::set_Profile(string value)
0x8a93  ldarg.0
0x8a94  ldarg.s  0xF
0x8a96  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x8a9b  call     instance void Microsoft.Crm.Sandbox.PluginTraceLogRecord::set_RequestId(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> value)
0x8aa0  ldarg.0
0x8aa1  ldarg.s  0x10
0x8aa3  call     instance void Microsoft.Crm.Sandbox.PluginTraceLogRecord::set_SecureConfiguration(string value)
0x8aa8  ldarg.0
0x8aa9  ldarg.s  0x11
0x8aab  call     instance void Microsoft.Crm.Sandbox.PluginTraceLogRecord::set_PluginTypeName(string value)
0x8ab0  ldarg.0
0x8ab1  ldarg.s  0x12
0x8ab3  call     instance void Microsoft.Crm.Sandbox.PluginTraceLogRecord::set_PluginStepId(valuetype [mscorlib]System.Guid value)
0x8ab8  ldarg.0
0x8ab9  ldarg.s  0x13
0x8abb  call     instance void Microsoft.Crm.Sandbox.PluginTraceLogRecord::set_TraceText(string value)
0x8ac0  ldarg.0
0x8ac1  ldarg.s  0x14
0x8ac3  call     instance void Microsoft.Crm.Sandbox.PluginTraceLogRecord::set_ExceptionDetails(string value)
0x8ac8  ldarg.0
0x8ac9  ldarg.s  0x15
0x8acb  call     instance void Microsoft.Crm.Sandbox.PluginTraceLogRecord::set_CorrelationId(valuetype [mscorlib]System.Guid value)
0x8ad0  ldarg.0
0x8ad1  ldarg.s  0x16
0x8ad3  call     instance void Microsoft.Crm.Sandbox.PluginTraceLogRecord::set_IsSystemCreated(bool value)
0x8ad8  ret
```
