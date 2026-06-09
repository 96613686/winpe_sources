# Microsoft.Crm.Data.InitialSolutionDataManager::TryDeleteRecord

- ea: `0x4c990`
- end: `0x4cb96`
- name: `Microsoft.Crm.Data.InitialSolutionDataManager::TryDeleteRecord`
- size: `518`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x50e70`

## callees

- `0x4c5d0`
- `0x4c990`
- `0x4d0a0`
- `0x4d0c0`
- `0x4d0f0`
- `0x4d100`
- `0x4d110`
- `0x4d120`

## string_xrefs

- `0x4ca0a`: `Success : Attempted on [`
- `0x4cafc`: ` Attempted on [`

## pseudocode

```c

```

## disassembly

```asm
0x4c990  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x4c995  stloc.0
0x4c996  ldarg.s  5
0x4c998  ldnull
0x4c999  stind.ref
0x4c99a  ldc.i4.0
0x4c99b  stloc.1
0x4c99c  ldarg.1
0x4c99d  callvirt instance bool Microsoft.Crm.Data.InitialSolutionPackageData::get_DeleteSuccessful()
0x4c9a2  brtrue   loc_4CA4B
0x4c9a7  ldarg.1
0x4c9a8  callvirt instance bool Microsoft.Crm.Data.InitialSolutionPackageData::get_DeleteSkipped()
0x4c9ad  brtrue   loc_4CA4B
0x4c9b2  ldarg.2
0x4c9b3  ldarg.1
0x4c9b4  callvirt instance string Microsoft.Crm.Data.InitialSolutionPackageData::get_EntityName()
0x4c9b9  ldarg.1
0x4c9ba  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Data.InitialSolutionPackageData::get_RecordId()
0x4c9bf  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor()
0x4c9c4  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Retrieve(string, valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x4c9c9  brtrue.s loc_4C9EF
0x4c9cb  ldarg.1
0x4c9cc  ldstr    aSuccessRecordD// "Success : Record does not exist. Pass :"...
0x4c9d1  ldarg.3
0x4c9d2  box      [mscorlib]System.Int32
0x4c9d7  call     string [mscorlib]System.String::Concat(object, object)
0x4c9dc  callvirt instance void Microsoft.Crm.Data.InitialSolutionPackageData::set_DeleteStatus(string value)
0x4c9e1  ldarg.1
0x4c9e2  ldc.i4.1
0x4c9e3  callvirt instance void Microsoft.Crm.Data.InitialSolutionPackageData::set_DeleteSuccessful(bool value)
0x4c9e8  ldloc.1
0x4c9e9  stloc.2
0x4c9ea  leave    loc_4CB94
0x4c9ef  ldarg.2
0x4c9f0  ldarg.1
0x4c9f1  callvirt instance string Microsoft.Crm.Data.InitialSolutionPackageData::get_EntityName()
0x4c9f6  ldarg.1
0x4c9f7  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Data.InitialSolutionPackageData::get_RecordId()
0x4c9fc  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Delete(string, valuetype [mscorlib]System.Guid)
0x4ca01  ldarg.1
0x4ca02  ldc.i4.4
0x4ca03  newarr   [mscorlib]System.Object
0x4ca08  dup
0x4ca09  ldc.i4.0
0x4ca0a  ldstr    aSuccessAttempt// "Success : Attempted on ["
0x4ca0f  stelem.ref
0x4ca10  dup
0x4ca11  ldc.i4.1
0x4ca12  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x4ca17  stloc.3
0x4ca18  ldloca.s 3
0x4ca1a  ldstr    aG// "G"
0x4ca1f  call     instance string [mscorlib]System.DateTime::ToString(string)
0x4ca24  stelem.ref
0x4ca25  dup
0x4ca26  ldc.i4.2
0x4ca27  ldstr    aPass// "] Pass : "
0x4ca2c  stelem.ref
0x4ca2d  dup
0x4ca2e  ldc.i4.3
0x4ca2f  ldarg.3
0x4ca30  box      [mscorlib]System.Int32
0x4ca35  stelem.ref
0x4ca36  call     string [mscorlib]System.String::Concat(object[])
0x4ca3b  callvirt instance void Microsoft.Crm.Data.InitialSolutionPackageData::set_DeleteStatus(string value)
0x4ca40  ldarg.1
0x4ca41  ldc.i4.1
0x4ca42  callvirt instance void Microsoft.Crm.Data.InitialSolutionPackageData::set_DeleteSuccessful(bool value)
0x4ca47  ldloc.1
0x4ca48  ldc.i4.1
0x4ca49  add
0x4ca4a  stloc.1
0x4ca4b  leave    loc_4CB92
0x4ca50  stloc.s  4
0x4ca52  ldloc.s  4
0x4ca54  isinst   class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>
0x4ca59  stloc.s  5
0x4ca5b  ldc.i4.m1
0x4ca5c  stloc.s  6
0x4ca5e  ldloc.s  5
0x4ca60  brfalse.s loc_4CACF
0x4ca62  ldloc.s  5
0x4ca64  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x4ca69  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_ErrorCode()
0x4ca6e  stloc.s  6
0x4ca70  ldloc.s  6
0x4ca72  ldc.i4   0x80040217
0x4ca77  bne.un.s loc_4CA9D
0x4ca79  ldarg.1
0x4ca7a  ldstr    aSuccessRecordD// "Success : Record does not exist. Pass :"...
0x4ca7f  ldarg.3
0x4ca80  box      [mscorlib]System.Int32
0x4ca85  call     string [mscorlib]System.String::Concat(object, object)
0x4ca8a  callvirt instance void Microsoft.Crm.Data.InitialSolutionPackageData::set_DeleteStatus(string value)
0x4ca8f  ldarg.1
0x4ca90  ldc.i4.1
0x4ca91  callvirt instance void Microsoft.Crm.Data.InitialSolutionPackageData::set_DeleteSuccessful(bool value)
0x4ca96  ldloc.1
0x4ca97  stloc.2
0x4ca98  leave    loc_4CB94
0x4ca9d  ldloc.s  6
0x4ca9f  ldc.i4   0x80040227
0x4caa4  bne.un.s loc_4CACF
0x4caa6  ldarg.0
0x4caa7  ldarg.2
0x4caa8  ldarg.1
0x4caa9  callvirt instance string Microsoft.Crm.Data.InitialSolutionPackageData::get_EntityName()
0x4caae  ldarg.1
0x4caaf  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Data.InitialSolutionPackageData::get_RecordId()
0x4cab4  ldloca.s 8
0x4cab6  ldloca.s 9
0x4cab8  call     instance void Microsoft.Crm.Data.InitialSolutionDataManager::FindAndFixProblematicRelatedRecords(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService sdk, string entityName, valuetype [mscorlib]System.Guid recordId, [out] string& debugMessage, [out] int32& recordsUpdated)
0x4cabd  ldarg.s  4
0x4cabf  brfalse.s loc_4CACA
0x4cac1  ldloc.0
0x4cac2  ldloc.s  8
0x4cac4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x4cac9  pop
0x4caca  ldloc.1
0x4cacb  ldloc.s  9
0x4cacd  add
0x4cace  stloc.1
0x4cacf  ldc.i4.s 9
0x4cad1  newarr   [mscorlib]System.Object
0x4cad6  dup
0x4cad7  ldc.i4.0
0x4cad8  ldstr    aError_1// "Error "
0x4cadd  stelem.ref
0x4cade  dup
0x4cadf  ldc.i4.1
0x4cae0  ldloc.s  6
0x4cae2  box      [mscorlib]System.Int32
0x4cae7  stelem.ref
0x4cae8  dup
0x4cae9  ldc.i4.2
0x4caea  ldstr    asc_7BC08// " : "
0x4caef  stelem.ref
0x4caf0  dup
0x4caf1  ldc.i4.3
0x4caf2  ldloc.s  4
0x4caf4  callvirt instance string [mscorlib]System.Object::ToString()
0x4caf9  stelem.ref
0x4cafa  dup
0x4cafb  ldc.i4.4
0x4cafc  ldstr    aAttemptedOn// " Attempted on ["
0x4cb01  stelem.ref
0x4cb02  dup
0x4cb03  ldc.i4.5
0x4cb04  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x4cb09  stloc.3
0x4cb0a  ldloca.s 3
0x4cb0c  ldstr    aG// "G"
0x4cb11  call     instance string [mscorlib]System.DateTime::ToString(string)
0x4cb16  stelem.ref
0x4cb17  dup
0x4cb18  ldc.i4.6
0x4cb19  ldstr    aPass// "] Pass : "
0x4cb1e  stelem.ref
0x4cb1f  dup
0x4cb20  ldc.i4.7
0x4cb21  ldarg.3
0x4cb22  box      [mscorlib]System.Int32
0x4cb27  stelem.ref
0x4cb28  dup
0x4cb29  ldc.i4.8
0x4cb2a  ldstr    asc_6B1E0// ","
0x4cb2f  stelem.ref
0x4cb30  call     string [mscorlib]System.String::Concat(object[])
0x4cb35  stloc.s  7
0x4cb37  ldloc.s  7
0x4cb39  ldloc.0
0x4cb3a  callvirt instance string [mscorlib]System.Object::ToString()
0x4cb3f  call     string [mscorlib]System.String::Concat(string, string)
0x4cb44  stloc.s  7
0x4cb46  ldarg.s  5
0x4cb48  ldc.i4.6
0x4cb49  newarr   [mscorlib]System.Object
0x4cb4e  dup
0x4cb4f  ldc.i4.0
0x4cb50  ldstr    aRecord// "Record ["
0x4cb55  stelem.ref
0x4cb56  dup
0x4cb57  ldc.i4.1
0x4cb58  ldarg.1
0x4cb59  callvirt instance string Microsoft.Crm.Data.InitialSolutionPackageData::get_EntityName()
0x4cb5e  stelem.ref
0x4cb5f  dup
0x4cb60  ldc.i4.2
0x4cb61  ldstr    asc_7BCEC// "] ["
0x4cb66  stelem.ref
0x4cb67  dup
0x4cb68  ldc.i4.3
0x4cb69  ldarg.1
0x4cb6a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Data.InitialSolutionPackageData::get_RecordId()
0x4cb6f  box      [mscorlib]System.Guid
0x4cb74  stelem.ref
0x4cb75  dup
0x4cb76  ldc.i4.4
0x4cb77  ldstr    asc_7BCF4// "] "
0x4cb7c  stelem.ref
0x4cb7d  dup
0x4cb7e  ldc.i4.5
0x4cb7f  ldloc.s  7
0x4cb81  stelem.ref
0x4cb82  call     string [mscorlib]System.String::Concat(object[])
0x4cb87  stind.ref
0x4cb88  ldarg.1
0x4cb89  ldloc.s  7
0x4cb8b  callvirt instance void Microsoft.Crm.Data.InitialSolutionPackageData::set_DeleteStatus(string value)
0x4cb90  leave.s  loc_4CB92
0x4cb92  ldloc.1
0x4cb93  ret
0x4cb94  ldloc.2
0x4cb95  ret
```
