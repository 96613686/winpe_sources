# Microsoft.Crm.BusinessEntities.SecurityFilterPopulatorBase::CreatePOACommandUsingTempTableForHSM

- ea: `0x76830`
- end: `0x768c3`
- name: `Microsoft.Crm.BusinessEntities.SecurityFilterPopulatorBase::CreatePOACommandUsingTempTableForHSM`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x75790`

## callees

- `0x768d0`
- `0x77580`

## string_xrefs

- `0x76880`: ` join PrincipalObjectAccess POA `
- `0x7689f`: ` where POA.ObjectTypeCode = @ObjectTypeCode and (POA.AccessRightsMask&1=1 or POA.InheritedAccessRightsMask&1=1)`

## pseudocode

```c

```

## disassembly

```asm
0x76830  ldarg.1
0x76831  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::get_Connection()
0x76836  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x7683b  dup
0x7683c  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x76841  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x76846  ldstr    aObjecttypecode_86// "@ObjectTypeCode"
0x7684b  ldarg.2
0x7684c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.BusinessEntities.SecurityTraits::get_Metadata()
0x76851  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x76856  box      [mscorlib]System.Int32
0x7685b  call     object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ConvertHelper::ToSqlParameter(object)
0x76860  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x76865  pop
0x76866  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x7686b  stloc.0
0x7686c  ldloc.0
0x7686d  ldstr    aSelectDistinct_0// "(select distinct POA.ObjectId from #Pri"...
0x76872  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x76877  pop
0x76878  ldloc.0
0x76879  ldarg.0
0x7687a  call     void Microsoft.Crm.BusinessEntities.SecurityFilterPopulatorBase::AddNoLock(class [mscorlib]System.Text.StringBuilder s, bool noLock)
0x7687f  ldloc.0
0x76880  ldstr    aJoinPrincipalo// " join PrincipalObjectAccess POA "
0x76885  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x7688a  pop
0x7688b  ldloc.0
0x7688c  ldarg.0
0x7688d  call     void Microsoft.Crm.BusinessEntities.SecurityFilterPopulatorBase::AddNoLock(class [mscorlib]System.Text.StringBuilder s, bool noLock)
0x76892  ldloc.0
0x76893  ldstr    aOnPoaPrincipal// "on POA.PrincipalId = pids.PrincipalId "
0x76898  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x7689d  pop
0x7689e  ldloc.0
0x7689f  ldstr    aWherePoaObject// " where POA.ObjectTypeCode = @ObjectType"...
0x768a4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x768a9  pop
0x768aa  ldloc.0
0x768ab  ldstr    asc_CC192// ")"
0x768b0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x768b5  pop
0x768b6  dup
0x768b7  ldloc.0
0x768b8  callvirt instance string [mscorlib]System.Object::ToString()
0x768bd  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x768c2  ret
```
