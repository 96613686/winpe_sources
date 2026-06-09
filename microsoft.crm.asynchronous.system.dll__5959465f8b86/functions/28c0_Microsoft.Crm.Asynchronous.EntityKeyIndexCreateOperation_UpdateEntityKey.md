# Microsoft.Crm.Asynchronous.EntityKeyIndexCreateOperation::UpdateEntityKey

- ea: `0x28c0`
- end: `0x29b5`
- name: `Microsoft.Crm.Asynchronous.EntityKeyIndexCreateOperation::UpdateEntityKey`
- size: `245`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2600`
- `0x2780`

## callees

- `0x28c0`
- `0x2ac0`
- `0x2ae0`

## string_xrefs

- `0x2970`: `update EntityKey set `

## pseudocode

```c

```

## disassembly

```asm
0x28c0  ldarg.3
0x28c1  ldc.i4.1
0x28c2  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::set_FlushMetadataCache(bool)
0x28c7  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x28cc  stloc.0
0x28cd  ldsfld   string [mscorlib]System.String::Empty
0x28d2  stloc.1
0x28d3  ldloc.0
0x28d4  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x28d9  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x28de  stloc.2
0x28df  ldarg.1
0x28e0  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::GetEnumerator()
0x28e5  stloc.3
0x28e6  br.s     loc_2944
0x28e8  ldloca.s 3
0x28ea  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, object>::get_Current()
0x28ef  stloc.s  4
0x28f1  ldc.i4.5
0x28f2  newarr   [mscorlib]System.String
0x28f7  dup
0x28f8  ldc.i4.0
0x28f9  ldloc.1
0x28fa  stelem.ref
0x28fb  dup
0x28fc  ldc.i4.1
0x28fd  ldloca.s 4
0x28ff  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Key()
0x2904  stelem.ref
0x2905  dup
0x2906  ldc.i4.2
0x2907  ldstr    asc_14218// " = @"
0x290c  stelem.ref
0x290d  dup
0x290e  ldc.i4.3
0x290f  ldloca.s 4
0x2911  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Key()
0x2916  stelem.ref
0x2917  dup
0x2918  ldc.i4.4
0x2919  ldstr    asc_14222// ","
0x291e  stelem.ref
0x291f  call     string [mscorlib]System.String::Concat(string[])
0x2924  stloc.1
0x2925  ldloc.2
0x2926  ldstr    asc_14226// "@"
0x292b  ldloca.s 4
0x292d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Key()
0x2932  call     string [mscorlib]System.String::Concat(string, string)
0x2937  ldloca.s 4
0x2939  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Value()
0x293e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2943  pop
0x2944  ldloca.s 3
0x2946  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, object>::MoveNext()
0x294b  brtrue.s loc_28E8
0x294d  leave.s  loc_295D
0x294f  ldloca.s 3
0x2951  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, object>
0x2957  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x295c  endfinally
0x295d  ldloc.1
0x295e  ldc.i4.1
0x295f  newarr   [mscorlib]System.Char
0x2964  dup
0x2965  ldc.i4.0
0x2966  ldc.i4.s 0x2C
0x2968  stelem.i2
0x2969  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x296e  stloc.1
0x296f  ldloc.0
0x2970  ldstr    aUpdateEntityke// "update EntityKey set "
0x2975  ldloc.1
0x2976  ldstr    aWhereEntitykey// " where EntityKeyId = @entityKeyId"
0x297b  call     string [mscorlib]System.String::Concat(string, string, string)
0x2980  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x2985  ldloc.2
0x2986  ldstr    aEntitykeyid// "@entityKeyId"
0x298b  ldarg.2
0x298c  box      [mscorlib]System.Guid
0x2991  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2996  pop
0x2997  ldarg.0
0x2998  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.EntityKeyIndexCreateOperation::_orgConfig
0x299d  newobj   instance void Microsoft.Crm.Asynchronous.EntityKeyDataAccess::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration config)
0x29a2  ldloc.0
0x29a3  callvirt instance void Microsoft.Crm.Asynchronous.EntityKeyDataAccess::ExecuteDbCommand(class [System.Data]System.Data.IDbCommand command)
0x29a8  leave.s  loc_29B4
0x29aa  ldloc.0
0x29ab  brfalse.s loc_29B3
0x29ad  ldloc.0
0x29ae  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x29b3  endfinally
0x29b4  ret
```
