# Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::EnsureValidTableHandle

- ea: `0x4e90`
- end: `0x4f11`
- name: `Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::EnsureValidTableHandle`
- size: `129`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x4d40`
- `0x4d90`

## callees

- `0x4d30`
- `0x4e90`
- `0x4f20`
- `0x4f40`
- `0x4fb0`
- `0x5000`

## pseudocode

```c

```

## disassembly

```asm
0x4e90  ldarg.0
0x4e91  ldfld    class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::tableCreationLock
0x4e96  callvirt instance void [System.Core]System.Threading.ReaderWriterLockSlim::EnterWriteLock()
0x4e9b  ldarg.1
0x4e9c  ldarg.0
0x4e9d  ldfld    native int Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::currentTableHandle
0x4ea2  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x4ea7  brfalse.s loc_4EAB
0x4ea9  leave.s  loc_4F10
0x4eab  ldarg.0
0x4eac  ldarg.1
0x4ead  call     instance void Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::CloseHandle(native int tableHandle)
0x4eb2  ldsfld   class [Microsoft.Cis.Monitoring.Tables]Microsoft.Cis.Monitoring.Tables.Writer Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::writer
0x4eb7  ldarg.0
0x4eb8  call     instance string Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::GetNextTableName()
0x4ebd  ldarg.0
0x4ebe  ldfld    string Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::workingDirectory
0x4ec3  ldc.i4.0
0x4ec4  ldarg.0
0x4ec5  callvirt instance valuetype [Microsoft.Cis.Monitoring.Tables]Microsoft.Cis.Monitoring.Tables.TablePriority Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::get_TablePriority()
0x4eca  ldc.i4   0x258
0x4ecf  conv.i8
0x4ed0  ldc.i4.s 0x1E
0x4ed2  conv.i8
0x4ed3  ldarg.0
0x4ed4  ldflda   native int Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::currentTableHandle
0x4ed9  callvirt instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 [Microsoft.Cis.Monitoring.Tables]Microsoft.Cis.Monitoring.Tables.Writer::CreateTable(string, string, valuetype [Microsoft.Cis.Monitoring.Tables]Microsoft.Cis.Monitoring.Tables.TableDisposition, valuetype [Microsoft.Cis.Monitoring.Tables]Microsoft.Cis.Monitoring.Tables.TablePriority, int64, int64, native int&)
0x4ede  pop
0x4edf  ldsfld   class [Microsoft.Cis.Monitoring.Tables]Microsoft.Cis.Monitoring.Tables.Writer Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::writer
0x4ee4  ldarg.0
0x4ee5  ldfld    native int Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::currentTableHandle
0x4eea  ldarg.0
0x4eeb  call     instance string[] Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::GetFieldNamesIncludingDefault()
0x4ef0  ldarg.0
0x4ef1  call     instance valuetype [Microsoft.Cis.Monitoring.Tables]Microsoft.Cis.Monitoring.Tables.TableFieldType[] Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::GetFieldTypesIncludingDefault()
0x4ef6  ldarg.0
0x4ef7  ldflda   unsigned int32 Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::currentSchemaHandle
0x4efc  callvirt instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 [Microsoft.Cis.Monitoring.Tables]Microsoft.Cis.Monitoring.Tables.Writer::AddTableSchema(native int, string[], valuetype [Microsoft.Cis.Monitoring.Tables]Microsoft.Cis.Monitoring.Tables.TableFieldType[], unsigned int32&)
0x4f01  pop
0x4f02  leave.s  loc_4F10
0x4f04  ldarg.0
0x4f05  ldfld    class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::tableCreationLock
0x4f0a  callvirt instance void [System.Core]System.Threading.ReaderWriterLockSlim::ExitWriteLock()
0x4f0f  endfinally
0x4f10  ret
```
