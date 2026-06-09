# Microsoft.Crm.ObjectModel.BpoSdkMessageProcessingStepInfoFactory::.cctor

- ea: `0x87680`
- end: `0x87914`
- name: `Microsoft.Crm.ObjectModel.BpoSdkMessageProcessingStepInfoFactory::.cctor`
- size: `660`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x87930`

## string_xrefs

- `0x87686`: `Create`
- `0x87704`: `Create`
- `0x87709`: `Create`
- `0x876d0`: `Update`
- `0x87798`: `Update`
- `0x8779d`: `Update`
- `0x876ab`: `Delete`
- `0x87729`: `Delete`
- `0x8772e`: `Delete`
- `0x87851`: `GrantAccess`
- `0x87856`: `GrantAccess`
- `0x87876`: `ModifyAccess`
- `0x8787b`: `ModifyAccess`
- `0x8789b`: `RetrievePrincipalAccess`
- `0x878a0`: `RetrievePrincipalAccess`
- `0x878e5`: `RetrieveSharedPrincipalsAndAccess`
- `0x878ea`: `RetrieveSharedPrincipalsAndAccess`
- `0x878c0`: `RevokeAccess`
- `0x878c5`: `RevokeAccess`
- `0x8768b`: `DoCreate`
- `0x876b0`: `DoDelete`
- `0x876d5`: `DoUpdate`
- `0x878af`: `<Field><Name>AccessRights</Name><Value>return-value</Value><ClrFormatter>Microsoft.Crm.Sdk.AccessRights,Microsoft.Crm.Sdk</ClrFormatter></Field>`
- `0x878f9`: `<Field><Name>PrincipalAccesses</Name><Value>PrincipalAccessArrayToEnum(return-value)</Value><ClrFormatter>Microsoft.Crm.Sdk.PrincipalAccess[],Microsoft.Crm.Sdk</ClrFormatter></Field>`

## pseudocode

```c

