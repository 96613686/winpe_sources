# Microsoft.Crm.Asynchronous.ImportOperationParse::ProcessSingleRowForUpdateViaImport

- ea: `0x15570`
- end: `0x156a3`
- name: `Microsoft.Crm.Asynchronous.ImportOperationParse::ProcessSingleRowForUpdateViaImport`
- size: `307`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x15220`

## callees

- `0x15570`

## pseudocode

```c

```

## disassembly

```asm
0x15570  ldarg.1
0x15571  brtrue.s loc_15584
0x15573  ldc.i4   0x8004F601
0x15578  ldc.i4.0
0x15579  newarr   [mscorlib]System.Object
0x1557e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x15583  throw
0x15584  ldarg.1
0x15585  callvirt instance class [System.Core]System.Collections.Generic.HashSet`1<int32> [Microsoft.Crm]Microsoft.Crm.SpreadsheetMLMetadata::get_ColumnIndexesToBeIgnored()
0x1558a  stloc.0
0x1558b  ldarg.1
0x1558c  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<valuetype [Microsoft.Crm]Microsoft.Crm.SpreadsheetMLCellType> [Microsoft.Crm]Microsoft.Crm.SpreadsheetMLMetadata::get_CellDataTypes()
0x15591  stloc.1
0x15592  ldloc.0
0x15593  brfalse.s loc_155A1
0x15595  ldloc.1
0x15596  brfalse.s loc_155A1
0x15598  ldloc.1
0x15599  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<valuetype [Microsoft.Crm]Microsoft.Crm.SpreadsheetMLCellType>::get_Count()
0x1559e  ldarg.2
0x1559f  bge.s    loc_155B2
0x155a1  ldc.i4   0x8004F601
0x155a6  ldc.i4.0
0x155a7  newarr   [mscorlib]System.Object
0x155ac  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x155b1  throw
0x155b2  ldc.i4.0
0x155b3  stloc.s  4
0x155b5  br.s     loc_1560E
0x155b7  ldloc.s  4
0x155b9  ldc.i4.1
0x155ba  add
0x155bb  stloc.s  5
0x155bd  ldarg.3
0x155be  ldloc.s  5
0x155c0  callvirt instance class [Microsoft.Crm]Microsoft.Crm.SpreadsheetMLCell [Microsoft.Crm]Microsoft.Crm.SpreadsheetMLRow::GetCellAtIndex(int32)
0x155c5  brfalse.s loc_15608
0x155c7  ldarg.3
0x155c8  ldloc.s  5
0x155ca  callvirt instance class [Microsoft.Crm]Microsoft.Crm.SpreadsheetMLCell [Microsoft.Crm]Microsoft.Crm.SpreadsheetMLRow::GetCellAtIndex(int32)
0x155cf  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.SpreadsheetMLCellType [Microsoft.Crm]Microsoft.Crm.SpreadsheetMLCell::get_DataType()
0x155d4  ldloc.1
0x155d5  ldloc.s  4
0x155d7  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<valuetype [Microsoft.Crm]Microsoft.Crm.SpreadsheetMLCellType>::get_Item(!!T0)
0x155dc  stloc.s  6
0x155de  ldloc.s  6
0x155e0  beq.s    loc_15608
0x155e2  ldarg.s  4
0x155e4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x155e9  ldstr    a0_2// "{0},"
0x155ee  ldc.i4.1
0x155ef  newarr   [mscorlib]System.Object
0x155f4  dup
0x155f5  ldc.i4.0
0x155f6  ldloc.s  5
0x155f8  box      [mscorlib]System.Int32
0x155fd  stelem.ref
0x155fe  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x15603  pop
0x15604  ldarg.s  6
0x15606  ldc.i4.1
0x15607  stind.i1
0x15608  ldloc.s  4
0x1560a  ldc.i4.1
0x1560b  add
0x1560c  stloc.s  4
0x1560e  ldloc.s  4
0x15610  ldarg.2
0x15611  blt.s    loc_155B7
0x15613  ldarg.s  5
0x15615  ldlen
0x15616  conv.i4
0x15617  newarr   [mscorlib]System.String
0x1561c  stloc.2
0x1561d  ldarg.s  5
0x1561f  ldloc.2
0x15620  ldc.i4.0
0x15621  callvirt instance void [mscorlib]System.Array::CopyTo(class [mscorlib]System.Array, int32)
0x15626  ldloc.2
0x15627  ldc.i4.1
0x15628  ldelem.ref
0x15629  stloc.3
0x1562a  ldloc.0
0x1562b  callvirt instance valuetype [System.Core]System.Collections.Generic.HashSet`1/Enumerator<var<u1>> class [System.Core]System.Collections.Generic.HashSet`1<int32>::GetEnumerator()
0x15630  stloc.s  7
0x15632  br.s     loc_15646
0x15634  ldloca.s 7
0x15636  call     instance var<u1> valuetype [System.Core]System.Collections.Generic.HashSet`1/Enumerator<int32>::get_Current()
0x1563b  stloc.s  8
0x1563d  ldloc.2
0x1563e  ldloc.s  8
0x15640  ldsfld   string [mscorlib]System.String::Empty
0x15645  stelem.ref
0x15646  ldloca.s 7
0x15648  call     instance bool valuetype [System.Core]System.Collections.Generic.HashSet`1/Enumerator<int32>::MoveNext()
0x1564d  brtrue.s loc_15634
0x1564f  leave.s  loc_1565F
0x15651  ldloca.s 7
0x15653  constrained. valuetype [System.Core]System.Collections.Generic.HashSet`1/Enumerator<int32>
0x15659  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1565e  endfinally
0x1565f  call     class [Microsoft.Crm]Microsoft.Crm.IChecksumGenerator [Microsoft.Crm]Microsoft.Crm.ChecksumGenerator::get_Instance()
0x15664  ldloc.2
0x15665  callvirt instance string [Microsoft.Crm]Microsoft.Crm.IChecksumGenerator::GenerateChecksum(class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x1566a  ldloc.3
0x1566b  ldc.i4.4
0x1566c  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x15671  brtrue.s loc_156A2
0x15673  ldarg.s  7
0x15675  ldc.i4.1
0x15676  stind.i1
0x15677  ldarg.0
0x15678  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0x1567d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x15682  ldc.i4.s 0x18
0x15684  ldstr    aIgnoringRow0Si// "Ignoring row {0} since no changes were "...
0x15689  ldc.i4.1
0x1568a  newarr   [mscorlib]System.Object
0x1568f  dup
0x15690  ldc.i4.0
0x15691  ldarg.3
0x15692  callvirt instance int64 [Microsoft.Crm]Microsoft.Crm.SpreadsheetMLRow::get_RowIndex()
0x15697  box      [mscorlib]System.Int64
0x1569c  stelem.ref
0x1569d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x156a2  ret
```
