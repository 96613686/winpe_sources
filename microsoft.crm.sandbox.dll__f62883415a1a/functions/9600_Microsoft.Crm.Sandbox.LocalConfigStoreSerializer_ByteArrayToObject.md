# Microsoft.Crm.Sandbox.LocalConfigStoreSerializer::ByteArrayToObject

- ea: `0x9600`
- end: `0x9657`
- name: `Microsoft.Crm.Sandbox.LocalConfigStoreSerializer::ByteArrayToObject`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x94f0`
- `0x9660`

## callees

- `0x9600`

## pseudocode

```c

```

## disassembly

```asm
0x9600  ldc.i4.0
0x9601  newobj   instance void [mscorlib]System.Security.PermissionSet::.ctor(valuetype [mscorlib]System.Security.Permissions.PermissionState)
0x9606  dup
0x9607  ldc.i4   0x80
0x960c  newobj   instance void [mscorlib]System.Security.Permissions.SecurityPermission::.ctor(valuetype [mscorlib]System.Security.Permissions.SecurityPermissionFlag)
0x9611  callvirt instance class [mscorlib]System.Security.IPermission [mscorlib]System.Security.PermissionSet::AddPermission(class [mscorlib]System.Security.IPermission)
0x9616  pop
0x9617  callvirt instance void [mscorlib]System.Security.PermissionSet::Assert()
0x961c  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor()
0x9621  stloc.0
0x9622  newobj   instance void [mscorlib]System.Runtime.Serialization.Formatters.Binary.BinaryFormatter::.ctor()
0x9627  ldloc.0
0x9628  ldarg.1
0x9629  ldc.i4.0
0x962a  ldarg.1
0x962b  ldlen
0x962c  conv.i4
0x962d  callvirt instance void [mscorlib]System.IO.Stream::Write(unsigned int8[], int32, int32)
0x9632  ldloc.0
0x9633  ldc.i4.0
0x9634  conv.i8
0x9635  ldc.i4.0
0x9636  callvirt instance int64 [mscorlib]System.IO.Stream::Seek(int64, valuetype [mscorlib]System.IO.SeekOrigin)
0x963b  pop
0x963c  ldloc.0
0x963d  callvirt instance object [mscorlib]System.Runtime.Serialization.Formatters.Binary.BinaryFormatter::Deserialize(class [mscorlib]System.IO.Stream)
0x9642  stloc.1
0x9643  leave.s  loc_9655
0x9645  ldloc.0
0x9646  brfalse.s loc_964E
0x9648  ldloc.0
0x9649  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x964e  endfinally
0x964f  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0x9654  endfinally
0x9655  ldloc.1
0x9656  ret
```
