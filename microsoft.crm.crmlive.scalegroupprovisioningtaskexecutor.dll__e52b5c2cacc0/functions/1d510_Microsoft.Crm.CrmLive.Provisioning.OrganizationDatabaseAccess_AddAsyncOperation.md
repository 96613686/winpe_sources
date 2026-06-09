# Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::AddAsyncOperation

- ea: `0x1d510`
- end: `0x1d65e`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::AddAsyncOperation`
- size: `334`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1d510`
- `0x20910`

## string_xrefs

- `0x1d59d`: `correlationupdatedtime`
- `0x1d5f6`: `GUID inconsistent for job {0}, may not be able to update through CrmLive admin tool`
- `0x1d62b`: `Error creating system task for recurring job {0}: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x1d510  ldarg.1
0x1d511  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::RetrieveSystemUserIdFromOrganizationBase(valuetype [mscorlib]System.Guid organizationId)
0x1d516  stloc.0
0x1d517  ldarg.1
0x1d518  ldc.i4.0
0x1d519  ldc.i4.0
0x1d51a  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x1d51f  stloc.1
0x1d520  ldc.i4.2
0x1d521  call     void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Win32Utility::ImpersonateSelf(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.SecurityImpersonationLevel)
0x1d526  ldloc.1
0x1d527  ldloc.0
0x1d528  ldc.i4.0
0x1d529  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(valuetype [mscorlib]System.Guid, bool)
0x1d52e  ldloc.1
0x1d52f  ldc.i4.1
0x1d530  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0x1d535  stloc.2
0x1d536  ldloc.1
0x1d537  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1d53c  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AsyncOperation::.ctor(valuetype [mscorlib]System.Guid)
0x1d541  stloc.3
0x1d542  ldloc.3
0x1d543  ldstr    aAsyncoperation// "asyncoperationid"
0x1d548  ldarg.2
0x1d549  box      [mscorlib]System.Guid
0x1d54e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1d553  ldloc.3
0x1d554  ldstr    aOperationtype_0// "operationtype"
0x1d559  ldarg.3
0x1d55a  box      [mscorlib]System.Int32
0x1d55f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1d564  ldloc.3
0x1d565  ldstr    aRecurrencepatt// "recurrencepattern"
0x1d56a  ldarg.s  4
0x1d56c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1d571  ldloc.3
0x1d572  ldstr    aRecurrencestar// "recurrencestarttime"
0x1d577  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x1d57c  ldc.i4.1
0x1d57d  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::FromUniversal(valuetype [mscorlib]System.DateTime, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Behavior)
0x1d582  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1d587  ldloc.3
0x1d588  ldstr    aCorrelationid// "correlationid"
0x1d58d  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x1d592  box      [mscorlib]System.Guid
0x1d597  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1d59c  ldloc.3
0x1d59d  ldstr    aCorrelationupd// "correlationupdatedtime"
0x1d5a2  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x1d5a7  ldc.i4.1
0x1d5a8  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::FromUniversal(valuetype [mscorlib]System.DateTime, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Behavior)
0x1d5ad  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1d5b2  ldloc.3
0x1d5b3  ldstr    aName_0// "name"
0x1d5b8  ldarg.s  5
0x1d5ba  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1d5bf  ldloc.3
0x1d5c0  ldstr    aDepth// "depth"
0x1d5c5  ldc.i4.1
0x1d5c6  box      [mscorlib]System.Int32
0x1d5cb  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1d5d0  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AsyncOperationService::.ctor()
0x1d5d5  ldloc.3
0x1d5d6  ldloc.1
0x1d5d7  ldc.i4.0
0x1d5d8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AsyncOperationServiceInternal`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.UpgradingOff>::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0x1d5dd  stloc.s  4
0x1d5df  ldarg.2
0x1d5e0  ldloc.s  4
0x1d5e2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x1d5e7  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1d5ec  brfalse.s loc_1D60B
0x1d5ee  ldloc.1
0x1d5ef  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1d5f4  ldc.i4.s 0x15
0x1d5f6  ldstr    aGuidInconsiste// "GUID inconsistent for job {0}, may not "...
0x1d5fb  ldc.i4.1
0x1d5fc  newarr   [mscorlib]System.Object
0x1d601  dup
0x1d602  ldc.i4.0
0x1d603  ldarg.s  5
0x1d605  stelem.ref
0x1d606  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1d60b  leave.s  loc_1D617
0x1d60d  ldloc.2
0x1d60e  brfalse.s loc_1D616
0x1d610  ldloc.2
0x1d611  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d616  endfinally
0x1d617  ldloc.1
0x1d618  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnEndRequest()
0x1d61d  leave.s  loc_1D65D
0x1d61f  stloc.s  5
0x1d621  ldloc.s  5
0x1d623  ldloc.1
0x1d624  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1d629  ldc.i4.s 0x15
0x1d62b  ldstr    aErrorCreatingS// "Error creating system task for recurrin"...
0x1d630  ldc.i4.2
0x1d631  newarr   [mscorlib]System.Object
0x1d636  dup
0x1d637  ldc.i4.0
0x1d638  ldarg.s  5
0x1d63a  stelem.ref
0x1d63b  dup
0x1d63c  ldc.i4.1
0x1d63d  ldloc.s  5
0x1d63f  stelem.ref
0x1d640  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1d645  ldloc.1
0x1d646  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnErrorRequest()
0x1d64b  rethrow
0x1d64d  call     void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Win32Utility::RevertToSelf()
0x1d652  endfinally
0x1d653  ldloc.1
0x1d654  brfalse.s loc_1D65C
0x1d656  ldloc.1
0x1d657  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d65c  endfinally
0x1d65d  ret
```
