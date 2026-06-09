# Microsoft.Crm.Admin.AdminService.RestorePoints.RestorePointUtility::CreateRestorePoint

- ea: `0x3b590`
- end: `0x3b73c`
- name: `Microsoft.Crm.Admin.AdminService.RestorePoints.RestorePointUtility::CreateRestorePoint`
- size: `428`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x25a40`
- `0x271f0`
- `0x3b590`
- `0x3c4f0`

## string_xrefs

- `0x3b611`: `CreatedOn`
- `0x3b68f`: `CreatedByUserId`
- `0x3b6cc`: `CreateRestorePoint`
- `0x3b6fc`: `RestorePoint entity created`

## pseudocode

```c

```

## disassembly

```asm
0x3b590  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x3b595  ldc.i4.s 0x1D
0x3b597  ldstr    aCreatingANewRe// "Creating a new restore point: Type = {0"...
0x3b59c  ldc.i4.5
0x3b59d  newarr   [mscorlib]System.Object
0x3b5a2  dup
0x3b5a3  ldc.i4.0
0x3b5a4  ldarg.0
0x3b5a5  box      [Microsoft.Crm.Core]Microsoft.Crm.RestorePointType
0x3b5aa  stelem.ref
0x3b5ab  dup
0x3b5ac  ldc.i4.1
0x3b5ad  ldarg.1
0x3b5ae  box      [mscorlib]System.Guid
0x3b5b3  stelem.ref
0x3b5b4  dup
0x3b5b5  ldc.i4.2
0x3b5b6  ldarg.2
0x3b5b7  stelem.ref
0x3b5b8  dup
0x3b5b9  ldc.i4.3
0x3b5ba  ldarg.3
0x3b5bb  stelem.ref
0x3b5bc  dup
0x3b5bd  ldc.i4.4
0x3b5be  ldarg.s  4
0x3b5c0  stelem.ref
0x3b5c1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3b5c6  ldarg.1
0x3b5c7  ldstr    aOrganizationid// "organizationId"
0x3b5cc  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x3b5d1  ldarg.2
0x3b5d2  ldstr    aLabel// "label"
0x3b5d7  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x3b5dc  ldarg.s  4
0x3b5de  ldstr    aOrganizationve// "organizationVersion"
0x3b5e3  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x3b5e8  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x3b5ed  stloc.0
0x3b5ee  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x3b5f3  stloc.1
0x3b5f4  newobj   instance void Microsoft.Crm.Admin.AdminService.CrmOrganizationService::.ctor()
0x3b5f9  ldarg.1
0x3b5fa  callvirt instance int32 Microsoft.Crm.Admin.AdminService.CrmOrganizationService::RetrieveEffectiveUsedStorageMB(valuetype [mscorlib]System.Guid organizationId)
0x3b5ff  stloc.2
0x3b600  ldstr    aId// "Id"
0x3b605  ldloc.0
0x3b606  box      [mscorlib]System.Guid
0x3b60b  ldloc.1
0x3b60c  call     void Microsoft.Crm.Admin.AdminService.RestorePoints.RestorePointUtility::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x3b611  ldstr    aCreatedon// "CreatedOn"
0x3b616  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x3b61b  box      [mscorlib]System.DateTime
0x3b620  ldloc.1
0x3b621  call     void Microsoft.Crm.Admin.AdminService.RestorePoints.RestorePointUtility::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x3b626  ldstr    aLabel_0// "Label"
0x3b62b  ldarg.2
0x3b62c  ldloc.1
0x3b62d  call     void Microsoft.Crm.Admin.AdminService.RestorePoints.RestorePointUtility::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x3b632  ldstr    aNotes// "Notes"
0x3b637  ldarg.3
0x3b638  ldloc.1
0x3b639  call     void Microsoft.Crm.Admin.AdminService.RestorePoints.RestorePointUtility::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x3b63e  ldstr    aOrganizationid_0// "OrganizationId"
0x3b643  ldarg.1
0x3b644  box      [mscorlib]System.Guid
0x3b649  ldloc.1
0x3b64a  call     void Microsoft.Crm.Admin.AdminService.RestorePoints.RestorePointUtility::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x3b64f  ldstr    aRestorepointty// "RestorePointType"
0x3b654  ldarg.0
0x3b655  box      [Microsoft.Crm.Core]Microsoft.Crm.RestorePointType
0x3b65a  ldloc.1
0x3b65b  call     void Microsoft.Crm.Admin.AdminService.RestorePoints.RestorePointUtility::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x3b660  ldstr    aState// "State"
0x3b665  ldc.i4.1
0x3b666  box      [Microsoft.Crm.Core]Microsoft.Crm.RestorePointState
0x3b66b  ldloc.1
0x3b66c  call     void Microsoft.Crm.Admin.AdminService.RestorePoints.RestorePointUtility::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x3b671  ldstr    aVersion// "Version"
0x3b676  ldarg.s  4
0x3b678  ldloc.1
0x3b679  call     void Microsoft.Crm.Admin.AdminService.RestorePoints.RestorePointUtility::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x3b67e  ldstr    aEffectiveuseds// "EffectiveUsedStorage"
0x3b683  ldloc.2
0x3b684  box      [mscorlib]System.Int32
0x3b689  ldloc.1
0x3b68a  call     void Microsoft.Crm.Admin.AdminService.RestorePoints.RestorePointUtility::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x3b68f  ldstr    aCreatedbyuseri// "CreatedByUserId"
0x3b694  ldnull
0x3b695  ldloc.1
0x3b696  call     void Microsoft.Crm.Admin.AdminService.RestorePoints.RestorePointUtility::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x3b69b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x3b6a0  stloc.3
0x3b6a1  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x3b6a6  ldc.i4.s 0x1D
0x3b6a8  ldstr    a0// "{0}"
0x3b6ad  ldc.i4.1
0x3b6ae  newarr   [mscorlib]System.Object
0x3b6b3  dup
0x3b6b4  ldc.i4.0
0x3b6b5  ldstr    aCreatingRestor// "Creating RestorePoint entity"
0x3b6ba  stelem.ref
0x3b6bb  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3b6c0  ldloc.3
0x3b6c1  ldstr    aRestorepoint// "RestorePoint"
0x3b6c6  ldloc.1
0x3b6c7  ldc.i4   0x81
0x3b6cc  ldstr    aCreaterestorep// "CreateRestorePoint"
0x3b6d1  ldstr    aDA1SSrcCrmlive_66// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Resto"...
0x3b6d6  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x3b6db  pop
0x3b6dc  leave.s  loc_3B6E8
0x3b6de  ldloc.3
0x3b6df  brfalse.s loc_3B6E7
0x3b6e1  ldloc.3
0x3b6e2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3b6e7  endfinally
0x3b6e8  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x3b6ed  ldc.i4.s 0x1D
0x3b6ef  ldstr    a0// "{0}"
0x3b6f4  ldc.i4.1
0x3b6f5  newarr   [mscorlib]System.Object
0x3b6fa  dup
0x3b6fb  ldc.i4.0
0x3b6fc  ldstr    aRestorepointEn// "RestorePoint entity created"
0x3b701  stelem.ref
0x3b702  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3b707  leave.s  loc_3B73A
0x3b709  stloc.s  4
0x3b70b  ldloc.s  4
0x3b70d  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x3b712  ldc.i4.s 0x1D
0x3b714  ldstr    aExceptionThrow_0// "Exception thrown while creating Restore"...
0x3b719  ldc.i4.2
0x3b71a  newarr   [mscorlib]System.Object
0x3b71f  dup
0x3b720  ldc.i4.0
0x3b721  ldloc.s  4
0x3b723  callvirt instance string [mscorlib]System.Exception::get_Message()
0x3b728  stelem.ref
0x3b729  dup
0x3b72a  ldc.i4.1
0x3b72b  ldloc.s  4
0x3b72d  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x3b732  stelem.ref
0x3b733  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3b738  rethrow
0x3b73a  ldloc.0
0x3b73b  ret
```
