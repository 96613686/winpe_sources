# Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::CleanupObjects

- ea: `0xe940`
- end: `0xe9b1`
- name: `Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::CleanupObjects`
- size: `113`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xf0a0`
- `0xf710`

## callees

- `0xf6d0`

## pseudocode

```c

```

## disassembly

```asm
0xe940  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0xe945  stloc.0
0xe946  ldloc.0
0xe947  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe94c  ldstr    aIfObjectIdN0NU// "IF (OBJECT_ID(N'{0}', N'U') IS NOT NULL"...
0xe951  ldc.i4.1
0xe952  newarr   [mscorlib]System.Object
0xe957  dup
0xe958  ldc.i4.0
0xe959  ldarg.1
0xe95a  stelem.ref
0xe95b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0xe960  pop
0xe961  ldloc.0
0xe962  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0xe967  pop
0xe968  ldloc.0
0xe969  ldstr    aBegin// "BEGIN"
0xe96e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xe973  pop
0xe974  ldloc.0
0xe975  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0xe97a  pop
0xe97b  ldloc.0
0xe97c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe981  ldstr    aTruncateTable0// "TRUNCATE TABLE {0}"
0xe986  ldc.i4.1
0xe987  newarr   [mscorlib]System.Object
0xe98c  dup
0xe98d  ldc.i4.0
0xe98e  ldarg.1
0xe98f  stelem.ref
0xe990  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0xe995  pop
0xe996  ldloc.0
0xe997  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0xe99c  pop
0xe99d  ldloc.0
0xe99e  ldstr    aEnd// "END"
0xe9a3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xe9a8  pop
0xe9a9  ldarg.0
0xe9aa  ldloc.0
0xe9ab  call     instance void Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::ExecuteSqlScript(class [mscorlib]System.Text.StringBuilder cleanupScript)
0xe9b0  ret
```
