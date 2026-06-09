# Microsoft.Crm.Data.InitialSolutionDataManager::TryRemoveAllSampleData_0

- ea: `0x4c190`
- end: `0x4c5cb`
- name: `Microsoft.Crm.Data.InitialSolutionDataManager::TryRemoveAllSampleData_0`
- size: `1083`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x4c170`

## callees

- `0x4b350`
- `0x4b390`
- `0x4b3a0`
- `0x4b3e0`
- `0x4ba10`
- `0x4bb40`
- `0x4bb90`
- `0x4bbe0`
- `0x4bc30`
- `0x4bc50`
- `0x4bfc0`
- `0x4c190`
- `0x4c8b0`
- `0x4cba0`
- `0x4d0c0`
- `0x4d0f0`
- `0x4d130`

## string_xrefs

- `0x4c1a7`: `Starting TryRemoveAllSampleData with `
- `0x4c2d7`: `SampleDataDeleteEntitiesToSkip`
- `0x4c3a0`: `Skipped since entityType was excluded by configuration`
- `0x4c3b9`: `Records to delete : `
- `0x4c40e`: `Starting data delete pass : `
- `0x4c44c`: `Records deleted\modified : `
- `0x4c5a2`: `Calling RenameAndDisableDemoUsers`
- `0x4c5c0`: `Completed TryRemoveAllSampleData`

## pseudocode

```c

