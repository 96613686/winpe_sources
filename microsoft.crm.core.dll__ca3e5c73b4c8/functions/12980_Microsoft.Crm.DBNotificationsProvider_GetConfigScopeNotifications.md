# Microsoft.Crm.DBNotificationsProvider::GetConfigScopeNotifications

- ea: `0x12980`
- end: `0x12b9e`
- name: `Microsoft.Crm.DBNotificationsProvider::GetConfigScopeNotifications`
- size: `542`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x12910`

## callees

- `0x12980`
- `0x12ba0`
- `0x12c00`
- `0x130c0`
- `0x130e0`
- `0x132c0`
- `0x1eaa0`
- `0x1f4b0`
- `0x4d810`
- `0x57bf0`
- `0x581e0`
- `0x58230`
- `0x582e0`
- `0x64c40`
- `0x66380`
- `0x663c0`
- `0x663f0`
- `0x66880`

## string_xrefs

- `0x12a20`: `@CreatedOn`
- `0x12a79`: ` ORDER BY N.CreatedOn ASC`

## pseudocode

```c

```

## disassembly

```asm
0x12980  newobj   instance void <>c__DisplayClass15_0::.ctor()
0x12985  stloc.0
0x12986  ldloc.0
0x12987  ldarg.s  4
0x12989  stfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass15_0::lastChecked
0x1298e  ldarg.s  5
0x12990  brfalse.s loc_129EB
0x12992  ldarg.2
0x12993  brfalse.s loc_129EB
0x12995  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class ScopeOrgKey, valuetype [mscorlib]System.DateTime> Microsoft.Crm.DBNotificationsProvider::_lastOrgNotificationDateTime
0x1299a  ldarg.1
0x1299b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x129a0  newobj   instance void ScopeOrgKey::.ctor(valuetype Microsoft.Crm.SharedDatabase.ConfigScope scope, valuetype [mscorlib]System.Guid organizationId)
0x129a5  ldloca.s 1
0x129a7  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class ScopeOrgKey, valuetype [mscorlib]System.DateTime>::TryGetValue(var<u1>, !!T0)
0x129ac  brfalse.s loc_129BC
0x129ae  ldloc.1
0x129af  ldloc.0
0x129b0  ldfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass15_0::lastChecked
0x129b5  call     bool [mscorlib]System.DateTime::op_LessThanOrEqual(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x129ba  brfalse.s loc_129EB
0x129bc  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class ScopeOrgKey, valuetype [mscorlib]System.DateTime> Microsoft.Crm.DBNotificationsProvider::_lastOrgNotificationDateTime
0x129c1  ldarg.1
0x129c2  ldarg.2
0x129c3  unbox.any [mscorlib]System.Guid
0x129c8  newobj   instance void ScopeOrgKey::.ctor(valuetype Microsoft.Crm.SharedDatabase.ConfigScope scope, valuetype [mscorlib]System.Guid organizationId)
0x129cd  ldloca.s 1
0x129cf  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class ScopeOrgKey, valuetype [mscorlib]System.DateTime>::TryGetValue(var<u1>, !!T0)
0x129d4  brfalse.s loc_129EB
0x129d6  ldloc.1
0x129d7  ldloc.0
0x129d8  ldfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass15_0::lastChecked
0x129dd  call     bool [mscorlib]System.DateTime::op_LessThanOrEqual(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x129e2  brfalse.s loc_129EB
0x129e4  ldc.i4.0
0x129e5  newarr   Microsoft.Crm.NotificationEvent
0x129ea  ret
0x129eb  ldarg.s  6
0x129ed  call     class Microsoft.Crm.SharedDatabase.IDatabaseService Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService(valuetype Microsoft.Crm.LocatorServiceContext locatorServiceContext)
0x129f2  stloc.2
0x129f3  newobj   instance void <>c__DisplayClass15_1::.ctor()
0x129f8  stloc.3
0x129f9  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x129fe  stloc.s  4
0x12a00  ldloc.s  4
0x12a02  ldarg.0
0x12a03  ldarg.1
0x12a04  ldarg.s  5
0x12a06  ldloc.0
0x12a07  ldfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass15_0::lastChecked
0x12a0c  call     instance string Microsoft.Crm.DBNotificationsProvider::GetNotificationSql(valuetype Microsoft.Crm.SharedDatabase.ConfigScope scope, bool usePaging, valuetype [mscorlib]System.DateTime lastChecked)
0x12a11  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12a16  pop
0x12a17  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter>::.ctor()
0x12a1c  stloc.s  5
0x12a1e  ldloc.s  5
0x12a20  ldstr    aCreatedon_0// "@CreatedOn"
0x12a25  ldloc.0
0x12a26  ldfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass15_0::lastChecked
0x12a2b  box      [mscorlib]System.DateTime
0x12a30  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, object)
0x12a35  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter>::Add(var<u1>)
0x12a3a  ldarg.3
0x12a3b  brfalse.s loc_12A55
0x12a3d  ldarg.3
0x12a3e  ldlen
0x12a3f  brfalse.s loc_12A55
0x12a41  ldarg.3
0x12a42  ldloc.s  5
0x12a44  call     string Microsoft.Crm.DBNotificationsProvider::BuildEventConditionSql(int32[] events, class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> sqlParameters)
0x12a49  stloc.s  7
0x12a4b  ldloc.s  4
0x12a4d  ldloc.s  7
0x12a4f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12a54  pop
0x12a55  ldarg.2
0x12a56  brfalse.s loc_12A77
0x12a58  ldloc.s  4
0x12a5a  ldstr    aAndOrganizatio// " AND (OrganizationId = @OrganizationId "...
0x12a5f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12a64  pop
0x12a65  ldloc.s  5
0x12a67  ldstr    aOrganizationid_2// "@OrganizationId"
0x12a6c  ldarg.2
0x12a6d  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, object)
0x12a72  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter>::Add(var<u1>)
0x12a77  ldloc.s  4
0x12a79  ldstr    aOrderByNCreate// " ORDER BY N.CreatedOn ASC"
0x12a7e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12a83  pop
0x12a84  ldloc.s  4
0x12a86  callvirt instance string [mscorlib]System.Object::ToString()
0x12a8b  ldc.i4.1
0x12a8c  newobj   instance void Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string commandText, [opt] valuetype [System.Data]System.Data.CommandType commandType)
0x12a91  stloc.s  6
0x12a93  ldloc.s  6
0x12a95  ldloc.s  5
0x12a97  callvirt instance void Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameters(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Data]System.Data.SqlClient.SqlParameter> parameters)
0x12a9c  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x12aa1  ldc.i4.s 0x1D
0x12aa3  ldstr    a0// "{0}"
0x12aa8  ldc.i4.1
0x12aa9  newarr   [mscorlib]System.Object
0x12aae  dup
0x12aaf  ldc.i4.0
0x12ab0  ldloc.s  6
0x12ab2  callvirt instance class [System.Data]System.Data.SqlClient.SqlCommand Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::get_Command()
0x12ab7  stelem.ref
0x12ab8  call     void Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x12abd  ldc.i4.0
0x12abe  ldarg.1
0x12abf  ldloc.s  6
0x12ac1  callvirt instance class [System.Data]System.Data.SqlClient.SqlCommand Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::get_Command()
0x12ac6  call     void Microsoft.Crm.NotificationInstrumentation::LogResult(valuetype Microsoft.Crm.InstrumentationOperationType operationType, valuetype Microsoft.Crm.SharedDatabase.ConfigScope scope, class [System.Data]System.Data.IDbCommand command)
0x12acb  ldloc.2
0x12acc  ldarg.1
0x12acd  callvirt instance class Microsoft.Crm.Core.SqlAccess.ISqlDataAccess Microsoft.Crm.SharedDatabase.IDatabaseService::GetSqlDataAccesser(valuetype Microsoft.Crm.SharedDatabase.ConfigScope scope)
0x12ad2  ldloc.3
0x12ad3  ldnull
0x12ad4  stfld    class Microsoft.Crm.NotificationEvent[] <>c__DisplayClass15_1::notifications
0x12ad9  ldloc.s  6
0x12adb  ldloc.3
0x12adc  ldftn    instance void <>c__DisplayClass15_1::<GetConfigScopeNotifications>b__0(class [System.Data]System.Data.IDataReader reader)
0x12ae2  newobj   instance void class [mscorlib]System.Action`1<class [System.Data]System.Data.IDataReader>::.ctor(object, native int)
0x12ae7  callvirt instance void Microsoft.Crm.Core.SqlAccess.ISqlDataAccess::ExecuteReaderAction(class Microsoft.Crm.Core.SqlAccess.SqlCommandInfo sqlCommandInfo, class [mscorlib]System.Action`1<class [System.Data]System.Data.IDataReader> readData)
0x12aec  ldloc.3
0x12aed  ldfld    class Microsoft.Crm.NotificationEvent[] <>c__DisplayClass15_1::notifications
0x12af2  ldlen
0x12af3  brfalse.s loc_12B5B
0x12af5  ldloc.3
0x12af6  ldfld    class Microsoft.Crm.NotificationEvent[] <>c__DisplayClass15_1::notifications
0x12afb  stloc.s  8
0x12afd  ldc.i4.0
0x12afe  stloc.s  9
0x12b00  br.s     loc_12B51
0x12b02  newobj   instance void <>c__DisplayClass15_2::.ctor()
0x12b07  stloc.s  0xA
0x12b09  ldloc.s  0xA
0x12b0b  ldloc.s  8
0x12b0d  ldloc.s  9
0x12b0f  ldelem.ref
0x12b10  stfld    class Microsoft.Crm.NotificationEvent <>c__DisplayClass15_2::notification
0x12b15  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class ScopeOrgKey, valuetype [mscorlib]System.DateTime> Microsoft.Crm.DBNotificationsProvider::_lastOrgNotificationDateTime
0x12b1a  ldarg.1
0x12b1b  ldloc.s  0xA
0x12b1d  ldfld    class Microsoft.Crm.NotificationEvent <>c__DisplayClass15_2::notification
0x12b22  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.NotificationEvent::get_OrganizationId()
0x12b27  newobj   instance void ScopeOrgKey::.ctor(valuetype Microsoft.Crm.SharedDatabase.ConfigScope scope, valuetype [mscorlib]System.Guid organizationId)
0x12b2c  ldloc.s  0xA
0x12b2e  ldfld    class Microsoft.Crm.NotificationEvent <>c__DisplayClass15_2::notification
0x12b33  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.NotificationEvent::get_CreatedOn()
0x12b38  ldloc.s  0xA
0x12b3a  ldftn    instance valuetype [mscorlib]System.DateTime <>c__DisplayClass15_2::<GetConfigScopeNotifications>b__2(class ScopeOrgKey key, valuetype [mscorlib]System.DateTime oldValue)
0x12b40  newobj   instance void class [mscorlib]System.Func`3<class ScopeOrgKey, valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime>::.ctor(object, native int)
0x12b45  callvirt instance var<u1> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class ScopeOrgKey, valuetype [mscorlib]System.DateTime>::AddOrUpdate(void, var<u1>, !!T0)
0x12b4a  pop
0x12b4b  ldloc.s  9
0x12b4d  ldc.i4.1
0x12b4e  add
0x12b4f  stloc.s  9
0x12b51  ldloc.s  9
0x12b53  ldloc.s  8
0x12b55  ldlen
0x12b56  conv.i4
0x12b57  blt.s    loc_12B02
0x12b59  br.s     loc_12B87
0x12b5b  ldarg.2
0x12b5c  brfalse.s loc_12B87
0x12b5e  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class ScopeOrgKey, valuetype [mscorlib]System.DateTime> Microsoft.Crm.DBNotificationsProvider::_lastOrgNotificationDateTime
0x12b63  ldarg.1
0x12b64  ldarg.2
0x12b65  unbox.any [mscorlib]System.Guid
0x12b6a  newobj   instance void ScopeOrgKey::.ctor(valuetype Microsoft.Crm.SharedDatabase.ConfigScope scope, valuetype [mscorlib]System.Guid organizationId)
0x12b6f  ldloc.0
0x12b70  ldfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass15_0::lastChecked
0x12b75  ldloc.0
0x12b76  ldftn    instance valuetype [mscorlib]System.DateTime <>c__DisplayClass15_0::<GetConfigScopeNotifications>b__1(class ScopeOrgKey key, valuetype [mscorlib]System.DateTime oldValue)
0x12b7c  newobj   instance void class [mscorlib]System.Func`3<class ScopeOrgKey, valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime>::.ctor(object, native int)
0x12b81  callvirt instance var<u1> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class ScopeOrgKey, valuetype [mscorlib]System.DateTime>::AddOrUpdate(void, var<u1>, !!T0)
0x12b86  pop
0x12b87  ldloc.3
0x12b88  ldfld    class Microsoft.Crm.NotificationEvent[] <>c__DisplayClass15_1::notifications
0x12b8d  stloc.s  8
0x12b8f  leave.s  loc_12B9B
0x12b91  ldloc.2
0x12b92  brfalse.s loc_12B9A
0x12b94  ldloc.2
0x12b95  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12b9a  endfinally
0x12b9b  ldloc.s  8
0x12b9d  ret
```
