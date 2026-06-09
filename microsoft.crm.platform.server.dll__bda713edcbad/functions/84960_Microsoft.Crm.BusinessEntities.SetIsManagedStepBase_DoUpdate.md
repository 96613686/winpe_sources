# Microsoft.Crm.BusinessEntities.SetIsManagedStepBase::DoUpdate

- ea: `0x84960`
- end: `0x84a23`
- name: `Microsoft.Crm.BusinessEntities.SetIsManagedStepBase::DoUpdate`
- size: `195`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x84a50`
- `0x84ab0`

## callees

- `0x66ae0`
- `0x84960`

## string_xrefs

- `0x849c7`: `DoUpdate`
- `0x849f2`: `Updated {0} table, setting IsManaged to true for all system entitites.  Count = {1}`

## pseudocode

```c

```

## disassembly

```asm
0x84960  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x84965  ldarg.1
0x84966  ldc.i4.2
0x84967  newarr   [mscorlib]System.Object
0x8496c  dup
0x8496d  ldc.i4.0
0x8496e  ldarg.2
0x8496f  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0x84974  stelem.ref
0x84975  dup
0x84976  ldc.i4.1
0x84977  ldarg.3
0x84978  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0x8497d  stelem.ref
0x8497e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x84983  stloc.0
0x84984  ldarg.s  5
0x84986  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x8498b  ldloc.0
0x8498c  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::CreateSqlCommand(string)
0x84991  stloc.1
0x84992  ldloc.1
0x84993  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x84998  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x8499d  dup
0x8499e  ldstr    aValue// "@value"
0x849a3  ldc.i4.1
0x849a4  box      [mscorlib]System.Boolean
0x849a9  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x849ae  pop
0x849af  ldstr    aSystemsolution// "@systemSolutionId"
0x849b4  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::SystemSolutionId
0x849b9  box      [mscorlib]System.Guid
0x849be  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x849c3  pop
0x849c4  ldloc.1
0x849c5  ldc.i4.s 0x41
0x849c7  ldstr    aDoupdate// "DoUpdate"
0x849cc  ldstr    aDA1SSrcManaged_20// "D:\\a\\1\\s\\src\\ManagedPlatform\\Serv"...
0x849d1  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x849d6  stloc.2
0x849d7  ldarg.s  5
0x849d9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x849de  ldc.i4.s 0x19
0x849e0  ldstr    a0// "{0}"
0x849e5  ldc.i4.1
0x849e6  newarr   [mscorlib]System.Object
0x849eb  dup
0x849ec  ldc.i4.0
0x849ed  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x849f2  ldstr    aUpdated0TableS// "Updated {0} table, setting IsManaged to"...
0x849f7  ldc.i4.2
0x849f8  newarr   [mscorlib]System.Object
0x849fd  dup
0x849fe  ldc.i4.0
0x849ff  ldarg.s  4
0x84a01  stelem.ref
0x84a02  dup
0x84a03  ldc.i4.1
0x84a04  ldloc.2
0x84a05  box      [mscorlib]System.Int32
0x84a0a  stelem.ref
0x84a0b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x84a10  stelem.ref
0x84a11  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x84a16  leave.s  loc_84A22
0x84a18  ldloc.1
0x84a19  brfalse.s loc_84A21
0x84a1b  ldloc.1
0x84a1c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x84a21  endfinally
0x84a22  ret
```
