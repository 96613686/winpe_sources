# Microsoft.Crm.Extensibility.OrganizationSdkServiceInternal::RetrieveMultiple

- ea: `0xaa70`
- end: `0xab70`
- name: `Microsoft.Crm.Extensibility.OrganizationSdkServiceInternal::RetrieveMultiple`
- size: `256`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0xa2b0`
- `0xbc90`
- `0x24cd0`

## callees

- `0xaa70`
- `0xab70`
- `0xb870`

## string_xrefs

- `0xab12`: `Warning: [ExtendedRetrieveMultipleNullChecks] OrganizationSdkServiceInternal.RetrieveMultiple did not find EntityCollection in the response from its call to ExecuteRequest; returning an empty EntityCollection instead.`

## pseudocode

```c

```

## disassembly

```asm
0xaa70  ldarg.0
0xaa71  ldstr    aQuery// "query"
0xaa76  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xaa7b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0xaa80  stloc.0
0xaa81  ldloc.0
0xaa82  ldstr    aRetrievemultip// "RetrieveMultiple"
0xaa87  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string)
0xaa8c  ldloc.0
0xaa8d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0xaa92  ldstr    aQuery_0// "Query"
0xaa97  ldarg.0
0xaa98  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0xaa9d  ldarg.s  5
0xaa9f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xaaa4  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xaaa9  brfalse.s loc_AAC2
0xaaab  ldloc.0
0xaaac  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0xaab1  ldstr    aAppmoduleid// "AppModuleId"
0xaab6  ldarg.s  5
0xaab8  box      [mscorlib]System.Guid
0xaabd  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0xaac2  ldloc.0
0xaac3  ldarg.1
0xaac4  ldarg.2
0xaac5  ldarg.3
0xaac6  ldarg.s  4
0xaac8  ldnull
0xaac9  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse Microsoft.Crm.Extensibility.OrganizationSdkServiceInternal::ExecuteRequest(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest request, class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken correlationToken, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken callerOriginToken, valuetype [Microsoft.Crm.Core]Microsoft.Crm.Performance.WebServiceType serviceType, bool checkAdminMode, [opt] class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0xaace  stloc.1
0xaacf  ldloc.1
0xaad0  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0xaad5  ldstr    aEntitycollecti// "EntityCollection"
0xaada  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0xaadf  brfalse.s loc_AAF9
0xaae1  ldloc.1
0xaae2  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0xaae7  ldstr    aEntitycollecti// "EntityCollection"
0xaaec  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xaaf1  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection
0xaaf6  stloc.2
0xaaf7  leave.s  loc_AB6E
0xaaf9  ldstr    aExtendedretrie// "ExtendedRetrieveMultipleNullChecks"
0xaafe  ldc.i4.0
0xaaff  box      [mscorlib]System.Int32
0xab04  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0xab09  unbox.any [mscorlib]System.Int32
0xab0e  ldc.i4.1
0xab0f  bne.un.s loc_AB2A
0xab11  ldnull
0xab12  ldstr    aWarningExtende// "Warning: [ExtendedRetrieveMultipleNullC"...
0xab17  ldc.i4.0
0xab18  newarr   [mscorlib]System.Object
0xab1d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::Error(class [mscorlib]System.Exception, string, object[])
0xab22  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::.ctor()
0xab27  stloc.2
0xab28  leave.s  loc_AB6E
0xab2a  ldnull
0xab2b  stloc.2
0xab2c  leave.s  loc_AB6E
0xab2e  stloc.3
0xab2f  ldloc.3
0xab30  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Watson.ExceptionManager::IsUnknownException(class [mscorlib]System.Exception)
0xab35  brfalse.s loc_AB61
0xab37  ldloc.3
0xab38  ldstr    aQueryType0// "Query Type: {0}"
0xab3d  ldc.i4.1
0xab3e  newarr   [mscorlib]System.Object
0xab43  dup
0xab44  ldc.i4.0
0xab45  ldarg.0
0xab46  brtrue.s loc_AB4F
0xab48  ldsfld   string [mscorlib]System.String::Empty
0xab4d  br.s     loc_AB5A
0xab4f  ldarg.0
0xab50  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xab55  callvirt instance string [mscorlib]System.Object::ToString()
0xab5a  stelem.ref
0xab5b  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Watson.ExceptionManager::ReportException(class [mscorlib]System.Exception, string, object[])
0xab60  pop
0xab61  ldarg.3
0xab62  call     void Microsoft.Crm.Extensibility.OrganizationSdkServiceInternal::SuppressRedirectTraceForException(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Performance.WebServiceType serviceType)
0xab67  ldloc.3
0xab68  call     class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault> [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.FaultHelper::ConvertToFault(class [mscorlib]System.Exception)
0xab6d  throw
0xab6e  ldloc.2
0xab6f  ret
```
