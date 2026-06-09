# Microsoft.Crm.ObjectModel.RelationshipInsightsUtility::GetActivityAnalysisServiceEndpoint

- ea: `0x1c7a70`
- end: `0x1c7cbe`
- name: `Microsoft.Crm.ObjectModel.RelationshipInsightsUtility::GetActivityAnalysisServiceEndpoint`
- size: `590`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x84b90`

## callees

- `0x862d0`
- `0x86310`
- `0x86340`
- `0x1c7a70`
- `0x1c8130`

## string_xrefs

- `0x1c7b0c`: `ActivityAnalysisServiceEndpoint`
- `0x1c7b24`: `ActivityAnalysisServiceEndpoint`
- `0x1c7b73`: `ActivityAnalysisServiceEndpoint`
- `0x1c7b33`: `Successfully retrieved the ActivityAnalysisServiceEndpoint for organization Id {0}.`
- `0x1c7b57`: `GetActivityAnalysisServiceEndpoint`
- `0x1c7baf`: `GetActivityAnalysisServiceEndpoint`
- `0x1c7bd6`: `GetActivityAnalysisServiceEndpoint`
- `0x1c7c24`: `GetActivityAnalysisServiceEndpoint`
- `0x1c7b5c`: `Successfully retrieved ActivityAnalysisServiceEndpoint for organization Id {0}.`
- `0x1c7b8b`: `Unable to retrieve ActivityAnalysisServiceEndpoint for organization Id {0}.`
- `0x1c7bb4`: `unable to retrieve ActivityAnalysisServiceEndpoint for organization Id {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x1c7a70  ldnull
0x1c7a71  stloc.0
0x1c7a72  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x1c7a77  stloc.1
0x1c7a78  ldloc.1
0x1c7a79  ldstr    aOrganizationid_5// "OrganizationId"
0x1c7a7e  ldarg.0
0x1c7a7f  box      [mscorlib]System.Guid
0x1c7a84  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1c7a89  ldloc.1
0x1c7a8a  ldstr    aOrgapplication_0// "OrgApplicationType"
0x1c7a8f  ldc.i4.6
0x1c7a90  box      [mscorlib]System.Int32
0x1c7a95  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1c7a9a  ldstr    aOrgapplication// "OrgApplicationMap"
0x1c7a9f  stloc.2
0x1c7aa0  ldc.i4.1
0x1c7aa1  newarr   [mscorlib]System.String
0x1c7aa6  dup
0x1c7aa7  ldc.i4.0
0x1c7aa8  ldstr    aId_0// "Id"
0x1c7aad  stelem.ref
0x1c7aae  stloc.3
0x1c7aaf  ldloc.2
0x1c7ab0  ldloc.3
0x1c7ab1  ldloc.1
0x1c7ab2  ldarg.0
0x1c7ab3  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.ObjectModel.RelationshipInsightsUtility::GetDataFromSiteDB(string tableName, string[] cols, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag condition, valuetype [mscorlib]System.Guid organizationId)
0x1c7ab8  stloc.s  4
0x1c7aba  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1c7abf  stloc.s  5
0x1c7ac1  ldloc.s  4
0x1c7ac3  brfalse  loc_1C7BCB
0x1c7ac8  ldloc.s  4
0x1c7aca  ldstr    aId_0// "Id"
0x1c7acf  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0x1c7ad4  brfalse  loc_1C7BCB
0x1c7ad9  ldloc.s  4
0x1c7adb  ldstr    aId_0// "Id"
0x1c7ae0  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x1c7ae5  unbox.any [mscorlib]System.Guid
0x1c7aea  stloc.s  5
0x1c7aec  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x1c7af1  stloc.1
0x1c7af2  ldloc.1
0x1c7af3  ldstr    aId_0// "Id"
0x1c7af8  ldloc.s  5
0x1c7afa  box      [mscorlib]System.Guid
0x1c7aff  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1c7b04  ldc.i4.1
0x1c7b05  newarr   [mscorlib]System.String
0x1c7b0a  dup
0x1c7b0b  ldc.i4.0
0x1c7b0c  ldstr    aActivityanalys// "ActivityAnalysisServiceEndpoint"
0x1c7b11  stelem.ref
0x1c7b12  stloc.3
0x1c7b13  ldloc.2
0x1c7b14  ldloc.3
0x1c7b15  ldloc.1
0x1c7b16  ldarg.0
0x1c7b17  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.ObjectModel.RelationshipInsightsUtility::GetDataFromSiteDB(string tableName, string[] cols, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag condition, valuetype [mscorlib]System.Guid organizationId)
0x1c7b1c  stloc.s  4
0x1c7b1e  ldloc.s  4
0x1c7b20  brfalse.s loc_1C7B88
0x1c7b22  ldloc.s  4
0x1c7b24  ldstr    aActivityanalys// "ActivityAnalysisServiceEndpoint"
0x1c7b29  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0x1c7b2e  brfalse.s loc_1C7B88
0x1c7b30  ldarg.0
0x1c7b31  ldc.i4.s 0x14
0x1c7b33  ldstr    aSuccessfullyRe_6// "Successfully retrieved the ActivityAnal"...
0x1c7b38  ldc.i4.1
0x1c7b39  newarr   [mscorlib]System.Object
0x1c7b3e  dup
0x1c7b3f  ldc.i4.0
0x1c7b40  ldarg.0
0x1c7b41  box      [mscorlib]System.Guid
0x1c7b46  stelem.ref
0x1c7b47  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1c7b4c  call     class Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource::get_Instance()
0x1c7b51  ldarg.0
0x1c7b52  ldstr    aRelationshipin_0// "RelationshipIntelligenceWarning"
0x1c7b57  ldstr    aGetactivityana// "GetActivityAnalysisServiceEndpoint"
0x1c7b5c  ldstr    aSuccessfullyRe_7// "Successfully retrieved ActivityAnalysis"...
0x1c7b61  ldarg.0
0x1c7b62  box      [mscorlib]System.Guid
0x1c7b67  call     string [mscorlib]System.String::Format(string, object)
0x1c7b6c  callvirt instance void Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource::LogWarning(valuetype [mscorlib]System.Guid organizationId, string EventName, string CallingMethod, string EventDetails)
0x1c7b71  ldloc.s  4
0x1c7b73  ldstr    aActivityanalys// "ActivityAnalysisServiceEndpoint"
0x1c7b78  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x1c7b7d  isinst   [mscorlib]System.String
0x1c7b82  stloc.0
0x1c7b83  br       loc_1C7C17
0x1c7b88  ldarg.0
0x1c7b89  ldc.i4.s 0x14
0x1c7b8b  ldstr    aUnableToRetrie// "Unable to retrieve ActivityAnalysisServ"...
0x1c7b90  ldc.i4.1
0x1c7b91  newarr   [mscorlib]System.Object
0x1c7b96  dup
0x1c7b97  ldc.i4.0
0x1c7b98  ldarg.0
0x1c7b99  box      [mscorlib]System.Guid
0x1c7b9e  stelem.ref
0x1c7b9f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1c7ba4  call     class Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource::get_Instance()
0x1c7ba9  ldarg.0
0x1c7baa  ldstr    aRelationshipin_0// "RelationshipIntelligenceWarning"
0x1c7baf  ldstr    aGetactivityana// "GetActivityAnalysisServiceEndpoint"
0x1c7bb4  ldstr    aUnableToRetrie_0// "unable to retrieve ActivityAnalysisServ"...
0x1c7bb9  ldarg.0
0x1c7bba  box      [mscorlib]System.Guid
0x1c7bbf  call     string [mscorlib]System.String::Format(string, object)
0x1c7bc4  callvirt instance void Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource::LogWarning(valuetype [mscorlib]System.Guid organizationId, string EventName, string CallingMethod, string EventDetails)
0x1c7bc9  br.s     loc_1C7C17
0x1c7bcb  call     class Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource::get_Instance()
0x1c7bd0  ldarg.0
0x1c7bd1  ldstr    aRelationshipin_0// "RelationshipIntelligenceWarning"
0x1c7bd6  ldstr    aGetactivityana// "GetActivityAnalysisServiceEndpoint"
0x1c7bdb  ldstr    aUnableToFindAn_2// "Unable to find any AA relevant OrgAppli"...
0x1c7be0  ldarg.0
0x1c7be1  box      [mscorlib]System.Guid
0x1c7be6  call     string [mscorlib]System.String::Format(string, object)
0x1c7beb  callvirt instance void Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource::LogWarning(valuetype [mscorlib]System.Guid organizationId, string EventName, string CallingMethod, string EventDetails)
0x1c7bf0  ldarg.0
0x1c7bf1  ldc.i4.s 0x14
0x1c7bf3  ldstr    aUnableToFindAn_3// "Unable to find any relevant OrgApplicat"...
0x1c7bf8  ldarg.0
0x1c7bf9  box      [mscorlib]System.Guid
0x1c7bfe  call     string [mscorlib]System.String::Format(string, object)
0x1c7c03  ldc.i4.1
0x1c7c04  newarr   [mscorlib]System.Object
0x1c7c09  dup
0x1c7c0a  ldc.i4.0
0x1c7c0b  ldarg.0
0x1c7c0c  box      [mscorlib]System.Guid
0x1c7c11  stelem.ref
0x1c7c12  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1c7c17  leave    loc_1C7CBC
0x1c7c1c  stloc.s  6
0x1c7c1e  call     class Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource::get_Instance()
0x1c7c23  ldarg.0
0x1c7c24  ldstr    aGetactivityana// "GetActivityAnalysisServiceEndpoint"
0x1c7c29  ldc.i4   0x80044290
0x1c7c2e  ldc.i4   0x80044290
0x1c7c33  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0x1c7c38  ldarg.0
0x1c7c39  box      [mscorlib]System.Guid
0x1c7c3e  ldloc.s  6
0x1c7c40  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1c7c45  call     string [mscorlib]System.String::Format(string, object, object)
0x1c7c4a  callvirt instance void Microsoft.Crm.ObjectModel.RelationshipIntelligenceEventSource::LogError(valuetype [mscorlib]System.Guid organizationId, string CallingMethod, int32 CrmErrorCode, string ErrorDetails)
0x1c7c4f  ldloc.s  6
0x1c7c51  ldarg.0
0x1c7c52  ldc.i4.s 0x14
0x1c7c54  ldc.i4   0x80044290
0x1c7c59  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0x1c7c5e  ldc.i4.2
0x1c7c5f  newarr   [mscorlib]System.Object
0x1c7c64  dup
0x1c7c65  ldc.i4.0
0x1c7c66  ldarg.0
0x1c7c67  box      [mscorlib]System.Guid
0x1c7c6c  stelem.ref
0x1c7c6d  dup
0x1c7c6e  ldc.i4.1
0x1c7c6f  ldloc.s  6
0x1c7c71  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1c7c76  stelem.ref
0x1c7c77  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1c7c7c  ldc.i4   0x80044290
0x1c7c81  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0x1c7c86  ldarg.0
0x1c7c87  box      [mscorlib]System.Guid
0x1c7c8c  ldloc.s  6
0x1c7c8e  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1c7c93  call     string [mscorlib]System.String::Format(string, object, object)
0x1c7c98  ldc.i4   0x80044290
0x1c7c9d  ldc.i4.2
0x1c7c9e  newarr   [mscorlib]System.Object
0x1c7ca3  dup
0x1c7ca4  ldc.i4.0
0x1c7ca5  ldarg.0
0x1c7ca6  box      [mscorlib]System.Guid
0x1c7cab  stelem.ref
0x1c7cac  dup
0x1c7cad  ldc.i4.1
0x1c7cae  ldloc.s  6
0x1c7cb0  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1c7cb5  stelem.ref
0x1c7cb6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32, object[])
0x1c7cbb  throw
0x1c7cbc  ldloc.0
0x1c7cbd  ret
```
