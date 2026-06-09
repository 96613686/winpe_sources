# Microsoft.Crm.BusinessEntities.SecurityFilterPopulatorBase::PopulateOwnerCommandUsingTempTableForHSM

- ea: `0x76310`
- end: `0x763cf`
- name: `Microsoft.Crm.BusinessEntities.SecurityFilterPopulatorBase::PopulateOwnerCommandUsingTempTableForHSM`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x75790`

## callees

- `0x76240`
- `0x763d0`
- `0x77580`

## string_xrefs

- `0x76351`: `@UserIdOwnerCommand`
- `0x76328`: `@OtcOwnerCommand`

## pseudocode

```c

```

## disassembly

```asm
0x76310  ldarg.3
0x76311  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::get_Connection()
0x76316  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x7631b  dup
0x7631c  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x76321  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x76326  stloc.0
0x76327  dup
0x76328  ldstr    aOtcownercomman// "@OtcOwnerCommand"
0x7632d  call     string Microsoft.Crm.BusinessEntities.SecurityFilterPopulatorBase::CreateUniqueParameterName(class [System.Data]System.Data.IDbCommand ownerCommand, string parameterNamePrefix)
0x76332  stloc.1
0x76333  ldloc.0
0x76334  ldloc.1
0x76335  ldarg.2
0x76336  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.BusinessEntities.SecurityTraits::get_Metadata()
0x7633b  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x76340  box      [mscorlib]System.Int32
0x76345  call     object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ConvertHelper::ToSqlParameter(object)
0x7634a  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7634f  pop
0x76350  dup
0x76351  ldstr    aUseridownercom// "@UserIdOwnerCommand"
0x76356  call     string Microsoft.Crm.BusinessEntities.SecurityFilterPopulatorBase::CreateUniqueParameterName(class [System.Data]System.Data.IDbCommand ownerCommand, string parameterNamePrefix)
0x7635b  stloc.2
0x7635c  ldloc.0
0x7635d  ldloc.2
0x7635e  ldarg.0
0x7635f  box      [mscorlib]System.Guid
0x76364  call     object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ConvertHelper::ToSqlParameter(object)
0x76369  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7636e  pop
0x7636f  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x76374  stloc.3
0x76375  ldloc.3
0x76376  ldstr    asc_CC172// "("
0x7637b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x76380  pop
0x76381  ldstr    aPem// "pem"
0x76386  stloc.s  4
0x76388  ldarg.1
0x76389  ldloc.2
0x7638a  ldloc.1
0x7638b  ldloc.3
0x7638c  ldloc.s  4
0x7638e  call     void Microsoft.Crm.BusinessEntities.SecurityFilterPopulatorBase::AppendOwnershipClauseForParentUser(bool noLock, string systemUserIdParameterName, string objectTypeCodeParameterName, class [mscorlib]System.Text.StringBuilder s, string pemAlias)
0x76393  ldloc.3
0x76394  ldstr    aUnion_2// " UNION "
0x76399  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x7639e  pop
0x7639f  ldloc.3
0x763a0  ldstr    aSelectPidsPrin// "select pids.PrincipalId from #Principal"...
0x763a5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x763aa  pop
0x763ab  ldloc.3
0x763ac  ldstr    asc_CC192// ")"
0x763b1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x763b6  pop
0x763b7  dup
0x763b8  dup
0x763b9  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x763be  ldloc.3
0x763bf  callvirt instance string [mscorlib]System.Object::ToString()
0x763c4  call     string [mscorlib]System.String::Concat(string, string)
0x763c9  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x763ce  ret
```
