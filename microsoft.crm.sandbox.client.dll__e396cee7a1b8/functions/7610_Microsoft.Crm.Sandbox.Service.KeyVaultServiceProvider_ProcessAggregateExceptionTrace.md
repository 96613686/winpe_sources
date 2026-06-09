# Microsoft.Crm.Sandbox.Service.KeyVaultServiceProvider::ProcessAggregateExceptionTrace

- ea: `0x7610`
- end: `0x7664`
- name: `Microsoft.Crm.Sandbox.Service.KeyVaultServiceProvider::ProcessAggregateExceptionTrace`
- size: `84`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x7350`
- `0x73a0`
- `0x7520`

## callees

- `0x7610`

## string_xrefs

- `0x762a`: `KeyVaultServiceProvider.ProcessAggregateExceptionTrace: {0} - {1}`

## pseudocode

```c

```

## disassembly

```asm
0x7610  ldarg.1
0x7611  stloc.0
0x7612  ldarg.1
0x7613  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x7618  brfalse.s loc_7621
0x761a  ldarg.1
0x761b  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x7620  stloc.0
0x7621  ldnull
0x7622  ldarg.2
0x7623  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x7628  ldc.i4.s 0x1F
0x762a  ldstr    aKeyvaultservic_2// "KeyVaultServiceProvider.ProcessAggregat"...
0x762f  ldc.i4.2
0x7630  newarr   [mscorlib]System.Object
0x7635  dup
0x7636  ldc.i4.0
0x7637  ldarg.3
0x7638  stelem.ref
0x7639  dup
0x763a  ldc.i4.1
0x763b  ldloc.0
0x763c  callvirt instance string [mscorlib]System.Exception::get_Message()
0x7641  stelem.ref
0x7642  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7647  ldstr    a01_0// "{0} - {1}"
0x764c  ldarg.3
0x764d  ldloc.0
0x764e  callvirt instance string [mscorlib]System.Exception::get_Message()
0x7653  call     string [mscorlib]System.String::Format(string, object, object)
0x7658  ldloc.0
0x7659  ldc.i4   0x8009100C
0x765e  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.CrmExceptions.CrmKeyVaultException::.ctor(string, class [mscorlib]System.Exception, int32)
0x7663  throw
```
