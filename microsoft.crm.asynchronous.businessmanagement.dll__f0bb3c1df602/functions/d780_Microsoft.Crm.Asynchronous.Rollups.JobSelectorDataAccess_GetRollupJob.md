# Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::GetRollupJob

- ea: `0xd780`
- end: `0xd85d`
- name: `Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::GetRollupJob`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x16f60`

## callees

- `0xd780`
- `0xd860`
- `0xddf0`

## string_xrefs

- `0xd794`: `rolluppropertiesid`
- `0xd835`: `recordcreatedon`

## pseudocode

```c

```

## disassembly

```asm
0xd780  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0xd785  dup
0xd786  ldstr    aRollupjobid// "rollupjobid"
0xd78b  ldarg.1
0xd78c  ldc.i4.0
0xd78d  ldelem.ref
0xd78e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xd793  dup
0xd794  ldstr    aRollupproperti_1// "rolluppropertiesid"
0xd799  ldarg.1
0xd79a  ldc.i4.1
0xd79b  ldelem.ref
0xd79c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xd7a1  dup
0xd7a2  ldstr    aRegardingobjec// "regardingobjectid"
0xd7a7  ldarg.1
0xd7a8  ldc.i4.2
0xd7a9  ldelem.ref
0xd7aa  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xd7af  dup
0xd7b0  ldstr    aRegardingobjec_0// "regardingobjecttypecode"
0xd7b5  ldarg.1
0xd7b6  ldc.i4.3
0xd7b7  ldelem.ref
0xd7b8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xd7bd  dup
0xd7be  ldstr    aSourceentityty_0// "sourceentitytypecode"
0xd7c3  ldarg.1
0xd7c4  ldc.i4.4
0xd7c5  ldelem.ref
0xd7c6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xd7cb  dup
0xd7cc  ldstr    aPostponeuntil// "postponeuntil"
0xd7d1  ldarg.1
0xd7d2  ldc.i4.5
0xd7d3  ldelem.ref
0xd7d4  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0xd7d9  call     valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::ParseSqlDateTime(object value, valuetype [mscorlib]System.DateTime defaultValue)
0xd7de  box      [mscorlib]System.DateTime
0xd7e3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xd7e8  ldc.i4.0
0xd7e9  stloc.0
0xd7ea  ldarg.1
0xd7eb  ldc.i4.6
0xd7ec  ldelem.ref
0xd7ed  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xd7f2  beq.s    loc_D7FD
0xd7f4  ldarg.1
0xd7f5  ldc.i4.6
0xd7f6  ldelem.ref
0xd7f7  unbox.any [mscorlib]System.Int32
0xd7fc  stloc.0
0xd7fd  dup
0xd7fe  ldstr    aRetrycount_1// "retrycount"
0xd803  ldloc.0
0xd804  box      [mscorlib]System.Int32
0xd809  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xd80e  ldc.i4.0
0xd80f  stloc.1
0xd810  ldarg.1
0xd811  ldc.i4.7
0xd812  ldelem.ref
0xd813  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xd818  beq.s    loc_D823
0xd81a  ldarg.1
0xd81b  ldc.i4.7
0xd81c  ldelem.ref
0xd81d  unbox.any [mscorlib]System.Int32
0xd822  stloc.1
0xd823  dup
0xd824  ldstr    aDepthprocessed// "depthprocessed"
0xd829  ldloc.1
0xd82a  box      [mscorlib]System.Int32
0xd82f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xd834  dup
0xd835  ldstr    aRecordcreatedo// "recordcreatedon"
0xd83a  ldarg.1
0xd83b  ldc.i4.8
0xd83c  ldelem.ref
0xd83d  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xd842  call     valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::ParseSqlDateTime(object value, valuetype [mscorlib]System.DateTime defaultValue)
0xd847  box      [mscorlib]System.DateTime
0xd84c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xd851  ldarg.0
0xd852  ldfld    class Microsoft.Crm.Asynchronous.Rollups.RollupJobModifier Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::_modifier
0xd857  newobj   instance void Microsoft.Crm.Asynchronous.Rollups.RollupJob::.ctor(class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> data, class Microsoft.Crm.Asynchronous.Rollups.RollupJobModifier jobModifier)
0xd85c  ret
```
