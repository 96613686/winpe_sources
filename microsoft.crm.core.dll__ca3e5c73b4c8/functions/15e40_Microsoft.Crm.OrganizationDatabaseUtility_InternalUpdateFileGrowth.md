# Microsoft.Crm.OrganizationDatabaseUtility::InternalUpdateFileGrowth

- ea: `0x15e40`
- end: `0x15f1f`
- name: `Microsoft.Crm.OrganizationDatabaseUtility::InternalUpdateFileGrowth`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x15e00`

## callees

- `0xd180`
- `0xd2f0`
- `0xd620`
- `0xdab0`
- `0x15e40`
- `0x16750`
- `0x16810`

## string_xrefs

- `0x15ee2`: `D:\a\1\s\src\Platform\Core\DataServices\OrganizationDatabaseUtility.cs`
- `0x15edd`: `InternalUpdateFileGrowth`

## pseudocode

```c

```

## disassembly

```asm
0x15e40  ldarg.0
0x15e41  call     instance string Microsoft.Crm.OrganizationDatabaseUtility::RetrieveDatabaseName()
0x15e46  stloc.0
0x15e47  ldarg.0
0x15e48  ldc.i4.1
0x15e49  call     instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.DatabaseFileInfo> Microsoft.Crm.OrganizationDatabaseUtility::GetDatabaseLogicalFileNames(bool dataFileOnly)
0x15e4e  ldsfld   class [mscorlib]System.Converter`2<class Microsoft.Crm.DatabaseFileInfo, string> <>c::<>9__17_0
0x15e53  dup
0x15e54  brtrue.s loc_15E6D
0x15e56  pop
0x15e57  ldsfld   class <>c <>c::<>9
0x15e5c  ldftn    instance string <>c::<InternalUpdateFileGrowth>b__17_0(class Microsoft.Crm.DatabaseFileInfo x)
0x15e62  newobj   instance void class [mscorlib]System.Converter`2<class Microsoft.Crm.DatabaseFileInfo, string>::.ctor(object, native int)
0x15e67  dup
0x15e68  stsfld   class [mscorlib]System.Converter`2<class Microsoft.Crm.DatabaseFileInfo, string> <>c::<>9__17_0
0x15e6d  callvirt T0x2B000049
0x15e72  stloc.1
0x15e73  ldarg.0
0x15e74  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.OrganizationDatabaseUtility::_organizationId
0x15e79  ldc.i4.0
0x15e7a  ldc.i4.0
0x15e7b  newobj   instance void Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid organizationId, [opt] bool isReader, [opt] valuetype Microsoft.Crm.ReadPriority priority)
0x15e80  stloc.2
0x15e81  ldloc.2
0x15e82  callvirt instance void Microsoft.Crm.CrmDbConnection::Open()
0x15e87  ldloc.1
0x15e88  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0x15e8d  stloc.3
0x15e8e  br.s     loc_15EFB
0x15e90  ldloca.s 3
0x15e92  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0x15e97  stloc.s  4
0x15e99  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15e9e  ldstr    aIfConvertNvarc// "if (convert(nvarchar, serverproperty('E"...
0x15ea3  ldc.i4.3
0x15ea4  newarr   [mscorlib]System.Object
0x15ea9  dup
0x15eaa  ldc.i4.0
0x15eab  ldloc.0
0x15eac  stelem.ref
0x15ead  dup
0x15eae  ldc.i4.1
0x15eaf  ldloc.s  4
0x15eb1  stelem.ref
0x15eb2  dup
0x15eb3  ldc.i4.2
0x15eb4  ldarg.1
0x15eb5  box      [mscorlib]System.Int32
0x15eba  ldstr    aMb_0// "MB"
0x15ebf  call     string [mscorlib]System.String::Concat(object, object)
0x15ec4  stelem.ref
0x15ec5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x15eca  stloc.s  5
0x15ecc  ldloc.2
0x15ecd  ldloc.s  5
0x15ecf  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.CrmDbConnection::CreateCommand(string commandText)
0x15ed4  stloc.s  6
0x15ed6  ldloc.s  6
0x15ed8  ldc.i4   0x1CC
0x15edd  ldstr    aInternalupdate_0// "InternalUpdateFileGrowth"
0x15ee2  ldstr    aDA1SSrcPlatfor_10// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x15ee7  call     int32 Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x15eec  pop
0x15eed  leave.s  loc_15EFB
0x15eef  ldloc.s  6
0x15ef1  brfalse.s loc_15EFA
0x15ef3  ldloc.s  6
0x15ef5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15efa  endfinally
0x15efb  ldloca.s 3
0x15efd  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::MoveNext()
0x15f02  brtrue.s loc_15E90
0x15f04  leave.s  loc_15F1E
0x15f06  ldloca.s 3
0x15f08  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>
0x15f0e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15f13  endfinally
0x15f14  ldloc.2
0x15f15  brfalse.s loc_15F1D
0x15f17  ldloc.2
0x15f18  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15f1d  endfinally
0x15f1e  ret
```
