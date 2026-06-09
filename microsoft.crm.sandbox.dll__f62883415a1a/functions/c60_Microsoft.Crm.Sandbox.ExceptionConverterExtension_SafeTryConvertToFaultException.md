# Microsoft.Crm.Sandbox.ExceptionConverterExtension::SafeTryConvertToFaultException

- ea: `0xc60`
- end: `0xcaf`
- name: `Microsoft.Crm.Sandbox.ExceptionConverterExtension::SafeTryConvertToFaultException`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0xc60`
- `0x1130`
- `0x1420`

## pseudocode

```c

```

## disassembly

```asm
0xc60  ldarg.0
0xc61  ldarg.1
0xc62  ldarg.2
0xc63  ldarg.3
0xc64  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.ExceptionConverter::TryConvertToFaultException(class [mscorlib]System.Exception, bool, class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>&)
0xc69  stloc.0
0xc6a  leave.s  loc_CAD
0xc6c  stloc.1
0xc6d  ldloc.1
0xc6e  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxTrace::get_OrganizationId()
0xc73  ldc.i4.s 0x21
0xc75  ldstr    aUnexpectedTryc// "UNEXPECTED TryConvertToFaultException. "...
0xc7a  ldc.i4.2
0xc7b  newarr   [mscorlib]System.Object
0xc80  dup
0xc81  ldc.i4.0
0xc82  ldarg.1
0xc83  callvirt instance string [mscorlib]System.Object::ToString()
0xc88  stelem.ref
0xc89  dup
0xc8a  ldc.i4.1
0xc8b  ldloc.1
0xc8c  callvirt instance string [mscorlib]System.Object::ToString()
0xc91  stelem.ref
0xc92  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0xc97  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault::.ctor()
0xc9c  dup
0xc9d  ldstr    aUnexpectedTryc_0// "UNEXPECTED TryConvertToFaultException. "...
0xca2  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::set_Message(string)
0xca7  newobj   instance void class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::.ctor(var<u1>)
0xcac  throw
0xcad  ldloc.0
0xcae  ret
```
