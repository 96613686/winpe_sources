# Microsoft.Crm.Entities.SdkMessage::.ctor_0

- ea: `0x36b0`
- end: `0x36e9`
- name: `Microsoft.Crm.Entities.SdkMessage::.ctor_0`
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
0x36b0  ldarg.0
0x36b1  ldstr    aSdkmessage// "SdkMessage"
0x36b6  ldarg.1
0x36b7  call     instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x36bc  ldarg.0
0x36bd  ldstr    aSdkmessagefilt// "SdkMessageFilter"
0x36c2  ldarg.1
0x36c3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x36c8  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::.ctor(string, valuetype [mscorlib]System.Guid)
0x36cd  stfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Entities.SdkMessage::_requestFilters
0x36d2  ldarg.0
0x36d3  ldstr    aSdkmessagepair// "SdkMessagePair"
0x36d8  ldarg.1
0x36d9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x36de  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::.ctor(string, valuetype [mscorlib]System.Guid)
0x36e3  stfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Entities.SdkMessage::_messagePairs
0x36e8  ret
```
