# Microsoft.Crm.BusinessEntities.SecurityFilterPopulatorBase::CreatePOACommandForSmallCount

- ea: `0x76980`
- end: `0x76a63`
- name: `Microsoft.Crm.BusinessEntities.SecurityFilterPopulatorBase::CreatePOACommandForSmallCount`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x764e0`

## callees

- `0x76470`
- `0x76980`
- `0x77540`
- `0x77580`

## string_xrefs

- `0x769d4`: `select ObjectId from fn_POARetrieveMultiple(@SystemUserId, @ObjectTypeCode,@isHierarchicalSecurityModelEnabled)`
- `0x76a47`: `@isHierarchicalSecurityModelEnabled`

## pseudocode

```c

```

## disassembly

```asm
0x76980  ldarg.2
0x76981  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::get_Connection()
0x76986  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x7698b  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x76990  stloc.0
0x76991  ldarg.3
0x76992  brfalse.s loc_769A0
0x76994  ldloc.0
0x76995  ldstr    asc_CC172// "("
0x7699a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x7699f  pop
0x769a0  ldarg.2
0x769a1  isinst   [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext
0x769a6  stloc.1
0x769a7  ldloc.1
0x769a8  call     bool Microsoft.Crm.BusinessEntities.SecurityFilterPopulatorBase::Isfn_POARetrieveMultipleHierarchyAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext context)
0x769ad  brfalse.s loc_769D3
0x769af  ldarg.1
0x769b0  callvirt instance bool Microsoft.Crm.BusinessEntities.SecurityTraits::get_UseHierarchicalSecurity()
0x769b5  brfalse.s loc_769C5
0x769b7  ldloc.0
0x769b8  ldstr    aSelectObjectid_0// "select ObjectId from fn_POARetrieveMult"...
0x769bd  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x769c2  pop
0x769c3  br.s     loc_769DF
0x769c5  ldloc.0
0x769c6  ldstr    aSelectObjectid_1// "select ObjectId from fn_POARetrieveMult"...
0x769cb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x769d0  pop
0x769d1  br.s     loc_769DF
0x769d3  ldloc.0
0x769d4  ldstr    aSelectObjectid_2// "select ObjectId from fn_POARetrieveMult"...
0x769d9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x769de  pop
0x769df  ldarg.3
0x769e0  brfalse.s loc_769EE
0x769e2  ldloc.0
0x769e3  ldstr    asc_CC192// ")"
0x769e8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x769ed  pop
0x769ee  dup
0x769ef  ldloc.0
0x769f0  callvirt instance string [mscorlib]System.Object::ToString()
0x769f5  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x769fa  dup
0x769fb  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x76a00  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x76a05  stloc.2
0x76a06  ldloc.2
0x76a07  ldstr    aSystemuserid// "@SystemUserId"
0x76a0c  ldarg.0
0x76a0d  box      [mscorlib]System.Guid
0x76a12  call     object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ConvertHelper::ToSqlParameter(object)
0x76a17  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x76a1c  pop
0x76a1d  ldloc.2
0x76a1e  ldstr    aObjecttypecode_86// "@ObjectTypeCode"
0x76a23  ldarg.1
0x76a24  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.BusinessEntities.SecurityTraits::get_Metadata()
0x76a29  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x76a2e  box      [mscorlib]System.Int32
0x76a33  call     object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ConvertHelper::ToSqlParameter(object)
0x76a38  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x76a3d  pop
0x76a3e  ldloc.1
0x76a3f  call     bool Microsoft.Crm.BusinessEntities.SecurityFilterPopulatorBase::Isfn_POARetrieveMultipleHierarchyAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext context)
0x76a44  brtrue.s loc_76A62
0x76a46  ldloc.2
0x76a47  ldstr    aIshierarchical_0// "@isHierarchicalSecurityModelEnabled"
0x76a4c  ldarg.1
0x76a4d  callvirt instance bool Microsoft.Crm.BusinessEntities.SecurityTraits::get_UseHierarchicalSecurity()
0x76a52  box      [mscorlib]System.Boolean
0x76a57  call     object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ConvertHelper::ToSqlParameter(object)
0x76a5c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x76a61  pop
0x76a62  ret
```
