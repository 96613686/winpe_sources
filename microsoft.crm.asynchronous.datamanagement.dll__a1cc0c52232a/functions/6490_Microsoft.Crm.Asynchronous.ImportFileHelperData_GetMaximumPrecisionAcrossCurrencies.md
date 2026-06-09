# Microsoft.Crm.Asynchronous.ImportFileHelperData::GetMaximumPrecisionAcrossCurrencies

- ea: `0x6490`
- end: `0x651b`
- name: `Microsoft.Crm.Asynchronous.ImportFileHelperData::GetMaximumPrecisionAcrossCurrencies`
- size: `139`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x62b0`

## string_xrefs

- `0x6491`: `parameter crmServiceInSystemUserContext should not be null`

## pseudocode

```c

```

## disassembly

```asm
0x6490  ldarg.1
0x6491  ldstr    aParameterCrmse// "parameter crmServiceInSystemUserContext"...
0x6496  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x649b  ldstr    aFetchDistinctF// "<fetch distinct=\"false\" no-lock=\"fal"...
0x64a0  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FetchExpression::.ctor(string)
0x64a5  stloc.0
0x64a6  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleRequest::.ctor()
0x64ab  stloc.1
0x64ac  ldloc.1
0x64ad  ldloc.0
0x64ae  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleRequest::set_Query(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase)
0x64b3  ldarg.1
0x64b4  ldloc.1
0x64b5  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x64ba  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleResponse
0x64bf  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleResponse::get_EntityCollection()
0x64c4  dup
0x64c5  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x64ca  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x64cf  ldc.i4.1
0x64d0  ceq
0x64d2  ldstr    aImporthelperAg// "ImportHelper : Aggregating over currenc"...
0x64d7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x64dc  ldc.i4.0
0x64dd  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Item(int32)
0x64e2  ldstr    aMaxcurrencypre// "maxcurrencyprecision"
0x64e7  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x64ec  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AliasedValue
0x64f1  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AliasedValue::get_Value()
0x64f6  dup
0x64f7  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x64fc  ldtoken  [mscorlib]System.Int32
0x6501  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6506  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x650b  ldstr    aImporthelperAg_0// "ImportHelper : Aggregating over currenc"...
0x6510  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x6515  unbox.any [mscorlib]System.Int32
0x651a  ret
```
