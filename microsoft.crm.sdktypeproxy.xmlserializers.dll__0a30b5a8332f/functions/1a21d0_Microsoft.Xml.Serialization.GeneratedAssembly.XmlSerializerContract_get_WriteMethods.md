# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializerContract::get_WriteMethods

- ea: `0x1a21d0`
- end: `0x1a22f7`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializerContract::get_WriteMethods`
- size: `295`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1a21d0`

## string_xrefs

- `0x1a21e2`: `Microsoft.Crm.SdkTypeProxy.CrmService:Microsoft.Crm.SdkTypeProxy.Response Execute(Microsoft.Crm.SdkTypeProxy.Request)`
- `0x1a21e7`: `Write1618_Execute`
- `0x1a21f2`: `Microsoft.Crm.SdkTypeProxy.CrmService:Microsoft.Crm.SdkTypeProxy.Response Execute(Microsoft.Crm.SdkTypeProxy.Request):InHeaders`
- `0x1a21f7`: `Write1619_ExecuteInHeaders`
- `0x1a2202`: `Microsoft.Crm.SdkTypeProxy.CrmService:System.String Fetch(System.String)`
- `0x1a2207`: `Write1620_Fetch`
- `0x1a2212`: `Microsoft.Crm.SdkTypeProxy.CrmService:System.String Fetch(System.String):InHeaders`
- `0x1a2217`: `Write1621_FetchInHeaders`
- `0x1a2222`: `Microsoft.Crm.SdkTypeProxy.CrmService:System.Guid Create(Microsoft.Crm.Sdk.BusinessEntity)`
- `0x1a2227`: `Write1622_Create`
- `0x1a2232`: `Microsoft.Crm.SdkTypeProxy.CrmService:System.Guid Create(Microsoft.Crm.Sdk.BusinessEntity):InHeaders`
- `0x1a2237`: `Write1623_CreateInHeaders`
- `0x1a2242`: `Microsoft.Crm.SdkTypeProxy.CrmService:Void Delete(System.String, System.Guid)`
- `0x1a2247`: `Write1624_Delete`
- `0x1a2252`: `Microsoft.Crm.SdkTypeProxy.CrmService:Void Delete(System.String, System.Guid):InHeaders`
- `0x1a2257`: `Write1625_DeleteInHeaders`
- `0x1a2262`: `Microsoft.Crm.SdkTypeProxy.CrmService:Microsoft.Crm.Sdk.BusinessEntity Retrieve(System.String, System.Guid, Microsoft.Crm.Sdk.Query.ColumnSetBase)`
- `0x1a2267`: `Write1626_Retrieve`
- `0x1a2272`: `Microsoft.Crm.SdkTypeProxy.CrmService:Microsoft.Crm.Sdk.BusinessEntity Retrieve(System.String, System.Guid, Microsoft.Crm.Sdk.Query.ColumnSetBase):InHeaders`
- `0x1a2277`: `Write1627_RetrieveInHeaders`
- `0x1a2282`: `Microsoft.Crm.SdkTypeProxy.CrmService:Microsoft.Crm.Sdk.BusinessEntityCollection RetrieveMultiple(Microsoft.Crm.Sdk.Query.QueryBase)`
- `0x1a2287`: `Write1628_RetrieveMultiple`
- `0x1a2292`: `Microsoft.Crm.SdkTypeProxy.CrmService:Microsoft.Crm.Sdk.BusinessEntityCollection RetrieveMultiple(Microsoft.Crm.Sdk.Query.QueryBase):InHeaders`
- `0x1a2297`: `Write1629_RetrieveMultipleInHeaders`
- `0x1a22a2`: `Microsoft.Crm.SdkTypeProxy.CrmService:Void Update(Microsoft.Crm.Sdk.BusinessEntity)`
- `0x1a22a7`: `Write1630_Update`
- `0x1a22b2`: `Microsoft.Crm.SdkTypeProxy.CrmService:Void Update(Microsoft.Crm.Sdk.BusinessEntity):InHeaders`
- `0x1a22b7`: `Write1631_UpdateInHeaders`
- `0x1a22c2`: `Microsoft.Crm.SdkTypeProxy.Metadata.MetadataService:Microsoft.Crm.SdkTypeProxy.Metadata.MetadataServiceResponse Execute(Microsoft.Crm.SdkTypeProxy.Metadata.MetadataServiceRequest)`
- `0x1a22c7`: `Write1632_Execute`
- `0x1a22d2`: `Microsoft.Crm.SdkTypeProxy.Metadata.MetadataService:Microsoft.Crm.SdkTypeProxy.Metadata.MetadataServiceResponse Execute(Microsoft.Crm.SdkTypeProxy.Metadata.MetadataServiceRequest):InHeaders`
- `0x1a22d7`: `Write1633_ExecuteInHeaders`

## pseudocode

```c

```

## disassembly

