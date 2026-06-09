# Microsoft.Crm.Asynchronous.AsyncExecutionContext::DeserializeAsyncData

- ea: `0x8d00`
- end: `0x8dd5`
- name: `Microsoft.Crm.Asynchronous.AsyncExecutionContext::DeserializeAsyncData`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x8be0`

## callees

- `0x2d30`
- `0x5f40`
- `0x8d00`

## pseudocode

```c

```

## disassembly

```asm
0x8d00  ldarg.0
0x8d01  callvirt instance string Microsoft.Crm.Asynchronous.AsyncEvent::get_Data()
0x8d06  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8d0b  brfalse.s loc_8D18
0x8d0d  ldstr    aData// "data"
0x8d12  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentNullException::.ctor(string)
0x8d17  throw
0x8d18  nop
0x8d19  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.WhoAmIRequest::.ctor()
0x8d1e  pop
0x8d1f  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.WhoAmIResponse::.ctor()
0x8d24  pop
0x8d25  ldarg.0
0x8d26  callvirt instance string Microsoft.Crm.Asynchronous.AsyncEvent::get_Data()
0x8d2b  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0x8d30  stloc.0
0x8d31  ldloc.0
0x8d32  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [mscorlib]System.IO.TextReader)
0x8d37  stloc.1
0x8d38  ldsfld   class [System.Runtime.Serialization]System.Runtime.Serialization.DataContractSerializer Microsoft.Crm.Asynchronous.AsyncExecutionContext::_serializer
0x8d3d  ldloc.1
0x8d3e  callvirt instance object [System.Runtime.Serialization]System.Runtime.Serialization.XmlObjectSerializer::ReadObject(class [System.Xml]System.Xml.XmlReader)
0x8d43  castclass [Microsoft.Crm]Microsoft.Crm.AsyncOperationData
0x8d48  stloc.2
0x8d49  leave    loc_8DD3
0x8d4e  ldloc.1
0x8d4f  brfalse.s loc_8D57
0x8d51  ldloc.1
0x8d52  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8d57  endfinally
0x8d58  ldloc.0
0x8d59  brfalse.s loc_8D61
0x8d5b  ldloc.0
0x8d5c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8d61  endfinally
0x8d62  stloc.3
0x8d63  ldloc.3
0x8d64  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x8d69  ldc.i4.s 0x15
0x8d6b  ldstr    aInvalidDataFou// "Invalid data found for operation type: "...
0x8d70  ldc.i4.2
0x8d71  newarr   [mscorlib]System.Object
0x8d76  dup
0x8d77  ldc.i4.0
0x8d78  ldarg.0
0x8d79  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncEventBase::get_OperationType()
0x8d7e  box      [mscorlib]System.Int32
0x8d83  stelem.ref
0x8d84  dup
0x8d85  ldc.i4.1
0x8d86  ldloc.3
0x8d87  stelem.ref
0x8d88  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8d8d  ldstr    aInvalidData// "Invalid data"
0x8d92  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x8d97  throw
0x8d98  stloc.s  4
0x8d9a  ldloc.s  4
0x8d9c  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x8da1  ldc.i4.s 0x15
0x8da3  ldstr    aInvalidDataFou// "Invalid data found for operation type: "...
0x8da8  ldc.i4.2
0x8da9  newarr   [mscorlib]System.Object
0x8dae  dup
0x8daf  ldc.i4.0
0x8db0  ldarg.0
0x8db1  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncEventBase::get_OperationType()
0x8db6  box      [mscorlib]System.Int32
0x8dbb  stelem.ref
0x8dbc  dup
0x8dbd  ldc.i4.1
0x8dbe  ldloc.s  4
0x8dc0  stelem.ref
0x8dc1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8dc6  ldstr    aInvalidData// "Invalid data"
0x8dcb  ldloc.s  4
0x8dcd  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string, class [mscorlib]System.Exception)
0x8dd2  throw
0x8dd3  ldloc.2
0x8dd4  ret
```
