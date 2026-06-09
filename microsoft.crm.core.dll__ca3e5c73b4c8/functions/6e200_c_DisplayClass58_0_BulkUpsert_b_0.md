# <>c__DisplayClass58_0::<BulkUpsert>b__0

- ea: `0x6e200`
- end: `0x6e437`
- name: `<>c__DisplayClass58_0::<BulkUpsert>b__0`
- size: `567`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, installer_update`

## callees

- `0x1a860`
- `0x1b940`
- `0x1be80`
- `0x1c060`
- `0x44810`
- `0x44d80`
- `0x44da0`
- `0x5de00`
- `0x611f0`
- `0x616e0`
- `0x61a70`
- `0x61aa0`
- `0x636c0`
- `0x636f0`
- `0x63a20`
- `0x64060`
- `0x6d3e0`
- `0x6e200`

## string_xrefs

- `0x6e29f`: `updateColumnsOnMatch`
- `0x6e31a`: `All values in 'updateColumnsOnMatch' must be of type UpsertSource. Error in '`
- `0x6e35b`: `Match columns must be a subset of the created rows.`
- `0x6e3d0`: `Columns to copy from the source table must be a subset of the created rows.`
- `0x6e3f2`: `BulkUpsert does not support creating or updating properties columns in 'updateColumnsOnMatch'`

## pseudocode

```c

```

## disassembly

