# Microsoft.Crm.Asynchronous.LanguagePacksDataAccess::CreateWorkerAsyncOperation

- ea: `0xcb60`
- end: `0xcceb`
- name: `Microsoft.Crm.Asynchronous.LanguagePacksDataAccess::CreateWorkerAsyncOperation`
- size: `395`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0xc920`

## callees

- `0xccf0`
- `0xcd60`
- `0xcdb0`

## string_xrefs

- `0xcb68`: `if exists (select 1 from AsyncOperationBase where OperationType = @operationType and Data = @data)\nbegin\n	delete from AsyncOperationBase where OperationType = @operationType and Data = @data\nend\n\ninsert into AsyncOperationBase\n(\n	[DependencyToken],\n	[StateCode],\n	[Data],\n	[AsyncOperationId],\n	[OperationType],\n	[Name],\n	[StatusCode],\n	[PostponeUntil],\n	[Depth],\n	[OwningBusinessUnit],\n	[ModifiedBy],\n	[CreatedBy],\n	[CorrelationId],\n	[OwnerId],\n	[OwnerIdType`
- `0xcba5`: `@dependencyToken`
- `0xcbaa`: `ReprovisionMuiPacksDependencyToken`
- `0xcc86`: `@createdBy`

## pseudocode

```c

```

## disassembly

```asm
0xcb60  ldarg.0
0xcb61  ldarg.1
0xcb62  call     instance string Microsoft.Crm.Asynchronous.LanguagePacksDataAccess::CompressData(int32 lcid)
0xcb67  stloc.0
0xcb68  ldstr    aIfExistsSelect// "if exists (select 1 from AsyncOperation"...
0xcb6d  ldc.i4.1
0xcb6e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0xcb73  stloc.1
0xcb74  ldloc.1
0xcb75  ldstr    aData_0// "@data"
0xcb7a  ldloc.0
0xcb7b  ldloca.s 3
0xcb7d  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0xcb83  ldloc.3
0xcb84  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0xcb89  ldloc.1
0xcb8a  ldstr    aOperationtype// "@operationType"
0xcb8f  ldc.i4.s 0x2B
0xcb91  box      [mscorlib]System.Int32
0xcb96  ldloca.s 3
0xcb98  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0xcb9e  ldloc.3
0xcb9f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0xcba4  ldloc.1
0xcba5  ldstr    aDependencytoke// "@dependencyToken"
0xcbaa  ldstr    aReprovisionmui// "ReprovisionMuiPacksDependencyToken"
0xcbaf  ldloca.s 3
0xcbb1  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0xcbb7  ldloc.3
0xcbb8  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0xcbbd  ldloc.1
0xcbbe  ldstr    aStatecode// "@stateCode"
0xcbc3  ldc.i4.1
0xcbc4  box      [mscorlib]System.Int32
0xcbc9  ldloca.s 3
0xcbcb  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0xcbd1  ldloc.3
0xcbd2  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0xcbd7  ldloc.1
0xcbd8  ldstr    aStatuscode// "@statusCode"
0xcbdd  ldc.i4.s 0xA
0xcbdf  box      [mscorlib]System.Int32
0xcbe4  ldloca.s 3
0xcbe6  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0xcbec  ldloc.3
0xcbed  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0xcbf2  ldloc.1
0xcbf3  ldstr    aPostponeuntil// "@postponeUntil"
0xcbf8  ldarg.2
0xcbf9  box      [mscorlib]System.DateTime
0xcbfe  ldloca.s 3
0xcc00  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0xcc06  ldloc.3
0xcc07  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0xcc0c  ldloc.1
0xcc0d  ldstr    aName_1// "@name"
0xcc12  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xcc17  ldstr    aReprovisioning_0// "Reprovisioning Job For {0}"
0xcc1c  ldc.i4.1
0xcc1d  newarr   [mscorlib]System.Object
0xcc22  dup
0xcc23  ldc.i4.0
0xcc24  ldarga.s 1
0xcc26  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xcc2b  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xcc30  stelem.ref
0xcc31  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xcc36  ldloca.s 3
0xcc38  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0xcc3e  ldloc.3
0xcc3f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0xcc44  ldloc.1
0xcc45  ldstr    aBusinessunitid// "@businessUnitId"
0xcc4a  ldarg.0
0xcc4b  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.LanguagePacksDataAccess::GetBusinessUnitId()
0xcc50  box      [mscorlib]System.Guid
0xcc55  ldloca.s 3
0xcc57  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0xcc5d  ldloc.3
0xcc5e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0xcc63  ldarg.0
0xcc64  ldarg.3
0xcc65  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.LanguagePacksDataAccess::GetSystemUserId(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent asyncEvent)
0xcc6a  stloc.2
0xcc6b  ldloc.1
0xcc6c  ldstr    aModifiedby// "@modifiedBy"
0xcc71  ldloc.2
0xcc72  box      [mscorlib]System.Guid
0xcc77  ldloca.s 3
0xcc79  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0xcc7f  ldloc.3
0xcc80  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0xcc85  ldloc.1
0xcc86  ldstr    aCreatedby// "@createdBy"
0xcc8b  ldloc.2
0xcc8c  box      [mscorlib]System.Guid
0xcc91  ldloca.s 3
0xcc93  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0xcc99  ldloc.3
0xcc9a  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0xcc9f  ldloc.1
0xcca0  ldstr    aOwnerid// "@ownerId"
0xcca5  ldloc.2
0xcca6  box      [mscorlib]System.Guid
0xccab  ldloca.s 3
0xccad  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0xccb3  ldloc.3
0xccb4  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0xccb9  ldloc.1
0xccba  ldstr    aCorrelationid// "@correlationId"
0xccbf  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0xccc4  box      [mscorlib]System.Guid
0xccc9  ldloca.s 3
0xcccb  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0xccd1  ldloc.3
0xccd2  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0xccd7  ldarg.0
0xccd8  ldloc.1
0xccd9  ldarg.0
0xccda  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0xccdf  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xcce4  call     instance object [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteScalar(class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo, valuetype [mscorlib]System.Guid)
0xcce9  pop
0xccea  ret
```
