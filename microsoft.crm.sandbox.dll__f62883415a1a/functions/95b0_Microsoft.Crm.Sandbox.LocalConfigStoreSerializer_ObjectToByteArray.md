# Microsoft.Crm.Sandbox.LocalConfigStoreSerializer::ObjectToByteArray

- ea: `0x95b0`
- end: `0x95fb`
- name: `Microsoft.Crm.Sandbox.LocalConfigStoreSerializer::ObjectToByteArray`
- size: `75`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x9580`
- `0x96b0`

## callees

- `0x95b0`

## pseudocode

```c

```

## disassembly

```asm
0x95b0  ldc.i4.0
0x95b1  newobj   instance void [mscorlib]System.Security.PermissionSet::.ctor(valuetype [mscorlib]System.Security.Permissions.PermissionState)
0x95b6  dup
0x95b7  ldc.i4   0x80
0x95bc  newobj   instance void [mscorlib]System.Security.Permissions.SecurityPermission::.ctor(valuetype [mscorlib]System.Security.Permissions.SecurityPermissionFlag)
0x95c1  callvirt instance class [mscorlib]System.Security.IPermission [mscorlib]System.Security.PermissionSet::AddPermission(class [mscorlib]System.Security.IPermission)
0x95c6  pop
0x95c7  callvirt instance void [mscorlib]System.Security.PermissionSet::Assert()
0x95cc  newobj   instance void [mscorlib]System.Runtime.Serialization.Formatters.Binary.BinaryFormatter::.ctor()
0x95d1  stloc.0
0x95d2  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor()
0x95d7  stloc.1
0x95d8  ldloc.0
0x95d9  ldloc.1
0x95da  ldarg.1
0x95db  callvirt instance void [mscorlib]System.Runtime.Serialization.Formatters.Binary.BinaryFormatter::Serialize(class [mscorlib]System.IO.Stream, object)
0x95e0  ldloc.1
0x95e1  callvirt instance unsigned int8[] [mscorlib]System.IO.MemoryStream::ToArray()
0x95e6  stloc.2
0x95e7  leave.s  loc_95F9
0x95e9  ldloc.1
0x95ea  brfalse.s loc_95F2
0x95ec  ldloc.1
0x95ed  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x95f2  endfinally
0x95f3  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0x95f8  endfinally
0x95f9  ldloc.2
0x95fa  ret
```
