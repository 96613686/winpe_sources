# Microsoft.Crm.Asynchronous.ImportOperationParse::.ctor

- ea: `0x140b0`
- end: `0x141f5`
- name: `Microsoft.Crm.Asynchronous.ImportOperationParse::.ctor`
- size: `325`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14350`

## callees

- `0xaac0`

## string_xrefs

- `0x140d2`: `CreatedBy`
- `0x140f2`: `CreatedOn`

## pseudocode

```c

```

## disassembly

```asm
0x140b0  ldarg.0
0x140b1  ldc.i4.s 0xD
0x140b3  newarr   [mscorlib]System.String
0x140b8  dup
0x140b9  ldc.i4.0
0x140ba  ldstr    aModifiedon_1// "ModifiedOn"
0x140bf  stelem.ref
0x140c0  dup
0x140c1  ldc.i4.1
0x140c2  ldstr    aOwnerid_2// "OwnerId"
0x140c7  stelem.ref
0x140c8  dup
0x140c9  ldc.i4.2
0x140ca  ldstr    aOwningbusiness_1// "OwningBusinessUnit"
0x140cf  stelem.ref
0x140d0  dup
0x140d1  ldc.i4.3
0x140d2  ldstr    aCreatedby_1// "CreatedBy"
0x140d7  stelem.ref
0x140d8  dup
0x140d9  ldc.i4.4
0x140da  ldstr    aStatuscode_2// "StatusCode"
0x140df  stelem.ref
0x140e0  dup
0x140e1  ldc.i4.5
0x140e2  ldstr    aModifiedby_1// "ModifiedBy"
0x140e7  stelem.ref
0x140e8  dup
0x140e9  ldc.i4.6
0x140ea  ldstr    aStatecode_2// "StateCode"
0x140ef  stelem.ref
0x140f0  dup
0x140f1  ldc.i4.7
0x140f2  ldstr    aCreatedon_0// "CreatedOn"
0x140f7  stelem.ref
0x140f8  dup
0x140f9  ldc.i4.8
0x140fa  ldstr    aImportdataid_2// "ImportDataId"
0x140ff  stelem.ref
0x14100  dup
0x14101  ldc.i4.s 9
0x14103  ldstr    aRecordid_0// "RecordId"
0x14108  stelem.ref
0x14109  dup
0x1410a  ldc.i4.s 0xA
0x1410c  ldstr    aImportfileid_3// "ImportFileId"
0x14111  stelem.ref
0x14112  dup
0x14113  ldc.i4.s 0xB
0x14115  ldstr    aData_1// "Data"
0x1411a  stelem.ref
0x1411b  dup
0x1411c  ldc.i4.s 0xC
0x1411e  ldstr    aLinenumber_0// "LineNumber"
0x14123  stelem.ref
0x14124  stfld    string[] Microsoft.Crm.Asynchronous.ImportOperationParse::_importDataBaseColumns
0x14129  ldarg.0
0x1412a  ldc.i4.s 0xD
0x1412c  newarr   [mscorlib]System.String
0x14131  dup
0x14132  ldc.i4.0
0x14133  ldstr    aSystemDatetime// "System.DateTime"
0x14138  stelem.ref
0x14139  dup
0x1413a  ldc.i4.1
0x1413b  ldstr    aSystemGuid// "System.Guid"
0x14140  stelem.ref
0x14141  dup
0x14142  ldc.i4.2
0x14143  ldstr    aSystemGuid// "System.Guid"
0x14148  stelem.ref
0x14149  dup
0x1414a  ldc.i4.3
0x1414b  ldstr    aSystemGuid// "System.Guid"
0x14150  stelem.ref
0x14151  dup
0x14152  ldc.i4.4
0x14153  ldstr    aSystemInt32// "System.Int32"
0x14158  stelem.ref
0x14159  dup
0x1415a  ldc.i4.5
0x1415b  ldstr    aSystemGuid// "System.Guid"
0x14160  stelem.ref
0x14161  dup
0x14162  ldc.i4.6
0x14163  ldstr    aSystemInt32// "System.Int32"
0x14168  stelem.ref
0x14169  dup
0x1416a  ldc.i4.7
0x1416b  ldstr    aSystemDatetime// "System.DateTime"
0x14170  stelem.ref
0x14171  dup
0x14172  ldc.i4.8
0x14173  ldstr    aSystemGuid// "System.Guid"
0x14178  stelem.ref
0x14179  dup
0x1417a  ldc.i4.s 9
0x1417c  ldstr    aSystemGuid// "System.Guid"
0x14181  stelem.ref
0x14182  dup
0x14183  ldc.i4.s 0xA
0x14185  ldstr    aSystemGuid// "System.Guid"
0x1418a  stelem.ref
0x1418b  dup
0x1418c  ldc.i4.s 0xB
0x1418e  ldstr    aSystemString// "System.String"
0x14193  stelem.ref
0x14194  dup
0x14195  ldc.i4.s 0xC
0x14197  ldstr    aSystemInt32// "System.Int32"
0x1419c  stelem.ref
0x1419d  stfld    string[] Microsoft.Crm.Asynchronous.ImportOperationParse::_importDataBaseColumnTypes
0x141a2  ldarg.0
0x141a3  ldc.i4.7
0x141a4  newarr   [mscorlib]System.String
0x141a9  dup
0x141aa  ldc.i4.0
0x141ab  ldstr    aFont// "Font"
0x141b0  stelem.ref
0x141b1  dup
0x141b2  ldc.i4.1
0x141b3  ldstr    aB// "B"
0x141b8  stelem.ref
0x141b9  dup
0x141ba  ldc.i4.2
0x141bb  ldstr    aI// "I"
0x141c0  stelem.ref
0x141c1  dup
0x141c2  ldc.i4.3
0x141c3  ldstr    aU// "U"
0x141c8  stelem.ref
0x141c9  dup
0x141ca  ldc.i4.4
0x141cb  ldstr    aS// "S"
0x141d0  stelem.ref
0x141d1  dup
0x141d2  ldc.i4.5
0x141d3  ldstr    aSup// "Sup"
0x141d8  stelem.ref
0x141d9  dup
0x141da  ldc.i4.6
0x141db  ldstr    aSub// "Sub"
0x141e0  stelem.ref
0x141e1  newobj   instance void class [System]System.Collections.Generic.SortedSet`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x141e6  stfld    class [System]System.Collections.Generic.SortedSet`1<string> Microsoft.Crm.Asynchronous.ImportOperationParse::_htmlElementsAllowedlist
0x141eb  ldarg.0
0x141ec  ldarg.1
0x141ed  ldarg.2
0x141ee  ldarg.3
0x141ef  call     instance void Microsoft.Crm.Asynchronous.ImportOperation::.ctor(class [CrmAsyncService]Microsoft.Crm.Asynchronous.AsyncService asyncService, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncHandlerGroup handlerGroup, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration config)
0x141f4  ret
```
