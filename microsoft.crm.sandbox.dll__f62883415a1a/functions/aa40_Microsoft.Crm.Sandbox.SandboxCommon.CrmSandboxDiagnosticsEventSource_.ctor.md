# Microsoft.Crm.Sandbox.SandboxCommon.CrmSandboxDiagnosticsEventSource::.ctor

- ea: `0xaa40`
- end: `0xaa7a`
- name: `Microsoft.Crm.Sandbox.SandboxCommon.CrmSandboxDiagnosticsEventSource::.ctor`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xb320`

## callees

- `0xaa40`

## pseudocode

```c

```

## disassembly

```asm
0xaa40  ldarg.0
0xaa41  call     instance void [Microsoft.Diagnostics.Tracing.EventSource]Microsoft.Diagnostics.Tracing.EventSource::.ctor()
0xaa46  ldarg.0
0xaa47  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xaa4c  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0xaa51  callvirt instance string [mscorlib]System.Reflection.Assembly::get_Location()
0xaa56  stloc.0
0xaa57  ldloc.0
0xaa58  brfalse.s loc_AA6E
0xaa5a  ldloc.0
0xaa5b  call     class [System]System.Diagnostics.FileVersionInfo [System]System.Diagnostics.FileVersionInfo::GetVersionInfo(string)
0xaa60  stloc.1
0xaa61  ldarg.0
0xaa62  ldloc.1
0xaa63  callvirt instance string [System]System.Diagnostics.FileVersionInfo::get_FileVersion()
0xaa68  stfld    string Microsoft.Crm.Sandbox.SandboxCommon.CrmSandboxDiagnosticsEventSource::_fileVersion
0xaa6d  ret
0xaa6e  ldarg.0
0xaa6f  ldstr    aUnknown// "unknown"
0xaa74  stfld    string Microsoft.Crm.Sandbox.SandboxCommon.CrmSandboxDiagnosticsEventSource::_fileVersion
0xaa79  ret
```
