# Microsoft.Crm.Data.InitialSolutionDataManager::TryDeleteSolution

- ea: `0x4cdc0`
- end: `0x4cf44`
- name: `Microsoft.Crm.Data.InitialSolutionDataManager::TryDeleteSolution`
- size: `388`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x4cba0`

## callees

- `0x4cdc0`
- `0x4d010`
- `0x4d040`
- `0x4d060`

## string_xrefs

- `0x4cdc2`: `TryDeleteSolution : `
- `0x4ce43`: `Calling SDK Delete for Id : `
- `0x4ce8a`: `Successfully deleted`

## pseudocode

```c

```

## disassembly

```asm
0x4cdc0  ldarg.s  4
0x4cdc2  ldstr    aTrydeletesolut// "TryDeleteSolution : "
0x4cdc7  ldarg.3
0x4cdc8  callvirt instance string Microsoft.Crm.Data.InitialSolutionInfo::get_UniqueName()
0x4cdcd  call     string [mscorlib]System.String::Concat(string, string)
0x4cdd2  callvirt instance void class [mscorlib]System.Action`1<string>::Invoke(var<u1>)
0x4cdd7  ldstr    aSolution// "solution"
0x4cddc  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0x4cde1  stloc.0
0x4cde2  ldloc.0
0x4cde3  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0x4cde8  ldc.i4.2
0x4cde9  newarr   [mscorlib]System.String
0x4cdee  dup
0x4cdef  ldc.i4.0
0x4cdf0  ldstr    aUniquename_0// "uniquename"
0x4cdf5  stelem.ref
0x4cdf6  dup
0x4cdf7  ldc.i4.1
0x4cdf8  ldstr    aSolutionid// "solutionid"
0x4cdfd  stelem.ref
0x4cdfe  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumns(string[])
0x4ce03  ldloc.0
0x4ce04  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x4ce09  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0x4ce0e  ldstr    aUniquename_0// "uniquename"
0x4ce13  ldc.i4.0
0x4ce14  ldarg.3
0x4ce15  callvirt instance string Microsoft.Crm.Data.InitialSolutionInfo::get_UniqueName()
0x4ce1a  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x4ce1f  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0x4ce24  ldarg.2
0x4ce25  ldloc.0
0x4ce26  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase)
0x4ce2b  stloc.1
0x4ce2c  ldloc.1
0x4ce2d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x4ce32  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0x4ce37  stloc.2
0x4ce38  br.s     loc_4CEA8
0x4ce3a  ldloc.2
0x4ce3b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Current()
0x4ce40  stloc.3
0x4ce41  ldarg.s  4
0x4ce43  ldstr    aCallingSdkDele// "Calling SDK Delete for Id : "
0x4ce48  ldloc.3
0x4ce49  ldstr    aSolutionid// "solutionid"
0x4ce4e  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x4ce53  unbox.any [mscorlib]System.Guid
0x4ce58  box      [mscorlib]System.Guid
0x4ce5d  call     string [mscorlib]System.String::Concat(object, object)
0x4ce62  callvirt instance void class [mscorlib]System.Action`1<string>::Invoke(var<u1>)
0x4ce67  ldarg.2
0x4ce68  ldstr    aSolution// "solution"
0x4ce6d  ldloc.3
0x4ce6e  ldstr    aSolutionid// "solutionid"
0x4ce73  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x4ce78  unbox.any [mscorlib]System.Guid
0x4ce7d  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Delete(string, valuetype [mscorlib]System.Guid)
0x4ce82  ldarg.3
0x4ce83  ldc.i4.1
0x4ce84  callvirt instance void Microsoft.Crm.Data.InitialSolutionInfo::set_DeleteSuccessful(bool value)
0x4ce89  ldarg.3
0x4ce8a  ldstr    aSuccessfullyDe// "Successfully deleted"
0x4ce8f  callvirt instance void Microsoft.Crm.Data.InitialSolutionInfo::set_DeleteStatus(string value)
0x4ce94  ldarg.s  4
0x4ce96  ldstr    aSuccess// "Success!"
0x4ce9b  callvirt instance void class [mscorlib]System.Action`1<string>::Invoke(var<u1>)
0x4cea0  ldc.i4.1
0x4cea1  stloc.s  4
0x4cea3  leave    loc_4CF41
0x4cea8  ldloc.2
0x4cea9  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4ceae  brtrue.s loc_4CE3A
0x4ceb0  leave.s  loc_4CEBC
0x4ceb2  ldloc.2
0x4ceb3  brfalse.s loc_4CEBB
0x4ceb5  ldloc.2
0x4ceb6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4cebb  endfinally
0x4cebc  ldloc.1
0x4cebd  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x4cec2  call     T0x2B00006D
0x4cec7  brtrue.s loc_4CEEC
0x4cec9  ldarg.3
0x4ceca  ldc.i4.1
0x4cecb  callvirt instance void Microsoft.Crm.Data.InitialSolutionInfo::set_DeleteSuccessful(bool value)
0x4ced0  ldarg.3
0x4ced1  ldstr    aNoMatchingSolu// "No matching solutions"
0x4ced6  callvirt instance void Microsoft.Crm.Data.InitialSolutionInfo::set_DeleteStatus(string value)
0x4cedb  ldarg.s  4
0x4cedd  ldstr    aNoMatchingSolu// "No matching solutions"
0x4cee2  callvirt instance void class [mscorlib]System.Action`1<string>::Invoke(var<u1>)
0x4cee7  ldc.i4.0
0x4cee8  stloc.s  4
0x4ceea  leave.s  loc_4CF41
0x4ceec  leave.s  loc_4CF3F
0x4ceee  stloc.s  5
0x4cef0  ldloc.s  5
0x4cef2  ldarg.1
0x4cef3  ldc.i4.s 0x14
0x4cef5  ldstr    aUnhandledError// "Unhandled error deleting {0} solution :"...
0x4cefa  ldc.i4.2
0x4cefb  newarr   [mscorlib]System.Object
0x4cf00  dup
0x4cf01  ldc.i4.0
0x4cf02  ldarg.3
0x4cf03  callvirt instance string Microsoft.Crm.Data.InitialSolutionInfo::get_UniqueName()
0x4cf08  stelem.ref
0x4cf09  dup
0x4cf0a  ldc.i4.1
0x4cf0b  ldloc.s  5
0x4cf0d  callvirt instance string [mscorlib]System.Object::ToString()
0x4cf12  stelem.ref
0x4cf13  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4cf18  ldarg.3
0x4cf19  ldloc.s  5
0x4cf1b  callvirt instance string [mscorlib]System.Object::ToString()
0x4cf20  callvirt instance void Microsoft.Crm.Data.InitialSolutionInfo::set_DeleteStatus(string value)
0x4cf25  ldarg.s  4
0x4cf27  ldstr    aException// "Exception : "
0x4cf2c  ldloc.s  5
0x4cf2e  callvirt instance string [mscorlib]System.Object::ToString()
0x4cf33  call     string [mscorlib]System.String::Concat(string, string)
0x4cf38  callvirt instance void class [mscorlib]System.Action`1<string>::Invoke(var<u1>)
0x4cf3d  leave.s  loc_4CF3F
0x4cf3f  ldc.i4.0
0x4cf40  ret
0x4cf41  ldloc.s  4
0x4cf43  ret
```
