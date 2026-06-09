# Microsoft.Crm.TableEntity::DeleteAll

- ea: `0x2560`
- end: `0x2671`
- name: `Microsoft.Crm.TableEntity::DeleteAll`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0xa98a0`

## callees

- `0x2500`
- `0x2520`
- `0x2550`
- `0x2560`
- `0x2790`

## string_xrefs

- `0x260d`: `DeletionService: Stale records exists in {0} Matchcode<> tables for Base table {1} ObjectTypeCode {2}`
- `0x2649`: `DeletionService: No MatchCode<> tables found for Base table {0} ObjectTypeCode {1}`

## pseudocode

```c

```

## disassembly

```asm
0x2560  ldarg.0
0x2561  ldc.i4.0
0x2562  call     instance void Microsoft.Crm.TableEntity::set_AllStaleMatchCodeRecordsDeleted(bool value)
0x2567  ldarg.0
0x2568  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.TableEntity::_matchingentitymatchcodetable
0x256d  ldarg.0
0x256e  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.TableEntity::_baseentitymatchcodetable
0x2573  call     T0x2B000002
0x2578  call     T0x2B000003
0x257d  stloc.0
0x257e  ldloc.0
0x257f  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x2584  ldc.i4.0
0x2585  ble      loc_263F
0x258a  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<bool>::.ctor()
0x258f  stloc.1
0x2590  ldloc.0
0x2591  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0x2596  stloc.2
0x2597  br.s     loc_25B1
0x2599  ldloca.s 2
0x259b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0x25a0  stloc.3
0x25a1  ldloc.1
0x25a2  ldarg.0
0x25a3  ldarg.1
0x25a4  ldloc.3
0x25a5  ldarg.2
0x25a6  ldarg.3
0x25a7  call     instance bool Microsoft.Crm.TableEntity::DeleteStaleMatchCodeRecords(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection connection, string matchCodeTableName, class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction transaction, valuetype [mscorlib]System.Guid orgId)
0x25ac  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<bool>::Add(var<u1>)
0x25b1  ldloca.s 2
0x25b3  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::MoveNext()
0x25b8  brtrue.s loc_2599
0x25ba  leave.s  loc_25CA
0x25bc  ldloca.s 2
0x25be  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>
0x25c4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x25c9  endfinally
0x25ca  ldloc.1
0x25cb  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<bool>::get_Count()
0x25d0  ldc.i4.0
0x25d1  ble      loc_2670
0x25d6  ldloc.1
0x25d7  ldsfld   class [mscorlib]System.Func`2<bool, bool> <>c::<>9__9_0
0x25dc  dup
0x25dd  brtrue.s loc_25F6
0x25df  pop
0x25e0  ldsfld   class <>c <>c::<>9
0x25e5  ldftn    instance bool <>c::<DeleteAll>b__9_0(bool t)
0x25eb  newobj   instance void class [mscorlib]System.Func`2<bool, bool>::.ctor(object, native int)
0x25f0  dup
0x25f1  stsfld   class [mscorlib]System.Func`2<bool, bool> <>c::<>9__9_0
0x25f6  call     T0x2B000004
0x25fb  stloc.s  4
0x25fd  ldloc.s  4
0x25ff  brtrue.s loc_2609
0x2601  ldarg.0
0x2602  ldc.i4.1
0x2603  call     instance void Microsoft.Crm.TableEntity::set_AllStaleMatchCodeRecordsDeleted(bool value)
0x2608  ret
0x2609  ldnull
0x260a  ldarg.3
0x260b  ldc.i4.s 0x14
0x260d  ldstr    aDeletionservic_59// "DeletionService: Stale records exists i"...
0x2612  ldc.i4.3
0x2613  newarr   [mscorlib]System.Object
0x2618  dup
0x2619  ldc.i4.0
0x261a  ldloc.s  4
0x261c  box      [mscorlib]System.Int32
0x2621  stelem.ref
0x2622  dup
0x2623  ldc.i4.1
0x2624  ldarg.0
0x2625  call     instance string Microsoft.Crm.TableEntity::get_BaseTableName()
0x262a  stelem.ref
0x262b  dup
0x262c  ldc.i4.2
0x262d  ldarg.0
0x262e  call     instance int32 Microsoft.Crm.TableEntity::get_ObjectTypeCode()
0x2633  box      [mscorlib]System.Int32
0x2638  stelem.ref
0x2639  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x263e  ret
0x263f  ldarg.0
0x2640  ldc.i4.1
0x2641  call     instance void Microsoft.Crm.TableEntity::set_AllStaleMatchCodeRecordsDeleted(bool value)
0x2646  ldarg.3
0x2647  ldc.i4.s 0x14
0x2649  ldstr    aDeletionservic_60// "DeletionService: No MatchCode<> tables "...
0x264e  ldc.i4.2
0x264f  newarr   [mscorlib]System.Object
0x2654  dup
0x2655  ldc.i4.0
0x2656  ldarg.0
0x2657  call     instance string Microsoft.Crm.TableEntity::get_BaseTableName()
0x265c  stelem.ref
0x265d  dup
0x265e  ldc.i4.1
0x265f  ldarg.0
0x2660  call     instance int32 Microsoft.Crm.TableEntity::get_ObjectTypeCode()
0x2665  box      [mscorlib]System.Int32
0x266a  stelem.ref
0x266b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2670  ret
```
