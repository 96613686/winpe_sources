# Microsoft.Crm.Sandbox.SandboxUtility::DeserializeDataContract_0

- ea: `0x2f20`
- end: `0x2fb4`
- name: `Microsoft.Crm.Sandbox.SandboxUtility::DeserializeDataContract_0`
- size: `148`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x2f20`
- `0x2fc0`

## pseudocode

```c

```

## disassembly

```asm
0x2f20  ldarg.0
0x2f21  brtrue.s loc_2F2D
0x2f23  ldloca.s 0
0x2f25  initobj  mvar<u1>
0x2f2b  ldloc.0
0x2f2c  ret
0x2f2d  nop
0x2f2e  ldc.i4.1
0x2f2f  newobj   instance void [mscorlib]System.Security.PermissionSet::.ctor(valuetype [mscorlib]System.Security.Permissions.PermissionState)
0x2f34  call     instance void [mscorlib]System.Security.PermissionSet::Assert()
0x2f39  call     void Microsoft.Crm.Sandbox.SandboxUtility::LoadKnownTypes()
0x2f3e  ldnull
0x2f3f  stloc.1
0x2f40  ldarg.1
0x2f41  ldnull
0x2f42  call     bool [mscorlib]System.Reflection.Assembly::op_Inequality(class [mscorlib]System.Reflection.Assembly, class [mscorlib]System.Reflection.Assembly)
0x2f47  brfalse.s loc_2F50
0x2f49  ldarg.1
0x2f4a  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ProxySerializationSurrogate::.ctor(class [mscorlib]System.Reflection.Assembly)
0x2f4f  stloc.1
0x2f50  ldtoken  mvar<u1>
0x2f55  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2f5a  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Type> Microsoft.Crm.Sandbox.SandboxUtility::_knownTypes
0x2f5f  ldc.i4   0x7FFFFFFF
0x2f64  ldc.i4.1
0x2f65  ldc.i4.0
0x2f66  ldloc.1
0x2f67  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.KnownTypesResolver::.ctor()
0x2f6c  newobj   instance void [System.Runtime.Serialization]System.Runtime.Serialization.DataContractSerializer::.ctor(class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Type>, int32, bool, bool, class [System.Runtime.Serialization]System.Runtime.Serialization.IDataContractSurrogate, class [System.Runtime.Serialization]System.Runtime.Serialization.DataContractResolver)
0x2f71  stloc.2
0x2f72  ldarg.0
0x2f73  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor(unsigned int8[])
0x2f78  stloc.3
0x2f79  ldloc.3
0x2f7a  call     class [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas::get_Max()
0x2f7f  call     class [System.Runtime.Serialization]System.Xml.XmlDictionaryReader [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::CreateBinaryReader(class [mscorlib]System.IO.Stream, class [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas)
0x2f84  stloc.s  4
0x2f86  ldloc.2
0x2f87  ldloc.s  4
0x2f89  callvirt instance object [System.Runtime.Serialization]System.Runtime.Serialization.XmlObjectSerializer::ReadObject(class [System.Runtime.Serialization]System.Xml.XmlDictionaryReader)
0x2f8e  unbox.any mvar<u1>
0x2f93  stloc.0
0x2f94  leave.s  loc_2FB2
0x2f96  ldloc.s  4
0x2f98  brfalse.s loc_2FA1
0x2f9a  ldloc.s  4
0x2f9c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2fa1  endfinally
0x2fa2  ldloc.3
0x2fa3  brfalse.s loc_2FAB
0x2fa5  ldloc.3
0x2fa6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2fab  endfinally
0x2fac  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0x2fb1  endfinally
0x2fb2  ldloc.0
0x2fb3  ret
```