```asm
0x6e200  ldsfld   string Microsoft.Crm.CustomPropertyConstants::CrmServiceName
0x6e205  call     string Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::get_ServiceIdentifier()
0x6e20a  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x6e20f  ldsfld   string Microsoft.Crm.CustomPropertyConstants::Caller
0x6e214  ldarg.0
0x6e215  ldfld    string <>c__DisplayClass58_0::memberName
0x6e21a  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x6e21f  ldsfld   string Microsoft.Crm.CustomPropertyConstants::CallerSourceFile
0x6e224  ldarg.0
0x6e225  ldfld    string <>c__DisplayClass58_0::sourceFilePath
0x6e22a  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x6e22f  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x6e234  ldsfld   string Microsoft.Crm.CustomPropertyConstants::CallerLineNumber
0x6e239  ldarg.0
0x6e23a  ldflda   int32 <>c__DisplayClass58_0::sourceLineNumber
0x6e23f  call     instance string [mscorlib]System.Int32::ToString()
0x6e244  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x6e249  ldsfld   string Microsoft.Crm.CustomPropertyConstants::Table
0x6e24e  ldarg.0
0x6e24f  ldfld    string <>c__DisplayClass58_0::tableName
0x6e254  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x6e259  ldarg.0
0x6e25a  ldfld    string <>c__DisplayClass58_0::tableName
0x6e25f  ldstr    aTablename// "tableName"
0x6e264  call     void Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string parameter, string name)
0x6e269  ldarg.0
0x6e26a  ldfld    class Microsoft.Crm.Data.PropertyBag[] <>c__DisplayClass58_0::rows
0x6e26f  ldstr    aRows// "rows"
0x6e274  call     void Microsoft.Crm.Exceptions::ThrowIfNull(object parameter, string name)
0x6e279  ldarg.0
0x6e27a  ldfld    string[] <>c__DisplayClass58_0::matchColumns
0x6e27f  ldstr    aMatchcolumns// "matchColumns"
0x6e284  call     void Microsoft.Crm.Exceptions::ThrowIfNull(object parameter, string name)
0x6e289  ldarg.0
0x6e28a  ldfld    string[] <>c__DisplayClass58_0::matchColumns
0x6e28f  ldstr    aMatchcolumns// "matchColumns"
0x6e294  call     T0x2B00000F
0x6e299  ldarg.0
0x6e29a  ldfld    class Microsoft.Crm.Data.PropertyBag <>c__DisplayClass58_0::updateColumnsOnMatch
0x6e29f  ldstr    aUpdatecolumnso// "updateColumnsOnMatch"
0x6e2a4  call     void Microsoft.Crm.Exceptions::ThrowIfNull(object parameter, string name)
0x6e2a9  ldarg.0
0x6e2aa  ldfld    class Microsoft.Crm.Data.PropertyBag[] <>c__DisplayClass58_0::rows
0x6e2af  ldlen
0x6e2b0  brtrue.s loc_6E2B3
0x6e2b2  ret
0x6e2b3  ldarg.0
0x6e2b4  ldfld    class Microsoft.Crm.SharedDatabase.DatabaseService <>c__DisplayClass58_0::<>4__this
0x6e2b9  ldarg.0
0x6e2ba  ldfld    string <>c__DisplayClass58_0::tableName
0x6e2bf  call     instance void Microsoft.Crm.SharedDatabase.DatabaseService::Initialize(string tableName)
0x6e2c4  ldarg.0
0x6e2c5  ldfld    class Microsoft.Crm.SharedDatabase.DatabaseService <>c__DisplayClass58_0::<>4__this
0x6e2ca  ldarg.0
0x6e2cb  ldfld    class Microsoft.Crm.Data.PropertyBag[] <>c__DisplayClass58_0::rows
0x6e2d0  call     T0x2B000118
0x6e2d5  call     instance void Microsoft.Crm.SharedDatabase.DatabaseService::CheckColumnSetColumns(class Microsoft.Crm.Data.PropertyBag columnSet)
0x6e2da  ldarg.0
0x6e2db  ldfld    class Microsoft.Crm.SharedDatabase.DatabaseService <>c__DisplayClass58_0::<>4__this
0x6e2e0  callvirt instance bool Microsoft.Crm.SharedDatabase.DatabaseService::get_HasPropertiesColumns()
0x6e2e5  brfalse.s loc_6E2F2
0x6e2e7  ldstr    aBulkupsertDoes// "BulkUpsert does not support creating or"...
0x6e2ec  newobj   instance void Microsoft.Crm.CrmNotImplementedException::.ctor(string objectName)
0x6e2f1  throw
0x6e2f2  ldarg.0
0x6e2f3  ldfld    class Microsoft.Crm.Data.PropertyBag <>c__DisplayClass58_0::updateColumnsOnMatch
0x6e2f8  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype Microsoft.Crm.Data.PropertyEntry> Microsoft.Crm.Data.PropertyBag::RetrievePropertyEntries()
0x6e2fd  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype Microsoft.Crm.Data.PropertyEntry>::GetEnumerator()
0x6e302  stloc.1
0x6e303  br.s     loc_6E336
0x6e305  ldloc.1
0x6e306  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype Microsoft.Crm.Data.PropertyEntry>::get_Current()
0x6e30b  stloc.2
0x6e30c  ldloca.s 2
0x6e30e  call     instance object Microsoft.Crm.Data.PropertyEntry::get_Value()
0x6e313  isinst   Microsoft.Crm.SharedDatabase.UpsertSource
0x6e318  brtrue.s loc_6E336
0x6e31a  ldstr    aAllValuesInUpd// "All values in 'updateColumnsOnMatch' mu"...
0x6e31f  ldloca.s 2
0x6e321  call     instance string Microsoft.Crm.Data.PropertyEntry::get_Name()
0x6e326  ldstr    asc_8A4BE// "'"
0x6e32b  call     string [mscorlib]System.String::Concat(string, string, string)
0x6e330  newobj   instance void Microsoft.Crm.CrmException::.ctor(string message)
0x6e335  throw
0x6e336  ldloc.1
0x6e337  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6e33c  brtrue.s loc_6E305
0x6e33e  leave.s  loc_6E34A
0x6e340  ldloc.1
0x6e341  brfalse.s loc_6E349
0x6e343  ldloc.1
0x6e344  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6e349  endfinally
0x6e34a  ldarg.0
0x6e34b  ldfld    class Microsoft.Crm.Data.PropertyBag[] <>c__DisplayClass58_0::rows
0x6e350  call     T0x2B000118
0x6e355  ldarg.0
0x6e356  ldfld    string[] <>c__DisplayClass58_0::matchColumns
0x6e35b  ldstr    aMatchColumnsMu// "Match columns must be a subset of the c"...
0x6e360  call     void Microsoft.Crm.SharedDatabase.DatabaseService::VerifyBulkUpsertColumns(class Microsoft.Crm.Data.PropertyBag row, class [mscorlib]System.Collections.Generic.IEnumerable`1<string> matchColumns, string exceptionText)
0x6e365  ldarg.0
0x6e366  ldfld    string[] <>c__DisplayClass58_0::matchColumns
0x6e36b  call     void Microsoft.Crm.SharedDatabase.DatabaseService::VerifyMatchColumns(string[] matchColumns)
0x6e370  ldarg.0
0x6e371  ldfld    class Microsoft.Crm.Data.PropertyBag <>c__DisplayClass58_0::updateColumnsOnMatch
0x6e376  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype Microsoft.Crm.Data.PropertyEntry> Microsoft.Crm.Data.PropertyBag::RetrievePropertyEntries()
0x6e37b  ldsfld   class [mscorlib]System.Func`2<valuetype Microsoft.Crm.Data.PropertyEntry, bool> <>c::<>9__58_1
0x6e380  dup
0x6e381  brtrue.s loc_6E39A
0x6e383  pop
0x6e384  ldsfld   class <>c <>c::<>9
0x6e389  ldftn    instance bool <>c::<BulkUpsert>b__58_1(valuetype Microsoft.Crm.Data.PropertyEntry x)
0x6e38f  newobj   instance void class [mscorlib]System.Func`2<valuetype Microsoft.Crm.Data.PropertyEntry, bool>::.ctor(object, native int)
0x6e394  dup
0x6e395  stsfld   class [mscorlib]System.Func`2<valuetype Microsoft.Crm.Data.PropertyEntry, bool> <>c::<>9__58_1
0x6e39a  call     T0x2B00011B
0x6e39f  ldsfld   class [mscorlib]System.Func`2<valuetype Microsoft.Crm.Data.PropertyEntry, string> <>c::<>9__58_2
0x6e3a4  dup
0x6e3a5  brtrue.s loc_6E3BE
0x6e3a7  pop
0x6e3a8  ldsfld   class <>c <>c::<>9
0x6e3ad  ldftn    instance string <>c::<BulkUpsert>b__58_2(valuetype Microsoft.Crm.Data.PropertyEntry x)
0x6e3b3  newobj   instance void class [mscorlib]System.Func`2<valuetype Microsoft.Crm.Data.PropertyEntry, string>::.ctor(object, native int)
0x6e3b8  dup
0x6e3b9  stsfld   class [mscorlib]System.Func`2<valuetype Microsoft.Crm.Data.PropertyEntry, string> <>c::<>9__58_2
0x6e3be  call     T0x2B00002D
0x6e3c3  stloc.0
0x6e3c4  ldarg.0
0x6e3c5  ldfld    class Microsoft.Crm.Data.PropertyBag[] <>c__DisplayClass58_0::rows
0x6e3ca  call     T0x2B000118
0x6e3cf  ldloc.0
0x6e3d0  ldstr    aColumnsToCopyF// "Columns to copy from the source table m"...
0x6e3d5  call     void Microsoft.Crm.SharedDatabase.DatabaseService::VerifyBulkUpsertColumns(class Microsoft.Crm.Data.PropertyBag row, class [mscorlib]System.Collections.Generic.IEnumerable`1<string> matchColumns, string exceptionText)
0x6e3da  ldarg.0
0x6e3db  ldfld    class Microsoft.Crm.SharedDatabase.DatabaseService <>c__DisplayClass58_0::<>4__this
0x6e3e0  ldarg.0
0x6e3e1  ldfld    class Microsoft.Crm.Data.PropertyBag <>c__DisplayClass58_0::updateColumnsOnMatch
0x6e3e6  call     instance class ColumnSetDescription Microsoft.Crm.SharedDatabase.DatabaseService::CheckColumns(class Microsoft.Crm.Data.PropertyBag columnSet)
0x6e3eb  callvirt instance bool ColumnSetDescription::get_HasPropertiesColumns()
0x6e3f0  brfalse.s loc_6E3FD
0x6e3f2  ldstr    aBulkupsertDoes_0// "BulkUpsert does not support creating or"...
0x6e3f7  newobj   instance void Microsoft.Crm.CrmNotImplementedException::.ctor(string objectName)
0x6e3fc  throw
0x6e3fd  ldarg.0
0x6e3fe  ldfld    class Microsoft.Crm.SharedDatabase.DatabaseService <>c__DisplayClass58_0::<>4__this
0x6e403  ldarg.0
0x6e404  ldfld    class [mscorlib]System.Action <>c__DisplayClass58_0::<>9__3
0x6e409  dup
0x6e40a  brtrue.s loc_6E422
0x6e40c  pop
0x6e40d  ldarg.0
0x6e40e  ldarg.0
0x6e40f  ldftn    instance void <>c__DisplayClass58_0::<BulkUpsert>b__3()
0x6e415  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x6e41a  dup
0x6e41b  stloc.3
0x6e41c  stfld    class [mscorlib]System.Action <>c__DisplayClass58_0::<>9__3
0x6e421  ldloc.3
0x6e422  ldc.i4.0
0x6e423  call     instance void Microsoft.Crm.SharedDatabase.DatabaseService::MeasurePerformance(class [mscorlib]System.Action executeAction, bool readQuery)
0x6e428  leave.s  loc_6E436
0x6e42a  ldarg.0
0x6e42b  ldfld    class Microsoft.Crm.SharedDatabase.DatabaseService <>c__DisplayClass58_0::<>4__this
0x6e430  call     instance void Microsoft.Crm.SharedDatabase.DatabaseService::Clear()
0x6e435  endfinally
0x6e436  ret
```
