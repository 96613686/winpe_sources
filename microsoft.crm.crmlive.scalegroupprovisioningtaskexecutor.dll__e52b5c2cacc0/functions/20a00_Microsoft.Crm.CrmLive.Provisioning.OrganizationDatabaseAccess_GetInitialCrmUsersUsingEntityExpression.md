# Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::GetInitialCrmUsersUsingEntityExpression

- ea: `0x20a00`
- end: `0x20b01`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::GetInitialCrmUsersUsingEntityExpression`
- size: `257`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1dc20`
- `0x20b10`

## callees

- `0x20a00`

## string_xrefs

- `0x20a48`: `accessmode`
- `0x20a93`: `createdon`
- `0x20ac3`: `createdon`

## pseudocode

```c

```

## disassembly

```asm
0x20a00  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ProvisionSystemUserService::.ctor()
0x20a05  stloc.0
0x20a06  ldnull
0x20a07  stloc.1
0x20a08  ldc.i4.2
0x20a09  call     void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Win32Utility::ImpersonateSelf(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.SecurityImpersonationLevel)
0x20a0e  ldarg.1
0x20a0f  ldc.i4.0
0x20a10  ldc.i4.0
0x20a11  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x20a16  stloc.2
0x20a17  ldloc.2
0x20a18  ldc.i4.0
0x20a19  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(bool)
0x20a1e  ldstr    aSystemuser// "SystemUser"
0x20a23  ldloc.2
0x20a24  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x20a29  stloc.3
0x20a2a  ldloc.3
0x20a2b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x20a30  ldstr    aIsdisabled// "isdisabled"
0x20a35  ldc.i4.0
0x20a36  ldc.i4.0
0x20a37  box      [mscorlib]System.Boolean
0x20a3c  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x20a41  pop
0x20a42  ldloc.3
0x20a43  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x20a48  ldstr    aAccessmode// "accessmode"
0x20a4d  ldc.i4.s 9
0x20a4f  ldc.i4.2
0x20a50  newarr   [mscorlib]System.Object
0x20a55  dup
0x20a56  ldc.i4.0
0x20a57  ldc.i4.3
0x20a58  box      [mscorlib]System.Int32
0x20a5d  stelem.ref
0x20a5e  dup
0x20a5f  ldc.i4.1
0x20a60  ldc.i4.5
0x20a61  box      [mscorlib]System.Int32
0x20a66  stelem.ref
0x20a67  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x20a6c  pop
0x20a6d  ldloc.3
0x20a6e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x20a73  ldstr    aSystemuserid_0// "systemuserid"
0x20a78  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x20a7d  ldloc.3
0x20a7e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x20a83  ldstr    aFullname// "fullname"
0x20a88  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x20a8d  ldloc.3
0x20a8e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x20a93  ldstr    aCreatedon_0// "createdon"
0x20a98  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x20a9d  ldloc.3
0x20a9e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x20aa3  ldstr    aWindowsliveid// "windowsliveid"
0x20aa8  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x20aad  ldloc.3
0x20aae  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x20ab3  ldstr    aDomainname_0// "domainname"
0x20ab8  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x20abd  ldloc.3
0x20abe  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.OrderExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Order()
0x20ac3  ldstr    aCreatedon_0// "createdon"
0x20ac8  ldc.i4.0
0x20ac9  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.OrderExpression::AddOrder(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderType)
0x20ace  ldloc.3
0x20acf  ldc.i4.1
0x20ad0  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::set_NoLock(bool)
0x20ad5  ldloc.0
0x20ad6  ldloc.3
0x20ad7  ldloc.2
0x20ad8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x20add  stloc.1
0x20ade  ldloc.2
0x20adf  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnEndRequest()
0x20ae4  leave.s  loc_20AFF
0x20ae6  pop
0x20ae7  ldloc.2
0x20ae8  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnErrorRequest()
0x20aed  rethrow
0x20aef  ldloc.2
0x20af0  brfalse.s loc_20AF8
0x20af2  ldloc.2
0x20af3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20af8  endfinally
0x20af9  call     void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Win32Utility::RevertToSelf()
0x20afe  endfinally
0x20aff  ldloc.1
0x20b00  ret
```
