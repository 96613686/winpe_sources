# Microsoft.Crm.Tools.Admin.OrganizationOperation::UpdateOrganizationDatabaseState

- ea: `0x9e90`
- end: `0x9f10`
- name: `Microsoft.Crm.Tools.Admin.OrganizationOperation::UpdateOrganizationDatabaseState`
- size: `128`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0xa460`
- `0x10e40`

## callees

- `0x9e90`

## string_xrefs

- `0x9e95`: `IF EXISTS (SELECT 1 FROM sys.columns WHERE name = 'OrganizationState' and object_id = OBJECT_ID('OrganizationBase', 'U'))\n					EXEC('UPDATE OrganizationBase SET OrganizationState = {0}')`
- `0x9ed1`: `UpdateOrganizationDatabaseState`

## pseudocode

```c

```

## disassembly

```asm
0x9e90  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9e95  ldstr    aIfExistsSelect// "IF EXISTS (SELECT 1 FROM sys.columns WH"...
0x9e9a  ldc.i4.1
0x9e9b  newarr   [mscorlib]System.Object
0x9ea0  dup
0x9ea1  ldc.i4.0
0x9ea2  ldarg.1
0x9ea3  box      [mscorlib]System.Int32
0x9ea8  stelem.ref
0x9ea9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9eae  stloc.0
0x9eaf  ldarg.0
0x9eb0  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::GetInstallConnectionTimeout()
0x9eb5  ldc.i4.0
0x9eb6  ldc.i4.0
0x9eb7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, int32, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x9ebc  stloc.1
0x9ebd  ldloc.1
0x9ebe  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x9ec3  ldloc.1
0x9ec4  ldloc.0
0x9ec5  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x9eca  stloc.2
0x9ecb  ldloc.2
0x9ecc  ldc.i4   0x260
0x9ed1  ldstr    aUpdateorganiza// "UpdateOrganizationDatabaseState"
0x9ed6  ldstr    aDDbsShDccm2110_6// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\4"...
0x9edb  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x9ee0  pop
0x9ee1  leave.s  loc_9EED
0x9ee3  ldloc.2
0x9ee4  brfalse.s loc_9EEC
0x9ee6  ldloc.2
0x9ee7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9eec  endfinally
0x9eed  ldloc.1
0x9eee  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Close()
0x9ef3  leave.s  loc_9EFF
0x9ef5  ldloc.1
0x9ef6  brfalse.s loc_9EFE
0x9ef8  ldloc.1
0x9ef9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9efe  endfinally
0x9eff  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x9f04  ldarg.0
0x9f05  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x9f0a  callvirt instance void class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::Flush(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9f0f  ret
```
