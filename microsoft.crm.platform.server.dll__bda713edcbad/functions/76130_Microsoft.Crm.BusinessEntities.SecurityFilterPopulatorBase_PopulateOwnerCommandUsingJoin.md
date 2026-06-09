# Microsoft.Crm.BusinessEntities.SecurityFilterPopulatorBase::PopulateOwnerCommandUsingJoin

- ea: `0x76130`
- end: `0x76231`
- name: `Microsoft.Crm.BusinessEntities.SecurityFilterPopulatorBase::PopulateOwnerCommandUsingJoin`
- size: `257`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x76bd0`
- `0x76f80`
- `0x771f0`

## callees

- `0x76130`
- `0x76240`
- `0x763d0`
- `0x76810`
- `0x768d0`
- `0x76930`
- `0x77540`
- `0x77580`

## string_xrefs

- `0x76151`: `@UserIdOwnerCommand`
- `0x76171`: `@OtcOwnerCommand`

## pseudocode

```c

```

## disassembly

```asm
0x76130  ldstr    aPem// "pem"
0x76135  ldc.i4.1
0x76136  ldarg.s  6
0x76138  call     string Microsoft.Crm.BusinessEntities.SecurityFilterPopulatorBase::SecurityQueryBucket(valuetype SecurityTypeAttribute securityTypeAttribute, class Microsoft.Crm.Query.EntitySecurityPOAattributes entitySecurityPOAattributes)
0x7613d  call     string [mscorlib]System.String::Concat(string, string)
0x76142  stloc.0
0x76143  ldarg.s  5
0x76145  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x7614a  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x7614f  ldarg.s  5
0x76151  ldstr    aUseridownercom// "@UserIdOwnerCommand"
0x76156  call     string Microsoft.Crm.BusinessEntities.SecurityFilterPopulatorBase::CreateUniqueParameterName(class [System.Data]System.Data.IDbCommand ownerCommand, string parameterNamePrefix)
0x7615b  stloc.1
0x7615c  dup
0x7615d  ldloc.1
0x7615e  ldarg.0
0x7615f  box      [mscorlib]System.Guid
0x76164  call     object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ConvertHelper::ToSqlParameter(object)
0x76169  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x7616e  pop
0x7616f  ldarg.s  5
0x76171  ldstr    aOtcownercomman// "@OtcOwnerCommand"
0x76176  call     string Microsoft.Crm.BusinessEntities.SecurityFilterPopulatorBase::CreateUniqueParameterName(class [System.Data]System.Data.IDbCommand ownerCommand, string parameterNamePrefix)
0x7617b  stloc.2
0x7617c  ldloc.2
0x7617d  ldarg.1
0x7617e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.BusinessEntities.SecurityTraits::get_Metadata()
0x76183  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x76188  box      [mscorlib]System.Int32
0x7618d  call     object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ConvertHelper::ToSqlParameter(object)
0x76192  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x76197  pop
0x76198  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x7619d  stloc.3
0x7619e  ldarg.3
0x7619f  brfalse.s loc_761DA
0x761a1  ldarg.s  4
0x761a3  brfalse.s loc_761DA
0x761a5  ldloc.3
0x761a6  ldstr    aSelectPrincipa_0// "(select PrincipalId from SystemUserPrin"...
0x761ab  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x761b0  pop
0x761b1  ldloc.3
0x761b2  ldarg.2
0x761b3  call     void Microsoft.Crm.BusinessEntities.SecurityFilterPopulatorBase::AddNoLock(class [mscorlib]System.Text.StringBuilder s, bool noLock)
0x761b8  ldloc.3
0x761b9  ldstr    aWhereSupSystem// "where sup.SystemUserId = "
0x761be  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x761c3  pop
0x761c4  ldloc.3
0x761c5  ldloc.1
0x761c6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x761cb  pop
0x761cc  ldloc.3
0x761cd  ldstr    asc_CC192// ")"
0x761d2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x761d7  pop
0x761d8  br.s     loc_76218
0x761da  ldloc.3
0x761db  ldstr    asc_CC172// "("
0x761e0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x761e5  pop
0x761e6  ldarg.2
0x761e7  ldloc.1
0x761e8  ldloc.2
0x761e9  ldloc.3
0x761ea  ldloc.0
0x761eb  call     void Microsoft.Crm.BusinessEntities.SecurityFilterPopulatorBase::AppendOwnershipClauseForParentUser(bool noLock, string systemUserIdParameterName, string objectTypeCodeParameterName, class [mscorlib]System.Text.StringBuilder s, string pemAlias)
0x761f0  ldarg.1
0x761f1  callvirt instance bool Microsoft.Crm.BusinessEntities.SecurityTraits::get_UseHierarchicalSecurity()
0x761f6  brfalse.s loc_7620C
0x761f8  ldloc.3
0x761f9  ldstr    aUnion_2// " UNION "
0x761fe  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x76203  pop
0x76204  ldarg.2
0x76205  ldloc.1
0x76206  ldloc.3
0x76207  call     void Microsoft.Crm.BusinessEntities.SecurityFilterPopulatorBase::AppendClauseToGetChildUserAndTeamPrincipalsForHSM(bool noLock, string systemUserIdParameterName, class [mscorlib]System.Text.StringBuilder s)
0x7620c  ldloc.3
0x7620d  ldstr    asc_CC192// ")"
0x76212  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x76217  pop
0x76218  ldarg.s  5
0x7621a  dup
0x7621b  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x76220  ldloc.3
0x76221  callvirt instance string [mscorlib]System.Object::ToString()
0x76226  call     string [mscorlib]System.String::Concat(string, string)
0x7622b  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x76230  ret
```
