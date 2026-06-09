# Microsoft.Crm.Entities.SdkMessagePair::SerializeAttributes

- ea: `0x3960`
- end: `0x3999`
- name: `Microsoft.Crm.Entities.SdkMessagePair::SerializeAttributes`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x3960  ldarg.0
0x3961  ldarg.1
0x3962  ldarg.2
0x3963  call     instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SerializeAttributes(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntitySerializationContext, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IEntitySerializationStrategy)
0x3968  ldarg.0
0x3969  ldfld    class Microsoft.Crm.Entities.SdkMessageRequest Microsoft.Crm.Entities.SdkMessagePair::_messageRequest
0x396e  ldarg.1
0x396f  callvirt instance class [System.Xml]System.Xml.XmlWriter [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntitySerializationContext::get_Writer()
0x3974  ldarg.1
0x3975  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntitySerializationContext::get_IncludeRootElement()
0x397a  ldarg.2
0x397b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::Serialize(class [System.Xml]System.Xml.XmlWriter, bool, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IEntitySerializationStrategy)
0x3980  ldarg.0
0x3981  ldfld    class Microsoft.Crm.Entities.SdkMessageResponse Microsoft.Crm.Entities.SdkMessagePair::_messageResponse
0x3986  ldarg.1
0x3987  callvirt instance class [System.Xml]System.Xml.XmlWriter [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntitySerializationContext::get_Writer()
0x398c  ldarg.1
0x398d  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntitySerializationContext::get_IncludeRootElement()
0x3992  ldarg.2
0x3993  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::Serialize(class [System.Xml]System.Xml.XmlWriter, bool, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IEntitySerializationStrategy)
0x3998  ret
```
