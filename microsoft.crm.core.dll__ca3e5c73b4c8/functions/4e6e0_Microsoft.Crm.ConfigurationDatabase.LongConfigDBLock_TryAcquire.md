# Microsoft.Crm.ConfigurationDatabase.LongConfigDBLock::TryAcquire

- ea: `0x4e6e0`
- end: `0x4e8ce`
- name: `Microsoft.Crm.ConfigurationDatabase.LongConfigDBLock::TryAcquire`
- size: `494`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1840`
- `0x1a860`
- `0x44400`
- `0x444f0`
- `0x44510`
- `0x4d3d0`
- `0x4d7e0`
- `0x4e6e0`
- `0x64ae0`
- `0x64b30`
- `0x64b60`

## string_xrefs

- `0x4e6e8`: `This object is already disposed`
- `0x4e6fb`: `Already acquired this lock : `
- `0x4e711`: `LongConfigDbLock_`
- `0x4e75e`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\ObjectModel\LongConfigDbLock.cs`
- `0x4e7bc`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\ObjectModel\LongConfigDbLock.cs`
- `0x4e84e`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\ObjectModel\LongConfigDbLock.cs`
- `0x4e7d3`: `LongConfigDBLockExpireTimeInMinutes`
- `0x4e883`: `LongConfigDBLockKeepAliveIntervalInSeconds`

## pseudocode

```c

```

## disassembly