```

## disassembly

```asm
0x87680  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.ObjectModel.BpoSdkMessageProcessingStepInfo>::.ctor()
0x87685  dup
0x87686  ldstr    aCreate// "Create"
0x8768b  ldstr    aDocreate// "DoCreate"
0x87690  ldstr    aIcreatable// "ICreatable"
0x87695  ldsfld   string Microsoft.Crm.ObjectModel.SdkInputMappings::CreateMapping
0x8769a  ldstr    aFieldNameIdNam// "<Field><Name>id</Name><Value>MonikerToI"...
0x8769f  ldc.i4.1
0x876a0  newobj   instance void Microsoft.Crm.ObjectModel.BpoSdkMessageProcessingStepInfo::.ctor(string methodName, string interfaceName, string inputMapping, string outputMapping, int32 messageInvocationSource)
0x876a5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.ObjectModel.BpoSdkMessageProcessingStepInfo>::Add(var<u1>, !!T0)
0x876aa  dup
0x876ab  ldstr    aDelete// "Delete"
0x876b0  ldstr    aDodelete// "DoDelete"
0x876b5  ldstr    aIdeletable// "IDeletable"
0x876ba  ldsfld   string Microsoft.Crm.ObjectModel.SdkInputMappings::DeleteMapping
0x876bf  ldsfld   string [mscorlib]System.String::Empty
0x876c4  ldc.i4.1
0x876c5  newobj   instance void Microsoft.Crm.ObjectModel.BpoSdkMessageProcessingStepInfo::.ctor(string methodName, string interfaceName, string inputMapping, string outputMapping, int32 messageInvocationSource)
0x876ca  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.ObjectModel.BpoSdkMessageProcessingStepInfo>::Add(var<u1>, !!T0)
0x876cf  dup
0x876d0  ldstr    aUpdate// "Update"
0x876d5  ldstr    aDoupdate// "DoUpdate"
0x876da  ldstr    aIupdatable// "IUpdatable"
0x876df  ldsfld   string Microsoft.Crm.ObjectModel.SdkInputMappings::DoUpdateMapping
0x876e4  ldsfld   string [mscorlib]System.String::Empty
0x876e9  ldc.i4.1
0x876ea  newobj   instance void Microsoft.Crm.ObjectModel.BpoSdkMessageProcessingStepInfo::.ctor(string methodName, string interfaceName, string inputMapping, string outputMapping, int32 messageInvocationSource)
0x876ef  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.ObjectModel.BpoSdkMessageProcessingStepInfo>::Add(var<u1>, !!T0)
0x876f4  newobj   instance void class [mscorlib]System.Collections.ObjectModel.ReadOnlyDictionary`2<string, class Microsoft.Crm.ObjectModel.BpoSdkMessageProcessingStepInfo>::.ctor(class [mscorlib]System.Collections.Generic.IDictionary`2<var<u1>, !!T0>)
0x876f9  stsfld   class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, class Microsoft.Crm.ObjectModel.BpoSdkMessageProcessingStepInfo> Microsoft.Crm.ObjectModel.BpoSdkMessageProcessingStepInfoFactory::ChildProcessingStepParams
0x876fe  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.ObjectModel.BpoSdkMessageProcessingStepInfo>::.ctor()
0x87703  dup
0x87704  ldstr    aCreate// "Create"
0x87709  ldstr    aCreate// "Create"
0x8770e  ldstr    aIcreatable// "ICreatable"
0x87713  ldsfld   string Microsoft.Crm.ObjectModel.SdkInputMappings::CreateMapping
0x87718  ldstr    aFieldNameIdNam// "<Field><Name>id</Name><Value>MonikerToI"...
0x8771d  ldc.i4.0
0x8771e  newobj   instance void Microsoft.Crm.ObjectModel.BpoSdkMessageProcessingStepInfo::.ctor(string methodName, string interfaceName, string inputMapping, string outputMapping, int32 messageInvocationSource)
0x87723  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.ObjectModel.BpoSdkMessageProcessingStepInfo>::Add(var<u1>, !!T0)
0x87728  dup
0x87729  ldstr    aDelete// "Delete"
0x8772e  ldstr    aDelete// "Delete"
0x87733  ldstr    aIdeletable// "IDeletable"
0x87738  ldsfld   string Microsoft.Crm.ObjectModel.SdkInputMappings::DeleteMapping
0x8773d  ldsfld   string [mscorlib]System.String::Empty
0x87742  ldc.i4.0
0x87743  newobj   instance void Microsoft.Crm.ObjectModel.BpoSdkMessageProcessingStepInfo::.ctor(string methodName, string interfaceName, string inputMapping, string outputMapping, int32 messageInvocationSource)
0x87748  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.ObjectModel.BpoSdkMessageProcessingStepInfo>::Add(var<u1>, !!T0)
0x8774d  dup
0x8774e  ldstr    aRetrieve// "Retrieve"
0x87753  ldstr    aRetrieve// "Retrieve"
0x87758  ldstr    aIretrievable// "IRetrievable"
0x8775d  ldsfld   string Microsoft.Crm.ObjectModel.SdkInputMappings::RetrieveMapping
0x87762  ldstr    aFieldNameBusin// "<Field><Name>BusinessEntity</Name><Valu"...
0x87767  ldc.i4.0
0x87768  newobj   instance void Microsoft.Crm.ObjectModel.BpoSdkMessageProcessingStepInfo::.ctor(string methodName, string interfaceName, string inputMapping, string outputMapping, int32 messageInvocationSource)
0x8776d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.ObjectModel.BpoSdkMessageProcessingStepInfo>::Add(var<u1>, !!T0)
0x87772  dup
0x87773  ldstr    aRetrievemultip// "RetrieveMultiple"
0x87778  ldstr    aRetrievemultip// "RetrieveMultiple"
0x8777d  ldstr    aIretrievable// "IRetrievable"
0x87782  ldsfld   string Microsoft.Crm.ObjectModel.SdkInputMappings::RetrieveMultipleMapping
0x87787  ldstr    aFieldNameBusin_0// "<Field><Name>BusinessEntityCollection</"...
0x8778c  ldc.i4.0
0x8778d  newobj   instance void Microsoft.Crm.ObjectModel.BpoSdkMessageProcessingStepInfo::.ctor(string methodName, string interfaceName, string inputMapping, string outputMapping, int32 messageInvocationSource)
0x87792  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.ObjectModel.BpoSdkMessageProcessingStepInfo>::Add(var<u1>, !!T0)
0x87797  dup
0x87798  ldstr    aUpdate// "Update"
0x8779d  ldstr    aUpdate// "Update"
0x877a2  ldstr    aIupdatable// "IUpdatable"
0x877a7  ldsfld   string Microsoft.Crm.ObjectModel.SdkInputMappings::UpdateMapping
0x877ac  ldsfld   string [mscorlib]System.String::Empty
0x877b1  ldc.i4.0
0x877b2  newobj   instance void Microsoft.Crm.ObjectModel.BpoSdkMessageProcessingStepInfo::.ctor(string methodName, string interfaceName, string inputMapping, string outputMapping, int32 messageInvocationSource)
0x877b7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.ObjectModel.BpoSdkMessageProcessingStepInfo>::Add(var<u1>, !!T0)
0x877bc  dup
0x877bd  ldstr    aSetstate// "SetState"
0x877c2  ldstr    aSetstatestatus// "SetStateStatus"
0x877c7  ldstr    aIstateful// "IStateful"
0x877cc  ldsfld   string Microsoft.Crm.ObjectModel.SdkInputMappings::SetStateMapping
0x877d1  ldsfld   string [mscorlib]System.String::Empty
0x877d6  ldc.i4.0
0x877d7  newobj   instance void Microsoft.Crm.ObjectModel.BpoSdkMessageProcessingStepInfo::.ctor(string methodName, string interfaceName, string inputMapping, string outputMapping, int32 messageInvocationSource)
0x877dc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.ObjectModel.BpoSdkMessageProcessingStepInfo>::Add(var<u1>, !!T0)
0x877e1  dup
0x877e2  ldstr    aIsvalidstatetr// "IsValidStateTransition"
0x877e7  ldstr    aIsvalidstatetr_0// "IsValidStateTransitionStatus"
0x877ec  ldstr    aIstateful// "IStateful"
0x877f1  ldsfld   string Microsoft.Crm.ObjectModel.SdkInputMappings::IsValidStateTransitionMapping
0x877f6  ldsfld   string [mscorlib]System.String::Empty
0x877fb  ldc.i4.0
0x877fc  newobj   instance void Microsoft.Crm.ObjectModel.BpoSdkMessageProcessingStepInfo::.ctor(string methodName, string interfaceName, string inputMapping, string outputMapping, int32 messageInvocationSource)
0x87801  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.ObjectModel.BpoSdkMessageProcessingStepInfo>::Add(var<u1>, !!T0)
0x87806  dup
0x87807  ldstr    aSetstatedynami// "SetStateDynamicEntity"
0x8780c  ldstr    aSetstatestatus// "SetStateStatus"
0x87811  ldstr    aIstateful// "IStateful"
0x87816  ldsfld   string Microsoft.Crm.ObjectModel.SdkInputMappings::SetStateDynamicEntityMapping
0x8781b  ldstr    aFieldNameIsval// "<Field><Name>IsValid</Name><Value>retur"...
0x87820  ldc.i4.0
0x87821  newobj   instance void Microsoft.Crm.ObjectModel.BpoSdkMessageProcessingStepInfo::.ctor(string methodName, string interfaceName, string inputMapping, string outputMapping, int32 messageInvocationSource)
0x87826  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.ObjectModel.BpoSdkMessageProcessingStepInfo>::Add(var<u1>, !!T0)
0x8782b  dup
0x8782c  ldstr    aAssign// "Assign"
0x87831  ldstr    aAssign// "Assign"
0x87836  ldstr    aIowned// "IOwned"
0x8783b  ldsfld   string Microsoft.Crm.ObjectModel.SdkInputMappings::AssignMapping
0x87840  ldsfld   string [mscorlib]System.String::Empty
0x87845  ldc.i4.0
0x87846  newobj   instance void Microsoft.Crm.ObjectModel.BpoSdkMessageProcessingStepInfo::.ctor(string methodName, string interfaceName, string inputMapping, string outputMapping, int32 messageInvocationSource)
0x8784b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.ObjectModel.BpoSdkMessageProcessingStepInfo>::Add(var<u1>, !!T0)
0x87850  dup
0x87851  ldstr    aGrantaccess// "GrantAccess"
0x87856  ldstr    aGrantaccess// "GrantAccess"
0x8785b  ldstr    aIowned// "IOwned"
0x87860  ldsfld   string Microsoft.Crm.ObjectModel.SdkInputMappings::GrantAccessMapping
0x87865  ldsfld   string [mscorlib]System.String::Empty
0x8786a  ldc.i4.0
0x8786b  newobj   instance void Microsoft.Crm.ObjectModel.BpoSdkMessageProcessingStepInfo::.ctor(string methodName, string interfaceName, string inputMapping, string outputMapping, int32 messageInvocationSource)
0x87870  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.ObjectModel.BpoSdkMessageProcessingStepInfo>::Add(var<u1>, !!T0)
0x87875  dup
0x87876  ldstr    aModifyaccess// "ModifyAccess"
0x8787b  ldstr    aModifyaccess// "ModifyAccess"
0x87880  ldstr    aIowned// "IOwned"
0x87885  ldsfld   string Microsoft.Crm.ObjectModel.SdkInputMappings::ModifyAccessMapping
0x8788a  ldsfld   string [mscorlib]System.String::Empty
0x8788f  ldc.i4.0
0x87890  newobj   instance void Microsoft.Crm.ObjectModel.BpoSdkMessageProcessingStepInfo::.ctor(string methodName, string interfaceName, string inputMapping, string outputMapping, int32 messageInvocationSource)
0x87895  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.ObjectModel.BpoSdkMessageProcessingStepInfo>::Add(var<u1>, !!T0)
0x8789a  dup
0x8789b  ldstr    aRetrieveprinci// "RetrievePrincipalAccess"
0x878a0  ldstr    aRetrieveprinci// "RetrievePrincipalAccess"
0x878a5  ldstr    aIowned// "IOwned"
0x878aa  ldsfld   string Microsoft.Crm.ObjectModel.SdkInputMappings::RetrievePrincipalAccessMapping
0x878af  ldstr    aFieldNameAcces// "<Field><Name>AccessRights</Name><Value>"...
0x878b4  ldc.i4.0
0x878b5  newobj   instance void Microsoft.Crm.ObjectModel.BpoSdkMessageProcessingStepInfo::.ctor(string methodName, string interfaceName, string inputMapping, string outputMapping, int32 messageInvocationSource)
0x878ba  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.ObjectModel.BpoSdkMessageProcessingStepInfo>::Add(var<u1>, !!T0)
0x878bf  dup
0x878c0  ldstr    aRevokeaccess// "RevokeAccess"
0x878c5  ldstr    aRevokeaccess// "RevokeAccess"
0x878ca  ldstr    aIowned// "IOwned"
0x878cf  ldsfld   string Microsoft.Crm.ObjectModel.SdkInputMappings::RevokeAccessMapping
0x878d4  ldsfld   string [mscorlib]System.String::Empty
0x878d9  ldc.i4.0
0x878da  newobj   instance void Microsoft.Crm.ObjectModel.BpoSdkMessageProcessingStepInfo::.ctor(string methodName, string interfaceName, string inputMapping, string outputMapping, int32 messageInvocationSource)
0x878df  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.ObjectModel.BpoSdkMessageProcessingStepInfo>::Add(var<u1>, !!T0)
0x878e4  dup
0x878e5  ldstr    aRetrieveshared// "RetrieveSharedPrincipalsAndAccess"
0x878ea  ldstr    aRetrieveshared// "RetrieveSharedPrincipalsAndAccess"
0x878ef  ldstr    aIowned// "IOwned"
0x878f4  ldsfld   string Microsoft.Crm.ObjectModel.SdkInputMappings::RetrieveSharedPrincipalsAndAccessMapping
0x878f9  ldstr    aFieldNamePrinc// "<Field><Name>PrincipalAccesses</Name><V"...
0x878fe  ldc.i4.0
0x878ff  newobj   instance void Microsoft.Crm.ObjectModel.BpoSdkMessageProcessingStepInfo::.ctor(string methodName, string interfaceName, string inputMapping, string outputMapping, int32 messageInvocationSource)
0x87904  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.ObjectModel.BpoSdkMessageProcessingStepInfo>::Add(var<u1>, !!T0)
0x87909  newobj   instance void class [mscorlib]System.Collections.ObjectModel.ReadOnlyDictionary`2<string, class Microsoft.Crm.ObjectModel.BpoSdkMessageProcessingStepInfo>::.ctor(class [mscorlib]System.Collections.Generic.IDictionary`2<var<u1>, !!T0>)
0x8790e  stsfld   class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, class Microsoft.Crm.ObjectModel.BpoSdkMessageProcessingStepInfo> Microsoft.Crm.ObjectModel.BpoSdkMessageProcessingStepInfoFactory::ParentProcessingStepParams
0x87913  ret
```
