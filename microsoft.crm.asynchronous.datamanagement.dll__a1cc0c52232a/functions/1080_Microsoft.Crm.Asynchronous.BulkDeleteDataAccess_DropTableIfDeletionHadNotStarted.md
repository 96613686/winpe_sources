# Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::DropTableIfDeletionHadNotStarted

- ea: `0x1080`
- end: `0x10ce`
- name: `Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::DropTableIfDeletionHadNotStarted`
- size: `78`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x2b10`

## pseudocode

```c

```

## disassembly

```asm
0x1080  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1085  ldstr    aIfExistsSelect// "IF EXISTS (SELECT 1 FROM dbo.sysobjects"...
0x108a  ldc.i4.1
0x108b  newarr   [mscorlib]System.Object
0x1090  dup
0x1091  ldc.i4.0
0x1092  ldarg.1
0x1093  stelem.ref
0x1094  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1099  ldc.i4.1
0x109a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0x109f  stloc.0
0x10a0  ldloc.0
0x10a1  ldstr    aTrue// "@true"
0x10a6  ldc.i4.1
0x10a7  box      [mscorlib]System.Boolean
0x10ac  ldloca.s 1
0x10ae  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x10b4  ldloc.1
0x10b5  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x10ba  ldarg.0
0x10bb  ldloc.0
0x10bc  ldarg.0
0x10bd  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x10c2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x10c7  call     instance object [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteScalar(class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo, valuetype [mscorlib]System.Guid)
0x10cc  pop
0x10cd  ret
```