```asm
0x4e6e0  ldarg.0
0x4e6e1  ldfld    bool Microsoft.Crm.ConfigurationDatabase.LongConfigDBLock::_disposed
0x4e6e6  brfalse.s loc_4E6F3
0x4e6e8  ldstr    aThisObjectIsAl// "This object is already disposed"
0x4e6ed  newobj   instance void Microsoft.Crm.CrmException::.ctor(string message)
0x4e6f2  throw
0x4e6f3  ldarg.0
0x4e6f4  ldfld    bool Microsoft.Crm.ConfigurationDatabase.LongConfigDBLock::_lockAcquired
0x4e6f9  brfalse.s loc_4E711
0x4e6fb  ldstr    aAlreadyAcquire// "Already acquired this lock : "
0x4e700  ldarg.0
0x4e701  ldfld    string Microsoft.Crm.ConfigurationDatabase.LongConfigDBLock::_lockName
0x4e706  call     string [mscorlib]System.String::Concat(string, string)
0x4e70b  newobj   instance void Microsoft.Crm.CrmException::.ctor(string message)
0x4e710  throw
0x4e711  ldstr    aLongconfigdblo// "LongConfigDbLock_"
0x4e716  ldarg.0
0x4e717  ldfld    string Microsoft.Crm.ConfigurationDatabase.LongConfigDBLock::_lockName
0x4e71c  call     string [mscorlib]System.String::Concat(string, string)
0x4e721  call     class Microsoft.Crm.ConfigurationDatabase.IConfigDBLock Microsoft.Crm.ConfigurationDatabase.ConfigDBLock::NewLock(string name)
0x4e726  stloc.0
0x4e727  call     class Microsoft.Crm.SharedDatabase.IDatabaseService Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x4e72c  stloc.1
0x4e72d  ldloc.1
0x4e72e  ldstr    aSitelock// "SiteLock"
0x4e733  ldarg.0
0x4e734  ldfld    string Microsoft.Crm.ConfigurationDatabase.LongConfigDBLock::_lockName
0x4e739  ldc.i4.3
0x4e73a  newarr   [mscorlib]System.String
0x4e73f  dup
0x4e740  ldc.i4.0
0x4e741  ldstr    aName// "Name"
0x4e746  stelem.ref
0x4e747  dup
0x4e748  ldc.i4.1
0x4e749  ldstr    aOwner// "Owner"
0x4e74e  stelem.ref
0x4e74f  dup
0x4e750  ldc.i4.2
0x4e751  ldstr    aModifiedon// "ModifiedOn"
0x4e756  stelem.ref
0x4e757  ldc.i4.s 0x38
0x4e759  ldstr    aTryacquire// "TryAcquire"
0x4e75e  ldstr    aDA1SSrcPlatfor_38// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x4e763  callvirt instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveById(string tableName, object id, string[] columns, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x4e768  stloc.2
0x4e769  ldloc.2
0x4e76a  brtrue.s loc_4E7CE
0x4e76c  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x4e771  stloc.s  4
0x4e773  ldloc.s  4
0x4e775  ldstr    aName// "Name"
0x4e77a  ldarg.0
0x4e77b  ldfld    string Microsoft.Crm.ConfigurationDatabase.LongConfigDBLock::_lockName
0x4e780  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x4e785  ldloc.s  4
0x4e787  ldstr    aOwner// "Owner"
0x4e78c  ldarg.0
0x4e78d  ldfld    string Microsoft.Crm.ConfigurationDatabase.LongConfigDBLock::_owner
0x4e792  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x4e797  ldloc.s  4
0x4e799  ldstr    aModifiedon// "ModifiedOn"
0x4e79e  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x4e7a3  box      [mscorlib]System.DateTime
0x4e7a8  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x4e7ad  ldloc.1
0x4e7ae  ldstr    aSitelock// "SiteLock"
0x4e7b3  ldloc.s  4
0x4e7b5  ldc.i4.s 0x41
0x4e7b7  ldstr    aTryacquire// "TryAcquire"
0x4e7bc  ldstr    aDA1SSrcPlatfor_38// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x4e7c1  callvirt instance object Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string tableName, class Microsoft.Crm.Data.PropertyBag columnSet, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x4e7c6  pop
0x4e7c7  ldarg.0
0x4e7c8  ldc.i4.1
0x4e7c9  stfld    bool Microsoft.Crm.ConfigurationDatabase.LongConfigDBLock::_lockAcquired
0x4e7ce  call     class Microsoft.Crm.ISiteSettingsProvider Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x4e7d3  ldstr    aLongconfigdblo_0// "LongConfigDBLockExpireTimeInMinutes"
0x4e7d8  ldc.i4.0
0x4e7d9  callvirt T0x2B000038
0x4e7de  conv.r8
0x4e7df  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0x4e7e4  stloc.3
0x4e7e5  ldloc.2
0x4e7e6  brfalse.s loc_4E860
0x4e7e8  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x4e7ed  ldloc.2
0x4e7ee  ldstr    aModifiedon// "ModifiedOn"
0x4e7f3  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x4e7f8  unbox.any [mscorlib]System.DateTime
0x4e7fd  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x4e802  ldloc.3
0x4e803  call     bool [mscorlib]System.TimeSpan::op_GreaterThan(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x4e808  brfalse.s loc_4E860
0x4e80a  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x4e80f  stloc.s  5
0x4e811  ldloc.s  5
0x4e813  ldstr    aOwner// "Owner"
0x4e818  ldarg.0
0x4e819  ldfld    string Microsoft.Crm.ConfigurationDatabase.LongConfigDBLock::_owner
0x4e81e  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x4e823  ldloc.s  5
0x4e825  ldstr    aModifiedon// "ModifiedOn"
0x4e82a  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x4e82f  box      [mscorlib]System.DateTime
0x4e834  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x4e839  ldloc.1
0x4e83a  ldstr    aSitelock// "SiteLock"
0x4e83f  ldarg.0
0x4e840  ldfld    string Microsoft.Crm.ConfigurationDatabase.LongConfigDBLock::_lockName
0x4e845  ldloc.s  5
0x4e847  ldc.i4.s 0x4C
0x4e849  ldstr    aTryacquire// "TryAcquire"
0x4e84e  ldstr    aDA1SSrcPlatfor_38// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x4e853  callvirt instance int32 Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string tableName, object id, class Microsoft.Crm.Data.PropertyBag columnSet, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x4e858  pop
0x4e859  ldarg.0
0x4e85a  ldc.i4.1
0x4e85b  stfld    bool Microsoft.Crm.ConfigurationDatabase.LongConfigDBLock::_lockAcquired
0x4e860  leave.s  loc_4E876
0x4e862  ldloc.1
0x4e863  brfalse.s loc_4E86B
0x4e865  ldloc.1
0x4e866  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4e86b  endfinally
0x4e86c  ldloc.0
0x4e86d  brfalse.s loc_4E875
0x4e86f  ldloc.0
0x4e870  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4e875  endfinally
0x4e876  ldarg.0
0x4e877  ldfld    bool Microsoft.Crm.ConfigurationDatabase.LongConfigDBLock::_lockAcquired
0x4e87c  brfalse.s loc_4E8C7
0x4e87e  call     class Microsoft.Crm.ISiteSettingsProvider Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x4e883  ldstr    aLongconfigdblo_1// "LongConfigDBLockKeepAliveIntervalInSeco"...
0x4e888  ldc.i4.0
0x4e889  callvirt T0x2B000038
0x4e88e  stloc.s  6
0x4e890  ldarg.0
0x4e891  ldloc.s  6
0x4e893  ldc.i4   0x3E8
0x4e898  mul
0x4e899  conv.r8
0x4e89a  newobj   instance void [System]System.Timers.Timer::.ctor(float64)
0x4e89f  stfld    class [System]System.Timers.Timer Microsoft.Crm.ConfigurationDatabase.LongConfigDBLock::_keepAliveTimer
0x4e8a4  ldarg.0
0x4e8a5  ldfld    class [System]System.Timers.Timer Microsoft.Crm.ConfigurationDatabase.LongConfigDBLock::_keepAliveTimer
0x4e8aa  ldarg.0
0x4e8ab  ldftn    instance void Microsoft.Crm.ConfigurationDatabase.LongConfigDBLock::OnKeepAliveEvent(object source, class [System]System.Timers.ElapsedEventArgs e)
0x4e8b1  newobj   instance void [System]System.Timers.ElapsedEventHandler::.ctor(object, native int)
0x4e8b6  callvirt instance void [System]System.Timers.Timer::add_Elapsed(class [System]System.Timers.ElapsedEventHandler)
0x4e8bb  ldarg.0
0x4e8bc  ldfld    class [System]System.Timers.Timer Microsoft.Crm.ConfigurationDatabase.LongConfigDBLock::_keepAliveTimer
0x4e8c1  ldc.i4.1
0x4e8c2  callvirt instance void [System]System.Timers.Timer::set_Enabled(bool)
0x4e8c7  ldarg.0
0x4e8c8  ldfld    bool Microsoft.Crm.ConfigurationDatabase.LongConfigDBLock::_lockAcquired
0x4e8cd  ret
```
