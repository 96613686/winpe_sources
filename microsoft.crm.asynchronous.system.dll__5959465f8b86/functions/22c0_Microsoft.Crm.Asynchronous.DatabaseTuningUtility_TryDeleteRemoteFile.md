# Microsoft.Crm.Asynchronous.DatabaseTuningUtility::TryDeleteRemoteFile

- ea: `0x22c0`
- end: `0x2325`
- name: `Microsoft.Crm.Asynchronous.DatabaseTuningUtility::TryDeleteRemoteFile`
- size: `101`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1e50`
- `0x2290`

## callees

- `0x22c0`

## pseudocode

```c

```

## disassembly

```asm
0x22c0  ldc.i4.1
0x22c1  stloc.0
0x22c2  ldarg.0
0x22c3  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x22c8  stloc.1
0x22c9  ldloc.1
0x22ca  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x22cf  ldstr    aDeclareResultI// "declare @result int\r\nexec @result=xp_"...
0x22d4  ldc.i4.1
0x22d5  newarr   [mscorlib]System.Object
0x22da  dup
0x22db  ldc.i4.0
0x22dc  ldarg.1
0x22dd  stelem.ref
0x22de  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x22e3  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x22e8  ldloc.1
0x22e9  callvirt instance class [System.Data]System.Data.IDataReader [System.Data]System.Data.IDbCommand::ExecuteReader()
0x22ee  stloc.2
0x22ef  ldloc.2
0x22f0  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x22f5  brfalse.s loc_2308
0x22f7  ldloc.2
0x22f8  ldstr    aReturnvalue// "ReturnValue"
0x22fd  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x2302  unbox.any [mscorlib]System.Int32
0x2307  stloc.0
0x2308  leave.s  loc_231E
0x230a  ldloc.2
0x230b  brfalse.s loc_2313
0x230d  ldloc.2
0x230e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2313  endfinally
0x2314  ldloc.1
0x2315  brfalse.s loc_231D
0x2317  ldloc.1
0x2318  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x231d  endfinally
0x231e  ldloc.0
0x231f  brfalse.s loc_2323
0x2321  ldc.i4.0
0x2322  ret
0x2323  ldc.i4.1
0x2324  ret
```
