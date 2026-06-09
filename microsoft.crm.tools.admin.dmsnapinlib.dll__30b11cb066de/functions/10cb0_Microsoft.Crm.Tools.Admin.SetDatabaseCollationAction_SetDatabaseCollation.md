# Microsoft.Crm.Tools.Admin.SetDatabaseCollationAction::SetDatabaseCollation

- ea: `0x10cb0`
- end: `0x10d78`
- name: `Microsoft.Crm.Tools.Admin.SetDatabaseCollationAction::SetDatabaseCollation`
- size: `200`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10c10`

## string_xrefs

- `0x10d4e`: `XRM\SQL\9\StoredProcedures\catalog.xml`

## pseudocode

```c

```

## disassembly

```asm
0x10cb0  ldstr    aSettingDatabas// "Setting Database Collation"
0x10cb5  ldc.i4.0
0x10cb6  newarr   [mscorlib]System.Object
0x10cbb  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x10cc0  ldstr    aOrganizationid_4// "organizationId={0}, databaseName={1}, f"...
0x10cc5  ldc.i4.5
0x10cc6  newarr   [mscorlib]System.Object
0x10ccb  dup
0x10ccc  ldc.i4.0
0x10ccd  ldarg.0
0x10cce  box      [mscorlib]System.Guid
0x10cd3  stelem.ref
0x10cd4  dup
0x10cd5  ldc.i4.1
0x10cd6  ldarg.2
0x10cd7  stelem.ref
0x10cd8  dup
0x10cd9  ldc.i4.2
0x10cda  ldarg.3
0x10cdb  box      [mscorlib]System.Int32
0x10ce0  stelem.ref
0x10ce1  dup
0x10ce2  ldc.i4.3
0x10ce3  ldarg.s  4
0x10ce5  stelem.ref
0x10ce6  dup
0x10ce7  ldc.i4.4
0x10ce8  ldarg.s  5
0x10cea  stelem.ref
0x10ceb  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x10cf0  ldarg.0
0x10cf1  newobj   instance void [Microsoft.Crm.Setup.DiffBuilder]Microsoft.Crm.Setup.DiffBuilder::.ctor(valuetype [mscorlib]System.Guid)
0x10cf6  stloc.0
0x10cf7  ldloc.0
0x10cf8  ldstr    aServer_0// "Server"
0x10cfd  ldstr    aMscrm// "mscrm"
0x10d02  ldstr    aFnGetformatstr// "fn_GetFormatStrings"
0x10d07  callvirt instance void [Microsoft.Crm.Setup.DiffBuilder]Microsoft.Crm.Setup.DiffBuilder::DropSingleStoredProcedure(string, string, string)
0x10d0c  ldarg.0
0x10d0d  newobj   instance void [Microsoft.Crm.Setup.DiffBuilder]Microsoft.Crm.Setup.IndexAndConstraintUpgradeService::.ctor(valuetype [mscorlib]System.Guid)
0x10d12  stloc.1
0x10d13  ldloc.1
0x10d14  callvirt instance valuetype [mscorlib]System.Guid[] [Microsoft.Crm.Setup.DiffBuilder]Microsoft.Crm.Setup.IndexAndConstraintUpgradeService::DropAllFilteredIndexes()
0x10d19  stloc.2
0x10d1a  ldstr    aUse0ExecPSetdb// "use {0};\r\nexec p_SetDbCollation '{0}'"...
0x10d1f  stloc.3
0x10d20  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10d25  ldloc.3
0x10d26  ldc.i4.2
0x10d27  newarr   [mscorlib]System.Object
0x10d2c  dup
0x10d2d  ldc.i4.0
0x10d2e  ldarg.2
0x10d2f  stelem.ref
0x10d30  dup
0x10d31  ldc.i4.1
0x10d32  ldarg.1
0x10d33  stelem.ref
0x10d34  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x10d39  ldarg.s  4
0x10d3b  ldarg.0
0x10d3c  call     void [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.SqlUtility::ExecuteSqlScript(string, string, valuetype [mscorlib]System.Guid)
0x10d41  ldloc.0
0x10d42  callvirt instance void [Microsoft.Crm.Setup.DiffBuilder]Microsoft.Crm.Setup.DiffBuilder::ClearConnectionPool()
0x10d47  ldloc.1
0x10d48  ldloc.2
0x10d49  callvirt instance void [Microsoft.Crm.Setup.DiffBuilder]Microsoft.Crm.Setup.IndexAndConstraintUpgradeService::RecreateIndexes(valuetype [mscorlib]System.Guid[])
0x10d4e  ldstr    aXrmSql9Storedp// "XRM\\SQL\\9\\StoredProcedures\\catalog."...
0x10d53  stloc.s  4
0x10d55  ldarg.s  5
0x10d57  ldloc.s  4
0x10d59  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x10d5e  stloc.s  5
0x10d60  ldloc.0
0x10d61  ldstr    aServer_0// "Server"
0x10d66  ldstr    aMscrm// "mscrm"
0x10d6b  ldloc.s  5
0x10d6d  ldstr    aFnGetformatstr// "fn_GetFormatStrings"
0x10d72  callvirt instance void [Microsoft.Crm.Setup.DiffBuilder]Microsoft.Crm.Setup.DiffBuilder::InstallStoredProcedure(string, string, string, string)
0x10d77  ret
```
