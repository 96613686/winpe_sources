# Microsoft.Crm.BusinessEntities.SecurityFilterPopulatorBase::CreatePOACommand

- ea: `0x76720`
- end: `0x76806`
- name: `Microsoft.Crm.BusinessEntities.SecurityFilterPopulatorBase::CreatePOACommand`
- size: `230`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x764e0`
- `0x771f0`

## callees

- `0x763d0`
- `0x76720`
- `0x76810`
- `0x768d0`
- `0x768e0`
- `0x77580`

## string_xrefs

- `0x7679f`: `select {0}.ObjectId from PrincipalObjectAccess {0} `
- `0x767dd`: ` and {0}.ObjectTypeCode = @ObjectTypeCode and (({0}.AccessRightsMask|{0}.InheritedAccessRightsMask) & 1) = 1`

## pseudocode

```c

```

## disassembly

```asm
0x76720  ldarg.3
0x76721  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::get_Connection()
0x76726  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x7672b  dup
0x7672c  ldstr    aSystemuserid// "@SystemUserId"
0x76731  call     string Microsoft.Crm.BusinessEntities.SecurityFilterPopulatorBase::CreateUniqueParameterName(class [System.Data]System.Data.IDbCommand ownerCommand, string parameterNamePrefix)
0x76736  stloc.0
0x76737  dup
0x76738  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x7673d  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x76742  dup
0x76743  ldloc.0
0x76744  ldarg.0
0x76745  box      [mscorlib]System.Guid
0x7674a  call     object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ConvertHelper::ToSqlParameter(object)
0x7674f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x76754  pop
0x76755  ldstr    aObjecttypecode_86// "@ObjectTypeCode"
0x7675a  ldarg.1
0x7675b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.BusinessEntities.SecurityTraits::get_Metadata()
0x76760  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x76765  box      [mscorlib]System.Int32
0x7676a  call     object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ConvertHelper::ToSqlParameter(object)
0x7676f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x76774  pop
0x76775  ldstr    aPoa// "POA"
0x7677a  ldc.i4.0
0x7677b  ldarg.s  5
0x7677d  call     string Microsoft.Crm.BusinessEntities.SecurityFilterPopulatorBase::SecurityQueryBucket(valuetype SecurityTypeAttribute securityTypeAttribute, class Microsoft.Crm.Query.EntitySecurityPOAattributes entitySecurityPOAattributes)
0x76782  call     string [mscorlib]System.String::Concat(string, string)
0x76787  stloc.1
0x76788  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x7678d  stloc.2
0x7678e  ldarg.s  4
0x76790  brfalse.s loc_7679E
0x76792  ldloc.2
0x76793  ldstr    asc_CC172// "("
0x76798  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x7679d  pop
0x7679e  ldloc.2
0x7679f  ldstr    aSelect0Objecti// "select {0}.ObjectId from PrincipalObjec"...
0x767a4  ldloc.1
0x767a5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x767aa  pop
0x767ab  ldloc.2
0x767ac  ldarg.2
0x767ad  call     void Microsoft.Crm.BusinessEntities.SecurityFilterPopulatorBase::AddNoLock(class [mscorlib]System.Text.StringBuilder s, bool noLock)
0x767b2  ldloc.2
0x767b3  ldstr    aJoinSystemuser// "join SystemUserPrincipals sup "
0x767b8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x767bd  pop
0x767be  ldloc.2
0x767bf  ldarg.2
0x767c0  call     void Microsoft.Crm.BusinessEntities.SecurityFilterPopulatorBase::AddNoLock(class [mscorlib]System.Text.StringBuilder s, bool noLock)
0x767c5  ldloc.2
0x767c6  ldstr    aOn0Principalid// "on {0}.PrincipalId = sup.PrincipalId "
0x767cb  ldloc.1
0x767cc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x767d1  pop
0x767d2  ldloca.s 2
0x767d4  ldarg.1
0x767d5  ldarg.2
0x767d6  ldloc.0
0x767d7  call     void Microsoft.Crm.BusinessEntities.SecurityFilterPopulatorBase::CheckForHSMAndAppendClauseToGetChildUserPrincipals(class [mscorlib]System.Text.StringBuilder& s, class Microsoft.Crm.BusinessEntities.SecurityTraits traits, bool noLock, string systemUserIdParameterName)
0x767dc  ldloc.2
0x767dd  ldstr    aAnd0Objecttype_0// " and {0}.ObjectTypeCode = @ObjectTypeCo"...
0x767e2  ldloc.1
0x767e3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x767e8  pop
0x767e9  ldarg.s  4
0x767eb  brfalse.s loc_767F9
0x767ed  ldloc.2
0x767ee  ldstr    asc_CC192// ")"
0x767f3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x767f8  pop
0x767f9  dup
0x767fa  ldloc.2
0x767fb  callvirt instance string [mscorlib]System.Object::ToString()
0x76800  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x76805  ret
```