```asm
0x1a21d0  ldarg.0
0x1a21d1  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializerContract::writeMethods
0x1a21d6  brtrue   loc_1A22F0
0x1a21db  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x1a21e0  stloc.0
0x1a21e1  ldloc.0
0x1a21e2  ldstr    aMicrosoftCrmSd_100// "Microsoft.Crm.SdkTypeProxy.CrmService:M"...
0x1a21e7  ldstr    aWrite1618Execu// "Write1618_Execute"
0x1a21ec  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x1a21f1  ldloc.0
0x1a21f2  ldstr    aMicrosoftCrmSd_101// "Microsoft.Crm.SdkTypeProxy.CrmService:M"...
0x1a21f7  ldstr    aWrite1619Execu// "Write1619_ExecuteInHeaders"
0x1a21fc  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x1a2201  ldloc.0
0x1a2202  ldstr    aMicrosoftCrmSd_102// "Microsoft.Crm.SdkTypeProxy.CrmService:S"...
0x1a2207  ldstr    aWrite1620Fetch// "Write1620_Fetch"
0x1a220c  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x1a2211  ldloc.0
0x1a2212  ldstr    aMicrosoftCrmSd_103// "Microsoft.Crm.SdkTypeProxy.CrmService:S"...
0x1a2217  ldstr    aWrite1621Fetch// "Write1621_FetchInHeaders"
0x1a221c  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x1a2221  ldloc.0
0x1a2222  ldstr    aMicrosoftCrmSd_104// "Microsoft.Crm.SdkTypeProxy.CrmService:S"...
0x1a2227  ldstr    aWrite1622Creat// "Write1622_Create"
0x1a222c  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x1a2231  ldloc.0
0x1a2232  ldstr    aMicrosoftCrmSd_105// "Microsoft.Crm.SdkTypeProxy.CrmService:S"...
0x1a2237  ldstr    aWrite1623Creat// "Write1623_CreateInHeaders"
0x1a223c  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x1a2241  ldloc.0
0x1a2242  ldstr    aMicrosoftCrmSd_106// "Microsoft.Crm.SdkTypeProxy.CrmService:V"...
0x1a2247  ldstr    aWrite1624Delet// "Write1624_Delete"
0x1a224c  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x1a2251  ldloc.0
0x1a2252  ldstr    aMicrosoftCrmSd_107// "Microsoft.Crm.SdkTypeProxy.CrmService:V"...
0x1a2257  ldstr    aWrite1625Delet// "Write1625_DeleteInHeaders"
0x1a225c  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x1a2261  ldloc.0
0x1a2262  ldstr    aMicrosoftCrmSd_108// "Microsoft.Crm.SdkTypeProxy.CrmService:M"...
0x1a2267  ldstr    aWrite1626Retri// "Write1626_Retrieve"
0x1a226c  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x1a2271  ldloc.0
0x1a2272  ldstr    aMicrosoftCrmSd_109// "Microsoft.Crm.SdkTypeProxy.CrmService:M"...
0x1a2277  ldstr    aWrite1627Retri// "Write1627_RetrieveInHeaders"
0x1a227c  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x1a2281  ldloc.0
0x1a2282  ldstr    aMicrosoftCrmSd_110// "Microsoft.Crm.SdkTypeProxy.CrmService:M"...
0x1a2287  ldstr    aWrite1628Retri// "Write1628_RetrieveMultiple"
0x1a228c  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x1a2291  ldloc.0
0x1a2292  ldstr    aMicrosoftCrmSd_111// "Microsoft.Crm.SdkTypeProxy.CrmService:M"...
0x1a2297  ldstr    aWrite1629Retri// "Write1629_RetrieveMultipleInHeaders"
0x1a229c  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x1a22a1  ldloc.0
0x1a22a2  ldstr    aMicrosoftCrmSd_112// "Microsoft.Crm.SdkTypeProxy.CrmService:V"...
0x1a22a7  ldstr    aWrite1630Updat// "Write1630_Update"
0x1a22ac  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x1a22b1  ldloc.0
0x1a22b2  ldstr    aMicrosoftCrmSd_113// "Microsoft.Crm.SdkTypeProxy.CrmService:V"...
0x1a22b7  ldstr    aWrite1631Updat// "Write1631_UpdateInHeaders"
0x1a22bc  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x1a22c1  ldloc.0
0x1a22c2  ldstr    aMicrosoftCrmSd_114// "Microsoft.Crm.SdkTypeProxy.Metadata.Met"...
0x1a22c7  ldstr    aWrite1632Execu// "Write1632_Execute"
0x1a22cc  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x1a22d1  ldloc.0
0x1a22d2  ldstr    aMicrosoftCrmSd_115// "Microsoft.Crm.SdkTypeProxy.Metadata.Met"...
0x1a22d7  ldstr    aWrite1633Execu// "Write1633_ExecuteInHeaders"
0x1a22dc  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x1a22e1  ldarg.0
0x1a22e2  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializerContract::writeMethods
0x1a22e7  brtrue.s loc_1A22F0
0x1a22e9  ldarg.0
0x1a22ea  ldloc.0
0x1a22eb  stfld    class [mscorlib]System.Collections.Hashtable Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializerContract::writeMethods
0x1a22f0  ldarg.0
0x1a22f1  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializerContract::writeMethods
0x1a22f6  ret
```
