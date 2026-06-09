# Microsoft.Crm.OrganizationDatabaseUtility::UpdateRelaxedHardLimit

- ea: `0x164d0`
- end: `0x1656e`
- name: `Microsoft.Crm.OrganizationDatabaseUtility::UpdateRelaxedHardLimit`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x159c0`

## callees

- `0xd180`
- `0xd2f0`
- `0xd620`
- `0xdab0`
- `0x164d0`
- `0x165e0`
- `0x16750`
- `0x16810`

## string_xrefs

- `0x16533`: `D:\a\1\s\src\Platform\Core\DataServices\OrganizationDatabaseUtility.cs`
- `0x1652e`: `UpdateRelaxedHardLimit`

## pseudocode

```c

```

## disassembly

```asm
0x164d0  ldarg.0
0x164d1  call     instance string Microsoft.Crm.OrganizationDatabaseUtility::RetrieveDatabaseName()
0x164d6  stloc.0
0x164d7  ldarg.0
0x164d8  ldc.i4.0
0x164d9  call     instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.DatabaseFileInfo> Microsoft.Crm.OrganizationDatabaseUtility::GetDatabaseLogicalFileNames(bool dataFileOnly)
0x164de  stloc.1
0x164df  ldarg.0
0x164e0  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.OrganizationDatabaseUtility::_organizationId
0x164e5  ldloc.0
0x164e6  ldloc.1
0x164e7  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.Crm.OrganizationDatabaseUtility::RetrieveHardLimitSqlToExecute(valuetype [mscorlib]System.Guid organizationId, string databaseName, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.DatabaseFileInfo> databaseFiles)
0x164ec  stloc.2
0x164ed  ldloc.2
0x164ee  call     T0x2B00004B
0x164f3  brtrue.s loc_164F6
0x164f5  ret
0x164f6  ldarg.0
0x164f7  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.OrganizationDatabaseUtility::_organizationId
0x164fc  ldc.i4.0
0x164fd  ldc.i4.0
0x164fe  newobj   instance void Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid organizationId, [opt] bool isReader, [opt] valuetype Microsoft.Crm.ReadPriority priority)
0x16503  stloc.3
0x16504  ldloc.3
0x16505  callvirt instance void Microsoft.Crm.CrmDbConnection::Open()
0x1650a  ldloc.2
0x1650b  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x16510  stloc.s  4
0x16512  br.s     loc_1654C
0x16514  ldloc.s  4
0x16516  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x1651b  stloc.s  5
0x1651d  ldloc.3
0x1651e  ldloc.s  5
0x16520  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.CrmDbConnection::CreateCommand(string commandText)
0x16525  stloc.s  6
0x16527  ldloc.s  6
0x16529  ldc.i4   0x2DF
0x1652e  ldstr    aUpdaterelaxedh// "UpdateRelaxedHardLimit"
0x16533  ldstr    aDA1SSrcPlatfor_10// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x16538  call     int32 Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x1653d  pop
0x1653e  leave.s  loc_1654C
0x16540  ldloc.s  6
0x16542  brfalse.s loc_1654B
0x16544  ldloc.s  6
0x16546  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1654b  endfinally
0x1654c  ldloc.s  4
0x1654e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x16553  brtrue.s loc_16514
0x16555  leave.s  loc_1656D
0x16557  ldloc.s  4
0x16559  brfalse.s loc_16562
0x1655b  ldloc.s  4
0x1655d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x16562  endfinally
0x16563  ldloc.3
0x16564  brfalse.s loc_1656C
0x16566  ldloc.3
0x16567  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1656c  endfinally
0x1656d  ret
```
