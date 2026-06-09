# Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::SetOrderedQuerySetXml

- ea: `0xf00`
- end: `0xff1`
- name: `Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::SetOrderedQuerySetXml`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1f350`

## string_xrefs

- `0xf00`: `if not exists (select 1 from BulkDeleteOperationBase where AsyncOperationId = @asyncOperationId) \nbegin\n	INSERT INTO BulkDeleteOperationBase \n		(AsyncOperationId, \n		BulkDeleteOperationId, \n		OrderedQuerySetXml, \n		ModifiedOn, \n		OwnerId, \n		OwnerIdType,\n		OwningUser, \n		OwningBusinessUnit, \n		CreatedOn, \n		ModifiedBy, \n		CreatedBy) \n	VALUES \n		(@asyncOperationId, \n		NEWID(), \n		@querySetXml, \n		@modifiedOn, \n		@ownerId, \n		8, \n		@owningUser,\n		@owning`
- `0xf27`: `@querySetXml`
- `0xfa5`: `@createdBy`

## pseudocode

```c

```

## disassembly

```asm
0xf00  ldstr    aIfNotExistsSel// "if not exists (select 1 from BulkDelete"...
0xf05  ldc.i4.1
0xf06  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0xf0b  stloc.0
0xf0c  ldloc.0
0xf0d  ldstr    aAsyncoperation// "@asyncOperationId"
0xf12  ldarg.1
0xf13  box      [mscorlib]System.Guid
0xf18  ldloca.s 1
0xf1a  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0xf20  ldloc.1
0xf21  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0xf26  ldloc.0
0xf27  ldstr    aQuerysetxml// "@querySetXml"
0xf2c  ldarg.2
0xf2d  ldloca.s 1
0xf2f  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0xf35  ldloc.1
0xf36  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0xf3b  ldloc.0
0xf3c  ldstr    aOwnerid// "@ownerId"
0xf41  ldarg.3
0xf42  box      [mscorlib]System.Guid
0xf47  ldloca.s 1
0xf49  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0xf4f  ldloc.1
0xf50  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0xf55  ldloc.0
0xf56  ldstr    aOwninguser// "@owningUser"
0xf5b  ldarg.3
0xf5c  box      [mscorlib]System.Guid
0xf61  ldloca.s 1
0xf63  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0xf69  ldloc.1
0xf6a  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0xf6f  ldloc.0
0xf70  ldstr    aOwningbusiness// "@owningBusinessUnit"
0xf75  ldarg.s  4
0xf77  box      [mscorlib]System.Guid
0xf7c  ldloca.s 1
0xf7e  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0xf84  ldloc.1
0xf85  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0xf8a  ldloc.0
0xf8b  ldstr    aModifiedby// "@modifiedBy"
0xf90  ldarg.3
0xf91  box      [mscorlib]System.Guid
0xf96  ldloca.s 1
0xf98  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0xf9e  ldloc.1
0xf9f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0xfa4  ldloc.0
0xfa5  ldstr    aCreatedby// "@createdBy"
0xfaa  ldarg.3
0xfab  box      [mscorlib]System.Guid
0xfb0  ldloca.s 1
0xfb2  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0xfb8  ldloc.1
0xfb9  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0xfbe  ldloc.0
0xfbf  ldstr    aModifiedon// "@modifiedOn"
0xfc4  ldarg.0
0xfc5  call     instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::GetUTCDateWithoutMilliseconds()
0xfca  box      [mscorlib]System.DateTime
0xfcf  ldloca.s 1
0xfd1  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0xfd7  ldloc.1
0xfd8  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0xfdd  ldarg.0
0xfde  ldloc.0
0xfdf  ldarg.0
0xfe0  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0xfe5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xfea  call     instance object [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteScalar(class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo, valuetype [mscorlib]System.Guid)
0xfef  pop
0xff0  ret
```
