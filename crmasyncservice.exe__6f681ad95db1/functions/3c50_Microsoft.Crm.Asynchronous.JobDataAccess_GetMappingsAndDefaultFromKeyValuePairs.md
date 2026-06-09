# Microsoft.Crm.Asynchronous.JobDataAccess::GetMappingsAndDefaultFromKeyValuePairs

- ea: `0x3c50`
- end: `0x3d10`
- name: `Microsoft.Crm.Asynchronous.JobDataAccess::GetMappingsAndDefaultFromKeyValuePairs`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x3930`

## callees

- `0x3c50`

## pseudocode

```c

```

## disassembly

```asm
0x3c50  ldnull
0x3c51  stloc.0
0x3c52  ldc.i4.0
0x3c53  stloc.1
0x3c54  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x3c59  stloc.2
0x3c5a  ldarg.0
0x3c5b  ldc.i4.1
0x3c5c  newarr   [mscorlib]System.Char
0x3c61  dup
0x3c62  ldc.i4.0
0x3c63  ldc.i4.s 0x3B
0x3c65  stelem.i2
0x3c66  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x3c6b  stloc.3
0x3c6c  ldc.i4.0
0x3c6d  stloc.s  4
0x3c6f  br       loc_3CFE
0x3c74  ldloc.3
0x3c75  ldloc.s  4
0x3c77  ldelem.ref
0x3c78  stloc.s  5
0x3c7a  ldloc.s  5
0x3c7c  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x3c81  brtrue.s loc_3CF8
0x3c83  ldloc.s  5
0x3c85  ldc.i4.1
0x3c86  newarr   [mscorlib]System.Char
0x3c8b  dup
0x3c8c  ldc.i4.0
0x3c8d  ldc.i4.s 0x3D
0x3c8f  stelem.i2
0x3c90  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x3c95  stloc.s  6
0x3c97  ldloc.s  6
0x3c99  ldlen
0x3c9a  conv.i4
0x3c9b  ldc.i4.2
0x3c9c  bne.un.s loc_3CF0
0x3c9e  ldloc.s  6
0x3ca0  ldc.i4.1
0x3ca1  ldelem.ref
0x3ca2  ldloca.s 1
0x3ca4  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0x3ca9  brfalse.s loc_3CF0
0x3cab  ldloc.s  6
0x3cad  ldc.i4.0
0x3cae  ldelem.ref
0x3caf  ldstr    aDefault// "Default"
0x3cb4  ldc.i4.5
0x3cb5  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x3cba  brfalse.s loc_3CC3
0x3cbc  ldloc.s  6
0x3cbe  ldc.i4.1
0x3cbf  ldelem.ref
0x3cc0  stloc.0
0x3cc1  br.s     loc_3CF8
0x3cc3  ldloc.s  6
0x3cc5  ldc.i4.0
0x3cc6  ldelem.ref
0x3cc7  callvirt instance string [mscorlib]System.String::Trim()
0x3ccc  stloc.s  7
0x3cce  ldloc.2
0x3ccf  ldloc.s  7
0x3cd1  callvirt instance bool [mscorlib]System.Collections.Hashtable::Contains(object)
0x3cd6  brtrue.s loc_3CE6
0x3cd8  ldloc.2
0x3cd9  ldloc.s  7
0x3cdb  ldloc.s  6
0x3cdd  ldc.i4.1
0x3cde  ldelem.ref
0x3cdf  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x3ce4  br.s     loc_3CF8
0x3ce6  ldarg.1
0x3ce7  ldloc.s  5
0x3ce9  callvirt instance void class [mscorlib]System.Action`1<string>::Invoke(var<u1>)
0x3cee  br.s     loc_3CF8
0x3cf0  ldarg.1
0x3cf1  ldloc.s  5
0x3cf3  callvirt instance void class [mscorlib]System.Action`1<string>::Invoke(var<u1>)
0x3cf8  ldloc.s  4
0x3cfa  ldc.i4.1
0x3cfb  add
0x3cfc  stloc.s  4
0x3cfe  ldloc.s  4
0x3d00  ldloc.3
0x3d01  ldlen
0x3d02  conv.i4
0x3d03  blt      loc_3C74
0x3d08  ldloc.2
0x3d09  ldloc.0
0x3d0a  call     T0x2B00000A
0x3d0f  ret
```
