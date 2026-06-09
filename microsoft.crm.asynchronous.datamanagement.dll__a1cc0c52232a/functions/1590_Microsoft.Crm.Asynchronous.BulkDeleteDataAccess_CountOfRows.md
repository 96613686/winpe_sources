# Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::CountOfRows

- ea: `0x1590`
- end: `0x15d2`
- name: `Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::CountOfRows`
- size: `66`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1f350`

## pseudocode

```c

```

## disassembly

```asm
0x1590  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1595  ldstr    aSelectCountFro// "SELECT count(*) from {0}"
0x159a  ldc.i4.1
0x159b  newarr   [mscorlib]System.Object
0x15a0  dup
0x15a1  ldc.i4.0
0x15a2  ldarg.1
0x15a3  stelem.ref
0x15a4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x15a9  ldc.i4.1
0x15aa  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0x15af  stloc.0
0x15b0  ldarg.0
0x15b1  ldloc.0
0x15b2  ldarg.0
0x15b3  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x15b8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x15bd  call     instance object [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteScalar(class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo, valuetype [mscorlib]System.Guid)
0x15c2  callvirt instance string [mscorlib]System.Object::ToString()
0x15c7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15cc  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x15d1  ret
```
