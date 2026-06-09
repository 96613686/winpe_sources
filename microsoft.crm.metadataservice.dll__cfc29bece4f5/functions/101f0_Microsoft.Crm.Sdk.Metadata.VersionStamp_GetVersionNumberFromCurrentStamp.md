# Microsoft.Crm.Sdk.Metadata.VersionStamp::GetVersionNumberFromCurrentStamp

- ea: `0x101f0`
- end: `0x1030e`
- name: `Microsoft.Crm.Sdk.Metadata.VersionStamp::GetVersionNumberFromCurrentStamp`
- size: `286`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x10130`

## callees

- `0x101e0`
- `0x101f0`

## string_xrefs

- `0x1028a`: `SELECT MetadataSyncLastTimeOfNeverExpiredDeletedObjects FROM OrganizationBase WITH (NOLOCK)`
- `0x1029f`: `D:\a\1\s\src\Core\ObjectModel\Metadata\MetadataService\SDK\VersionStamp.cs`

## pseudocode

```c

```

## disassembly

```asm
0x101f0  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x101f5  stloc.1
0x101f6  ldarg.0
0x101f7  ldfld    string Microsoft.Crm.Sdk.Metadata.VersionStamp::_current
0x101fc  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x10201  brfalse.s loc_1020D
0x10203  ldc.i8   0x8000000000000000
0x1020c  ret
0x1020d  ldc.i4.1
0x1020e  stloc.2
0x1020f  ldarg.0
0x10210  ldfld    string Microsoft.Crm.Sdk.Metadata.VersionStamp::_current
0x10215  ldc.i4.1
0x10216  newarr   [mscorlib]System.Char
0x1021b  dup
0x1021c  ldc.i4.0
0x1021d  ldc.i4.s 0x21
0x1021f  stelem.i2
0x10220  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x10225  stloc.3
0x10226  ldloc.3
0x10227  ldc.i4.0
0x10228  ldelem.ref
0x10229  ldc.i4.0
0x1022a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1022f  ldloca.s 0
0x10231  call     bool [mscorlib]System.Int64::TryParse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider, int64&)
0x10236  brtrue.s loc_1023C
0x10238  ldc.i4.0
0x10239  stloc.2
0x1023a  br.s     loc_10257
0x1023c  ldloc.3
0x1023d  ldlen
0x1023e  conv.i4
0x1023f  ldc.i4.2
0x10240  bne.un.s loc_10255
0x10242  ldloc.3
0x10243  ldc.i4.1
0x10244  ldelem.ref
0x10245  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1024a  ldc.i4.s 0x40
0x1024c  ldloca.s 1
0x1024e  call     bool [mscorlib]System.DateTime::TryParse(string, class [mscorlib]System.IFormatProvider, valuetype [mscorlib]System.Globalization.DateTimeStyles, valuetype [mscorlib]System.DateTime&)
0x10253  brtrue.s loc_10257
0x10255  ldc.i4.0
0x10256  stloc.2
0x10257  ldloc.2
0x10258  brtrue.s loc_10265
0x1025a  ldstr    aUnableToParseT// "Unable to parse the version stamp"
0x1025f  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x10264  throw
0x10265  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x1026a  ldarg.1
0x1026b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x10270  ldarg.1
0x10271  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x10276  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_DeletedMetadataExpiryInDays()
0x1027b  stloc.s  4
0x1027d  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x10282  stloc.s  5
0x10284  ldarg.1
0x10285  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::get_Connection()
0x1028a  ldstr    aSelectMetadata// "SELECT MetadataSyncLastTimeOfNeverExpir"...
0x1028f  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x10294  stloc.s  6
0x10296  ldloc.s  6
0x10298  ldc.i4.s 0x47
0x1029a  ldstr    aGetversionnumb// "GetVersionNumberFromCurrentStamp"
0x1029f  ldstr    aDA1SSrcCoreObj_2// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Me"...
0x102a4  call     object [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteScalar(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x102a9  stloc.s  7
0x102ab  ldloc.s  7
0x102ad  isinst   [mscorlib]System.DBNull
0x102b2  brtrue.s loc_102D1
0x102b4  ldloc.s  7
0x102b6  isinst   [mscorlib]System.DateTime
0x102bb  ldnull
0x102bc  cgt.un
0x102be  ldstr    aUnexpectedValu// "Unexpected value from database"
0x102c3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x102c8  ldloc.s  7
0x102ca  unbox.any [mscorlib]System.DateTime
0x102cf  stloc.s  5
0x102d1  leave.s  loc_102DF
0x102d3  ldloc.s  6
0x102d5  brfalse.s loc_102DE
0x102d7  ldloc.s  6
0x102d9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x102de  endfinally
0x102df  ldloc.s  4
0x102e1  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x102e6  stloc.s  8
0x102e8  ldloca.s 8
0x102ea  ldloc.1
0x102eb  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::Subtract(valuetype [mscorlib]System.DateTime)
0x102f0  stloc.s  9
0x102f2  ldloca.s 9
0x102f4  call     instance int32 [mscorlib]System.TimeSpan::get_Days()
0x102f9  blt.s    loc_10305
0x102fb  ldloc.s  5
0x102fd  ldloc.1
0x102fe  call     bool [mscorlib]System.DateTime::op_GreaterThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x10303  brfalse.s loc_1030C
0x10305  ldarg.0
0x10306  ldc.i4.1
0x10307  call     instance void Microsoft.Crm.Sdk.Metadata.VersionStamp::set_HasExpired(bool value)
0x1030c  ldloc.0
0x1030d  ret
```
