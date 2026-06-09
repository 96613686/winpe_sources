# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::get_AccessRightsValues

- ea: `0x79e50`
- end: `0x79f0d`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::get_AccessRightsValues`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x79f10`

## callees

- `0x79e50`

## string_xrefs

- `0x79e62`: `ReadAccess`
- `0x79e74`: `WriteAccess`
- `0x79e86`: `AppendAccess`
- `0x79e98`: `AppendToAccess`
- `0x79eab`: `CreateAccess`
- `0x79ebe`: `DeleteAccess`
- `0x79ed4`: `ShareAccess`
- `0x79eea`: `AssignAccess`

## pseudocode

```c

```

## disassembly

```asm
0x79e50  ldarg.0
0x79e51  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::_AccessRightsValues
0x79e56  brtrue   loc_79F06
0x79e5b  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x79e60  stloc.0
0x79e61  ldloc.0
0x79e62  ldstr    aReadaccess// "ReadAccess"
0x79e67  ldc.i4.1
0x79e68  conv.i8
0x79e69  box      [mscorlib]System.Int64
0x79e6e  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x79e73  ldloc.0
0x79e74  ldstr    aWriteaccess// "WriteAccess"
0x79e79  ldc.i4.2
0x79e7a  conv.i8
0x79e7b  box      [mscorlib]System.Int64
0x79e80  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x79e85  ldloc.0
0x79e86  ldstr    aAppendaccess// "AppendAccess"
0x79e8b  ldc.i4.4
0x79e8c  conv.i8
0x79e8d  box      [mscorlib]System.Int64
0x79e92  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x79e97  ldloc.0
0x79e98  ldstr    aAppendtoaccess// "AppendToAccess"
0x79e9d  ldc.i4.s 0x10
0x79e9f  conv.i8
0x79ea0  box      [mscorlib]System.Int64
0x79ea5  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x79eaa  ldloc.0
0x79eab  ldstr    aCreateaccess// "CreateAccess"
0x79eb0  ldc.i4.s 0x20
0x79eb2  conv.i8
0x79eb3  box      [mscorlib]System.Int64
0x79eb8  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x79ebd  ldloc.0
0x79ebe  ldstr    aDeleteaccess// "DeleteAccess"
0x79ec3  ldc.i4   0x10000
0x79ec8  conv.i8
0x79ec9  box      [mscorlib]System.Int64
0x79ece  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x79ed3  ldloc.0
0x79ed4  ldstr    aShareaccess// "ShareAccess"
0x79ed9  ldc.i4   0x40000
0x79ede  conv.i8
0x79edf  box      [mscorlib]System.Int64
0x79ee4  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x79ee9  ldloc.0
0x79eea  ldstr    aAssignaccess// "AssignAccess"
0x79eef  ldc.i4   0x80000
0x79ef4  conv.i8
0x79ef5  box      [mscorlib]System.Int64
0x79efa  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x79eff  ldarg.0
0x79f00  ldloc.0
0x79f01  stfld    class [mscorlib]System.Collections.Hashtable Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::_AccessRightsValues
0x79f06  ldarg.0
0x79f07  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::_AccessRightsValues
0x79f0c  ret
```
