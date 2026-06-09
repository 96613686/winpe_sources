# Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::RegisterEntityAndTableAliasForSecurityCheck

- ea: `0x2a750`
- end: `0x2a7a9`
- name: `Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::RegisterEntityAndTableAliasForSecurityCheck`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x25910`

## callees

- `0x236b0`
- `0x27fe0`
- `0x2a750`
- `0x2a7b0`
- `0x2b530`
- `0x2b570`

## string_xrefs

- `0x2a75e`: `The table alias {0} has already been registered for this query`
- `0x2a77a`: `Security`

## pseudocode

```c

```

## disassembly

```asm
0x2a750  ldarg.0
0x2a751  ldarg.2
0x2a752  call     instance bool Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::IsRowLevelSecurityRequiredForTableAlias(string tableAlias)
0x2a757  brfalse.s loc_2A778
0x2a759  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2a75e  ldstr    aTheTableAlias0// "The table alias {0} has already been re"...
0x2a763  ldc.i4.1
0x2a764  newarr   [mscorlib]System.Object
0x2a769  dup
0x2a76a  ldc.i4.0
0x2a76b  ldarg.2
0x2a76c  stelem.ref
0x2a76d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2a772  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0x2a777  throw
0x2a778  ldarg.0
0x2a779  ldarg.2
0x2a77a  ldstr    aSecurity// "Security"
0x2a77f  call     string [mscorlib]System.String::Concat(string, string)
0x2a784  call     instance string Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::GenerateUniqueTopLevelTableAlias(string tableAliasBase)
0x2a789  stloc.0
0x2a78a  ldarg.0
0x2a78b  ldfld    class Microsoft.Crm.Query.ICrmQueryContainer Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::_queryContainer
0x2a790  callvirt instance class Microsoft.Crm.Query.RowLevelSecurityData Microsoft.Crm.Query.ICrmQueryContainer::get_EntitySecurityInformation()
0x2a795  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Query.RowLevelEntitySecurityInfo> Microsoft.Crm.Query.RowLevelSecurityData::get_SecurityInfoByTableAlias()
0x2a79a  ldarg.2
0x2a79b  ldarg.1
0x2a79c  ldarg.2
0x2a79d  ldloc.0
0x2a79e  newobj   instance void Microsoft.Crm.Query.RowLevelEntitySecurityInfo::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata, string tableAlias, string securityTableAlias)
0x2a7a3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Query.RowLevelEntitySecurityInfo>::Add(var<u1>, !!T0)
0x2a7a8  ret
```
