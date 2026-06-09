# Microsoft.Crm.Extensibility.OData.CrmODataModelProvider::.cctor

- ea: `0x1b530`
- end: `0x1b559`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataModelProvider::.cctor`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x1b530`: `<?xml version="1.0" ?>\n<!--\n  Copyright (c) Microsoft Corporation.  All rights reserved.\n  Licensed under the MIT License.  See license.md at\n  https://github.com/OData/vocabularies for license information.\n-->\n<edmx:Edmx Version="4.0" xmlns:edmx="http://docs.oasis-open.org/odata/ns/edmx">\n  <edmx:Reference Uri="http://docs.oasis-open.org/odata/odata/v4.0/os/vocabularies/Org.OData.Core.V1.xml">\n	<edmx:Include Alias="Core" Namespace="Org.OData.Core.V1"/>\n  </edmx:Reference>\n  `

## pseudocode

```c

```

## disassembly

```asm
0x1b530  ldstr    aXmlVersion10Co// "<?xml version=\"1.0\" ?>\r\n<!--\r\n  C"...
0x1b535  stsfld   string Microsoft.Crm.Extensibility.OData.CrmODataModelProvider::odataCommunityDisplayEdmx
0x1b53a  call     class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILoggerFactory [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmLoggerFactory::get_LoggerFactory()
0x1b53f  ldtoken  Microsoft.Crm.Extensibility.OData.CrmODataModelProvider
0x1b544  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b549  callvirt instance string [mscorlib]System.Type::get_FullName()
0x1b54e  callvirt instance class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILoggerFactory::CreateLogger(string)
0x1b553  stsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Extensibility.OData.CrmODataModelProvider::Logger
0x1b558  ret
```
