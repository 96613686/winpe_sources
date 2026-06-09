# Microsoft.Crm.BusinessEntities.TempTableSecurityFilterPopulator::CreatePreVisitCommand

- ea: `0x771f0`
- end: `0x7730e`
- name: `Microsoft.Crm.BusinessEntities.TempTableSecurityFilterPopulator::CreatePreVisitCommand`
- size: `286`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x77150`

## callees

- `0x66ae0`
- `0x76130`
- `0x76720`
- `0x76a70`
- `0x771f0`
- `0x77310`
- `0x775c0`

## string_xrefs

- `0x771f0`: `CreateIndexAfterInsertsForERMO1`
- `0x77222`: `\ncreate table #ObjectsIds (ObjectId uniqueidentifier);\n`
- `0x77231`: `\ncreate NONCLUSTERED index ndx_ObjectsIds_objId on #ObjectsIds (ObjectId ASC);\n`
- `0x772fd`: `\ncreate NONCLUSTERED index ndx_ObjectsIds_objId on #ObjectsIds (ObjectId ASC);\n`
- `0x7723d`: `\ninsert into #ObjectsIds\n`
- `0x77261`: `\ninsert into #ObjectsIds\n`
- `0x772b3`: `\ninsert into #ObjectsIds\n`

## pseudocode

```c

```

## disassembly

```asm
0x771f0  ldstr    aCreateindexaft// "CreateIndexAfterInsertsForERMO1"
0x771f5  ldc.i4.0
0x771f6  box      [mscorlib]System.Int32
0x771fb  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x77200  unbox.any [mscorlib]System.Int32
0x77205  ldc.i4.1
0x77206  ceq
0x77208  ldarg.1
0x77209  ldarg.3
0x7720a  ldarg.s  5
0x7720c  ldarg.s  4
0x7720e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x77213  ldc.i4.0
0x77214  ldnull
0x77215  call     class [System.Data]System.Data.IDbCommand Microsoft.Crm.BusinessEntities.SecurityFilterPopulatorBase::CreatePOACommand(valuetype [mscorlib]System.Guid user, class Microsoft.Crm.BusinessEntities.SecurityTraits traits, bool noLock, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context, bool addBrackets, class Microsoft.Crm.Query.EntitySecurityPOAattributes entitySecurityPOAattributes)
0x7721a  stloc.0
0x7721b  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x77220  stloc.1
0x77221  ldloc.1
0x77222  ldstr    aCreateTableObj// "\r\ncreate table #ObjectsIds (ObjectId "...
0x77227  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x7722c  pop
0x7722d  dup
0x7722e  brtrue.s loc_7723C
0x77230  ldloc.1
0x77231  ldstr    aCreateNonclust// "\r\ncreate NONCLUSTERED index ndx_Objec"...
0x77236  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x7723b  pop
0x7723c  ldloc.1
0x7723d  ldstr    aInsertIntoObje// "\r\ninsert into #ObjectsIds\r\n"
0x77242  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x77247  pop
0x77248  ldloc.1
0x77249  ldloc.0
0x7724a  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x7724f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x77254  pop
0x77255  ldloc.1
0x77256  ldstr    asc_CC58E// ";"
0x7725b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x77260  pop
0x77261  ldstr    aInsertIntoObje// "\r\ninsert into #ObjectsIds\r\n"
0x77266  ldarg.2
0x77267  ldarg.3
0x77268  ldarg.s  5
0x7726a  ldloc.1
0x7726b  call     void Microsoft.Crm.BusinessEntities.TempTableSecurityFilterPopulator::AppendInsertIntoTempTablePrimaryKeyColumn(string insertIntoTempTable, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata, class Microsoft.Crm.BusinessEntities.SecurityTraits traits, bool noLock, class [mscorlib]System.Text.StringBuilder s)
0x77270  ldloc.1
0x77271  ldstr    aWhereOwneridIn// "\r\nwhere OwnerId in \r\n"
0x77276  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x7727b  pop
0x7727c  ldloc.0
0x7727d  ldloc.1
0x7727e  callvirt instance string [mscorlib]System.Object::ToString()
0x77283  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x77288  ldarg.1
0x77289  ldarg.3
0x7728a  ldarg.s  5
0x7728c  ldc.i4.0
0x7728d  ldnull
0x7728e  ldloc.0
0x7728f  ldnull
0x77290  call     void Microsoft.Crm.BusinessEntities.SecurityFilterPopulatorBase::PopulateOwnerCommandUsingJoin(valuetype [mscorlib]System.Guid user, class Microsoft.Crm.BusinessEntities.SecurityTraits traits, bool noLock, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth privilegeDepth, string privateAttribute, class [System.Data]System.Data.IDbCommand ownerCommand, class Microsoft.Crm.Query.EntitySecurityPOAattributes entitySecurityPOAattributes)
0x77295  ldarg.s  6
0x77297  ldc.i4.1
0x77298  beq.s    loc_7729F
0x7729a  ldarg.s  6
0x7729c  ldc.i4.2
0x7729d  bne.un.s loc_772F4
0x7729f  ldloc.1
0x772a0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Clear()
0x772a5  pop
0x772a6  ldloc.1
0x772a7  ldloc.0
0x772a8  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x772ad  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x772b2  pop
0x772b3  ldstr    aInsertIntoObje// "\r\ninsert into #ObjectsIds\r\n"
0x772b8  ldarg.2
0x772b9  ldarg.3
0x772ba  ldarg.s  5
0x772bc  ldloc.1
0x772bd  call     void Microsoft.Crm.BusinessEntities.TempTableSecurityFilterPopulator::AppendInsertIntoTempTablePrimaryKeyColumn(string insertIntoTempTable, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata, class Microsoft.Crm.BusinessEntities.SecurityTraits traits, bool noLock, class [mscorlib]System.Text.StringBuilder s)
0x772c2  ldloc.1
0x772c3  ldstr    aWhere0In// "\r\nwhere {0} in\r\n"
0x772c8  ldarg.3
0x772c9  callvirt instance string Microsoft.Crm.BusinessEntities.SecurityTraits::get_BusinessColumnName()
0x772ce  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x772d3  pop
0x772d4  ldloc.1
0x772d5  ldarg.1
0x772d6  ldarg.s  5
0x772d8  ldarg.3
0x772d9  ldloc.0
0x772da  ldnull
0x772db  ldarg.s  4
0x772dd  call     string Microsoft.Crm.BusinessEntities.SecurityFilterPopulatorBase::GetRoleConditionWithTableCommandText(valuetype [mscorlib]System.Guid user, bool noLock, class Microsoft.Crm.BusinessEntities.SecurityTraits traits, class [System.Data]System.Data.IDbCommand command, class Microsoft.Crm.Query.EntitySecurityPOAattributes entitySecurityPOAattributes, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x772e2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x772e7  pop
0x772e8  ldloc.0
0x772e9  ldloc.1
0x772ea  callvirt instance string [mscorlib]System.Object::ToString()
0x772ef  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x772f4  brfalse.s loc_7730C
0x772f6  ldloc.0
0x772f7  dup
0x772f8  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x772fd  ldstr    aCreateNonclust// "\r\ncreate NONCLUSTERED index ndx_Objec"...
0x77302  call     string [mscorlib]System.String::Concat(string, string)
0x77307  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x7730c  ldloc.0
0x7730d  ret
```
