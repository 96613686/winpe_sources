# Microsoft.Crm.Sandbox.SandboxUtility::get_ProcessId

- ea: `0x3150`
- end: `0x3187`
- name: `Microsoft.Crm.Sandbox.SandboxUtility::get_ProcessId`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x3150`

## pseudocode

```c

```

## disassembly

```asm
0x3150  ldsfld   string Microsoft.Crm.Sandbox.SandboxUtility::_processId
0x3155  brtrue.s loc_3181
0x3157  call     class [System]System.Diagnostics.Process [System]System.Diagnostics.Process::GetCurrentProcess()
0x315c  stloc.0
0x315d  ldloc.0
0x315e  callvirt instance int32 [System]System.Diagnostics.Process::get_Id()
0x3163  stloc.1
0x3164  ldloca.s 1
0x3166  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x316b  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x3170  stsfld   string Microsoft.Crm.Sandbox.SandboxUtility::_processId
0x3175  leave.s  loc_3181
0x3177  ldloc.0
0x3178  brfalse.s loc_3180
0x317a  ldloc.0
0x317b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3180  endfinally
0x3181  ldsfld   string Microsoft.Crm.Sandbox.SandboxUtility::_processId
0x3186  ret
```
