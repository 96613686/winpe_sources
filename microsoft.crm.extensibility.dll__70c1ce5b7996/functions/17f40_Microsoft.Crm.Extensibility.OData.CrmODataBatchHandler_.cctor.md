# Microsoft.Crm.Extensibility.OData.CrmODataBatchHandler::.cctor

- ea: `0x17f40`
- end: `0x1803c`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataBatchHandler::.cctor`
- size: `252`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## string_xrefs

- `0x17f6a`: `DELETE`
- `0x17fbc`: `UpdateOptionValue`
- `0x17fc8`: `DeleteOptionValue`
- `0x17fe0`: `UpdateStateValue`
- `0x17fec`: `CreateCustomerRelationships`

## pseudocode

```c

```

## disassembly

```asm
0x17f40  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor()
0x17f45  dup
0x17f46  ldstr    aPost_0// "POST"
0x17f4b  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x17f50  pop
0x17f51  dup
0x17f52  ldstr    aPut_0// "PUT"
0x17f57  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x17f5c  pop
0x17f5d  dup
0x17f5e  ldstr    aPatch_0// "PATCH"
0x17f63  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x17f68  pop
0x17f69  dup
0x17f6a  ldstr    aDelete_1// "DELETE"
0x17f6f  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x17f74  pop
0x17f75  stsfld   class [System.Core]System.Collections.Generic.HashSet`1<string> Microsoft.Crm.Extensibility.OData.CrmODataBatchHandler::_NonSafeOperations
0x17f7a  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor()
0x17f7f  dup
0x17f80  ldstr    aEntitydefiniti// "EntityDefinitions"
0x17f85  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x17f8a  pop
0x17f8b  dup
0x17f8c  ldstr    aRelationshipde// "RelationshipDefinitions"
0x17f91  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x17f96  pop
0x17f97  dup
0x17f98  ldstr    aGlobaloptionse// "GlobalOptionSetDefinitions"
0x17f9d  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x17fa2  pop
0x17fa3  dup
0x17fa4  ldstr    aManagedpropert_0// "ManagedPropertyDefinitions"
0x17fa9  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x17fae  pop
0x17faf  dup
0x17fb0  ldstr    aInsertoptionva// "InsertOptionValue"
0x17fb5  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x17fba  pop
0x17fbb  dup
0x17fbc  ldstr    aUpdateoptionva// "UpdateOptionValue"
0x17fc1  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x17fc6  pop
0x17fc7  dup
0x17fc8  ldstr    aDeleteoptionva// "DeleteOptionValue"
0x17fcd  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x17fd2  pop
0x17fd3  dup
0x17fd4  ldstr    aInsertstatusva// "InsertStatusValue"
0x17fd9  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x17fde  pop
0x17fdf  dup
0x17fe0  ldstr    aUpdatestateval// "UpdateStateValue"
0x17fe5  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x17fea  pop
0x17feb  dup
0x17fec  ldstr    aCreatecustomer// "CreateCustomerRelationships"
0x17ff1  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x17ff6  pop
0x17ff7  stsfld   class [System.Core]System.Collections.Generic.HashSet`1<string> Microsoft.Crm.Extensibility.OData.CrmODataBatchHandler::_MetadataPaths
0x17ffc  ldstr    aApiDataVDD// "api/data/v\\d+\\.\\d+/([^/(]+)"
0x18001  stsfld   string Microsoft.Crm.Extensibility.OData.CrmODataBatchHandler::RegexPattern
0x18006  ldsfld   string Microsoft.Crm.Extensibility.OData.CrmODataBatchHandler::RegexPattern
0x1800b  ldc.i4.s 9
0x1800d  call     class [System]System.Text.RegularExpressions.Regex [Microsoft.Crm.Core]Microsoft.Crm.CrmRegexCache::GetRegex(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x18012  stsfld   class [System]System.Text.RegularExpressions.Regex Microsoft.Crm.Extensibility.OData.CrmODataBatchHandler::SegmentExtractionRegex
0x18017  call     class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILoggerFactory [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmLoggerFactory::get_LoggerFactory()
0x1801c  ldtoken  Microsoft.Crm.Extensibility.OData.CrmODataBatchHandler
0x18021  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18026  callvirt instance string [mscorlib]System.Type::get_FullName()
0x1802b  callvirt instance class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILoggerFactory::CreateLogger(string)
0x18030  stsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Extensibility.OData.CrmODataBatchHandler::Logger
0x18035  ldc.i4.0
0x18036  stsfld   int32 Microsoft.Crm.Extensibility.OData.CrmODataBatchHandler::BatchRequestCounter
0x1803b  ret
```
