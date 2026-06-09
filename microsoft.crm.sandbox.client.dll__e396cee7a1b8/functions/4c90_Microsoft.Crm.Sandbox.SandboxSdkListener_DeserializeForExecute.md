# Microsoft.Crm.Sandbox.SandboxSdkListener::DeserializeForExecute

- ea: `0x4c90`
- end: `0x4cc7`
- name: `Microsoft.Crm.Sandbox.SandboxSdkListener::DeserializeForExecute`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4b40`

## pseudocode

```c

```

## disassembly

```asm
0x4c90  ldarg.1
0x4c91  ldstr    aSerializedrequ// "serializedRequest"
0x4c96  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x4c9b  ldarg.1
0x4c9c  call     T0x2B000012
0x4ca1  stloc.0
0x4ca2  ldarg.2
0x4ca3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x4ca8  ldc.i4.s 0x27
0x4caa  ldstr    aExecuteSeriali// "Execute: serializedRequest.LongLength: "...
0x4caf  ldc.i4.1
0x4cb0  newarr   [mscorlib]System.Object
0x4cb5  dup
0x4cb6  ldc.i4.0
0x4cb7  ldarg.1
0x4cb8  ldlen
0x4cb9  conv.i8
0x4cba  box      [mscorlib]System.Int64
0x4cbf  stelem.ref
0x4cc0  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4cc5  ldloc.0
0x4cc6  ret
```
