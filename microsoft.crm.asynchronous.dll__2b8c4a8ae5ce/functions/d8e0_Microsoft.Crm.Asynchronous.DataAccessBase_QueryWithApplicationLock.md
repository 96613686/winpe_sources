# Microsoft.Crm.Asynchronous.DataAccessBase::QueryWithApplicationLock

- ea: `0xd8e0`
- end: `0xd964`
- name: `Microsoft.Crm.Asynchronous.DataAccessBase::QueryWithApplicationLock`
- size: `132`
- prototype: ``
- caller_count: `7`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x3230`
- `0x3490`
- `0x36b0`
- `0x3cc0`
- `0x4030`
- `0x40f0`
- `0x4240`

## callees

- `0xc310`
- `0xd8e0`
- `0xdba0`
- `0xdbc0`

## string_xrefs

- `0xd8f7`: `tempdb..`
- `0xd92f`: `\n		END\n	COMMIT TRANSACTION         --COMMIT will release app Lock\nEND TRY\nBEGIN CATCH\n	IF @@TRANCOUNT > 0\n		ROLLBACK TRANSACTION;         --ROLLBACK will release appLock\n\n	THROW;                  --Throw Original error message error to Client \nEND CATCH\n`

## pseudocode

```c

```

## disassembly

```asm
0xd8e0  ldarg.0
0xd8e1  ldarg.1
0xd8e2  call     instance string Microsoft.Crm.Asynchronous.DataAccessBase::AppendOrganizationId(string applicationLockName)
0xd8e7  stloc.0
0xd8e8  ldarg.0
0xd8e9  callvirt instance bool Microsoft.Crm.Asynchronous.DataAccessBase::get_ApplicationLockOnTempDB()
0xd8ee  brtrue.s loc_D8F7
0xd8f0  ldsfld   string [mscorlib]System.String::Empty
0xd8f5  br.s     loc_D8FC
0xd8f7  ldstr    aTempdb// "tempdb.."
0xd8fc  stloc.1
0xd8fd  call     int32 Microsoft.Crm.Asynchronous.ServerConfiguration::get_AsyncAppLockTimeoutInMilliSeconds()
0xd902  stloc.2
0xd903  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xd908  ldstr    aSetDeadlockPri// "\r\nSET DEADLOCK_PRIORITY LOW\r\nSET XA"...
0xd90d  ldc.i4.3
0xd90e  newarr   [mscorlib]System.Object
0xd913  dup
0xd914  ldc.i4.0
0xd915  ldloc.1
0xd916  stelem.ref
0xd917  dup
0xd918  ldc.i4.1
0xd919  ldloc.0
0xd91a  stelem.ref
0xd91b  dup
0xd91c  ldc.i4.2
0xd91d  ldloc.2
0xd91e  box      [mscorlib]System.Int32
0xd923  stelem.ref
0xd924  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xd929  stloc.3
0xd92a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xd92f  ldstr    aEndCommitTrans// "\r\n\t\tEND\r\n\tCOMMIT TRANSACTION    "...
0xd934  ldc.i4.0
0xd935  newarr   [mscorlib]System.Object
0xd93a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xd93f  stloc.s  4
0xd941  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xd946  ldstr    a012_0// "{0}\n{1}\n{2}"
0xd94b  ldc.i4.3
0xd94c  newarr   [mscorlib]System.Object
0xd951  dup
0xd952  ldc.i4.0
0xd953  ldloc.3
0xd954  stelem.ref
0xd955  dup
0xd956  ldc.i4.1
0xd957  ldarg.2
0xd958  stelem.ref
0xd959  dup
0xd95a  ldc.i4.2
0xd95b  ldloc.s  4
0xd95d  stelem.ref
0xd95e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xd963  ret
```
