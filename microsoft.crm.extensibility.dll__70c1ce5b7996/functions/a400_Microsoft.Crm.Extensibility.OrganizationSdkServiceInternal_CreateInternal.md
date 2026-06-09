# Microsoft.Crm.Extensibility.OrganizationSdkServiceInternal::CreateInternal

- ea: `0xa400`
- end: `0xa4c5`
- name: `Microsoft.Crm.Extensibility.OrganizationSdkServiceInternal::CreateInternal`
- size: `197`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0xa3d0`
- `0xcc20`
- `0x24b60`

## callees

- `0xa400`
- `0xab70`
- `0xb870`

## string_xrefs

- `0xa412`: `Create`

## pseudocode

```c

```

## disassembly

```asm
0xa400  ldarg.0
0xa401  ldstr    aEntity// "entity"
0xa406  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xa40b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0xa410  stloc.0
0xa411  ldloc.0
0xa412  ldstr    aCreate// "Create"
0xa417  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string)
0xa41c  ldloc.0
0xa41d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0xa422  ldstr    aTarget// "Target"
0xa427  ldarg.0
0xa428  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0xa42d  ldarg.s  5
0xa42f  brfalse.s loc_A475
0xa431  ldarg.s  5
0xa433  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Keys()
0xa438  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<string, object>::GetEnumerator()
0xa43d  stloc.1
0xa43e  br.s     loc_A45C
0xa440  ldloca.s 1
0xa442  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, object>::get_Current()
0xa447  stloc.2
0xa448  ldloc.0
0xa449  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0xa44e  ldloc.2
0xa44f  ldarg.s  5
0xa451  ldloc.2
0xa452  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0xa457  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0xa45c  ldloca.s 1
0xa45e  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, object>::MoveNext()
0xa463  brtrue.s loc_A440
0xa465  leave.s  loc_A475
0xa467  ldloca.s 1
0xa469  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, object>
0xa46f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa474  endfinally
0xa475  ldloc.0
0xa476  ldarg.1
0xa477  ldarg.2
0xa478  ldarg.3
0xa479  ldarg.s  4
0xa47b  ldnull
0xa47c  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse Microsoft.Crm.Extensibility.OrganizationSdkServiceInternal::ExecuteRequest(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest request, class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken correlationToken, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken callerOriginToken, valuetype [Microsoft.Crm.Core]Microsoft.Crm.Performance.WebServiceType serviceType, bool checkAdminMode, [opt] class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0xa481  stloc.3
0xa482  leave.s  loc_A4C3
0xa484  stloc.s  4
0xa486  ldloc.s  4
0xa488  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Watson.ExceptionManager::IsUnknownException(class [mscorlib]System.Exception)
0xa48d  brfalse.s loc_A4B5
0xa48f  ldloc.s  4
0xa491  ldstr    aEntityname0// "EntityName: {0}"
0xa496  ldc.i4.1
0xa497  newarr   [mscorlib]System.Object
0xa49c  dup
0xa49d  ldc.i4.0
0xa49e  ldarg.0
0xa49f  brtrue.s loc_A4A8
0xa4a1  ldsfld   string [mscorlib]System.String::Empty
0xa4a6  br.s     loc_A4AE
0xa4a8  ldarg.0
0xa4a9  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0xa4ae  stelem.ref
0xa4af  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Watson.ExceptionManager::ReportException(class [mscorlib]System.Exception, string, object[])
0xa4b4  pop
0xa4b5  ldarg.3
0xa4b6  call     void Microsoft.Crm.Extensibility.OrganizationSdkServiceInternal::SuppressRedirectTraceForException(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Performance.WebServiceType serviceType)
0xa4bb  ldloc.s  4
0xa4bd  call     class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault> [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.FaultHelper::ConvertToFault(class [mscorlib]System.Exception)
0xa4c2  throw
0xa4c3  ldloc.3
0xa4c4  ret
```
