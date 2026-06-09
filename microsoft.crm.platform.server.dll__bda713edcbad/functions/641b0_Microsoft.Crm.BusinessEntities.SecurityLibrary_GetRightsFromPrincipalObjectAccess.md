# Microsoft.Crm.BusinessEntities.SecurityLibrary::GetRightsFromPrincipalObjectAccess

- ea: `0x641b0`
- end: `0x642c2`
- name: `Microsoft.Crm.BusinessEntities.SecurityLibrary::GetRightsFromPrincipalObjectAccess`
- size: `274`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x64970`

## callees

- `0x5d600`
- `0x641b0`
- `0x642d0`
- `0x66b00`
- `0x67920`

## string_xrefs

- `0x641e5`: `SecurityQueryHint`
- `0x64219`: `select MAX((POA.AccessRightsMask|POA.InheritedAccessRightsMask) & 0x00000001) + MAX((POA.AccessRightsMask|POA.InheritedAccessRightsMask) & 0x00000002) + MAX((POA.AccessRightsMask|POA.InheritedAccessRightsMask) & 0x00010000) + MAX((POA.AccessRightsMask|POA.InheritedAccessRightsMask) & 0x00000004) + MAX((POA.AccessRightsMask|POA.InheritedAccessRightsMask) & 0x00080000) + MAX((POA.AccessRightsMask|POA.InheritedAccessRightsMask) & 0x00040000) + MAX((POA.AccessRightsMask|POA.InheritedAccessRightsMask`
- `0x64298`: `Error when retrieving principal access: {0} Exception: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x641b0  ldarg.0
0x641b1  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x641b6  ldarg.3
0x641b7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x641bc  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsActivity()
0x641c1  brfalse.s loc_641CA
0x641c3  ldc.i4   0x1068
0x641c8  starg.s  3
0x641ca  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x641cf  ldarg.0
0x641d0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x641d5  ldarg.0
0x641d6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x641db  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x641e0  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x641e5  ldstr    aSecurityqueryh// "SecurityQueryHint"
0x641ea  ldc.i4.1
0x641eb  box      [mscorlib]System.Int32
0x641f0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::GetOrgDBOrgSetting(string, object)
0x641f5  unbox.any [mscorlib]System.Int32
0x641fa  stloc.0
0x641fb  ldnull
0x641fc  stloc.1
0x641fd  ldnull
0x641fe  stloc.2
0x641ff  ldarg.0
0x64200  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x64205  stloc.2
0x64206  ldloc.2
0x64207  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x6420c  ldarg.0
0x6420d  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.BusinessEntities.ExecutionContext::CreateCommand()
0x64212  stloc.1
0x64213  ldloc.1
0x64214  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x64219  ldstr    aSelectMaxPoaAc// "select MAX((POA.AccessRightsMask|POA.In"...
0x6421e  ldc.i4.1
0x6421f  newarr   [mscorlib]System.Object
0x64224  dup
0x64225  ldc.i4.0
0x64226  ldloc.0
0x64227  call     string Microsoft.Crm.BusinessEntities.SecurityLibrary::GetQueryHintClause(valuetype Microsoft.Crm.BusinessEntities.SecurityQueryHint queryHint)
0x6422c  stelem.ref
0x6422d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x64232  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x64237  ldloc.1
0x64238  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x6423d  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x64242  dup
0x64243  ldstr    aObjectid_3// "@ObjectId"
0x64248  ldarg.2
0x64249  box      [mscorlib]System.Guid
0x6424e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x64253  pop
0x64254  dup
0x64255  ldstr    aPrincipalid_1// "@PrincipalId"
0x6425a  ldarg.1
0x6425b  box      [mscorlib]System.Guid
0x64260  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x64265  pop
0x64266  ldstr    aObjecttypecode_86// "@ObjectTypeCode"
0x6426b  ldarg.3
0x6426c  box      [mscorlib]System.Int32
0x64271  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x64276  pop
0x64277  ldloc.2
0x64278  ldloc.1
0x64279  ldarg.0
0x6427a  call     object Microsoft.Crm.BusinessEntities.BusinessProcessObject::ExecuteScalar(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection dbConnection, class [System.Data]System.Data.IDbCommand command, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x6427f  stloc.3
0x64280  ldloc.3
0x64281  brfalse.s loc_6428D
0x64283  ldloc.3
0x64284  unbox.any [mscorlib]System.Int32
0x64289  stloc.s  4
0x6428b  leave.s  loc_642BF
0x6428d  leave.s  loc_642BD
0x6428f  stloc.s  5
0x64291  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x64296  ldc.i4.s 0x1D
0x64298  ldstr    aErrorWhenRetri// "Error when retrieving principal access:"...
0x6429d  ldc.i4.2
0x6429e  newarr   [mscorlib]System.Object
0x642a3  dup
0x642a4  ldc.i4.0
0x642a5  ldloc.1
0x642a6  stelem.ref
0x642a7  dup
0x642a8  ldc.i4.1
0x642a9  ldloc.s  5
0x642ab  stelem.ref
0x642ac  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x642b1  leave.s  loc_642BD
0x642b3  ldloc.2
0x642b4  brfalse.s loc_642BC
0x642b6  ldloc.2
0x642b7  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Close()
0x642bc  endfinally
0x642bd  ldc.i4.0
0x642be  ret
0x642bf  ldloc.s  4
0x642c1  ret
```
