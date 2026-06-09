# Microsoft.Crm.Transformations.Replace::Evaluate

- ea: `0x1e40`
- end: `0x1f7f`
- name: `Microsoft.Crm.Transformations.Replace::Evaluate`
- size: `319`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1e40`

## pseudocode

```c

```

## disassembly

```asm
0x1e40  ldarg.1
0x1e41  brfalse.s loc_1E49
0x1e43  ldarg.1
0x1e44  ldlen
0x1e45  conv.i4
0x1e46  ldc.i4.3
0x1e47  beq.s    loc_1E5A
0x1e49  ldc.i4   0x80048506
0x1e4e  ldc.i4.0
0x1e4f  newarr   [mscorlib]System.Object
0x1e54  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x1e59  throw
0x1e5a  ldnull
0x1e5b  stloc.0
0x1e5c  ldnull
0x1e5d  stloc.1
0x1e5e  ldnull
0x1e5f  stloc.2
0x1e60  ldarg.1
0x1e61  ldc.i4.0
0x1e62  ldelem.ref
0x1e63  brtrue.s loc_1E6C
0x1e65  ldc.i4.1
0x1e66  newarr   [mscorlib]System.Object
0x1e6b  ret
0x1e6c  ldarg.1
0x1e6d  ldc.i4.0
0x1e6e  ldelem.ref
0x1e6f  isinst   [mscorlib]System.String
0x1e74  brtrue.s loc_1E9D
0x1e76  ldc.i4   0x80048507
0x1e7b  ldc.i4.3
0x1e7c  newarr   [mscorlib]System.Object
0x1e81  dup
0x1e82  ldc.i4.0
0x1e83  ldstr    a1// "1"
0x1e88  stelem.ref
0x1e89  dup
0x1e8a  ldc.i4.1
0x1e8b  ldarg.1
0x1e8c  ldc.i4.0
0x1e8d  ldelem.ref
0x1e8e  stelem.ref
0x1e8f  dup
0x1e90  ldc.i4.2
0x1e91  ldstr    aString// "String"
0x1e96  stelem.ref
0x1e97  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x1e9c  throw
0x1e9d  ldarg.1
0x1e9e  ldc.i4.0
0x1e9f  ldelem.ref
0x1ea0  castclass [mscorlib]System.String
0x1ea5  dup
0x1ea6  stloc.0
0x1ea7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1eac  brfalse.s loc_1ECD
0x1eae  ldc.i4   0x80048508
0x1eb3  ldc.i4.2
0x1eb4  newarr   [mscorlib]System.Object
0x1eb9  dup
0x1eba  ldc.i4.0
0x1ebb  ldstr    a1// "1"
0x1ec0  stelem.ref
0x1ec1  dup
0x1ec2  ldc.i4.1
0x1ec3  ldarg.1
0x1ec4  ldc.i4.0
0x1ec5  ldelem.ref
0x1ec6  stelem.ref
0x1ec7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x1ecc  throw
0x1ecd  ldarg.1
0x1ece  ldc.i4.1
0x1ecf  ldelem.ref
0x1ed0  isinst   [mscorlib]System.String
0x1ed5  brtrue.s loc_1EFE
0x1ed7  ldc.i4   0x80048507
0x1edc  ldc.i4.3
0x1edd  newarr   [mscorlib]System.Object
0x1ee2  dup
0x1ee3  ldc.i4.0
0x1ee4  ldstr    a2// "2"
0x1ee9  stelem.ref
0x1eea  dup
0x1eeb  ldc.i4.1
0x1eec  ldarg.1
0x1eed  ldc.i4.1
0x1eee  ldelem.ref
0x1eef  stelem.ref
0x1ef0  dup
0x1ef1  ldc.i4.2
0x1ef2  ldstr    aString// "String"
0x1ef7  stelem.ref
0x1ef8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x1efd  throw
0x1efe  ldarg.1
0x1eff  ldc.i4.1
0x1f00  ldelem.ref
0x1f01  castclass [mscorlib]System.String
0x1f06  dup
0x1f07  stloc.1
0x1f08  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1f0d  brfalse.s loc_1F2E
0x1f0f  ldc.i4   0x80048508
0x1f14  ldc.i4.2
0x1f15  newarr   [mscorlib]System.Object
0x1f1a  dup
0x1f1b  ldc.i4.0
0x1f1c  ldstr    a2// "2"
0x1f21  stelem.ref
0x1f22  dup
0x1f23  ldc.i4.1
0x1f24  ldarg.1
0x1f25  ldc.i4.1
0x1f26  ldelem.ref
0x1f27  stelem.ref
0x1f28  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x1f2d  throw
0x1f2e  ldarg.1
0x1f2f  ldc.i4.2
0x1f30  ldelem.ref
0x1f31  brfalse.s loc_1F64
0x1f33  ldarg.1
0x1f34  ldc.i4.2
0x1f35  ldelem.ref
0x1f36  isinst   [mscorlib]System.String
0x1f3b  brtrue.s loc_1F64
0x1f3d  ldc.i4   0x80048507
0x1f42  ldc.i4.3
0x1f43  newarr   [mscorlib]System.Object
0x1f48  dup
0x1f49  ldc.i4.0
0x1f4a  ldstr    a3// "3"
0x1f4f  stelem.ref
0x1f50  dup
0x1f51  ldc.i4.1
0x1f52  ldarg.1
0x1f53  ldc.i4.2
0x1f54  ldelem.ref
0x1f55  stelem.ref
0x1f56  dup
0x1f57  ldc.i4.2
0x1f58  ldstr    aString// "String"
0x1f5d  stelem.ref
0x1f5e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x1f63  throw
0x1f64  ldarg.1
0x1f65  ldc.i4.2
0x1f66  ldelem.ref
0x1f67  castclass [mscorlib]System.String
0x1f6c  stloc.2
0x1f6d  ldc.i4.1
0x1f6e  newarr   [mscorlib]System.Object
0x1f73  dup
0x1f74  ldc.i4.0
0x1f75  ldloc.0
0x1f76  ldloc.1
0x1f77  ldloc.2
0x1f78  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x1f7d  stelem.ref
0x1f7e  ret
```
