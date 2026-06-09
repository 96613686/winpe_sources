# Microsoft.Crm.Asynchronous.ImportOperationImport::SubmitAsyncJob

- ea: `0xc8e0`
- end: `0xcbcd`
- name: `Microsoft.Crm.Asynchronous.ImportOperationImport::SubmitAsyncJob`
- size: `749`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0xc4c0`
- `0xc560`
- `0xc5a0`
- `0xd5a0`

## callees

- `0x3b80`
- `0xc8e0`
- `0xcbd0`
- `0xcc10`
- `0xcdc0`

## string_xrefs

- `0xc9e2`: `dependencytoken`
- `0xca21`: `correlationupdatedtime`

## pseudocode

```c

```

## disassembly

```asm
0xc8e0  ldarg.2
0xc8e1  stloc.2
0xc8e2  ldloca.s 2
0xc8e4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc8e9  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xc8ee  stloc.0
0xc8ef  ldarg.0
0xc8f0  ldarg.1
0xc8f1  ldloc.0
0xc8f2  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection Microsoft.Crm.Asynchronous.ImportOperationImport::AsyncOperationAlreadyExists(valuetype [mscorlib]System.Guid importFileId, string passInfo)
0xc8f7  stloc.1
0xc8f8  ldloc.1
0xc8f9  brtrue   loc_CB5D
0xc8fe  ldarg.0
0xc8ff  ldfld    class Microsoft.Crm.Asynchronous.ImportSampleData Microsoft.Crm.Asynchronous.ImportOperationImport::_sampleDataOperation
0xc904  brfalse.s loc_C925
0xc906  ldarg.0
0xc907  ldarg.1
0xc908  ldarg.2
0xc909  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult Microsoft.Crm.Asynchronous.ImportOperationImport::ExecuteImportFileOperation(valuetype [mscorlib]System.Guid importFileId, valuetype PassPhase passInfo)
0xc90e  isinst   [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncFailedResult
0xc913  brfalse  loc_CBCC
0xc918  ldarg.0
0xc919  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.ImportOperationImport::_failedJobs
0xc91e  ldarg.1
0xc91f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0xc924  ret
0xc925  ldarg.0
0xc926  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xc92b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xc930  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0xc935  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc93a  ldstr    aImportfile_0// "ImportFile"
0xc93f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string)
0xc944  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xc949  ldarg.1
0xc94a  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0xc94f  stloc.3
0xc950  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor()
0xc955  stloc.s  4
0xc957  ldloc.s  4
0xc959  ldstr    aAsyncoperation_0// "asyncoperation"
0xc95e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_LogicalName(string)
0xc963  ldloc.s  4
0xc965  ldstr    aName_0// "name"
0xc96a  ldarg.0
0xc96b  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.ImportOperation::_asyncEvent
0xc970  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_RegardingObject()
0xc975  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::get_name()
0xc97a  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0xc97f  ldarg.0
0xc980  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.ImportOperation::_crmService
0xc985  ldstr    aImportfile// "importfile"
0xc98a  ldloc.3
0xc98b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0xc990  ldc.i4.1
0xc991  newarr   [mscorlib]System.String
0xc996  dup
0xc997  ldc.i4.0
0xc998  ldstr    aName_0// "name"
0xc99d  stelem.ref
0xc99e  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0xc9a3  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Retrieve(string, valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0xc9a8  stloc.s  5
0xc9aa  ldloc.s  5
0xc9ac  brfalse.s loc_C9D3
0xc9ae  ldloc.s  5
0xc9b0  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xc9b5  ldstr    aName_0// "name"
0xc9ba  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0xc9bf  brfalse.s loc_C9D3
0xc9c1  ldloc.3
0xc9c2  ldloc.s  5
0xc9c4  ldstr    aName_0// "name"
0xc9c9  call     string Microsoft.Crm.Asynchronous.DataManagementHelper::GetStringFromDynamicEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity de, string propertyName)
0xc9ce  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::set_Name(string)
0xc9d3  ldloc.s  4
0xc9d5  ldstr    aRegardingobjec_2// "regardingobjectid"
0xc9da  ldloc.3
0xc9db  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0xc9e0  ldloc.s  4
0xc9e2  ldstr    aDependencytoke_0// "dependencytoken"
0xc9e7  ldarg.3
0xc9e8  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0xc9ed  ldloc.s  4
0xc9ef  ldstr    aData_0// "data"
0xc9f4  ldloc.0
0xc9f5  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0xc9fa  ldloc.s  4
0xc9fc  ldstr    aOperationtype// "operationtype"
0xca01  ldc.i4.s 0x11
0xca03  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0xca08  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0xca0d  ldloc.s  4
0xca0f  ldstr    aDepth// "depth"
0xca14  ldc.i4.2
0xca15  box      [mscorlib]System.Int32
0xca1a  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0xca1f  ldloc.s  4
0xca21  ldstr    aCorrelationupd// "correlationupdatedtime"
0xca26  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xca2b  box      [mscorlib]System.DateTime
0xca30  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0xca35  ldloc.s  4
0xca37  ldstr    aRequestid// "requestid"
0xca3c  ldarg.0
0xca3d  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.ImportOperation::_asyncEvent
0xca42  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_RegardingObject()
0xca47  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::get_Value()
0xca4c  box      [mscorlib]System.Guid
0xca51  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0xca56  ldloc.s  4
0xca58  ldstr    aCorrelationid_0// "correlationid"
0xca5d  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0xca62  box      [mscorlib]System.Guid
0xca67  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0xca6c  ldloc.s  4
0xca6e  ldstr    aOwnerid_1// "ownerid"
0xca73  ldstr    aSystemuser// "systemuser"
0xca78  ldarg.0
0xca79  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.ImportOperation::_asyncEvent
0xca7e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_OwnerId()
0xca83  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0xca88  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0xca8d  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.CreateRequest::.ctor()
0xca92  stloc.s  6
0xca94  ldloc.s  6
0xca96  ldloc.s  4
0xca98  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.CreateRequest::set_Target(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0xca9d  ldarg.0
0xca9e  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.ImportOperation::_asyncEvent
0xcaa3  ldc.i4.1
0xcaa4  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService [Microsoft.Crm.Asynchronous.HandlerUtility]Microsoft.Crm.Asynchronous.SdkServiceFactory::CreateInstance(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent, bool)
0xcaa9  ldloc.s  6
0xcaab  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0xcab0  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.CreateResponse
0xcab5  pop
0xcab6  leave    loc_CBCC
0xcabb  stloc.s  7
0xcabd  ldloc.s  7
0xcabf  ldarg.0
0xcac0  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xcac5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xcaca  ldc.i4.s 0x15
0xcacc  ldstr    aErrorCreatingA// "Error creating asyncoperation for filei"...
0xcad1  ldc.i4.2
0xcad2  newarr   [mscorlib]System.Object
0xcad7  dup
0xcad8  ldc.i4.0
0xcad9  ldarg.1
0xcada  box      [mscorlib]System.Guid
0xcadf  stelem.ref
0xcae0  dup
0xcae1  ldc.i4.1
0xcae2  ldloc.s  7
0xcae4  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0xcae9  stelem.ref
0xcaea  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xcaef  rethrow
0xcaf1  stloc.s  8
0xcaf3  ldloc.s  8
0xcaf5  ldarg.0
0xcaf6  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xcafb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xcb00  ldc.i4.s 0x15
0xcb02  ldstr    aErrorCreatingA// "Error creating asyncoperation for filei"...
0xcb07  ldc.i4.2
0xcb08  newarr   [mscorlib]System.Object
0xcb0d  dup
0xcb0e  ldc.i4.0
0xcb0f  ldarg.1
0xcb10  box      [mscorlib]System.Guid
0xcb15  stelem.ref
0xcb16  dup
0xcb17  ldc.i4.1
0xcb18  ldloc.s  8
0xcb1a  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0xcb1f  stelem.ref
0xcb20  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xcb25  rethrow
0xcb27  stloc.s  9
0xcb29  ldloc.s  9
0xcb2b  ldarg.0
0xcb2c  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xcb31  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xcb36  ldc.i4.s 0x15
0xcb38  ldstr    aErrorCreatingA// "Error creating asyncoperation for filei"...
0xcb3d  ldc.i4.2
0xcb3e  newarr   [mscorlib]System.Object
0xcb43  dup
0xcb44  ldc.i4.0
0xcb45  ldarg.1
0xcb46  box      [mscorlib]System.Guid
0xcb4b  stelem.ref
0xcb4c  dup
0xcb4d  ldc.i4.1
0xcb4e  ldloc.s  9
0xcb50  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0xcb55  stelem.ref
0xcb56  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xcb5b  rethrow
0xcb5d  ldloc.1
0xcb5e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0xcb63  ldc.i4.0
0xcb64  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Item(!!T0)
0xcb69  stloc.s  0xA
0xcb6b  ldloc.s  0xA
0xcb6d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0xcb72  stloc.s  0xB
0xcb74  ldloc.s  0xA
0xcb76  ldstr    aStatecode// "statecode"
0xcb7b  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0xcb80  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0xcb85  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0xcb8a  ldc.i4.1
0xcb8b  bne.un.s loc_CBBF
0xcb8d  ldloc.s  0xA
0xcb8f  ldstr    aStatuscode// "statuscode"
0xcb94  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0xcb99  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0xcb9e  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0xcba3  ldc.i4.s 0xA
0xcba5  bne.un.s loc_CBBF
0xcba7  ldarg.0
0xcba8  ldloc.s  0xB
0xcbaa  call     instance bool Microsoft.Crm.Asynchronous.ImportOperationImport::MoveAsyncJobToReadyState(valuetype [mscorlib]System.Guid asyncOpId)
0xcbaf  brtrue.s loc_CBCC
0xcbb1  ldarg.0
0xcbb2  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.ImportOperationImport::_JobsToBeResumed
0xcbb7  ldloc.s  0xB
0xcbb9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0xcbbe  ret
0xcbbf  ldarg.0
0xcbc0  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.ImportOperationImport::_JobsToBeResumed
0xcbc5  ldloc.s  0xB
0xcbc7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0xcbcc  ret
```
