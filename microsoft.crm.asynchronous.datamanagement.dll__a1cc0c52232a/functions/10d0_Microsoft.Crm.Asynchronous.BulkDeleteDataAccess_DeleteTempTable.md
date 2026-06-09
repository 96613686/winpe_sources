# Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::DeleteTempTable

- ea: `0x10d0`
- end: `0x1104`
- name: `Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::DeleteTempTable`
- size: `52`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1ba0`
- `0x1db0`
- `0x1f350`

## pseudocode

```c

```

## disassembly

```asm
0x10d0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10d5  ldstr    aIfExistsSelect_0// "IF EXISTS (SELECT 1 FROM dbo.sysobjects"...
0x10da  ldc.i4.1
0x10db  newarr   [mscorlib]System.Object
0x10e0  dup
0x10e1  ldc.i4.0
0x10e2  ldarg.1
0x10e3  stelem.ref
0x10e4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x10e9  ldc.i4.1
0x10ea  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0x10ef  stloc.0
0x10f0  ldarg.0
0x10f1  ldloc.0
0x10f2  ldarg.0
0x10f3  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x10f8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x10fd  call     instance object [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteScalar(class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo, valuetype [mscorlib]System.Guid)
0x1102  pop
0x1103  ret
```
