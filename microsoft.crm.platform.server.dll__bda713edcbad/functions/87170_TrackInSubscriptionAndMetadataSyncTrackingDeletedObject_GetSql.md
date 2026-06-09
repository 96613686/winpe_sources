# TrackInSubscriptionAndMetadataSyncTrackingDeletedObject::GetSql

- ea: `0x87170`
- end: `0x87257`
- name: `TrackInSubscriptionAndMetadataSyncTrackingDeletedObject::GetSql`
- size: `231`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x86e60`
- `0x86e80`
- `0x86ea0`
- `0x86ed0`
- `0x87260`

## string_xrefs

- `0x8717b`: `\ndeclare @t table (id uniqueidentifier)\n\ndelete from [{0}]\n	OUTPUT DELETED.[{1}] \n		into @t (id)\n`
- `0x871cd`: `\ninsert into SubscriptionTrackingDeletedObject (ObjectId, ObjectTypeCode)\n	select id, {2} from @t\n\n`
- `0x87217`: `	insert into MetadataSyncTrackingDeletedObject (ObjectId, MetadataObjectTypeCode)\n		select id, {3} from @t\n`

## pseudocode

```c

```

## disassembly

```asm
0x87170  ldarg.1
0x87171  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Query.DeleteVisitor::sqlString
0x87176  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8717b  ldstr    aDeclareTTableI// "\r\ndeclare @t table (id uniqueidentifi"...
0x87180  ldc.i4.4
0x87181  newarr   [mscorlib]System.Object
0x87186  dup
0x87187  ldc.i4.0
0x87188  ldarg.0
0x87189  call     instance string TrackingDeletedObject::get_BaseTableName()
0x8718e  stelem.ref
0x8718f  dup
0x87190  ldc.i4.1
0x87191  ldarg.0
0x87192  call     instance string TrackingDeletedObject::get_PrimaryKey()
0x87197  stelem.ref
0x87198  dup
0x87199  ldc.i4.2
0x8719a  ldarg.0
0x8719b  call     instance int32 TrackingDeletedObject::get_ObjectTypeCode()
0x871a0  box      [mscorlib]System.Int32
0x871a5  stelem.ref
0x871a6  dup
0x871a7  ldc.i4.3
0x871a8  ldarg.0
0x871a9  call     instance int32 TrackInSubscriptionAndMetadataSyncTrackingDeletedObject::get_MetadataObjectTypeCode()
0x871ae  box      [mscorlib]System.Int32
0x871b3  stelem.ref
0x871b4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x871b9  pop
0x871ba  ldarg.0
0x871bb  ldarg.1
0x871bc  ldarg.2
0x871bd  call     instance void TrackingDeletedObject::GetSqlCriteria(class Microsoft.Crm.Query.DeleteVisitor visitor, class Microsoft.Crm.Query.FilterExpression criteria)
0x871c2  ldarg.1
0x871c3  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Query.DeleteVisitor::sqlString
0x871c8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x871cd  ldstr    aInsertIntoSubs_0// "\r\ninsert into SubscriptionTrackingDel"...
0x871d2  ldc.i4.4
0x871d3  newarr   [mscorlib]System.Object
0x871d8  dup
0x871d9  ldc.i4.0
0x871da  ldarg.0
0x871db  call     instance string TrackingDeletedObject::get_BaseTableName()
0x871e0  stelem.ref
0x871e1  dup
0x871e2  ldc.i4.1
0x871e3  ldarg.0
0x871e4  call     instance string TrackingDeletedObject::get_PrimaryKey()
0x871e9  stelem.ref
0x871ea  dup
0x871eb  ldc.i4.2
0x871ec  ldarg.0
0x871ed  call     instance int32 TrackingDeletedObject::get_ObjectTypeCode()
0x871f2  box      [mscorlib]System.Int32
0x871f7  stelem.ref
0x871f8  dup
0x871f9  ldc.i4.3
0x871fa  ldarg.0
0x871fb  call     instance int32 TrackInSubscriptionAndMetadataSyncTrackingDeletedObject::get_MetadataObjectTypeCode()
0x87200  box      [mscorlib]System.Int32
0x87205  stelem.ref
0x87206  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x8720b  pop
0x8720c  ldarg.1
0x8720d  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Query.DeleteVisitor::sqlString
0x87212  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x87217  ldstr    aInsertIntoMeta_2// "\tinsert into MetadataSyncTrackingDelet"...
0x8721c  ldc.i4.4
0x8721d  newarr   [mscorlib]System.Object
0x87222  dup
0x87223  ldc.i4.0
0x87224  ldarg.0
0x87225  call     instance string TrackingDeletedObject::get_BaseTableName()
0x8722a  stelem.ref
0x8722b  dup
0x8722c  ldc.i4.1
0x8722d  ldarg.0
0x8722e  call     instance string TrackingDeletedObject::get_PrimaryKey()
0x87233  stelem.ref
0x87234  dup
0x87235  ldc.i4.2
0x87236  ldarg.0
0x87237  call     instance int32 TrackingDeletedObject::get_ObjectTypeCode()
0x8723c  box      [mscorlib]System.Int32
0x87241  stelem.ref
0x87242  dup
0x87243  ldc.i4.3
0x87244  ldarg.0
0x87245  call     instance int32 TrackInSubscriptionAndMetadataSyncTrackingDeletedObject::get_MetadataObjectTypeCode()
0x8724a  box      [mscorlib]System.Int32
0x8724f  stelem.ref
0x87250  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x87255  pop
0x87256  ret
```
