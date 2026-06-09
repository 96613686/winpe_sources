# Microsoft.Crm.Sdk.ServiceDescription::CreateRequestDescription

- ea: `0x8fd0`
- end: `0x9094`
- name: `Microsoft.Crm.Sdk.ServiceDescription::CreateRequestDescription`
- size: `196`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x8bf0`

## callees

- `0x5d30`
- `0x5dd0`
- `0x64b0`
- `0x8770`
- `0x8fa0`
- `0x8fd0`
- `0x90a0`

## pseudocode

```c

```

## disassembly

```asm
0x8fd0  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x8fd5  ldc.i4.s 0x1A
0x8fd7  ldstr    aCreatingReques// "Creating Request: {0}."
0x8fdc  ldc.i4.1
0x8fdd  newarr   [mscorlib]System.Object
0x8fe2  dup
0x8fe3  ldc.i4.0
0x8fe4  ldarg.2
0x8fe5  callvirt instance class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageRequestType [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessagePairType::get_SdkMessageRequest()
0x8fea  callvirt instance string [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageRequestType::get_Name()
0x8fef  stelem.ref
0x8ff0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8ff5  ldarg.0
0x8ff6  ldarg.1
0x8ff7  ldarg.2
0x8ff8  callvirt instance class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageRequestType [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessagePairType::get_SdkMessageRequest()
0x8ffd  ldarg.0
0x8ffe  ldfld    class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Sdk.ServiceDescription::_fieldParsers
0x9003  call     instance class Microsoft.Crm.Sdk.RequestFieldDescription[] Microsoft.Crm.Sdk.ServiceDescription::LoadRequestFields(class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageType message, class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageRequestType request, class [mscorlib]System.Collections.IDictionary fieldParsers)
0x9008  stloc.0
0x9009  ldc.i4.1
0x900a  newobj   instance void [System]System.Collections.Specialized.HybridDictionary::.ctor(bool)
0x900f  stloc.1
0x9010  ldloc.0
0x9011  stloc.s  4
0x9013  ldc.i4.0
0x9014  stloc.s  5
0x9016  br.s     loc_9033
0x9018  ldloc.s  4
0x901a  ldloc.s  5
0x901c  ldelem.ref
0x901d  stloc.s  6
0x901f  ldloc.1
0x9020  ldloc.s  6
0x9022  callvirt instance string Microsoft.Crm.Sdk.RequestFieldDescription::get_Name()
0x9027  ldnull
0x9028  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x902d  ldloc.s  5
0x902f  ldc.i4.1
0x9030  add
0x9031  stloc.s  5
0x9033  ldloc.s  5
0x9035  ldloc.s  4
0x9037  ldlen
0x9038  conv.i4
0x9039  blt.s    loc_9018
0x903b  ldarg.1
0x903c  callvirt instance class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFiltersType [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageType::get_SdkMessageFilters()
0x9041  call     class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFiltersType Microsoft.Crm.Sdk.ServiceDescription::CopyFilters(class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFiltersType filters)
0x9046  stloc.2
0x9047  ldarg.2
0x9048  callvirt instance class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageRequestType [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessagePairType::get_SdkMessageRequest()
0x904d  callvirt instance string [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageRequestType::get_Name()
0x9052  ldarg.2
0x9053  callvirt instance string [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessagePairType::get_Namespace()
0x9058  ldarg.1
0x9059  callvirt instance bool [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageType::get_Template()
0x905e  ldloc.2
0x905f  ldarg.2
0x9060  callvirt instance class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageResponseType [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessagePairType::get_SdkMessageResponse()
0x9065  ldnull
0x9066  ldnull
0x9067  newobj   instance void Microsoft.Crm.Sdk.ResponseDescription::.ctor(string name, string namespaceName, bool template, class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFiltersType filters, class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageResponseType response, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PropertyBagMapper outputMapping, class Microsoft.Crm.Sdk.ResponseFieldDescription[] fields)
0x906c  stloc.3
0x906d  ldarg.0
0x906e  ldloc.3
0x906f  call     instance void Microsoft.Crm.Sdk.ServiceDescription::SetResponseFields(class Microsoft.Crm.Sdk.ResponseDescription response)
0x9074  ldarg.2
0x9075  callvirt instance class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageRequestType [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessagePairType::get_SdkMessageRequest()
0x907a  callvirt instance string [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageRequestType::get_Name()
0x907f  ldarg.2
0x9080  callvirt instance string [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessagePairType::get_Namespace()
0x9085  ldarg.1
0x9086  ldarg.2
0x9087  callvirt instance class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageRequestType [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessagePairType::get_SdkMessageRequest()
0x908c  ldloc.3
0x908d  ldloc.0
0x908e  newobj   instance void Microsoft.Crm.Sdk.RequestDescription::.ctor(string name, string namespaceName, class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageType message, class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageRequestType request, class Microsoft.Crm.Sdk.ResponseDescription response, class Microsoft.Crm.Sdk.RequestFieldDescription[] fields)
0x9093  ret
```
