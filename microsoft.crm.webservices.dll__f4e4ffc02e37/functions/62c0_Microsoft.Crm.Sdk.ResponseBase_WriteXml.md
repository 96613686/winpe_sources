# Microsoft.Crm.Sdk.ResponseBase::WriteXml

- ea: `0x62c0`
- end: `0x6305`
- name: `Microsoft.Crm.Sdk.ResponseBase::WriteXml`
- size: `69`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0xce0`
- `0x62c0`
- `0x66f0`
- `0x6790`

## pseudocode

```c

```

## disassembly

```asm
0x62c0  ldarg.0
0x62c1  ldfld    class Microsoft.Crm.Sdk.IRequestBuilder Microsoft.Crm.Sdk.ResponseBase::_requestBuilder
0x62c6  brtrue.s loc_62D3
0x62c8  ldstr    aInstanceOfResp// "Instance of Response must be initialize"...
0x62cd  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0x62d2  throw
0x62d3  newobj   instance void Microsoft.Crm.Sdk.ResponseFormatter::.ctor()
0x62d8  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::GetOrganizationGuid()
0x62dd  stloc.0
0x62de  ldarg.1
0x62df  ldarg.0
0x62e0  ldfld    string Microsoft.Crm.Sdk.ResponseBase::_typeNamespace
0x62e5  ldarg.0
0x62e6  ldfld    bool Microsoft.Crm.Sdk.ResponseBase::_returnsDynamicEntities
0x62eb  ldloc.0
0x62ec  newobj   instance void Microsoft.Crm.Sdk.FormattingContext::.ctor(class [System.Xml]System.Xml.XmlWriter writer, string namespaceName, bool returnDynamicEntities, valuetype [mscorlib]System.Guid organizationId)
0x62f1  stloc.1
0x62f2  ldloc.1
0x62f3  ldarg.0
0x62f4  ldfld    class Microsoft.Crm.Sdk.IRequestBuilder Microsoft.Crm.Sdk.ResponseBase::_requestBuilder
0x62f9  ldarg.0
0x62fa  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropertyBag Microsoft.Crm.Sdk.ResponseBase::_outputs
0x62ff  callvirt instance void Microsoft.Crm.Sdk.ResponseFormatter::Format(class Microsoft.Crm.Sdk.FormattingContext context, class Microsoft.Crm.Sdk.IRequestBuilder requestBuilder, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropertyBag outputs)
0x6304  ret
```
