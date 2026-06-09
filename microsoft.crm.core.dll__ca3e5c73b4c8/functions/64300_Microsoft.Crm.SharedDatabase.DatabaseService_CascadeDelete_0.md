# Microsoft.Crm.SharedDatabase.DatabaseService::CascadeDelete_0

- ea: `0x64300`
- end: `0x64579`
- name: `Microsoft.Crm.SharedDatabase.DatabaseService::CascadeDelete_0`
- size: `633`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callers

- `0x642f0`
- `0x6eb30`

## callees

- `0x1f80`
- `0x1a880`
- `0x44400`
- `0x444f0`
- `0x44510`
- `0x5f120`
- `0x5f5d0`
- `0x60070`
- `0x60080`
- `0x607d0`
- `0x607f0`
- `0x60800`
- `0x60830`
- `0x60870`
- `0x61520`
- `0x62600`
- `0x63a20`
- `0x64080`
- `0x64300`

## string_xrefs

- `0x643ff`: `D:\a\1\s\src\Platform\Core\DataServices\ObjectModel\DatabaseService.cs`
- `0x64537`: `D:\a\1\s\src\Platform\Core\DataServices\ObjectModel\DatabaseService.cs`
- `0x643fa`: `CascadeDelete`
- `0x64532`: `CascadeDelete`

## pseudocode

```c

```

## disassembly

