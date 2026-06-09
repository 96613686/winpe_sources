# Microsoft.Crm.Workflow.WorkflowContext::DeserializeAsyncData

- ea: `0x1d80`
- end: `0x1e5d`
- name: `Microsoft.Crm.Workflow.WorkflowContext::DeserializeAsyncData`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18e0`

## callees

- `0x1d80`

## pseudocode

```c

```

## disassembly

```asm
0x1d80  ldarg.0
0x1d81  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1d86  brfalse.s loc_1D93
0x1d88  ldstr    aSerialized// "serialized"
0x1d8d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentNullException::.ctor(string)
0x1d92  throw
0x1d93  nop
0x1d94  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.WhoAmIRequest::.ctor()
0x1d99  pop
0x1d9a  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.WhoAmIResponse::.ctor()
0x1d9f  pop
0x1da0  ldarg.0
0x1da1  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0x1da6  stloc.0
0x1da7  ldloc.0
0x1da8  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [mscorlib]System.IO.TextReader)
0x1dad  stloc.1
0x1dae  ldsfld   class [System.Runtime.Serialization]System.Runtime.Serialization.DataContractSerializer Microsoft.Crm.Workflow.WorkflowContext::_serializer
0x1db3  ldloc.1
0x1db4  callvirt instance object [System.Runtime.Serialization]System.Runtime.Serialization.XmlObjectSerializer::ReadObject(class [System.Xml]System.Xml.XmlReader)
0x1db9  castclass [Microsoft.Crm]Microsoft.Crm.AsyncOperationData
0x1dbe  stloc.2
0x1dbf  leave    loc_1E5B
0x1dc4  ldloc.1
0x1dc5  brfalse.s loc_1DCD
0x1dc7  ldloc.1
0x1dc8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1dcd  endfinally
0x1dce  ldloc.0
0x1dcf  brfalse.s loc_1DD7
0x1dd1  ldloc.0
0x1dd2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1dd7  endfinally
0x1dd8  stloc.3
0x1dd9  ldloc.3
0x1dda  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1ddf  ldc.i4.s 0x15
0x1de1  ldstr    aInvalidDataFou// "Invalid data found for operation type: "...
0x1de6  ldc.i4.3
0x1de7  newarr   [mscorlib]System.Object
0x1dec  dup
0x1ded  ldc.i4.0
0x1dee  ldarg.1
0x1def  callvirt instance int32 [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IGenericEventData::get_OperationType()
0x1df4  box      [mscorlib]System.Int32
0x1df9  stelem.ref
0x1dfa  dup
0x1dfb  ldc.i4.1
0x1dfc  ldarg.1
0x1dfd  callvirt instance string [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IGenericEventData::get_Data()
0x1e02  stelem.ref
0x1e03  dup
0x1e04  ldc.i4.2
0x1e05  ldloc.3
0x1e06  stelem.ref
0x1e07  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1e0c  ldstr    aInvalidData// "Invalid data"
0x1e11  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x1e16  throw
0x1e17  stloc.s  4
0x1e19  ldloc.s  4
0x1e1b  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1e20  ldc.i4.s 0x15
0x1e22  ldstr    aInvalidDataFou// "Invalid data found for operation type: "...
0x1e27  ldc.i4.3
0x1e28  newarr   [mscorlib]System.Object
0x1e2d  dup
0x1e2e  ldc.i4.0
0x1e2f  ldarg.1
0x1e30  callvirt instance int32 [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IGenericEventData::get_OperationType()
0x1e35  box      [mscorlib]System.Int32
0x1e3a  stelem.ref
0x1e3b  dup
0x1e3c  ldc.i4.1
0x1e3d  ldarg.1
0x1e3e  callvirt instance string [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IGenericEventData::get_Data()
0x1e43  stelem.ref
0x1e44  dup
0x1e45  ldc.i4.2
0x1e46  ldloc.s  4
0x1e48  stelem.ref
0x1e49  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1e4e  ldstr    aInvalidData// "Invalid data"
0x1e53  ldloc.s  4
0x1e55  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string, class [mscorlib]System.Exception)
0x1e5a  throw
0x1e5b  ldloc.2
0x1e5c  ret
```
