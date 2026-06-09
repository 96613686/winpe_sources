# Microsoft.Crm.SharedDatabase.DatabaseService::.cctor

- ea: `0x647b0`
- end: `0x64814`
- name: `Microsoft.Crm.SharedDatabase.DatabaseService::.cctor`
- size: `100`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x64690`

## string_xrefs

- `0x647ee`: `YammerOathAccessToken`
- `0x647f6`: `AzureMLRecommendationServiceAccountKey`
- `0x647fe`: `AzureMLTextAnalyticsServiceAccountKey`

## pseudocode

```c

```

## disassembly

```asm
0x647b0  call     class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILoggerFactory [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmLoggerFactory::get_LoggerFactory()
0x647b5  ldtoken  Microsoft.Crm.SharedDatabase.DatabaseService
0x647ba  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x647bf  callvirt instance string [mscorlib]System.Type::get_Namespace()
0x647c4  callvirt instance class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILoggerFactory::CreateLogger(string)
0x647c9  stsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.SharedDatabase.DatabaseService::_logger
0x647ce  ldc.i4.6
0x647cf  newarr   [mscorlib]System.String
0x647d4  dup
0x647d5  ldc.i4.0
0x647d6  ldstr    aDatabasemaster// "DatabaseMasterKeyPassword"
0x647db  stelem.ref
0x647dc  dup
0x647dd  ldc.i4.1
0x647de  ldstr    aSymmetrickeypa// "SymmetricKeyPassword"
0x647e3  stelem.ref
0x647e4  dup
0x647e5  ldc.i4.2
0x647e6  ldstr    aSymmetrickeyso// "SymmetricKeySource"
0x647eb  stelem.ref
0x647ec  dup
0x647ed  ldc.i4.3
0x647ee  ldstr    aYammeroathacce// "YammerOathAccessToken"
0x647f3  stelem.ref
0x647f4  dup
0x647f5  ldc.i4.4
0x647f6  ldstr    aAzuremlrecomme// "AzureMLRecommendationServiceAccountKey"
0x647fb  stelem.ref
0x647fc  dup
0x647fd  ldc.i4.5
0x647fe  ldstr    aAzuremltextana// "AzureMLTextAnalyticsServiceAccountKey"
0x64803  stelem.ref
0x64804  stsfld   string[] Microsoft.Crm.SharedDatabase.DatabaseService::OrganizationEncryptedColumns
0x64809  call     class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [System.Data]System.Data.SqlDbType, class [mscorlib]System.Type> Microsoft.Crm.SharedDatabase.DatabaseService::GetDbTypeMapping()
0x6480e  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [System.Data]System.Data.SqlDbType, class [mscorlib]System.Type> Microsoft.Crm.SharedDatabase.DatabaseService::_dbTypeMapping
0x64813  ret
```
