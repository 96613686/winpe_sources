# Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::UpdateSiteMapXmlInSiteMapBase

- ea: `0x1f390`
- end: `0x1f44d`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::UpdateSiteMapXmlInSiteMapBase`
- size: `189`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1f390`

## string_xrefs

- `0x1f39c`: `updates`
- `0x1f3c6`: `update SiteMapBase set SiteMapXml = @updatedValue where SiteMapIdUnique = @uniqueId`
- `0x1f3e2`: `updatedValue`

## pseudocode

```c

```

## disassembly

```asm
0x1f390  ldarg.1
0x1f391  ldstr    aOrganizationid// "organizationId"
0x1f396  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x1f39b  ldarg.2
0x1f39c  ldstr    aUpdates// "updates"
0x1f3a1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1f3a6  ldarg.1
0x1f3a7  ldc.i4.0
0x1f3a8  ldc.i4.0
0x1f3a9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x1f3ae  stloc.0
0x1f3af  ldloc.0
0x1f3b0  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x1f3b5  ldarg.2
0x1f3b6  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string>::GetEnumerator()
0x1f3bb  stloc.1
0x1f3bc  br.s     loc_1F421
0x1f3be  ldloca.s 1
0x1f3c0  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, string>::get_Current()
0x1f3c5  stloc.2
0x1f3c6  ldstr    aUpdateSitemapb// "update SiteMapBase set SiteMapXml = @up"...
0x1f3cb  stloc.3
0x1f3cc  ldloc.0
0x1f3cd  ldloc.3
0x1f3ce  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x1f3d3  stloc.s  4
0x1f3d5  ldloc.s  4
0x1f3d7  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x1f3dc  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x1f3e1  dup
0x1f3e2  ldstr    aUpdatedvalue// "updatedValue"
0x1f3e7  ldloca.s 2
0x1f3e9  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, string>::get_Value()
0x1f3ee  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1f3f3  pop
0x1f3f4  ldstr    aUniqueid// "uniqueId"
0x1f3f9  ldloca.s 2
0x1f3fb  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, string>::get_Key()
0x1f400  box      [mscorlib]System.Guid
0x1f405  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1f40a  pop
0x1f40b  ldloc.s  4
0x1f40d  callvirt instance int32 [System.Data]System.Data.IDbCommand::ExecuteNonQuery()
0x1f412  pop
0x1f413  leave.s  loc_1F421
0x1f415  ldloc.s  4
0x1f417  brfalse.s loc_1F420
0x1f419  ldloc.s  4
0x1f41b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f420  endfinally
0x1f421  ldloca.s 1
0x1f423  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, string>::MoveNext()
0x1f428  brtrue.s loc_1F3BE
0x1f42a  leave.s  loc_1F43A
0x1f42c  ldloca.s 1
0x1f42e  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, string>
0x1f434  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f439  endfinally
0x1f43a  ldloc.0
0x1f43b  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Close()
0x1f440  leave.s  loc_1F44C
0x1f442  ldloc.0
0x1f443  brfalse.s loc_1F44B
0x1f445  ldloc.0
0x1f446  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f44b  endfinally
0x1f44c  ret
```
