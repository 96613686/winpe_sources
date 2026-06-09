# Microsoft.Crm.Asynchronous.ImportOperationParse::.ctor_0

- ea: `0x14200`
- end: `0x14342`
- name: `Microsoft.Crm.Asynchronous.ImportOperationParse::.ctor_0`
- size: `322`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xaa60`

## string_xrefs

- `0x14222`: `CreatedBy`
- `0x14242`: `CreatedOn`

## pseudocode

```c

```

## disassembly

```asm
0x14200  ldarg.0
0x14201  ldc.i4.s 0xD
0x14203  newarr   [mscorlib]System.String
0x14208  dup
0x14209  ldc.i4.0
0x1420a  ldstr    aModifiedon_1// "ModifiedOn"
0x1420f  stelem.ref
0x14210  dup
0x14211  ldc.i4.1
0x14212  ldstr    aOwnerid_2// "OwnerId"
0x14217  stelem.ref
0x14218  dup
0x14219  ldc.i4.2
0x1421a  ldstr    aOwningbusiness_1// "OwningBusinessUnit"
0x1421f  stelem.ref
0x14220  dup
0x14221  ldc.i4.3
0x14222  ldstr    aCreatedby_1// "CreatedBy"
0x14227  stelem.ref
0x14228  dup
0x14229  ldc.i4.4
0x1422a  ldstr    aStatuscode_2// "StatusCode"
0x1422f  stelem.ref
0x14230  dup
0x14231  ldc.i4.5
0x14232  ldstr    aModifiedby_1// "ModifiedBy"
0x14237  stelem.ref
0x14238  dup
0x14239  ldc.i4.6
0x1423a  ldstr    aStatecode_2// "StateCode"
0x1423f  stelem.ref
0x14240  dup
0x14241  ldc.i4.7
0x14242  ldstr    aCreatedon_0// "CreatedOn"
0x14247  stelem.ref
0x14248  dup
0x14249  ldc.i4.8
0x1424a  ldstr    aImportdataid_2// "ImportDataId"
0x1424f  stelem.ref
0x14250  dup
0x14251  ldc.i4.s 9
0x14253  ldstr    aRecordid_0// "RecordId"
0x14258  stelem.ref
0x14259  dup
0x1425a  ldc.i4.s 0xA
0x1425c  ldstr    aImportfileid_3// "ImportFileId"
0x14261  stelem.ref
0x14262  dup
0x14263  ldc.i4.s 0xB
0x14265  ldstr    aData_1// "Data"
0x1426a  stelem.ref
0x1426b  dup
0x1426c  ldc.i4.s 0xC
0x1426e  ldstr    aLinenumber_0// "LineNumber"
0x14273  stelem.ref
0x14274  stfld    string[] Microsoft.Crm.Asynchronous.ImportOperationParse::_importDataBaseColumns
0x14279  ldarg.0
0x1427a  ldc.i4.s 0xD
0x1427c  newarr   [mscorlib]System.String
0x14281  dup
0x14282  ldc.i4.0
0x14283  ldstr    aSystemDatetime// "System.DateTime"
0x14288  stelem.ref
0x14289  dup
0x1428a  ldc.i4.1
0x1428b  ldstr    aSystemGuid// "System.Guid"
0x14290  stelem.ref
0x14291  dup
0x14292  ldc.i4.2
0x14293  ldstr    aSystemGuid// "System.Guid"
0x14298  stelem.ref
0x14299  dup
0x1429a  ldc.i4.3
0x1429b  ldstr    aSystemGuid// "System.Guid"
0x142a0  stelem.ref
0x142a1  dup
0x142a2  ldc.i4.4
0x142a3  ldstr    aSystemInt32// "System.Int32"
0x142a8  stelem.ref
0x142a9  dup
0x142aa  ldc.i4.5
0x142ab  ldstr    aSystemGuid// "System.Guid"
0x142b0  stelem.ref
0x142b1  dup
0x142b2  ldc.i4.6
0x142b3  ldstr    aSystemInt32// "System.Int32"
0x142b8  stelem.ref
0x142b9  dup
0x142ba  ldc.i4.7
0x142bb  ldstr    aSystemDatetime// "System.DateTime"
0x142c0  stelem.ref
0x142c1  dup
0x142c2  ldc.i4.8
0x142c3  ldstr    aSystemGuid// "System.Guid"
0x142c8  stelem.ref
0x142c9  dup
0x142ca  ldc.i4.s 9
0x142cc  ldstr    aSystemGuid// "System.Guid"
0x142d1  stelem.ref
0x142d2  dup
0x142d3  ldc.i4.s 0xA
0x142d5  ldstr    aSystemGuid// "System.Guid"
0x142da  stelem.ref
0x142db  dup
0x142dc  ldc.i4.s 0xB
0x142de  ldstr    aSystemString// "System.String"
0x142e3  stelem.ref
0x142e4  dup
0x142e5  ldc.i4.s 0xC
0x142e7  ldstr    aSystemInt32// "System.Int32"
0x142ec  stelem.ref
0x142ed  stfld    string[] Microsoft.Crm.Asynchronous.ImportOperationParse::_importDataBaseColumnTypes
0x142f2  ldarg.0
0x142f3  ldc.i4.7
0x142f4  newarr   [mscorlib]System.String
0x142f9  dup
0x142fa  ldc.i4.0
0x142fb  ldstr    aFont// "Font"
0x14300  stelem.ref
0x14301  dup
0x14302  ldc.i4.1
0x14303  ldstr    aB// "B"
0x14308  stelem.ref
0x14309  dup
0x1430a  ldc.i4.2
0x1430b  ldstr    aI// "I"
0x14310  stelem.ref
0x14311  dup
0x14312  ldc.i4.3
0x14313  ldstr    aU// "U"
0x14318  stelem.ref
0x14319  dup
0x1431a  ldc.i4.4
0x1431b  ldstr    aS// "S"
0x14320  stelem.ref
0x14321  dup
0x14322  ldc.i4.5
0x14323  ldstr    aSup// "Sup"
0x14328  stelem.ref
0x14329  dup
0x1432a  ldc.i4.6
0x1432b  ldstr    aSub// "Sub"
0x14330  stelem.ref
0x14331  newobj   instance void class [System]System.Collections.Generic.SortedSet`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x14336  stfld    class [System]System.Collections.Generic.SortedSet`1<string> Microsoft.Crm.Asynchronous.ImportOperationParse::_htmlElementsAllowedlist
0x1433b  ldarg.0
0x1433c  call     instance void Microsoft.Crm.Asynchronous.ImportOperation::.ctor()
0x14341  ret
```
