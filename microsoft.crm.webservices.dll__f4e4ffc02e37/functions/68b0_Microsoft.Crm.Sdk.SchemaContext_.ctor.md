# Microsoft.Crm.Sdk.SchemaContext::.ctor

- ea: `0x68b0`
- end: `0x6908`
- name: `Microsoft.Crm.Sdk.SchemaContext::.ctor`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xa480`

## callees

- `0x7ed0`

## string_xrefs

- `0x68c2`: `serviceDescription`

## pseudocode

```c

```

## disassembly

```asm
0x68b0  ldarg.0
0x68b1  call     instance void [mscorlib]System.Object::.ctor()
0x68b6  ldarg.1
0x68b7  ldstr    aSchemas// "schemas"
0x68bc  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x68c1  ldarg.2
0x68c2  ldstr    aServicedescrip// "serviceDescription"
0x68c7  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x68cc  ldarg.3
0x68cd  ldstr    aNamespacename// "namespaceName"
0x68d2  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x68d7  ldarg.0
0x68d8  ldarg.1
0x68d9  stfld    class [System.Xml]System.Xml.Serialization.XmlSchemas Microsoft.Crm.Sdk.SchemaContext::_schemas
0x68de  ldarg.0
0x68df  ldarg.2
0x68e0  stfld    class Microsoft.Crm.Sdk.ServiceDescription Microsoft.Crm.Sdk.SchemaContext::_serviceDescription
0x68e5  ldarg.0
0x68e6  ldarg.3
0x68e7  stfld    string Microsoft.Crm.Sdk.SchemaContext::_currentNamespace
0x68ec  ldarg.0
0x68ed  ldarg.s  4
0x68ef  stfld    bool Microsoft.Crm.Sdk.SchemaContext::_renderPrivate
0x68f4  ldarg.0
0x68f5  ldnull
0x68f6  stfld    class Microsoft.Crm.Sdk.RequestDescription Microsoft.Crm.Sdk.SchemaContext::_request
0x68fb  ldarg.0
0x68fc  ldarg.0
0x68fd  newobj   instance void Microsoft.Crm.Sdk.AttributeTypeSchemaCache::.ctor(class Microsoft.Crm.Sdk.SchemaContext context)
0x6902  stfld    class Microsoft.Crm.Sdk.AttributeTypeSchemaCache Microsoft.Crm.Sdk.SchemaContext::_attributeTypeSchemaCache
0x6907  ret
```
