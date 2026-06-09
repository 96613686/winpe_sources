# Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::GetCrmUsersInDatabase

- ea: `0x1ea80`
- end: `0x1eb76`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::GetCrmUsersInDatabase`
- size: `246`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x214e0`
- `0x2b340`

## callees

- `0x1ea80`

## string_xrefs

- `0x1eabd`: `accessmode`
- `0x1ead6`: `accessmode`

## pseudocode

```c

```

## disassembly

```asm
0x1ea80  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x1ea85  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x1ea8a  stloc.0
0x1ea8b  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ProvisionSystemUserService::.ctor()
0x1ea90  stloc.1
0x1ea91  ldnull
0x1ea92  stloc.2
0x1ea93  ldc.i4.2
0x1ea94  call     void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Win32Utility::ImpersonateSelf(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.SecurityImpersonationLevel)
0x1ea99  ldarg.1
0x1ea9a  ldc.i4.0
0x1ea9b  ldc.i4.0
0x1ea9c  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x1eaa1  stloc.3
0x1eaa2  ldloc.3
0x1eaa3  ldc.i4.0
0x1eaa4  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(bool)
0x1eaa9  ldstr    aSystemuser// "SystemUser"
0x1eaae  ldloc.3
0x1eaaf  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x1eab4  stloc.s  4
0x1eab6  ldloc.s  4
0x1eab8  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1eabd  ldstr    aAccessmode// "accessmode"
0x1eac2  ldc.i4.1
0x1eac3  ldc.i4.3
0x1eac4  box      [mscorlib]System.Int32
0x1eac9  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1eace  pop
0x1eacf  ldloc.s  4
0x1ead1  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1ead6  ldstr    aAccessmode// "accessmode"
0x1eadb  ldc.i4.1
0x1eadc  ldc.i4.5
0x1eadd  box      [mscorlib]System.Int32
0x1eae2  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1eae7  pop
0x1eae8  ldloc.s  4
0x1eaea  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x1eaef  ldstr    aWindowsliveid// "windowsliveid"
0x1eaf4  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x1eaf9  ldloc.1
0x1eafa  ldloc.s  4
0x1eafc  ldloc.3
0x1eafd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1eb02  stloc.2
0x1eb03  ldloc.3
0x1eb04  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnEndRequest()
0x1eb09  leave.s  loc_1EB24
0x1eb0b  pop
0x1eb0c  ldloc.3
0x1eb0d  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnErrorRequest()
0x1eb12  rethrow
0x1eb14  ldloc.3
0x1eb15  brfalse.s loc_1EB1D
0x1eb17  ldloc.3
0x1eb18  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1eb1d  endfinally
0x1eb1e  call     void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Win32Utility::RevertToSelf()
0x1eb23  endfinally
0x1eb24  ldloc.2
0x1eb25  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x1eb2a  stloc.s  5
0x1eb2c  br.s     loc_1EB54
0x1eb2e  ldloc.s  5
0x1eb30  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1eb35  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x1eb3a  stloc.s  6
0x1eb3c  ldloc.0
0x1eb3d  ldloc.s  6
0x1eb3f  ldstr    aWindowsliveid// "windowsliveid"
0x1eb44  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1eb49  castclass [mscorlib]System.String
0x1eb4e  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1eb53  pop
0x1eb54  ldloc.s  5
0x1eb56  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1eb5b  brtrue.s loc_1EB2E
0x1eb5d  leave.s  loc_1EB74
0x1eb5f  ldloc.s  5
0x1eb61  isinst   [mscorlib]System.IDisposable
0x1eb66  stloc.s  7
0x1eb68  ldloc.s  7
0x1eb6a  brfalse.s loc_1EB73
0x1eb6c  ldloc.s  7
0x1eb6e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1eb73  endfinally
0x1eb74  ldloc.0
0x1eb75  ret
```
