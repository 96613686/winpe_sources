# Microsoft.Crm.Sandbox.SandboxCallbackService::Initialize

- ea: `0x2010`
- end: `0x202a`
- name: `Microsoft.Crm.Sandbox.SandboxCallbackService::Initialize`
- size: `26`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1f70`
- `0x2480`
- `0x2680`
- `0x2780`

## callees

- `0x2240`

## pseudocode

```c

```

## disassembly

```asm
0x2010  ldarg.0
0x2011  call     instance class Microsoft.Crm.Sandbox.SandboxSdkClient Microsoft.Crm.Sandbox.SandboxCallbackService::InitializeInternal()
0x2016  dup
0x2017  ldc.i4.0
0x2018  ldc.i4.0
0x2019  ldarg.0
0x201a  ldfld    int32 Microsoft.Crm.Sandbox.SandboxMarshalByRefObject::leaseTime
0x201f  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x2024  callvirt instance void class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientBase`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxSdkListener>::SetOperationTimeout(valuetype [mscorlib]System.TimeSpan)
0x2029  ret
```