```

## disassembly

```asm
0x4c190  ldarg.2
0x4c191  ldstr    aSdklist// "sdkList"
0x4c196  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x4c19b  ldarg.2
0x4c19c  ldstr    aSdklist// "sdkList"
0x4c1a1  call     T0x2B000063
0x4c1a6  ldarg.3
0x4c1a7  ldstr    aStartingTryrem// "Starting TryRemoveAllSampleData with "
0x4c1ac  ldarg.2
0x4c1ad  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService>::get_Count()
0x4c1b2  box      [mscorlib]System.Int32
0x4c1b7  ldstr    aSdkInstances// " sdk instances"
0x4c1bc  call     string [mscorlib]System.String::Concat(object, object, object)
0x4c1c1  callvirt instance void class [mscorlib]System.Action`1<string>::Invoke(var<u1>)
0x4c1c6  ldarg.2
0x4c1c7  call     T0x2B000064
0x4c1cc  stloc.0
0x4c1cd  ldsfld   string [mscorlib]System.String::Empty
0x4c1d2  stloc.1
0x4c1d3  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x4c1d8  ldstr    aSampledataproc// "SampleDataProcessingStepsToDisable"
0x4c1dd  ldc.i4.1
0x4c1de  callvirt T0x2B000001
0x4c1e3  stloc.1
0x4c1e4  leave.s  loc_4C1FA
0x4c1e6  stloc.2
0x4c1e7  ldarg.3
0x4c1e8  ldstr    aExceptionRetri// "Exception retrieving SampleDataProcessi"...
0x4c1ed  ldloc.2
0x4c1ee  call     string [mscorlib]System.String::Concat(object, object)
0x4c1f3  callvirt instance void class [mscorlib]System.Action`1<string>::Invoke(var<u1>)
0x4c1f8  leave.s  loc_4C1FA
0x4c1fa  ldarg.3
0x4c1fb  ldstr    aStepstodisable// "StepsToDisable ["
0x4c200  ldloc.1
0x4c201  ldstr    asc_6E6E2// "]"
0x4c206  call     string [mscorlib]System.String::Concat(string, string, string)
0x4c20b  callvirt instance void class [mscorlib]System.Action`1<string>::Invoke(var<u1>)
0x4c210  ldloc.1
0x4c211  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x4c216  brtrue   loc_4C2AF
0x4c21b  ldloc.1
0x4c21c  ldc.i4.1
0x4c21d  newarr   [mscorlib]System.Char
0x4c222  dup
0x4c223  ldc.i4.0
0x4c224  ldc.i4.s 0x2C
0x4c226  stelem.i2
0x4c227  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x4c22c  stloc.3
0x4c22d  ldc.i4.0
0x4c22e  stloc.s  4
0x4c230  br.s     loc_4C2A8
0x4c232  ldloc.3
0x4c233  ldloc.s  4
0x4c235  ldelem.ref
0x4c236  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Parse(string)
0x4c23b  stloc.s  5
0x4c23d  ldarg.3
0x4c23e  ldstr    aDisablingSdkme// "Disabling sdkmessageprocessingstep : "
0x4c243  ldloc.s  5
0x4c245  box      [mscorlib]System.Guid
0x4c24a  call     string [mscorlib]System.String::Concat(object, object)
0x4c24f  callvirt instance void class [mscorlib]System.Action`1<string>::Invoke(var<u1>)
0x4c254  ldloc.0
0x4c255  newobj   instance void Microsoft.Crm.Data.SetStateRequest::.ctor()
0x4c25a  dup
0x4c25b  ldstr    aSdkmessageproc// "sdkmessageprocessingstep"
0x4c260  ldloc.s  5
0x4c262  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x4c267  callvirt instance void Microsoft.Crm.Data.SetStateRequest::set_EntityMoniker(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference value)
0x4c26c  dup
0x4c26d  ldc.i4.1
0x4c26e  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x4c273  callvirt instance void Microsoft.Crm.Data.SetStateRequest::set_State(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue value)
0x4c278  dup
0x4c279  ldc.i4.2
0x4c27a  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x4c27f  callvirt instance void Microsoft.Crm.Data.SetStateRequest::set_Status(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue value)
0x4c284  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x4c289  pop
0x4c28a  leave.s  loc_4C2A2
0x4c28c  stloc.s  6
0x4c28e  ldarg.3
0x4c28f  ldstr    aExceptionDisab// "Exception disabling step : "
0x4c294  ldloc.s  6
0x4c296  call     string [mscorlib]System.String::Concat(object, object)
0x4c29b  callvirt instance void class [mscorlib]System.Action`1<string>::Invoke(var<u1>)
0x4c2a0  leave.s  loc_4C2A2
0x4c2a2  ldloc.s  4
0x4c2a4  ldc.i4.1
0x4c2a5  add
0x4c2a6  stloc.s  4
0x4c2a8  ldloc.s  4
0x4c2aa  ldloc.3
0x4c2ab  ldlen
0x4c2ac  conv.i4
0x4c2ad  blt.s    loc_4C232
0x4c2af  ldarg.1
0x4c2b0  call     class Microsoft.Crm.Data.IBasicOrganizationDataContext Microsoft.Crm.Data.BasicOrganizationDataContext::New(valuetype [mscorlib]System.Guid orgId)
0x4c2b5  stloc.s  7
0x4c2b7  ldloc.s  7
0x4c2b9  callvirt instance class [System.Data.Linq]System.Data.Linq.ITable`1<class Microsoft.Crm.Data.InitialSolutionPackageData> Microsoft.Crm.Data.IBasicOrganizationDataContext::get_InitialSolutionPackageDataTable()
0x4c2be  call     T0x2B00005F
0x4c2c3  stloc.s  8
0x4c2c5  ldloc.s  7
0x4c2c7  callvirt instance class [System.Data.Linq]System.Data.Linq.ITable`1<class Microsoft.Crm.Data.InitialSolutionPackageDataStatus> Microsoft.Crm.Data.IBasicOrganizationDataContext::get_InitialSolutionPackageDataStatusTable()
0x4c2cc  call     T0x2B00005D
0x4c2d1  pop
0x4c2d2  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x4c2d7  ldstr    aSampledatadele// "SampleDataDeleteEntitiesToSkip"
0x4c2dc  ldc.i4.1
0x4c2dd  callvirt T0x2B000001
0x4c2e2  stloc.s  9
0x4c2e4  ldloc.s  9
0x4c2e6  ldc.i4.1
0x4c2e7  newarr   [mscorlib]System.Char
0x4c2ec  dup
0x4c2ed  ldc.i4.0
0x4c2ee  ldc.i4.s 0x2C
0x4c2f0  stelem.i2
0x4c2f1  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x4c2f6  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x4c2fb  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>, !!T0)
0x4c300  pop
0x4c301  ldloc.s  8
0x4c303  ldsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Data.InitialSolutionPackageData, int32> <>c::<>9__8_0
0x4c308  dup
0x4c309  brtrue.s loc_4C322
0x4c30b  pop
0x4c30c  ldsfld   class <>c <>c::<>9
0x4c311  ldftn    instance int32 <>c::<TryRemoveAllSampleData>b__8_0(class Microsoft.Crm.Data.InitialSolutionPackageData x)
0x4c317  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.Data.InitialSolutionPackageData, int32>::.ctor(object, native int)
0x4c31c  dup
0x4c31d  stsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Data.InitialSolutionPackageData, int32> <>c::<>9__8_0
0x4c322  call     T0x2B000065
0x4c327  ldsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Data.InitialSolutionPackageData, string> <>c::<>9__8_1
0x4c32c  dup
0x4c32d  brtrue.s loc_4C346
0x4c32f  pop
0x4c330  ldsfld   class <>c <>c::<>9
0x4c335  ldftn    instance string <>c::<TryRemoveAllSampleData>b__8_1(class Microsoft.Crm.Data.InitialSolutionPackageData x)
0x4c33b  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.Data.InitialSolutionPackageData, string>::.ctor(object, native int)
0x4c340  dup
0x4c341  stsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Data.InitialSolutionPackageData, string> <>c::<>9__8_1
0x4c346  call     T0x2B000066
0x4c34b  ldsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Data.InitialSolutionPackageData, valuetype [mscorlib]System.Guid> <>c::<>9__8_2
0x4c350  dup
0x4c351  brtrue.s loc_4C36A
0x4c353  pop
0x4c354  ldsfld   class <>c <>c::<>9
0x4c359  ldftn    instance valuetype [mscorlib]System.Guid <>c::<TryRemoveAllSampleData>b__8_2(class Microsoft.Crm.Data.InitialSolutionPackageData x)
0x4c35f  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.Data.InitialSolutionPackageData, valuetype [mscorlib]System.Guid>::.ctor(object, native int)
0x4c364  dup
0x4c365  stsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Data.InitialSolutionPackageData, valuetype [mscorlib]System.Guid> <>c::<>9__8_2
0x4c36a  call     T0x2B000067
0x4c36f  call     T0x2B00005F
0x4c374  stloc.s  8
0x4c376  ldloc.s  8
0x4c378  stloc.s  0xC
0x4c37a  ldc.i4.0
0x4c37b  stloc.s  4
0x4c37d  br.s     loc_4C3B0
0x4c37f  ldloc.s  0xC
0x4c381  ldloc.s  4
0x4c383  ldelem.ref
0x4c384  stloc.s  0xD
0x4c386  ldloc.s  9
0x4c388  ldloc.s  0xD
0x4c38a  callvirt instance string Microsoft.Crm.Data.InitialSolutionPackageData::get_EntityName()
0x4c38f  callvirt instance bool [mscorlib]System.String::Contains(string)
0x4c394  brfalse.s loc_4C3AA
0x4c396  ldloc.s  0xD
0x4c398  ldc.i4.1
0x4c399  callvirt instance void Microsoft.Crm.Data.InitialSolutionPackageData::set_DeleteSkipped(bool value)
0x4c39e  ldloc.s  0xD
0x4c3a0  ldstr    aSkippedSinceEn// "Skipped since entityType was excluded b"...
0x4c3a5  callvirt instance void Microsoft.Crm.Data.InitialSolutionPackageData::set_DeleteStatus(string value)
0x4c3aa  ldloc.s  4
0x4c3ac  ldc.i4.1
0x4c3ad  add
0x4c3ae  stloc.s  4
0x4c3b0  ldloc.s  4
0x4c3b2  ldloc.s  0xC
0x4c3b4  ldlen
0x4c3b5  conv.i4
0x4c3b6  blt.s    loc_4C37F
0x4c3b8  ldarg.3
0x4c3b9  ldstr    aRecordsToDelet// "Records to delete : "
0x4c3be  ldloc.s  8
0x4c3c0  ldsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Data.InitialSolutionPackageData, bool> <>c::<>9__8_3
0x4c3c5  dup
0x4c3c6  brtrue.s loc_4C3DF
0x4c3c8  pop
0x4c3c9  ldsfld   class <>c <>c::<>9
0x4c3ce  ldftn    instance bool <>c::<TryRemoveAllSampleData>b__8_3(class Microsoft.Crm.Data.InitialSolutionPackageData x)
0x4c3d4  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.Data.InitialSolutionPackageData, bool>::.ctor(object, native int)
0x4c3d9  dup
0x4c3da  stsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Data.InitialSolutionPackageData, bool> <>c::<>9__8_3
0x4c3df  call     T0x2B000068
0x4c3e4  box      [mscorlib]System.Int32
0x4c3e9  call     string [mscorlib]System.String::Concat(object, object)
0x4c3ee  callvirt instance void class [mscorlib]System.Action`1<string>::Invoke(var<u1>)
0x4c3f3  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x4c3f8  stloc.s  0xA
0x4c3fa  ldc.i4.0
0x4c3fb  stloc.s  0xB
0x4c3fd  ldc.i4.0
0x4c3fe  stloc.s  0xE
0x4c400  br       loc_4C48F
0x4c405  ldarg.3
0x4c406  ldc.i4.4
0x4c407  newarr   [mscorlib]System.Object
0x4c40c  dup
0x4c40d  ldc.i4.0
0x4c40e  ldstr    aStartingDataDe// "Starting data delete pass : "
0x4c413  stelem.ref
0x4c414  dup
0x4c415  ldc.i4.1
0x4c416  ldloc.s  0xE
0x4c418  box      [mscorlib]System.Int32
0x4c41d  stelem.ref
0x4c41e  dup
0x4c41f  ldc.i4.2
0x4c420  ldstr    aIsfinal// " isFinal: "
0x4c425  stelem.ref
0x4c426  dup
0x4c427  ldc.i4.3
0x4c428  ldloca.s 0xB
0x4c42a  call     instance string [mscorlib]System.Boolean::ToString()
0x4c42f  stelem.ref
0x4c430  call     string [mscorlib]System.String::Concat(object[])
0x4c435  callvirt instance void class [mscorlib]System.Action`1<string>::Invoke(var<u1>)
0x4c43a  ldarg.0
0x4c43b  ldloc.s  8
0x4c43d  ldarg.2
0x4c43e  ldloc.s  0xE
0x4c440  ldloc.s  0xB
0x4c442  ldloca.s 0xA
0x4c444  call     instance int32 Microsoft.Crm.Data.InitialSolutionDataManager::DeletionPass(class Microsoft.Crm.Data.InitialSolutionPackageData[] records, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService> sdkList, int32 passNumber, bool collectDebugInformation, [out] class [mscorlib]System.Collections.Generic.List`1<string>& errors)
0x4c449  stloc.s  0xF
0x4c44b  ldarg.3
0x4c44c  ldstr    aRecordsDeleted// "Records deleted\\modified : "
0x4c451  ldloc.s  0xF
0x4c453  box      [mscorlib]System.Int32
0x4c458  call     string [mscorlib]System.String::Concat(object, object)
0x4c45d  callvirt instance void class [mscorlib]System.Action`1<string>::Invoke(var<u1>)
0x4c462  ldarg.3
0x4c463  ldstr    aDeletionErrors// "Deletion errors : "
0x4c468  ldloc.s  0xA
0x4c46a  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x4c46f  box      [mscorlib]System.Int32
0x4c474  call     string [mscorlib]System.String::Concat(object, object)
0x4c479  callvirt instance void class [mscorlib]System.Action`1<string>::Invoke(var<u1>)
0x4c47e  ldloc.s  0xB
0x4c480  brtrue.s loc_4C498
0x4c482  ldloc.s  0xF
0x4c484  brtrue.s loc_4C489
0x4c486  ldc.i4.1
0x4c487  stloc.s  0xB
0x4c489  ldloc.s  0xE
0x4c48b  ldc.i4.1
0x4c48c  add
0x4c48d  stloc.s  0xE
0x4c48f  ldloc.s  0xE
0x4c491  ldc.i4.s 0xA
0x4c493  blt      loc_4C405
0x4c498  ldarg.3
0x4c499  ldstr    aRecordErrorsSt// "---RECORD ERRORS START---"
0x4c49e  callvirt instance void class [mscorlib]System.Action`1<string>::Invoke(var<u1>)
0x4c4a3  ldloc.s  0xA
0x4c4a5  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0x4c4aa  stloc.s  0x10
0x4c4ac  br.s     loc_4C4BF
0x4c4ae  ldloca.s 0x10
0x4c4b0  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0x4c4b5  stloc.s  0x11
0x4c4b7  ldarg.3
0x4c4b8  ldloc.s  0x11
0x4c4ba  callvirt instance void class [mscorlib]System.Action`1<string>::Invoke(var<u1>)
0x4c4bf  ldloca.s 0x10
0x4c4c1  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::MoveNext()
0x4c4c6  brtrue.s loc_4C4AE
0x4c4c8  leave.s  loc_4C4D8
0x4c4ca  ldloca.s 0x10
0x4c4cc  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>
0x4c4d2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4c4d7  endfinally
0x4c4d8  ldarg.3
0x4c4d9  ldstr    aRecordErrorsEn// "---RECORD ERRORS END---"
0x4c4de  callvirt instance void class [mscorlib]System.Action`1<string>::Invoke(var<u1>)
0x4c4e3  ldloc.s  7
0x4c4e5  callvirt instance void Microsoft.Crm.Data.IBasicOrganizationDataContext::SubmitChanges()
0x4c4ea  leave.s  loc_4C4F8
0x4c4ec  ldloc.s  7
0x4c4ee  brfalse.s loc_4C4F7
0x4c4f0  ldloc.s  7
0x4c4f2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4c4f7  endfinally
0x4c4f8  ldloc.1
  ... truncated ...
```