```asm
0x64300  ldarg.0
0x64301  ldarg.1
0x64302  call     instance void Microsoft.Crm.SharedDatabase.DatabaseService::Initialize(string tableName)
0x64307  ldnull
0x64308  stloc.0
0x64309  ldarg.0
0x6430a  call     instance class Microsoft.Crm.SharedDatabase.DBMetadataCache Microsoft.Crm.SharedDatabase.DatabaseService::get_Cache()
0x6430f  callvirt instance class Microsoft.Crm.SharedDatabase.TableCollection Microsoft.Crm.SharedDatabase.DBMetadataCache::get_Tables()
0x64314  ldarg.1
0x64315  ldloca.s 0
0x64317  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.SharedDatabase.Table>::TryGetValue(var<u1>, !!T0)
0x6431c  stloc.1
0x6431d  ldloc.1
0x6431e  brtrue.s loc_6433B
0x64320  ldstr    aTable_2// "Table '"
0x64325  ldarg.1
0x64326  ldstr    aDoesNotExist_0// "' does not exist"
0x6432b  call     string [mscorlib]System.String::Concat(string, string, string)
0x64330  ldc.i4   0x80040216
0x64335  newobj   instance void Microsoft.Crm.CrmException::.ctor(string message, int32 errorCode)
0x6433a  throw
0x6433b  ldc.i4.0
0x6433c  stloc.1
0x6433d  ldarg.0
0x6433e  call     instance class Microsoft.Crm.SharedDatabase.DBMetadataCache Microsoft.Crm.SharedDatabase.DatabaseService::get_Cache()
0x64343  callvirt instance class Microsoft.Crm.SharedDatabase.TableCollection Microsoft.Crm.SharedDatabase.DBMetadataCache::get_Tables()
0x64348  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.SharedDatabase.Table>::get_Values()
0x6434d  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<string, class Microsoft.Crm.SharedDatabase.Table>::GetEnumerator()
0x64352  stloc.s  4
0x64354  br.s     loc_643C1
0x64356  ldloca.s 4
0x64358  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class Microsoft.Crm.SharedDatabase.Table>::get_Current()
0x6435d  stloc.s  5
0x6435f  ldloc.s  5
0x64361  callvirt instance valuetype Microsoft.Crm.SharedDatabase.ConfigSku Microsoft.Crm.SharedDatabase.Table::get_Sku()
0x64366  call     valuetype Microsoft.Crm.SharedDatabase.ConfigSku Microsoft.Crm.BootstrapService::GetSku()
0x6436b  and
0x6436c  brfalse.s loc_643C1
0x6436e  ldloc.s  5
0x64370  callvirt instance valuetype Microsoft.Crm.SharedDatabase.ConfigScope Microsoft.Crm.SharedDatabase.Table::get_Scope()
0x64375  ldloc.0
0x64376  callvirt instance valuetype Microsoft.Crm.SharedDatabase.ConfigScope Microsoft.Crm.SharedDatabase.Table::get_Scope()
0x6437b  bne.un.s loc_643C1
0x6437d  ldloc.s  5
0x6437f  callvirt instance class Microsoft.Crm.SharedDatabase.RelationshipCollection Microsoft.Crm.SharedDatabase.Table::get_Relationships()
0x64384  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.SharedDatabase.Relationship>::GetEnumerator()
0x64389  stloc.s  6
0x6438b  br.s     loc_643A5
0x6438d  ldloc.s  6
0x6438f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.SharedDatabase.Relationship>::get_Current()
0x64394  callvirt instance string Microsoft.Crm.SharedDatabase.Relationship::get_ReferencedTableName()
0x64399  ldarg.1
0x6439a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6439f  brfalse.s loc_643A5
0x643a1  ldc.i4.1
0x643a2  stloc.1
0x643a3  leave.s  loc_643BC
0x643a5  ldloc.s  6
0x643a7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x643ac  brtrue.s loc_6438D
0x643ae  leave.s  loc_643BC
0x643b0  ldloc.s  6
0x643b2  brfalse.s loc_643BB
0x643b4  ldloc.s  6
0x643b6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x643bb  endfinally
0x643bc  ldloc.1
0x643bd  brfalse.s loc_643C1
0x643bf  leave.s  loc_643DA
0x643c1  ldloca.s 4
0x643c3  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class Microsoft.Crm.SharedDatabase.Table>::MoveNext()
0x643c8  brtrue.s loc_64356
0x643ca  leave.s  loc_643DA
0x643cc  ldloca.s 4
0x643ce  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class Microsoft.Crm.SharedDatabase.Table>
0x643d4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x643d9  endfinally
0x643da  ldloc.1
0x643db  brtrue.s loc_643DE
0x643dd  ret
0x643de  ldarg.0
0x643df  ldarg.1
0x643e0  ldc.i4.1
0x643e1  newarr   [mscorlib]System.String
0x643e6  dup
0x643e7  ldc.i4.0
0x643e8  ldloc.0
0x643e9  callvirt instance class Microsoft.Crm.SharedDatabase.Column Microsoft.Crm.SharedDatabase.Table::get_PrimaryKey()
0x643ee  callvirt instance string Microsoft.Crm.SharedDatabase.Column::get_Name()
0x643f3  stelem.ref
0x643f4  ldarg.2
0x643f5  ldc.i4   0xD0F
0x643fa  ldstr    aCascadedelete// "CascadeDelete"
0x643ff  ldstr    aDA1SSrcPlatfor_44// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x64404  call     instance class Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.SharedDatabase.DatabaseService::Retrieve(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag[] conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x64409  stloc.2
0x6440a  ldloc.2
0x6440b  brfalse.s loc_64415
0x6440d  ldloc.2
0x6440e  callvirt instance int32 class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Count()
0x64413  brtrue.s loc_64416
0x64415  ret
0x64416  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<object>::.ctor()
0x6441b  stloc.3
0x6441c  ldloc.2
0x6441d  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Values()
0x64422  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x64427  stloc.s  7
0x64429  br.s     loc_6444C
0x6442b  ldloca.s 7
0x6442d  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::get_Current()
0x64432  stloc.s  8
0x64434  ldloc.3
0x64435  ldloc.s  8
0x64437  ldloc.0
0x64438  callvirt instance class Microsoft.Crm.SharedDatabase.Column Microsoft.Crm.SharedDatabase.Table::get_PrimaryKey()
0x6443d  callvirt instance string Microsoft.Crm.SharedDatabase.Column::get_Name()
0x64442  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x64447  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<object>::Add(var<u1>)
0x6444c  ldloca.s 7
0x6444e  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x64453  brtrue.s loc_6442B
0x64455  leave.s  loc_64465
0x64457  ldloca.s 7
0x64459  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>
0x6445f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x64464  endfinally
0x64465  ldarg.0
0x64466  ldarg.1
0x64467  call     instance void Microsoft.Crm.SharedDatabase.DatabaseService::Initialize(string tableName)
0x6446c  ldarg.0
0x6446d  call     instance class Microsoft.Crm.SharedDatabase.DBMetadataCache Microsoft.Crm.SharedDatabase.DatabaseService::get_Cache()
0x64472  callvirt instance class Microsoft.Crm.SharedDatabase.TableCollection Microsoft.Crm.SharedDatabase.DBMetadataCache::get_Tables()
0x64477  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.SharedDatabase.Table>::get_Values()
0x6447c  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<string, class Microsoft.Crm.SharedDatabase.Table>::GetEnumerator()
0x64481  stloc.s  4
0x64483  br       loc_6455C
0x64488  ldloca.s 4
0x6448a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class Microsoft.Crm.SharedDatabase.Table>::get_Current()
0x6448f  stloc.s  9
0x64491  ldloc.s  9
0x64493  callvirt instance valuetype Microsoft.Crm.SharedDatabase.ConfigSku Microsoft.Crm.SharedDatabase.Table::get_Sku()
0x64498  call     valuetype Microsoft.Crm.SharedDatabase.ConfigSku Microsoft.Crm.BootstrapService::GetSku()
0x6449d  and
0x6449e  brfalse  loc_6455C
0x644a3  ldloc.s  9
0x644a5  callvirt instance valuetype Microsoft.Crm.SharedDatabase.ConfigScope Microsoft.Crm.SharedDatabase.Table::get_Scope()
0x644aa  ldloc.0
0x644ab  callvirt instance valuetype Microsoft.Crm.SharedDatabase.ConfigScope Microsoft.Crm.SharedDatabase.Table::get_Scope()
0x644b0  bne.un   loc_6455C
0x644b5  ldloc.s  9
0x644b7  callvirt instance class Microsoft.Crm.SharedDatabase.RelationshipCollection Microsoft.Crm.SharedDatabase.Table::get_Relationships()
0x644bc  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.SharedDatabase.Relationship>::GetEnumerator()
0x644c1  stloc.s  6
0x644c3  br.s     loc_64542
0x644c5  ldloc.s  6
0x644c7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.SharedDatabase.Relationship>::get_Current()
0x644cc  stloc.s  0xA
0x644ce  ldloc.s  0xA
0x644d0  callvirt instance string Microsoft.Crm.SharedDatabase.Relationship::get_ReferencedTableName()
0x644d5  ldarg.1
0x644d6  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x644db  brtrue.s loc_64542
0x644dd  ldloc.3
0x644de  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<object>::get_Count()
0x644e3  newarr   Microsoft.Crm.Data.PropertyBag
0x644e8  stloc.s  0xB
0x644ea  ldc.i4.0
0x644eb  stloc.s  0xC
0x644ed  br.s     loc_64518
0x644ef  ldloc.s  0xB
0x644f1  ldloc.s  0xC
0x644f3  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x644f8  stelem.ref
0x644f9  ldloc.s  0xB
0x644fb  ldloc.s  0xC
0x644fd  ldelem.ref
0x644fe  ldloc.s  0xA
0x64500  callvirt instance string Microsoft.Crm.SharedDatabase.Relationship::get_ReferencingColumnName()
0x64505  ldloc.3
0x64506  ldloc.s  0xC
0x64508  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<object>::get_Item(!!T0)
0x6450d  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x64512  ldloc.s  0xC
0x64514  ldc.i4.1
0x64515  add
0x64516  stloc.s  0xC
0x64518  ldloc.s  0xC
0x6451a  ldloc.3
0x6451b  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<object>::get_Count()
0x64520  blt.s    loc_644EF
0x64522  ldarg.0
0x64523  ldloc.s  9
0x64525  callvirt instance string Microsoft.Crm.SharedDatabase.Table::get_Name()
0x6452a  ldloc.s  0xB
0x6452c  ldarg.3
0x6452d  ldc.i4   0xD40
0x64532  ldstr    aCascadedelete// "CascadeDelete"
0x64537  ldstr    aDA1SSrcPlatfor_44// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x6453c  call     instance int32 Microsoft.Crm.SharedDatabase.DatabaseService::Delete(string tableName, class Microsoft.Crm.Data.PropertyBag[] conditions, bool flushTable, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x64541  pop
0x64542  ldloc.s  6
0x64544  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x64549  brtrue   loc_644C5
0x6454e  leave.s  loc_6455C
0x64550  ldloc.s  6
0x64552  brfalse.s loc_6455B
0x64554  ldloc.s  6
0x64556  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6455b  endfinally
0x6455c  ldloca.s 4
0x6455e  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class Microsoft.Crm.SharedDatabase.Table>::MoveNext()
0x64563  brtrue   loc_64488
0x64568  leave.s  loc_64578
0x6456a  ldloca.s 4
0x6456c  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class Microsoft.Crm.SharedDatabase.Table>
0x64572  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x64577  endfinally
0x64578  ret
```
