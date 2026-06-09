# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializerContract::get_ReadMethods

- ea: `0x1a20a0`
- end: `0x1a21c7`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializerContract::get_ReadMethods`
- size: `295`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1a20a0`

## string_xrefs

- `0x1a20b2`: `Microsoft.Crm.SdkTypeProxy.CrmService:Microsoft.Crm.SdkTypeProxy.Response Execute(Microsoft.Crm.SdkTypeProxy.Request):Response`
- `0x1a20b7`: `Read1618_ExecuteResponse`
- `0x1a20c2`: `Microsoft.Crm.SdkTypeProxy.CrmService:Microsoft.Crm.SdkTypeProxy.Response Execute(Microsoft.Crm.SdkTypeProxy.Request):OutHeaders`
- `0x1a20c7`: `Read1619_ExecuteResponseOutHeaders`
- `0x1a20d2`: `Microsoft.Crm.SdkTypeProxy.CrmService:System.String Fetch(System.String):Response`
- `0x1a20d7`: `Read1620_FetchResponse`
- `0x1a20e2`: `Microsoft.Crm.SdkTypeProxy.CrmService:System.String Fetch(System.String):OutHeaders`
- `0x1a20e7`: `Read1621_FetchResponseOutHeaders`
- `0x1a20f2`: `Microsoft.Crm.SdkTypeProxy.CrmService:System.Guid Create(Microsoft.Crm.Sdk.BusinessEntity):Response`
- `0x1a20f7`: `Read1622_CreateResponse`
- `0x1a2102`: `Microsoft.Crm.SdkTypeProxy.CrmService:System.Guid Create(Microsoft.Crm.Sdk.BusinessEntity):OutHeaders`
- `0x1a2107`: `Read1623_CreateResponseOutHeaders`
- `0x1a2112`: `Microsoft.Crm.SdkTypeProxy.CrmService:Void Delete(System.String, System.Guid):Response`
- `0x1a2117`: `Read1624_DeleteResponse`
- `0x1a2122`: `Microsoft.Crm.SdkTypeProxy.CrmService:Void Delete(System.String, System.Guid):OutHeaders`
- `0x1a2127`: `Read1625_DeleteResponseOutHeaders`
- `0x1a2132`: `Microsoft.Crm.SdkTypeProxy.CrmService:Microsoft.Crm.Sdk.BusinessEntity Retrieve(System.String, System.Guid, Microsoft.Crm.Sdk.Query.ColumnSetBase):Response`
- `0x1a2137`: `Read1626_RetrieveResponse`
- `0x1a2142`: `Microsoft.Crm.SdkTypeProxy.CrmService:Microsoft.Crm.Sdk.BusinessEntity Retrieve(System.String, System.Guid, Microsoft.Crm.Sdk.Query.ColumnSetBase):OutHeaders`
- `0x1a2147`: `Read1627_RetrieveResponseOutHeaders`
- `0x1a2152`: `Microsoft.Crm.SdkTypeProxy.CrmService:Microsoft.Crm.Sdk.BusinessEntityCollection RetrieveMultiple(Microsoft.Crm.Sdk.Query.QueryBase):Response`
- `0x1a2157`: `Read1628_RetrieveMultipleResponse`
- `0x1a2162`: `Microsoft.Crm.SdkTypeProxy.CrmService:Microsoft.Crm.Sdk.BusinessEntityCollection RetrieveMultiple(Microsoft.Crm.Sdk.Query.QueryBase):OutHeaders`
- `0x1a2167`: `Read1629_Item`
- `0x1a2172`: `Microsoft.Crm.SdkTypeProxy.CrmService:Void Update(Microsoft.Crm.Sdk.BusinessEntity):Response`
- `0x1a2177`: `Read1630_UpdateResponse`
- `0x1a2182`: `Microsoft.Crm.SdkTypeProxy.CrmService:Void Update(Microsoft.Crm.Sdk.BusinessEntity):OutHeaders`
- `0x1a2187`: `Read1631_UpdateResponseOutHeaders`
- `0x1a2192`: `Microsoft.Crm.SdkTypeProxy.Metadata.MetadataService:Microsoft.Crm.SdkTypeProxy.Metadata.MetadataServiceResponse Execute(Microsoft.Crm.SdkTypeProxy.Metadata.MetadataServiceRequest):Response`
- `0x1a2197`: `Read1632_ExecuteResponse`
- `0x1a21a2`: `Microsoft.Crm.SdkTypeProxy.Metadata.MetadataService:Microsoft.Crm.SdkTypeProxy.Metadata.MetadataServiceResponse Execute(Microsoft.Crm.SdkTypeProxy.Metadata.MetadataServiceRequest):OutHeaders`
- `0x1a21a7`: `Read1633_ExecuteResponseOutHeaders`

## pseudocode

```c

```

## disassembly

