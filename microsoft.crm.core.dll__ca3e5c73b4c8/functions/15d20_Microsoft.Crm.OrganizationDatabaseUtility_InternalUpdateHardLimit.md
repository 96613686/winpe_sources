# Microsoft.Crm.OrganizationDatabaseUtility::InternalUpdateHardLimit

- ea: `0x15d20`
- end: `0x15df5`
- name: `Microsoft.Crm.OrganizationDatabaseUtility::InternalUpdateHardLimit`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x159c0`

## callees

- `0xd180`
- `0xd2f0`
- `0xd620`
- `0xdab0`
- `0x15d20`
- `0x16750`
- `0x16810`

## string_xrefs

- `0x15db8`: `D:\a\1\s\src\Platform\Core\DataServices\OrganizationDatabaseUtility.cs`
- `0x15db3`: `InternalUpdateHardLimit`

## pseudocode

```c

```

## disassembly

```asm
0x15d20  ldarg.0
0x15d21  call     instance string Microsoft.Crm.OrganizationDatabaseUtility::RetrieveDatabaseName()
0x15d26  stloc.0
0x15d27  ldarg.0
0x15d28  ldc.i4.0
0x15d29  call     instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.DatabaseFileInfo> Microsoft.Crm.OrganizationDatabaseUtility::GetDatabaseLogicalFileNames(bool dataFileOnly)
0x15d2e  ldsfld   class [mscorlib]System.Converter`2<class Microsoft.Crm.DatabaseFileInfo, string> <>c::<>9__14_0
0x15d33  dup
0x15d34  brtrue.s loc_15D4D
0x15d36  pop
0x15d37  ldsfld   class <>c <>c::<>9
0x15d3c  ldftn    instance string <>c::<InternalUpdateHardLimit>b__14_0(class Microsoft.Crm.DatabaseFileInfo x)
0x15d42  newobj   instance void class [mscorlib]System.Converter`2<class Microsoft.Crm.DatabaseFileInfo, string>::.ctor(object, native int)
0x15d47  dup
0x15d48  stsfld   class [mscorlib]System.Converter`2<class Microsoft.Crm.DatabaseFileInfo, string> <>c::<>9__14_0
0x15d4d  callvirt T0x2B000049
0x15d52  stloc.1
0x15d53  ldarg.0
0x15d54  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.OrganizationDatabaseUtility::_organizationId
0x15d59  ldc.i4.0
0x15d5a  ldc.i4.0
0x15d5b  newobj   instance void Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid organizationId, [opt] bool isReader, [opt] valuetype Microsoft.Crm.ReadPriority priority)
0x15d60  stloc.2
0x15d61  ldloc.2
0x15d62  callvirt instance void Microsoft.Crm.CrmDbConnection::Open()
0x15d67  ldloc.1
0x15d68  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0x15d6d  stloc.3
0x15d6e  br.s     loc_15DD1
0x15d70  ldloca.s 3
0x15d72  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0x15d77  stloc.s  4
0x15d79  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15d7e  ldstr    aAlterDatabase0// "alter database {0} modify file (name = "...
0x15d83  ldc.i4.3
0x15d84  newarr   [mscorlib]System.Object
0x15d89  dup
0x15d8a  ldc.i4.0
0x15d8b  ldloc.0
0x15d8c  stelem.ref
0x15d8d  dup
0x15d8e  ldc.i4.1
0x15d8f  ldloc.s  4
0x15d91  stelem.ref
0x15d92  dup
0x15d93  ldc.i4.2
0x15d94  ldarg.1
0x15d95  box      [mscorlib]System.Int32
0x15d9a  stelem.ref
0x15d9b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x15da0  stloc.s  5
0x15da2  ldloc.2
0x15da3  ldloc.s  5
0x15da5  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.CrmDbConnection::CreateCommand(string commandText)
0x15daa  stloc.s  6
0x15dac  ldloc.s  6
0x15dae  ldc.i4   0x1A1
0x15db3  ldstr    aInternalupdate// "InternalUpdateHardLimit"
0x15db8  ldstr    aDA1SSrcPlatfor_10// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x15dbd  call     int32 Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x15dc2  pop
0x15dc3  leave.s  loc_15DD1
0x15dc5  ldloc.s  6
0x15dc7  brfalse.s loc_15DD0
0x15dc9  ldloc.s  6
0x15dcb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15dd0  endfinally
0x15dd1  ldloca.s 3
0x15dd3  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::MoveNext()
0x15dd8  brtrue.s loc_15D70
0x15dda  leave.s  loc_15DF4
0x15ddc  ldloca.s 3
0x15dde  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>
0x15de4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15de9  endfinally
0x15dea  ldloc.2
0x15deb  brfalse.s loc_15DF3
0x15ded  ldloc.2
0x15dee  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15df3  endfinally
0x15df4  ret
```
