# Microsoft.Crm.ObjectModel.PluginTypeStatisticService::Write

- ea: `0x1398e0`
- end: `0x139bae`
- name: `Microsoft.Crm.ObjectModel.PluginTypeStatisticService::Write`
- size: `718`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x682b0`
- `0x682c0`
- `0x682d0`
- `0x1398e0`

## string_xrefs

- `0x139a61`: `plugintypeid`
- `0x139914`: `PluginType`
- `0x1398ec`: `pluginTypeId`
- `0x139987`: `PluginTypeStatistic`
- `0x1398f7`: `writer`
- `0x139955`: `PluginTypeStatisticService: Skipping statistic creation as plugin type with id: {0} not found in org: {1}.`
- `0x1399a7`: `plugintypestatisticid`
- `0x139a4f`: `plugintypestatisticid`
- `0x1399e2`: `PluginTypeStatisticService: RetrieveMultiple failed: `
- `0x139a17`: `PluginTypeStatisticService: RetrieveMultiple OK`
- `0x139a9b`: `PluginTypeStatisticService: Create OK`
- `0x139abc`: `PluginTypeStatisticService: Create failed: `
- `0x139b1c`: `PluginTypeStatisticService: Update OK`
- `0x139b3d`: `PluginTypeStatisticService: Update failed: `
- `0x139b84`: `PluginTypeStatisticService: request failed: `

## pseudocode

```c

