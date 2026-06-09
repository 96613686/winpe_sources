# Microsoft.Crm.Asynchronous.BackupOrganizationLogOperation::CleanupManifestFiles

- ea: `0x14c0`
- end: `0x156e`
- name: `Microsoft.Crm.Asynchronous.BackupOrganizationLogOperation::CleanupManifestFiles`
- size: `174`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0xb80`

## callees

- `0x14c0`

## string_xrefs

- `0x14cc`: `*_MANIFEST.xml`

## pseudocode

```c

```

## disassembly

```asm
0x14c0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x14c5  stloc.0
0x14c6  ldarg.0
0x14c7  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x14cc  ldstr    aManifestXml_0// "*_MANIFEST.xml"
0x14d1  callvirt instance class [mscorlib]System.IO.FileInfo[] [mscorlib]System.IO.DirectoryInfo::GetFiles(string)
0x14d6  stloc.1
0x14d7  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x14dc  stloc.2
0x14dd  ldloc.1
0x14de  stloc.3
0x14df  ldc.i4.0
0x14e0  stloc.s  4
0x14e2  br.s     loc_1523
0x14e4  ldloc.3
0x14e5  ldloc.s  4
0x14e7  ldelem.ref
0x14e8  stloc.s  5
0x14ea  ldloc.s  5
0x14ec  callvirt instance valuetype [mscorlib]System.DateTime [mscorlib]System.IO.FileSystemInfo::get_CreationTimeUtc()
0x14f1  ldarg.1
0x14f2  call     bool [mscorlib]System.DateTime::op_GreaterThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x14f7  brfalse.s loc_151D
0x14f9  ldloc.s  5
0x14fb  callvirt instance valuetype [mscorlib]System.DateTime [mscorlib]System.IO.FileSystemInfo::get_CreationTimeUtc()
0x1500  ldloc.2
0x1501  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x1506  brtrue.s loc_1515
0x1508  ldloc.2
0x1509  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x150e  call     bool [mscorlib]System.DateTime::op_Equality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x1513  brfalse.s loc_151D
0x1515  ldloc.s  5
0x1517  callvirt instance valuetype [mscorlib]System.DateTime [mscorlib]System.IO.FileSystemInfo::get_CreationTimeUtc()
0x151c  stloc.2
0x151d  ldloc.s  4
0x151f  ldc.i4.1
0x1520  add
0x1521  stloc.s  4
0x1523  ldloc.s  4
0x1525  ldloc.3
0x1526  ldlen
0x1527  conv.i4
0x1528  blt.s    loc_14E4
0x152a  ldloc.1
0x152b  stloc.3
0x152c  ldc.i4.0
0x152d  stloc.s  4
0x152f  br.s     loc_1565
0x1531  ldloc.3
0x1532  ldloc.s  4
0x1534  ldelem.ref
0x1535  stloc.s  6
0x1537  ldloc.s  6
0x1539  callvirt instance valuetype [mscorlib]System.DateTime [mscorlib]System.IO.FileSystemInfo::get_CreationTimeUtc()
0x153e  ldloc.2
0x153f  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x1544  brfalse.s loc_155F
0x1546  ldloc.s  6
0x1548  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x154d  call     void [mscorlib]System.IO.File::Delete(string)
0x1552  ldloc.0
0x1553  ldloc.s  6
0x1555  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x155a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x155f  ldloc.s  4
0x1561  ldc.i4.1
0x1562  add
0x1563  stloc.s  4
0x1565  ldloc.s  4
0x1567  ldloc.3
0x1568  ldlen
0x1569  conv.i4
0x156a  blt.s    loc_1531
0x156c  ldloc.0
0x156d  ret
```
