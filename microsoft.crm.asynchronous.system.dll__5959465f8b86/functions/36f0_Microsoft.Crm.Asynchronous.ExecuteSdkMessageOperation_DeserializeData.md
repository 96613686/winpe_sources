# Microsoft.Crm.Asynchronous.ExecuteSdkMessageOperation::DeserializeData

- ea: `0x36f0`
- end: `0x3740`
- name: `Microsoft.Crm.Asynchronous.ExecuteSdkMessageOperation::DeserializeData`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x3680`

## callees

- `0x36f0`

## pseudocode

```c

```

## disassembly

```asm
0x36f0  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest
0x36f5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x36fa  ldnull
0x36fb  ldc.i4   0x7FFFFFFF
0x3700  ldc.i4.1
0x3701  ldc.i4.0
0x3702  ldnull
0x3703  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.KnownTypesResolver::.ctor()
0x3708  newobj   instance void [System.Runtime.Serialization]System.Runtime.Serialization.DataContractSerializer::.ctor(class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Type>, int32, bool, bool, class [System.Runtime.Serialization]System.Runtime.Serialization.IDataContractSurrogate, class [System.Runtime.Serialization]System.Runtime.Serialization.DataContractResolver)
0x370d  stloc.0
0x370e  ldarg.1
0x370f  ldstr    aData// "data"
0x3714  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x3719  ldarg.1
0x371a  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0x371f  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [mscorlib]System.IO.TextReader)
0x3724  stloc.1
0x3725  ldloc.0
0x3726  ldloc.1
0x3727  callvirt instance object [System.Runtime.Serialization]System.Runtime.Serialization.XmlObjectSerializer::ReadObject(class [System.Xml]System.Xml.XmlReader)
0x372c  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest
0x3731  stloc.2
0x3732  leave.s  loc_373E
0x3734  ldloc.1
0x3735  brfalse.s loc_373D
0x3737  ldloc.1
0x3738  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x373d  endfinally
0x373e  ldloc.2
0x373f  ret
```