```

## disassembly

```asm
0x1398e0  ldarg.1
0x1398e1  ldstr    aOrganizationid_0// "organizationId"
0x1398e6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x1398eb  ldarg.2
0x1398ec  ldstr    aPlugintypeid_1// "pluginTypeId"
0x1398f1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x1398f6  ldarg.3
0x1398f7  ldstr    aWriter// "writer"
0x1398fc  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x139901  ldarg.1
0x139902  ldc.i4.0
0x139903  ldc.i4.0
0x139904  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x139909  stloc.0
0x13990a  ldloc.0
0x13990b  ldc.i4.1
0x13990c  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(bool)
0x139911  ldc.i4.1
0x139912  stloc.1
0x139913  ldarg.2
0x139914  ldstr    aPlugintype// "PluginType"
0x139919  ldloc.0
0x13991a  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x13991f  stloc.2
0x139920  ldloc.0
0x139921  ldc.i4.1
0x139922  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0x139927  stloc.3
0x139928  ldarg.0
0x139929  ldloc.2
0x13992a  ldloc.0
0x13992b  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x139930  pop
0x139931  leave.s  loc_13993D
0x139933  ldloc.3
0x139934  brfalse.s loc_13993C
0x139936  ldloc.3
0x139937  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x13993c  endfinally
0x13993d  leave.s  loc_139981
0x13993f  pop
0x139940  ldarg.1
0x139941  ldc.i4.s 0x28
0x139943  ldstr    a0_0// "{0}"
0x139948  ldc.i4.1
0x139949  newarr   [mscorlib]System.Object
0x13994e  dup
0x13994f  ldc.i4.0
0x139950  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x139955  ldstr    aPlugintypestat_0// "PluginTypeStatisticService: Skipping st"...
0x13995a  ldc.i4.2
0x13995b  newarr   [mscorlib]System.Object
0x139960  dup
0x139961  ldc.i4.0
0x139962  ldarg.2
0x139963  box      [mscorlib]System.Guid
0x139968  stelem.ref
0x139969  dup
0x13996a  ldc.i4.1
0x13996b  ldarg.1
0x13996c  box      [mscorlib]System.Guid
0x139971  stelem.ref
0x139972  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x139977  stelem.ref
0x139978  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x13997d  ldc.i4.0
0x13997e  stloc.1
0x13997f  leave.s  loc_139981
0x139981  ldloc.1
0x139982  brfalse  loc_139B62
0x139987  ldstr    aPlugintypestat// "PluginTypeStatistic"
0x13998c  ldloc.0
0x13998d  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x139992  stloc.s  4
0x139994  ldloc.s  4
0x139996  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x13999b  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddAllColumns()
0x1399a0  ldloc.s  4
0x1399a2  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1399a7  ldstr    aPlugintypestat_1// "plugintypestatisticid"
0x1399ac  ldc.i4.0
0x1399ad  ldarg.2
0x1399ae  box      [mscorlib]System.Guid
0x1399b3  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1399b8  pop
0x1399b9  ldloc.0
0x1399ba  ldc.i4.1
0x1399bb  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0x1399c0  stloc.3
0x1399c1  ldarg.0
0x1399c2  ldloc.s  4
0x1399c4  ldloc.0
0x1399c5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1399ca  stloc.s  5
0x1399cc  leave.s  loc_1399FB
0x1399ce  stloc.s  6
0x1399d0  ldloc.s  6
0x1399d2  ldarg.1
0x1399d3  ldc.i4.s 0x28
0x1399d5  ldstr    a0_0// "{0}"
0x1399da  ldc.i4.1
0x1399db  newarr   [mscorlib]System.Object
0x1399e0  dup
0x1399e1  ldc.i4.0
0x1399e2  ldstr    aPlugintypestat_2// "PluginTypeStatisticService: RetrieveMul"...
0x1399e7  ldloc.s  6
0x1399e9  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1399ee  call     string [mscorlib]System.String::Concat(string, string)
0x1399f3  stelem.ref
0x1399f4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1399f9  rethrow
0x1399fb  leave.s  loc_139A07
0x1399fd  ldloc.3
0x1399fe  brfalse.s loc_139A06
0x139a00  ldloc.3
0x139a01  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x139a06  endfinally
0x139a07  ldarg.1
0x139a08  ldc.i4.s 0x28
0x139a0a  ldstr    a0_0// "{0}"
0x139a0f  ldc.i4.1
0x139a10  newarr   [mscorlib]System.Object
0x139a15  dup
0x139a16  ldc.i4.0
0x139a17  ldstr    aPlugintypestat_3// "PluginTypeStatisticService: RetrieveMul"...
0x139a1c  stelem.ref
0x139a1d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x139a22  ldloc.s  5
0x139a24  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x139a29  ldc.i4.1
0x139a2a  cgt
0x139a2c  ldc.i4.0
0x139a2d  ceq
0x139a2f  ldstr    aBecCount// "bec.Count"
0x139a34  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x139a39  ldloc.s  5
0x139a3b  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x139a40  brtrue   loc_139AE4
0x139a45  ldarg.1
0x139a46  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.PluginTypeStatistic::.ctor(valuetype [mscorlib]System.Guid)
0x139a4b  stloc.s  7
0x139a4d  ldloc.s  7
0x139a4f  ldstr    aPlugintypestat_1// "plugintypestatisticid"
0x139a54  ldarg.2
0x139a55  box      [mscorlib]System.Guid
0x139a5a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x139a5f  ldloc.s  7
0x139a61  ldstr    aPlugintypeid// "plugintypeid"
0x139a66  ldarg.2
0x139a67  box      [mscorlib]System.Guid
0x139a6c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x139a71  ldarg.3
0x139a72  ldloc.s  7
0x139a74  callvirt instance void Microsoft.Crm.ObjectModel.ISandboxStatisticWriter::CreateInitial(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.PluginTypeStatistic entity)
0x139a79  ldloc.0
0x139a7a  ldc.i4.1
0x139a7b  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0x139a80  stloc.3
0x139a81  ldarg.0
0x139a82  ldloc.s  7
0x139a84  ldloc.0
0x139a85  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x139a8a  pop
0x139a8b  ldarg.1
0x139a8c  ldc.i4.s 0x28
0x139a8e  ldstr    a0_0// "{0}"
0x139a93  ldc.i4.1
0x139a94  newarr   [mscorlib]System.Object
0x139a99  dup
0x139a9a  ldc.i4.0
0x139a9b  ldstr    aPlugintypestat_4// "PluginTypeStatisticService: Create OK"
0x139aa0  stelem.ref
0x139aa1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x139aa6  leave.s  loc_139AD5
0x139aa8  stloc.s  8
0x139aaa  ldloc.s  8
0x139aac  ldarg.1
0x139aad  ldc.i4.s 0x28
0x139aaf  ldstr    a0_0// "{0}"
0x139ab4  ldc.i4.1
0x139ab5  newarr   [mscorlib]System.Object
0x139aba  dup
0x139abb  ldc.i4.0
0x139abc  ldstr    aPlugintypestat_5// "PluginTypeStatisticService: Create fail"...
0x139ac1  ldloc.s  8
0x139ac3  callvirt instance string [mscorlib]System.Exception::get_Message()
0x139ac8  call     string [mscorlib]System.String::Concat(string, string)
0x139acd  stelem.ref
0x139ace  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x139ad3  rethrow
0x139ad5  leave    loc_139B62
0x139ada  ldloc.3
0x139adb  brfalse.s loc_139AE3
0x139add  ldloc.3
0x139ade  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x139ae3  endfinally
0x139ae4  ldloc.s  5
0x139ae6  ldc.i4.0
0x139ae7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x139aec  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.PluginTypeStatistic
0x139af1  stloc.s  9
0x139af3  ldarg.3
0x139af4  ldloc.s  9
0x139af6  callvirt instance void Microsoft.Crm.ObjectModel.ISandboxStatisticWriter::UpdateExisting(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.PluginTypeStatistic entity)
0x139afb  ldloc.0
0x139afc  ldc.i4.1
0x139afd  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0x139b02  stloc.3
0x139b03  ldarg.0
0x139b04  ldloc.s  9
0x139b06  ldloc.0
0x139b07  call     instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x139b0c  ldarg.1
0x139b0d  ldc.i4.s 0x28
0x139b0f  ldstr    a0_0// "{0}"
0x139b14  ldc.i4.1
0x139b15  newarr   [mscorlib]System.Object
0x139b1a  dup
0x139b1b  ldc.i4.0
0x139b1c  ldstr    aPlugintypestat_6// "PluginTypeStatisticService: Update OK"
0x139b21  stelem.ref
0x139b22  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x139b27  leave.s  loc_139B56
0x139b29  stloc.s  0xA
0x139b2b  ldloc.s  0xA
0x139b2d  ldarg.1
0x139b2e  ldc.i4.s 0x28
0x139b30  ldstr    a0_0// "{0}"
0x139b35  ldc.i4.1
0x139b36  newarr   [mscorlib]System.Object
0x139b3b  dup
0x139b3c  ldc.i4.0
0x139b3d  ldstr    aPlugintypestat_7// "PluginTypeStatisticService: Update fail"...
0x139b42  ldloc.s  0xA
0x139b44  callvirt instance string [mscorlib]System.Exception::get_Message()
0x139b49  call     string [mscorlib]System.String::Concat(string, string)
0x139b4e  stelem.ref
0x139b4f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x139b54  rethrow
0x139b56  leave.s  loc_139B62
0x139b58  ldloc.3
0x139b59  brfalse.s loc_139B61
0x139b5b  ldloc.3
0x139b5c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x139b61  endfinally
0x139b62  ldloc.0
0x139b63  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnEndRequest()
0x139b68  ldarg.3
0x139b69  callvirt instance void Microsoft.Crm.ObjectModel.ISandboxStatisticWriter::ConfirmWrite()
0x139b6e  leave.s  loc_139BAD
0x139b70  stloc.s  0xB
0x139b72  ldloc.s  0xB
0x139b74  ldarg.1
0x139b75  ldc.i4.s 0x28
0x139b77  ldstr    a0_0// "{0}"
0x139b7c  ldc.i4.1
0x139b7d  newarr   [mscorlib]System.Object
0x139b82  dup
0x139b83  ldc.i4.0
0x139b84  ldstr    aPlugintypestat_8// "PluginTypeStatisticService: request fai"...
0x139b89  ldloc.s  0xB
0x139b8b  callvirt instance string [mscorlib]System.Exception::get_Message()
0x139b90  call     string [mscorlib]System.String::Concat(string, string)
0x139b95  stelem.ref
0x139b96  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x139b9b  ldloc.0
0x139b9c  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnErrorRequest()
0x139ba1  rethrow
0x139ba3  ldloc.0
0x139ba4  brfalse.s loc_139BAC
0x139ba6  ldloc.0
0x139ba7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x139bac  endfinally
0x139bad  ret
```
