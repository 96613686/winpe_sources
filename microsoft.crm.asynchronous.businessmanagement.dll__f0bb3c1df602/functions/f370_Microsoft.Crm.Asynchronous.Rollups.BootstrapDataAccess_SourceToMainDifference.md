# Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::SourceToMainDifference

- ea: `0xf370`
- end: `0xf3e6`
- name: `Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::SourceToMainDifference`
- size: `118`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0xe7d0`
- `0xe7e0`
- `0xe930`
- `0xf370`

## pseudocode

```c

```

## disassembly

```asm
0xf370  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0xf375  stloc.0
0xf376  ldloc.0
0xf377  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf37c  ldstr    aSelectSelectTo// "SELECT ((SELECT TOP 1 {2} FROM {0} ORDE"...
0xf381  ldc.i4.3
0xf382  newarr   [mscorlib]System.Object
0xf387  dup
0xf388  ldc.i4.0
0xf389  ldarg.0
0xf38a  call     instance string Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::get_SourceTableName()
0xf38f  stelem.ref
0xf390  dup
0xf391  ldc.i4.1
0xf392  ldarg.0
0xf393  call     instance string Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::get_MainTableName()
0xf398  stelem.ref
0xf399  dup
0xf39a  ldc.i4.2
0xf39b  ldstr    aId_0// "Id"
0xf3a0  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0xf3a5  stelem.ref
0xf3a6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0xf3ab  pop
0xf3ac  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0xf3b1  stloc.1
0xf3b2  ldloc.1
0xf3b3  ldloc.0
0xf3b4  callvirt instance string [mscorlib]System.Object::ToString()
0xf3b9  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xf3be  ldarg.0
0xf3bf  ldloc.1
0xf3c0  call     instance object Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand command)
0xf3c5  stloc.2
0xf3c6  ldloc.2
0xf3c7  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xf3cc  beq.s    loc_F3D6
0xf3ce  ldloc.2
0xf3cf  unbox.any [mscorlib]System.Int32
0xf3d4  br.s     loc_F3D7
0xf3d6  ldc.i4.0
0xf3d7  stloc.3
0xf3d8  leave.s  loc_F3E4
0xf3da  ldloc.1
0xf3db  brfalse.s loc_F3E3
0xf3dd  ldloc.1
0xf3de  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf3e3  endfinally
0xf3e4  ldloc.3
0xf3e5  ret
```
