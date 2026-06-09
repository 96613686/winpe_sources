# Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::IsMarketingAppInstalled

- ea: `0x1f830`
- end: `0x1f8a6`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::IsMarketingAppInstalled`
- size: `118`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1f830`

## string_xrefs

- `0x1f83f`: `IF EXISTS (SELECT TOP 1 EntityId  FROM [MetadataSchema].[Entity] e  WHERE e.Name = 'msdyncrm_marketingconfiguration')\n									BEGIN;\n										IF EXISTS (SELECT msdyncrm_IsInstallComplete FROM dbo.msdyncrm_marketingconfiguration WHERE msdyncrm_default=1)\n										BEGIN;\n											SELECT msdyncrm_IsInstallComplete FROM dbo.msdyncrm_marketingconfiguration WHERE msdyncrm_default=1;\n										END;\n										ELSE\n										BEGIN;\n											SELECT 'False';\n										END;\n						`
- `0x1f884`: `Could not retrieve msdyncrm_isinstallcomplete status from dbo.msdyncrm_marketingconfiguration. {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1f830  ldarg.1
0x1f831  ldc.i4.0
0x1f832  ldc.i4.0
0x1f833  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x1f838  stloc.0
0x1f839  ldloc.0
0x1f83a  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x1f83f  ldstr    aIfExistsSelect_0// "IF EXISTS (SELECT TOP 1 EntityId  FROM "...
0x1f844  stloc.1
0x1f845  ldloc.0
0x1f846  ldloc.1
0x1f847  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x1f84c  stloc.2
0x1f84d  ldloc.2
0x1f84e  callvirt instance object [System.Data]System.Data.IDbCommand::ExecuteScalar()
0x1f853  callvirt instance string [mscorlib]System.Object::ToString()
0x1f858  ldc.i4.0
0x1f859  stloc.3
0x1f85a  ldloca.s 3
0x1f85c  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x1f861  brtrue.s loc_1F865
0x1f863  ldc.i4.0
0x1f864  stloc.3
0x1f865  ldloc.3
0x1f866  stloc.s  4
0x1f868  leave.s  loc_1F8A3
0x1f86a  ldloc.2
0x1f86b  brfalse.s loc_1F873
0x1f86d  ldloc.2
0x1f86e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f873  endfinally
0x1f874  ldloc.0
0x1f875  brfalse.s loc_1F87D
0x1f877  ldloc.0
0x1f878  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f87d  endfinally
0x1f87e  stloc.s  5
0x1f880  ldnull
0x1f881  ldarg.1
0x1f882  ldc.i4.s 0xA
0x1f884  ldstr    aCouldNotRetrie_0// "Could not retrieve msdyncrm_isinstallco"...
0x1f889  ldc.i4.1
0x1f88a  newarr   [mscorlib]System.Object
0x1f88f  dup
0x1f890  ldc.i4.0
0x1f891  ldloc.s  5
0x1f893  callvirt instance string [mscorlib]System.Object::ToString()
0x1f898  stelem.ref
0x1f899  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1f89e  ldc.i4.0
0x1f89f  stloc.s  4
0x1f8a1  leave.s  loc_1F8A3
0x1f8a3  ldloc.s  4
0x1f8a5  ret
```
