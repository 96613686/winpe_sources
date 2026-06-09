# Microsoft.Crm.Sandbox.ExceptionConverterExtension::SafeTryConvertToFaultException_0

- ea: `0xcb0`
- end: `0xcfe`
- name: `Microsoft.Crm.Sandbox.ExceptionConverterExtension::SafeTryConvertToFaultException_0`
- size: `78`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0xcb0`
- `0x1130`
- `0x1420`

## pseudocode

```c

```

## disassembly

```asm
0xcb0  ldarg.0
0xcb1  ldarg.1
0xcb2  ldarg.2
0xcb3  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.ExceptionConverter::TryConvertToFaultException(class [mscorlib]System.Exception, class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>&)
0xcb8  stloc.0
0xcb9  leave.s  loc_CFC
0xcbb  stloc.1
0xcbc  ldloc.1
0xcbd  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxTrace::get_OrganizationId()
0xcc2  ldc.i4.s 0x21
0xcc4  ldstr    aSandboxhostHan// "SandboxHost.HandleException: UNEXPECTED"...
0xcc9  ldc.i4.2
0xcca  newarr   [mscorlib]System.Object
0xccf  dup
0xcd0  ldc.i4.0
0xcd1  ldarg.1
0xcd2  callvirt instance string [mscorlib]System.Object::ToString()
0xcd7  stelem.ref
0xcd8  dup
0xcd9  ldc.i4.1
0xcda  ldloc.1
0xcdb  callvirt instance string [mscorlib]System.Object::ToString()
0xce0  stelem.ref
0xce1  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0xce6  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault::.ctor()
0xceb  dup
0xcec  ldstr    aUnexpectedTryc_0// "UNEXPECTED TryConvertToFaultException. "...
0xcf1  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::set_Message(string)
0xcf6  newobj   instance void class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::.ctor(var<u1>)
0xcfb  throw
0xcfc  ldloc.0
0xcfd  ret
```