```asm
0x1a20a0  ldarg.0
0x1a20a1  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializerContract::readMethods
0x1a20a6  brtrue   loc_1A21C0
0x1a20ab  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x1a20b0  stloc.0
0x1a20b1  ldloc.0
0x1a20b2  ldstr    aMicrosoftCrmSd_84// "Microsoft.Crm.SdkTypeProxy.CrmService:M"...
0x1a20b7  ldstr    aRead1618Execut// "Read1618_ExecuteResponse"
0x1a20bc  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x1a20c1  ldloc.0
0x1a20c2  ldstr    aMicrosoftCrmSd_85// "Microsoft.Crm.SdkTypeProxy.CrmService:M"...
0x1a20c7  ldstr    aRead1619Execut// "Read1619_ExecuteResponseOutHeaders"
0x1a20cc  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x1a20d1  ldloc.0
0x1a20d2  ldstr    aMicrosoftCrmSd_86// "Microsoft.Crm.SdkTypeProxy.CrmService:S"...
0x1a20d7  ldstr    aRead1620Fetchr// "Read1620_FetchResponse"
0x1a20dc  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x1a20e1  ldloc.0
0x1a20e2  ldstr    aMicrosoftCrmSd_87// "Microsoft.Crm.SdkTypeProxy.CrmService:S"...
0x1a20e7  ldstr    aRead1621Fetchr// "Read1621_FetchResponseOutHeaders"
0x1a20ec  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x1a20f1  ldloc.0
0x1a20f2  ldstr    aMicrosoftCrmSd_88// "Microsoft.Crm.SdkTypeProxy.CrmService:S"...
0x1a20f7  ldstr    aRead1622Create// "Read1622_CreateResponse"
0x1a20fc  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x1a2101  ldloc.0
0x1a2102  ldstr    aMicrosoftCrmSd_89// "Microsoft.Crm.SdkTypeProxy.CrmService:S"...
0x1a2107  ldstr    aRead1623Create// "Read1623_CreateResponseOutHeaders"
0x1a210c  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x1a2111  ldloc.0
0x1a2112  ldstr    aMicrosoftCrmSd_90// "Microsoft.Crm.SdkTypeProxy.CrmService:V"...
0x1a2117  ldstr    aRead1624Delete// "Read1624_DeleteResponse"
0x1a211c  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x1a2121  ldloc.0
0x1a2122  ldstr    aMicrosoftCrmSd_91// "Microsoft.Crm.SdkTypeProxy.CrmService:V"...
0x1a2127  ldstr    aRead1625Delete// "Read1625_DeleteResponseOutHeaders"
0x1a212c  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x1a2131  ldloc.0
0x1a2132  ldstr    aMicrosoftCrmSd_92// "Microsoft.Crm.SdkTypeProxy.CrmService:M"...
0x1a2137  ldstr    aRead1626Retrie// "Read1626_RetrieveResponse"
0x1a213c  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x1a2141  ldloc.0
0x1a2142  ldstr    aMicrosoftCrmSd_93// "Microsoft.Crm.SdkTypeProxy.CrmService:M"...
0x1a2147  ldstr    aRead1627Retrie// "Read1627_RetrieveResponseOutHeaders"
0x1a214c  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x1a2151  ldloc.0
0x1a2152  ldstr    aMicrosoftCrmSd_94// "Microsoft.Crm.SdkTypeProxy.CrmService:M"...
0x1a2157  ldstr    aRead1628Retrie// "Read1628_RetrieveMultipleResponse"
0x1a215c  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x1a2161  ldloc.0
0x1a2162  ldstr    aMicrosoftCrmSd_95// "Microsoft.Crm.SdkTypeProxy.CrmService:M"...
0x1a2167  ldstr    aRead1629Item// "Read1629_Item"
0x1a216c  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x1a2171  ldloc.0
0x1a2172  ldstr    aMicrosoftCrmSd_96// "Microsoft.Crm.SdkTypeProxy.CrmService:V"...
0x1a2177  ldstr    aRead1630Update// "Read1630_UpdateResponse"
0x1a217c  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x1a2181  ldloc.0
0x1a2182  ldstr    aMicrosoftCrmSd_97// "Microsoft.Crm.SdkTypeProxy.CrmService:V"...
0x1a2187  ldstr    aRead1631Update// "Read1631_UpdateResponseOutHeaders"
0x1a218c  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x1a2191  ldloc.0
0x1a2192  ldstr    aMicrosoftCrmSd_98// "Microsoft.Crm.SdkTypeProxy.Metadata.Met"...
0x1a2197  ldstr    aRead1632Execut// "Read1632_ExecuteResponse"
0x1a219c  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x1a21a1  ldloc.0
0x1a21a2  ldstr    aMicrosoftCrmSd_99// "Microsoft.Crm.SdkTypeProxy.Metadata.Met"...
0x1a21a7  ldstr    aRead1633Execut// "Read1633_ExecuteResponseOutHeaders"
0x1a21ac  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x1a21b1  ldarg.0
0x1a21b2  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializerContract::readMethods
0x1a21b7  brtrue.s loc_1A21C0
0x1a21b9  ldarg.0
0x1a21ba  ldloc.0
0x1a21bb  stfld    class [mscorlib]System.Collections.Hashtable Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializerContract::readMethods
0x1a21c0  ldarg.0
0x1a21c1  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializerContract::readMethods
0x1a21c6  ret
```
