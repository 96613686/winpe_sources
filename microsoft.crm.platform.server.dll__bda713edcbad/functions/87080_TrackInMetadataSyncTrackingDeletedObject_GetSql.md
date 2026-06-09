# TrackInMetadataSyncTrackingDeletedObject::GetSql

- ea: `0x87080`
- end: `0x87109`
- name: `TrackInMetadataSyncTrackingDeletedObject::GetSql`
- size: `137`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x86e60`
- `0x86e80`
- `0x86ed0`
- `0x87110`

## string_xrefs

- `0x8708b`: `	delete from [{0}]\n		OUTPUT DELETED.[{1}], {2}\n			into MetadataSyncTrackingDeletedObject (ObjectId, MetadataObjectTypeCode) \n`
- `0x870cf`: `ELSE \n	delete from [{0}]\n`

## pseudocode

```c

```

## disassembly

```asm
0x87080  ldarg.1
0x87081  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Query.DeleteVisitor::sqlString
0x87086  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8708b  ldstr    aDeleteFrom0Out_1// "\tdelete from [{0}]\r\n\t\tOUTPUT DELET"...
0x87090  ldc.i4.3
0x87091  newarr   [mscorlib]System.Object
0x87096  dup
0x87097  ldc.i4.0
0x87098  ldarg.0
0x87099  call     instance string TrackingDeletedObject::get_BaseTableName()
0x8709e  stelem.ref
0x8709f  dup
0x870a0  ldc.i4.1
0x870a1  ldarg.0
0x870a2  call     instance string TrackingDeletedObject::get_PrimaryKey()
0x870a7  stelem.ref
0x870a8  dup
0x870a9  ldc.i4.2
0x870aa  ldarg.0
0x870ab  call     instance int32 TrackInMetadataSyncTrackingDeletedObject::get_MetadataObjectTypeCode()
0x870b0  box      [mscorlib]System.Int32
0x870b5  stelem.ref
0x870b6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x870bb  pop
0x870bc  ldarg.0
0x870bd  ldarg.1
0x870be  ldarg.2
0x870bf  call     instance void TrackingDeletedObject::GetSqlCriteria(class Microsoft.Crm.Query.DeleteVisitor visitor, class Microsoft.Crm.Query.FilterExpression criteria)
0x870c4  ldarg.1
0x870c5  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Query.DeleteVisitor::sqlString
0x870ca  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x870cf  ldstr    aElseDeleteFrom// "ELSE \r\n\tdelete from [{0}]\r\n"
0x870d4  ldc.i4.3
0x870d5  newarr   [mscorlib]System.Object
0x870da  dup
0x870db  ldc.i4.0
0x870dc  ldarg.0
0x870dd  call     instance string TrackingDeletedObject::get_BaseTableName()
0x870e2  stelem.ref
0x870e3  dup
0x870e4  ldc.i4.1
0x870e5  ldarg.0
0x870e6  call     instance string TrackingDeletedObject::get_PrimaryKey()
0x870eb  stelem.ref
0x870ec  dup
0x870ed  ldc.i4.2
0x870ee  ldarg.0
0x870ef  call     instance int32 TrackInMetadataSyncTrackingDeletedObject::get_MetadataObjectTypeCode()
0x870f4  box      [mscorlib]System.Int32
0x870f9  stelem.ref
0x870fa  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x870ff  pop
0x87100  ldarg.0
0x87101  ldarg.1
0x87102  ldarg.2
0x87103  call     instance void TrackingDeletedObject::GetSqlCriteria(class Microsoft.Crm.Query.DeleteVisitor visitor, class Microsoft.Crm.Query.FilterExpression criteria)
0x87108  ret
```
