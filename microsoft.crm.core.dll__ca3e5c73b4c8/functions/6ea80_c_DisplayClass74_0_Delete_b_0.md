# <>c__DisplayClass74_0::<Delete>b__0

- ea: `0x6ea80`
- end: `0x6eb01`
- name: `<>c__DisplayClass74_0::<Delete>b__0`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task`

## callees

- `0x5de00`
- `0x62600`

## string_xrefs

- `0x6eaf1`: `Delete`
- `0x6eaf6`: `D:\a\1\s\src\Platform\Core\DataServices\ObjectModel\DatabaseService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x6ea80  ldsfld   string Microsoft.Crm.CustomPropertyConstants::CrmServiceName
0x6ea85  call     string Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::get_ServiceIdentifier()
0x6ea8a  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x6ea8f  ldsfld   string Microsoft.Crm.CustomPropertyConstants::Caller
0x6ea94  ldarg.0
0x6ea95  ldfld    string <>c__DisplayClass74_0::memberName
0x6ea9a  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x6ea9f  ldsfld   string Microsoft.Crm.CustomPropertyConstants::CallerSourceFile
0x6eaa4  ldarg.0
0x6eaa5  ldfld    string <>c__DisplayClass74_0::sourceFilePath
0x6eaaa  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x6eaaf  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x6eab4  ldsfld   string Microsoft.Crm.CustomPropertyConstants::CallerLineNumber
0x6eab9  ldarg.0
0x6eaba  ldflda   int32 <>c__DisplayClass74_0::sourceLineNumber
0x6eabf  call     instance string [mscorlib]System.Int32::ToString()
0x6eac4  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x6eac9  ldsfld   string Microsoft.Crm.CustomPropertyConstants::Table
0x6eace  ldarg.0
0x6eacf  ldfld    string <>c__DisplayClass74_0::tableName
0x6ead4  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x6ead9  ldarg.0
0x6eada  ldfld    class Microsoft.Crm.SharedDatabase.DatabaseService <>c__DisplayClass74_0::<>4__this
0x6eadf  ldarg.0
0x6eae0  ldfld    string <>c__DisplayClass74_0::tableName
0x6eae5  ldarg.0
0x6eae6  ldfld    class Microsoft.Crm.Data.PropertyBag[] <>c__DisplayClass74_0::conditions
0x6eaeb  ldc.i4.1
0x6eaec  ldc.i4   0x60B
0x6eaf1  ldstr    aDelete_0// "Delete"
0x6eaf6  ldstr    aDA1SSrcPlatfor_44// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x6eafb  call     instance int32 Microsoft.Crm.SharedDatabase.DatabaseService::Delete(string tableName, class Microsoft.Crm.Data.PropertyBag[] conditions, bool flushTable, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x6eb00  ret
```
