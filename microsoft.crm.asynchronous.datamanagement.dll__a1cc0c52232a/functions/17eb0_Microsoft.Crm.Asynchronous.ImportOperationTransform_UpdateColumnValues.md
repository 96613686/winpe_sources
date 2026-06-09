# Microsoft.Crm.Asynchronous.ImportOperationTransform::UpdateColumnValues

- ea: `0x17eb0`
- end: `0x18488`
- name: `Microsoft.Crm.Asynchronous.ImportOperationTransform::UpdateColumnValues`
- size: `1496`
- prototype: ``
- caller_count: `6`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x17130`
- `0x17750`
- `0x17eb0`
- `0x19b90`
- `0x1b1e0`
- `0x1c630`

## callees

- `0x4420`
- `0x58b0`
- `0x58e0`
- `0x58f0`
- `0x5a60`
- `0x5a90`
- `0x17eb0`

## string_xrefs

- `0x17fbd`: `UPDATE dbo.{0} SET `
- `0x18402`: `Not an Error; Append fileId in Update statement = {0}`

## pseudocode

```c

```

## disassembly

```asm
0x17eb0  ldarg.s  5
0x17eb2  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.ParsedDataRow>::get_Count()
0x17eb7  ldc.i4.0
0x17eb8  ble.s    loc_17ECA
0x17eba  ldarg.s  5
0x17ebc  ldc.i4.0
0x17ebd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.ParsedDataRow>::get_Item(!!T0)
0x17ec2  callvirt instance int32 Microsoft.Crm.Asynchronous.ParsedDataRow::get_Length()
0x17ec7  ldc.i4.0
0x17ec8  bgt.s    loc_17F09
0x17eca  ldarg.0
0x17ecb  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0x17ed0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x17ed5  ldc.i4.s 0x18
0x17ed7  ldstr    aNoValuesFoundF_0// "No values found for updating additional"...
0x17edc  ldc.i4.4
0x17edd  newarr   [mscorlib]System.Object
0x17ee2  dup
0x17ee3  ldc.i4.0
0x17ee4  ldarg.2
0x17ee5  stelem.ref
0x17ee6  dup
0x17ee7  ldc.i4.1
0x17ee8  ldarg.1
0x17ee9  box      [mscorlib]System.Guid
0x17eee  stelem.ref
0x17eef  dup
0x17ef0  ldc.i4.2
0x17ef1  ldarg.s  7
0x17ef3  box      [mscorlib]System.Int64
0x17ef8  stelem.ref
0x17ef9  dup
0x17efa  ldc.i4.3
0x17efb  ldarg.s  8
0x17efd  box      [mscorlib]System.Int64
0x17f02  stelem.ref
0x17f03  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x17f08  ret
0x17f09  ldarg.s  5
0x17f0b  ldc.i4.0
0x17f0c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.ParsedDataRow>::get_Item(!!T0)
0x17f11  callvirt instance int32 Microsoft.Crm.Asynchronous.ParsedDataRow::get_Length()
0x17f16  ldc.i4.1
0x17f17  add
0x17f18  ldarg.0
0x17f19  ldfld    int32 Microsoft.Crm.Asynchronous.ImportOperationTransform::_updateBatchParameters
0x17f1e  ble.s    loc_17F8C
0x17f20  ldarg.s  5
0x17f22  ldc.i4.0
0x17f23  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.ParsedDataRow>::get_Item(!!T0)
0x17f28  callvirt instance int32 Microsoft.Crm.Asynchronous.ParsedDataRow::get_Length()
0x17f2d  ldc.i4.1
0x17f2e  add
0x17f2f  ldc.i4   0x7D0
0x17f34  ble.s    loc_17F81
0x17f36  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x17f3b  ldstr    aNumberOfTransf// "Number of transformation mappings ({1})"...
0x17f40  ldc.i4.3
0x17f41  newarr   [mscorlib]System.Object
0x17f46  dup
0x17f47  ldc.i4.0
0x17f48  ldarg.1
0x17f49  box      [mscorlib]System.Guid
0x17f4e  stelem.ref
0x17f4f  dup
0x17f50  ldc.i4.1
0x17f51  ldarg.s  5
0x17f53  ldc.i4.0
0x17f54  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.ParsedDataRow>::get_Item(!!T0)
0x17f59  callvirt instance int32 Microsoft.Crm.Asynchronous.ParsedDataRow::get_Length()
0x17f5e  box      [mscorlib]System.Int32
0x17f63  stelem.ref
0x17f64  dup
0x17f65  ldc.i4.2
0x17f66  ldc.i4   0x7D0
0x17f6b  box      [mscorlib]System.Int32
0x17f70  stelem.ref
0x17f71  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x17f76  ldc.i4   0x80040315
0x17f7b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x17f80  throw
0x17f81  ldarg.0
0x17f82  ldc.i4   0x7D0
0x17f87  stfld    int32 Microsoft.Crm.Asynchronous.ImportOperationTransform::_updateBatchParameters
0x17f8c  ldarg.s  6
0x17f8e  ldsfld   string [mscorlib]System.String::Empty
0x17f93  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x17f98  ldarg.s  6
0x17f9a  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x17f9f  callvirt instance void [mscorlib]System.Collections.IList::Clear()
0x17fa4  ldarg.s  6
0x17fa6  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x17fab  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x17fb0  stloc.0
0x17fb1  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x17fb6  stloc.1
0x17fb7  ldloc.1
0x17fb8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x17fbd  ldstr    aUpdateDbo0Set// "UPDATE dbo.{0} SET "
0x17fc2  ldc.i4.1
0x17fc3  newarr   [mscorlib]System.Object
0x17fc8  dup
0x17fc9  ldc.i4.0
0x17fca  ldarg.2
0x17fcb  stelem.ref
0x17fcc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x17fd1  pop
0x17fd2  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor()
0x17fd7  stloc.2
0x17fd8  ldarg.s  5
0x17fda  ldc.i4.0
0x17fdb  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.ParsedDataRow>::get_Item(!!T0)
0x17fe0  callvirt instance int32 Microsoft.Crm.Asynchronous.ParsedDataRow::get_Length()
0x17fe5  ldc.i4.1
0x17fe6  add
0x17fe7  newarr   [mscorlib]System.Text.StringBuilder
0x17fec  stloc.3
0x17fed  ldarg.s  5
0x17fef  ldc.i4.0
0x17ff0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.ParsedDataRow>::get_Item(!!T0)
0x17ff5  callvirt instance int32 Microsoft.Crm.Asynchronous.ParsedDataRow::get_Length()
0x17ffa  ldc.i4.1
0x17ffb  add
0x17ffc  newarr   [mscorlib]System.String
0x18001  stloc.s  4
0x18003  ldc.i4.0
0x18004  stloc.s  0xB
0x18006  br       loc_1808B
0x1800b  ldc.i4.0
0x1800c  stloc.s  0xC
0x1800e  br.s     loc_1807A
0x18010  ldarg.s  5
0x18012  ldloc.s  0xC
0x18014  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.ParsedDataRow>::get_Item(!!T0)
0x18019  ldloc.s  0xB
0x1801b  callvirt instance class Microsoft.Crm.Asynchronous.ParsedDataObject Microsoft.Crm.Asynchronous.ParsedDataRow::get_Item(int32 index)
0x18020  brfalse.s loc_18074
0x18022  ldarg.s  5
0x18024  ldloc.s  0xC
0x18026  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.ParsedDataRow>::get_Item(!!T0)
0x1802b  ldloc.s  0xB
0x1802d  callvirt instance class Microsoft.Crm.Asynchronous.ParsedDataObject Microsoft.Crm.Asynchronous.ParsedDataRow::get_Item(int32 index)
0x18032  callvirt instance string Microsoft.Crm.Asynchronous.ParsedDataObject::get_ColumnName()
0x18037  stloc.s  0xD
0x18039  ldloc.3
0x1803a  ldloc.s  0xB
0x1803c  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x18041  stelem.ref
0x18042  ldloc.3
0x18043  ldloc.s  0xB
0x18045  ldelem.ref
0x18046  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1804b  ldstr    a0Case// "{0} = CASE"
0x18050  ldc.i4.1
0x18051  newarr   [mscorlib]System.Object
0x18056  dup
0x18057  ldc.i4.0
0x18058  ldloc.s  0xD
0x1805a  stelem.ref
0x1805b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x18060  pop
0x18061  ldloc.s  4
0x18063  ldloc.s  0xB
0x18065  ldloc.s  0xD
0x18067  stelem.ref
0x18068  ldloc.2
0x18069  ldloc.s  0xD
0x1806b  ldloc.s  0xB
0x1806d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x18072  br.s     loc_18085
0x18074  ldloc.s  0xC
0x18076  ldc.i4.1
0x18077  add
0x18078  stloc.s  0xC
0x1807a  ldloc.s  0xC
0x1807c  ldarg.s  5
0x1807e  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.ParsedDataRow>::get_Count()
0x18083  blt.s    loc_18010
0x18085  ldloc.s  0xB
0x18087  ldc.i4.1
0x18088  add
0x18089  stloc.s  0xB
0x1808b  ldloc.s  0xB
0x1808d  ldloc.3
0x1808e  ldlen
0x1808f  conv.i4
0x18090  ldc.i4.1
0x18091  sub
0x18092  blt      loc_1800B
0x18097  ldloc.3
0x18098  ldloc.3
0x18099  ldlen
0x1809a  conv.i4
0x1809b  ldc.i4.1
0x1809c  sub
0x1809d  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x180a2  stelem.ref
0x180a3  ldloc.3
0x180a4  ldloc.3
0x180a5  ldlen
0x180a6  conv.i4
0x180a7  ldc.i4.1
0x180a8  sub
0x180a9  ldelem.ref
0x180aa  ldstr    aIstransformedC// "IsTransformed = CASE"
0x180af  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x180b4  pop
0x180b5  ldloc.s  4
0x180b7  ldloc.3
0x180b8  ldlen
0x180b9  conv.i4
0x180ba  ldc.i4.1
0x180bb  sub
0x180bc  ldstr    aIstransformed// "IsTransformed"
0x180c1  stelem.ref
0x180c2  ldc.i4.0
0x180c3  stloc.s  5
0x180c5  ldc.i4.0
0x180c6  stloc.s  6
0x180c8  ldarg.s  5
0x180ca  ldc.i4.0
0x180cb  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.ParsedDataRow>::get_Item(!!T0)
0x180d0  callvirt instance int32 Microsoft.Crm.Asynchronous.ParsedDataRow::get_Length()
0x180d5  ldc.i4.1
0x180d6  add
0x180d7  stloc.s  7
0x180d9  ldarg.s  5
0x180db  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.ParsedDataRow>::GetEnumerator()
0x180e0  stloc.s  0xE
0x180e2  br       loc_1829C
0x180e7  ldloca.s 0xE
0x180e9  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.ParsedDataRow>::get_Current()
0x180ee  stloc.s  0xF
0x180f0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x180f5  ldstr    a012Key// "@{0}{1}_{2}key"
0x180fa  ldc.i4.3
0x180fb  newarr   [mscorlib]System.Object
0x18100  dup
0x18101  ldc.i4.0
0x18102  ldarg.3
0x18103  stelem.ref
0x18104  dup
0x18105  ldc.i4.1
0x18106  ldc.i4.0
0x18107  box      [mscorlib]System.Int32
0x1810c  stelem.ref
0x1810d  dup
0x1810e  ldc.i4.2
0x1810f  ldloc.s  5
0x18111  box      [mscorlib]System.Int32
0x18116  stelem.ref
0x18117  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1811c  stloc.s  0x10
0x1811e  ldc.i4.0
0x1811f  stloc.s  0x11
0x18121  br       loc_18231
0x18126  ldloc.s  0xF
0x18128  ldloc.s  0x11
0x1812a  callvirt instance class Microsoft.Crm.Asynchronous.ParsedDataObject Microsoft.Crm.Asynchronous.ParsedDataRow::get_Item(int32 index)
0x1812f  brfalse  loc_1822B
0x18134  ldloc.s  0xF
0x18136  ldloc.s  0x11
0x18138  callvirt instance class Microsoft.Crm.Asynchronous.ParsedDataObject Microsoft.Crm.Asynchronous.ParsedDataRow::get_Item(int32 index)
0x1813d  callvirt instance string Microsoft.Crm.Asynchronous.ParsedDataObject::get_ColumnName()
0x18142  stloc.s  0x12
0x18144  ldloc.s  0xF
0x18146  ldloc.s  0x11
0x18148  callvirt instance class Microsoft.Crm.Asynchronous.ParsedDataObject Microsoft.Crm.Asynchronous.ParsedDataRow::get_Item(int32 index)
0x1814d  callvirt instance string Microsoft.Crm.Asynchronous.ParsedDataObject::get_ColumnValue()
0x18152  stloc.s  0x13
0x18154  ldloc.s  0xF
0x18156  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ParsedDataRow::get_RecordId()
0x1815b  stloc.s  0x14
0x1815d  ldloc.2
0x1815e  ldloc.s  0x12
0x18160  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0x18165  stloc.s  0x15
0x18167  ldloc.3
0x18168  ldloc.s  0x15
0x1816a  ldelem.ref
0x1816b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18170  ldstr    aWhen4012KeyThe// " WHEN {4} = @{0}{1}_{2}key THEN @{3}_{2"...
0x18175  ldc.i4.5
0x18176  newarr   [mscorlib]System.Object
0x1817b  dup
0x1817c  ldc.i4.0
0x1817d  ldarg.3
0x1817e  stelem.ref
0x1817f  dup
0x18180  ldc.i4.1
0x18181  ldc.i4.0
0x18182  box      [mscorlib]System.Int32
0x18187  stelem.ref
0x18188  dup
0x18189  ldc.i4.2
0x1818a  ldloc.s  5
0x1818c  box      [mscorlib]System.Int32
0x18191  stelem.ref
0x18192  dup
0x18193  ldc.i4.3
  ... truncated ...
```
