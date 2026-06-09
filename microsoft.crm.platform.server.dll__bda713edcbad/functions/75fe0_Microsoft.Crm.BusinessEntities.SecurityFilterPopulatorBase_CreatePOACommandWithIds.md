# Microsoft.Crm.BusinessEntities.SecurityFilterPopulatorBase::CreatePOACommandWithIds

- ea: `0x75fe0`
- end: `0x76083`
- name: `Microsoft.Crm.BusinessEntities.SecurityFilterPopulatorBase::CreatePOACommandWithIds`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x76d40`

## callees

- `0x76090`
- `0x768d0`
- `0x77580`

## string_xrefs

- `0x75fff`: `select POA.ObjectId from PrincipalObjectAccess POA `
- `0x76017`: `where POA.PrincipalId in ({0}) and POA.ObjectTypeCode = @ObjectTypeCode and ((POA.AccessRightsMask|POA.InheritedAccessRightsMask) & 1) = 1`

## pseudocode

```c

```

## disassembly

```asm
0x75fe0  ldarg.3
0x75fe1  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::get_Connection()
0x75fe6  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x75feb  stloc.0
0x75fec  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x75ff1  stloc.1
0x75ff2  ldloc.1
0x75ff3  ldstr    asc_CC172// "("
0x75ff8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x75ffd  pop
0x75ffe  ldloc.1
0x75fff  ldstr    aSelectPoaObjec// "select POA.ObjectId from PrincipalObjec"...
0x76004  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x76009  pop
0x7600a  ldloc.1
0x7600b  ldarg.2
0x7600c  call     void Microsoft.Crm.BusinessEntities.SecurityFilterPopulatorBase::AddNoLock(class [mscorlib]System.Text.StringBuilder s, bool noLock)
0x76011  ldloc.1
0x76012  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x76017  ldstr    aWherePoaPrinci// "where POA.PrincipalId in ({0}) and POA."...
0x7601c  ldc.i4.1
0x7601d  newarr   [mscorlib]System.Object
0x76022  dup
0x76023  ldc.i4.0
0x76024  ldarg.0
0x76025  ldarg.1
0x76026  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.BusinessEntities.SecurityTraits::get_Metadata()
0x7602b  ldloc.0
0x7602c  ldarg.3
0x7602d  call     string Microsoft.Crm.BusinessEntities.SecurityFilterPopulatorBase::BuildPrincipalIdsList(valuetype [mscorlib]System.Guid user, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata, class [System.Data]System.Data.IDbCommand command, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x76032  stelem.ref
0x76033  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x76038  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x7603d  pop
0x7603e  ldloc.1
0x7603f  ldstr    asc_CC192// ")"
0x76044  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x76049  pop
0x7604a  ldloc.0
0x7604b  ldloc.1
0x7604c  callvirt instance string [mscorlib]System.Object::ToString()
0x76051  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x76056  ldloc.0
0x76057  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x7605c  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x76061  ldstr    aObjecttypecode_86// "@ObjectTypeCode"
0x76066  ldarg.1
0x76067  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.BusinessEntities.SecurityTraits::get_Metadata()
0x7606c  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x76071  box      [mscorlib]System.Int32
0x76076  call     object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ConvertHelper::ToSqlParameter(object)
0x7607b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x76080  pop
0x76081  ldloc.0
0x76082  ret
```
