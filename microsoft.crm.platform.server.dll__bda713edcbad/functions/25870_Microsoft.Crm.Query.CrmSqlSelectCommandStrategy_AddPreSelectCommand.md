# Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::AddPreSelectCommand

- ea: `0x25870`
- end: `0x258d6`
- name: `Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::AddPreSelectCommand`
- size: `102`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x23f20`
- `0x25870`
- `0x25f50`
- `0x26290`

## string_xrefs

- `0x25871`: `preSelectCommand`
- `0x258ac`: `Incorrect processing order. Preselect Command with Rollup should not be added after the QuickFindFilter is processed.`

## pseudocode

```c

```

## disassembly

```asm
0x25870  ldarg.1
0x25871  ldstr    aPreselectcomma// "preSelectCommand"
0x25876  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2587b  ldarg.0
0x2587c  ldfld    bool Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::_hasQuickFindFilterBeenProvided
0x25881  brfalse.s loc_258B7
0x25883  ldarg.0
0x25884  ldarg.1
0x25885  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x2588a  call     instance bool Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::HasRollupInQuery(string preselectCommand)
0x2588f  brfalse.s loc_258B7
0x25891  ldnull
0x25892  ldarg.0
0x25893  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::_context
0x25898  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x2589d  ldc.i4.s 0x1D
0x2589f  ldstr    a0// "{0}"
0x258a4  ldc.i4.1
0x258a5  newarr   [mscorlib]System.Object
0x258aa  dup
0x258ab  ldc.i4.0
0x258ac  ldstr    aIncorrectProce// "Incorrect processing order. Preselect C"...
0x258b1  stelem.ref
0x258b2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x258b7  ldarg.0
0x258b8  call     instance class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::get_PreSelectCommand()
0x258bd  ldarg.1
0x258be  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x258c3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x258c8  pop
0x258c9  ldarg.0
0x258ca  ldarg.1
0x258cb  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x258d0  call     instance void Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::AddParameters(class [System.Data]System.Data.IDataParameterCollection parameters)
0x258d5  ret
```
