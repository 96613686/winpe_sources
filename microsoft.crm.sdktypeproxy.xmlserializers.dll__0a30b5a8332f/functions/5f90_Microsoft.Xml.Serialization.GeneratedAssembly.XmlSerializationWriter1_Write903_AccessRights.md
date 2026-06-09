# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write903_AccessRights

- ea: `0x5f90`
- end: `0x608b`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write903_AccessRights`
- size: `251`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1940`
- `0x5f00`
- `0x6ac0`
- `0x5f7d0`

## callees

- `0x5f90`

## string_xrefs

- `0x5fd7`: `ReadAccess`
- `0x602e`: `ReadAccess`
- `0x5fe2`: `WriteAccess`
- `0x6036`: `WriteAccess`
- `0x5fed`: `AppendAccess`
- `0x603e`: `AppendAccess`
- `0x5ff8`: `AppendToAccess`
- `0x6046`: `AppendToAccess`
- `0x6003`: `CreateAccess`
- `0x604e`: `CreateAccess`
- `0x600b`: `DeleteAccess`
- `0x6056`: `DeleteAccess`
- `0x6013`: `ShareAccess`
- `0x605e`: `ShareAccess`
- `0x601b`: `AssignAccess`
- `0x6066`: `AssignAccess`
- `0x607e`: `Microsoft.Crm.Sdk.AccessRights`

## pseudocode

```c

```

## disassembly

```asm
0x5f90  ldnull
0x5f91  stloc.0
0x5f92  ldarg.1
0x5f93  stloc.1
0x5f94  ldloc.1
0x5f95  ldc.i4.s 0x20
0x5f97  bgt.s    loc_5FBD
0x5f99  ldloc.1
0x5f9a  ldc.i4.1
0x5f9b  sub
0x5f9c  switch   loc_5FD7, loc_5FE2, loc_6023, loc_5FED
0x5fb1  ldloc.1
0x5fb2  ldc.i4.s 0x10
0x5fb4  beq.s    loc_5FF8
0x5fb6  ldloc.1
0x5fb7  ldc.i4.s 0x20
0x5fb9  beq.s    loc_6003
0x5fbb  br.s     loc_6023
0x5fbd  ldloc.1
0x5fbe  ldc.i4   0x10000
0x5fc3  beq.s    loc_600B
0x5fc5  ldloc.1
0x5fc6  ldc.i4   0x40000
0x5fcb  beq.s    loc_6013
0x5fcd  ldloc.1
0x5fce  ldc.i4   0x80000
0x5fd3  beq.s    loc_601B
0x5fd5  br.s     loc_6023
0x5fd7  ldstr    aReadaccess// "ReadAccess"
0x5fdc  stloc.0
0x5fdd  br       loc_6089
0x5fe2  ldstr    aWriteaccess// "WriteAccess"
0x5fe7  stloc.0
0x5fe8  br       loc_6089
0x5fed  ldstr    aAppendaccess// "AppendAccess"
0x5ff2  stloc.0
0x5ff3  br       loc_6089
0x5ff8  ldstr    aAppendtoaccess// "AppendToAccess"
0x5ffd  stloc.0
0x5ffe  br       loc_6089
0x6003  ldstr    aCreateaccess// "CreateAccess"
0x6008  stloc.0
0x6009  br.s     loc_6089
0x600b  ldstr    aDeleteaccess// "DeleteAccess"
0x6010  stloc.0
0x6011  br.s     loc_6089
0x6013  ldstr    aShareaccess// "ShareAccess"
0x6018  stloc.0
0x6019  br.s     loc_6089
0x601b  ldstr    aAssignaccess// "AssignAccess"
0x6020  stloc.0
0x6021  br.s     loc_6089
0x6023  ldarg.1
0x6024  conv.i8
0x6025  ldc.i4.8
0x6026  newarr   [mscorlib]System.String
0x602b  stloc.2
0x602c  ldloc.2
0x602d  ldc.i4.0
0x602e  ldstr    aReadaccess// "ReadAccess"
0x6033  stelem.ref
0x6034  ldloc.2
0x6035  ldc.i4.1
0x6036  ldstr    aWriteaccess// "WriteAccess"
0x603b  stelem.ref
0x603c  ldloc.2
0x603d  ldc.i4.2
0x603e  ldstr    aAppendaccess// "AppendAccess"
0x6043  stelem.ref
0x6044  ldloc.2
0x6045  ldc.i4.3
0x6046  ldstr    aAppendtoaccess// "AppendToAccess"
0x604b  stelem.ref
0x604c  ldloc.2
0x604d  ldc.i4.4
0x604e  ldstr    aCreateaccess// "CreateAccess"
0x6053  stelem.ref
0x6054  ldloc.2
0x6055  ldc.i4.5
0x6056  ldstr    aDeleteaccess// "DeleteAccess"
0x605b  stelem.ref
0x605c  ldloc.2
0x605d  ldc.i4.6
0x605e  ldstr    aShareaccess// "ShareAccess"
0x6063  stelem.ref
0x6064  ldloc.2
0x6065  ldc.i4.7
0x6066  ldstr    aAssignaccess// "AssignAccess"
0x606b  stelem.ref
0x606c  ldloc.2
0x606d  ldc.i4.8
0x606e  newarr   [mscorlib]System.Int64
0x6073  dup
0x6074  ldtoken  valuetype __StaticArrayInitTypeSize=64 <PrivateImplementationDetails>{2A7F62EC-DA79-4395-A090-8A18F3452A43}::$$method0x6000030-1
0x6079  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::InitializeArray(class [mscorlib]System.Array, valuetype [mscorlib]System.RuntimeFieldHandle)
0x607e  ldstr    aMicrosoftCrmSd_4// "Microsoft.Crm.Sdk.AccessRights"
0x6083  call     string [System.Xml]System.Xml.Serialization.XmlSerializationWriter::FromEnum(int64, string[], int64[], string)
0x6088  stloc.0
0x6089  ldloc.0
0x608a  ret
```
