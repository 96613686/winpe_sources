# Microsoft.Crm.Entities.SdkMessagePair::ReadAttribute

- ea: `0x39c0`
- end: `0x3a09`
- name: `Microsoft.Crm.Entities.SdkMessagePair::ReadAttribute`
- size: `73`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x39c0`

## pseudocode

```c

```

## disassembly

```asm
0x39c0  ldarg.3
0x39c1  ldstr    aSdkmessagerequ// "sdkmessagerequest"
0x39c6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x39cb  brfalse.s loc_39DF
0x39cd  ldarg.0
0x39ce  ldfld    class Microsoft.Crm.Entities.SdkMessageRequest Microsoft.Crm.Entities.SdkMessagePair::_messageRequest
0x39d3  ldarg.1
0x39d4  callvirt instance class [System.Xml]System.Xml.XmlReader [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityDeserializationContext::get_Reader()
0x39d9  ldarg.2
0x39da  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::Deserialize(class [System.Xml]System.Xml.XmlReader, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IEntityDeserializationStrategy)
0x39df  ldarg.3
0x39e0  ldstr    aSdkmessageresp// "sdkmessageresponse"
0x39e5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x39ea  brfalse.s loc_39FF
0x39ec  ldarg.0
0x39ed  ldfld    class Microsoft.Crm.Entities.SdkMessageResponse Microsoft.Crm.Entities.SdkMessagePair::_messageResponse
0x39f2  ldarg.1
0x39f3  callvirt instance class [System.Xml]System.Xml.XmlReader [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityDeserializationContext::get_Reader()
0x39f8  ldarg.2
0x39f9  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::Deserialize(class [System.Xml]System.Xml.XmlReader, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IEntityDeserializationStrategy)
0x39fe  ret
0x39ff  ldarg.0
0x3a00  ldarg.1
0x3a01  ldarg.2
0x3a02  ldarg.3
0x3a03  call     instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::ReadAttribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityDeserializationContext, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IEntityDeserializationStrategy, string)
0x3a08  ret
```
