# <>c__DisplayClass71_0::<Update>b__0

- ea: `0x6e6a0`
- end: `0x6e727`
- name: `<>c__DisplayClass71_0::<Update>b__0`
- size: `135`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, installer_update`

## callees

- `0x5de00`
- `0x62500`

## string_xrefs

- `0x6e717`: `Update`
- `0x6e71c`: `D:\a\1\s\src\Platform\Core\DataServices\ObjectModel\DatabaseService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x6e6a0  ldsfld   string Microsoft.Crm.CustomPropertyConstants::CrmServiceName
0x6e6a5  call     string Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::get_ServiceIdentifier()
0x6e6aa  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x6e6af  ldsfld   string Microsoft.Crm.CustomPropertyConstants::Caller
0x6e6b4  ldarg.0
0x6e6b5  ldfld    string <>c__DisplayClass71_0::memberName
0x6e6ba  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x6e6bf  ldsfld   string Microsoft.Crm.CustomPropertyConstants::CallerSourceFile
0x6e6c4  ldarg.0
0x6e6c5  ldfld    string <>c__DisplayClass71_0::sourceFilePath
0x6e6ca  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x6e6cf  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x6e6d4  ldsfld   string Microsoft.Crm.CustomPropertyConstants::CallerLineNumber
0x6e6d9  ldarg.0
0x6e6da  ldflda   int32 <>c__DisplayClass71_0::sourceLineNumber
0x6e6df  call     instance string [mscorlib]System.Int32::ToString()
0x6e6e4  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x6e6e9  ldsfld   string Microsoft.Crm.CustomPropertyConstants::Table
0x6e6ee  ldarg.0
0x6e6ef  ldfld    string <>c__DisplayClass71_0::tableName
0x6e6f4  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x6e6f9  ldarg.0
0x6e6fa  ldfld    class Microsoft.Crm.SharedDatabase.DatabaseService <>c__DisplayClass71_0::<>4__this
0x6e6ff  ldarg.0
0x6e700  ldfld    string <>c__DisplayClass71_0::tableName
0x6e705  ldarg.0
0x6e706  ldfld    class Microsoft.Crm.Data.PropertyBag <>c__DisplayClass71_0::columnSet
0x6e70b  ldarg.0
0x6e70c  ldfld    class Microsoft.Crm.Data.PropertyBag[] <>c__DisplayClass71_0::conditions
0x6e711  ldc.i4.1
0x6e712  ldc.i4   0x578
0x6e717  ldstr    aUpdate// "Update"
0x6e71c  ldstr    aDA1SSrcPlatfor_44// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x6e721  call     instance int32 Microsoft.Crm.SharedDatabase.DatabaseService::Update(string tableName, class Microsoft.Crm.Data.PropertyBag columnSet, class Microsoft.Crm.Data.PropertyBag[] conditions, bool fireNotification, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x6e726  ret
```
