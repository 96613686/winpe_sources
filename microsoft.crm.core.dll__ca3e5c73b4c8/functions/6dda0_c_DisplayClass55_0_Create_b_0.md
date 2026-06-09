# <>c__DisplayClass55_0::<Create>b__0

- ea: `0x6dda0`
- end: `0x6de21`
- name: `<>c__DisplayClass55_0::<Create>b__0`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x5de00`
- `0x61960`

## string_xrefs

- `0x6de11`: `Create`
- `0x6de16`: `D:\a\1\s\src\Platform\Core\DataServices\ObjectModel\DatabaseService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x6dda0  ldsfld   string Microsoft.Crm.CustomPropertyConstants::CrmServiceName
0x6dda5  call     string Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::get_ServiceIdentifier()
0x6ddaa  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x6ddaf  ldsfld   string Microsoft.Crm.CustomPropertyConstants::Caller
0x6ddb4  ldarg.0
0x6ddb5  ldfld    string <>c__DisplayClass55_0::memberName
0x6ddba  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x6ddbf  ldsfld   string Microsoft.Crm.CustomPropertyConstants::CallerSourceFile
0x6ddc4  ldarg.0
0x6ddc5  ldfld    string <>c__DisplayClass55_0::sourceFilePath
0x6ddca  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x6ddcf  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x6ddd4  ldsfld   string Microsoft.Crm.CustomPropertyConstants::CallerLineNumber
0x6ddd9  ldarg.0
0x6ddda  ldflda   int32 <>c__DisplayClass55_0::sourceLineNumber
0x6dddf  call     instance string [mscorlib]System.Int32::ToString()
0x6dde4  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x6dde9  ldsfld   string Microsoft.Crm.CustomPropertyConstants::Table
0x6ddee  ldarg.0
0x6ddef  ldfld    string <>c__DisplayClass55_0::tableName
0x6ddf4  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x6ddf9  ldarg.0
0x6ddfa  ldfld    class Microsoft.Crm.SharedDatabase.DatabaseService <>c__DisplayClass55_0::<>4__this
0x6ddff  ldc.i4.1
0x6de00  ldarg.0
0x6de01  ldfld    string <>c__DisplayClass55_0::tableName
0x6de06  ldarg.0
0x6de07  ldfld    class Microsoft.Crm.Data.PropertyBag <>c__DisplayClass55_0::columnSet
0x6de0c  ldc.i4   0x2A0
0x6de11  ldstr    aCreate// "Create"
0x6de16  ldstr    aDA1SSrcPlatfor_44// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x6de1b  call     instance object Microsoft.Crm.SharedDatabase.DatabaseService::Create(bool fireNotification, string tableName, class Microsoft.Crm.Data.PropertyBag columnSet, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x6de20  ret
```
