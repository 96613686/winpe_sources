# Microsoft.Crm.Asynchronous.ImportOperationImport::MoveAsyncJobToReadyState

- ea: `0xcc10`
- end: `0xcdb3`
- name: `Microsoft.Crm.Asynchronous.ImportOperationImport::MoveAsyncJobToReadyState`
- size: `419`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xc8e0`
- `0xd8f0`

## callees

- `0xcc10`

## string_xrefs

- `0xcce0`: ` could not be moved to Ready State | {0}`
- `0xcd4a`: ` could not be moved to Ready State | {0}`
- `0xcd8e`: ` could not be moved to Ready State | {0}`
- `0xcca4`: ` could not be moved to Ready State`

## pseudocode

```c

```

## disassembly

```asm
0xcc10  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor()
0xcc15  stloc.0
0xcc16  ldloc.0
0xcc17  ldstr    aAsyncoperation_0// "asyncoperation"
0xcc1c  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_LogicalName(string)
0xcc21  ldloc.0
0xcc22  ldarg.1
0xcc23  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Id(valuetype [mscorlib]System.Guid)
0xcc28  ldloc.0
0xcc29  ldstr    aStatecode// "statecode"
0xcc2e  ldc.i4.0
0xcc2f  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0xcc34  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0xcc39  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.UpdateRequest::.ctor()
0xcc3e  stloc.1
0xcc3f  ldloc.1
0xcc40  ldloc.0
0xcc41  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.UpdateRequest::set_Target(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0xcc46  ldarg.0
0xcc47  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.ImportOperation::_crmService
0xcc4c  ldloc.1
0xcc4d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0xcc52  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.UpdateResponse
0xcc57  pop
0xcc58  leave    loc_CDAF
0xcc5d  stloc.2
0xcc5e  ldloc.2
0xcc5f  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0xcc64  ldc.i4   0x80044165
0xcc69  beq.s    loc_CC85
0xcc6b  ldloc.2
0xcc6c  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0xcc71  ldc.i4   0x80044166
0xcc76  beq.s    loc_CC85
0xcc78  ldloc.2
0xcc79  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0xcc7e  ldc.i4   0x80044162
0xcc83  bne.un.s loc_CCC0
0xcc85  ldarg.0
0xcc86  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xcc8b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xcc90  ldc.i4.s 0x18
0xcc92  ldstr    aChildJobWithId// "Child job with Id"
0xcc97  ldarga.s 1
0xcc99  constrained. [mscorlib]System.Guid
0xcc9f  callvirt instance string [mscorlib]System.Object::ToString()
0xcca4  ldstr    aCouldNotBeMove_0// " could not be moved to Ready State"
0xcca9  call     string [mscorlib]System.String::Concat(string, string, string)
0xccae  ldc.i4.0
0xccaf  newarr   [mscorlib]System.Object
0xccb4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xccb9  ldc.i4.0
0xccba  stloc.3
0xccbb  leave    loc_CDB1
0xccc0  ldloc.2
0xccc1  ldarg.0
0xccc2  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xccc7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xcccc  ldc.i4.s 0x18
0xccce  ldstr    aChildJobWithId// "Child job with Id"
0xccd3  ldarga.s 1
0xccd5  constrained. [mscorlib]System.Guid
0xccdb  callvirt instance string [mscorlib]System.Object::ToString()
0xcce0  ldstr    aCouldNotBeMove// " could not be moved to Ready State | {0"...
0xcce5  call     string [mscorlib]System.String::Concat(string, string, string)
0xccea  ldc.i4.1
0xcceb  newarr   [mscorlib]System.Object
0xccf0  dup
0xccf1  ldc.i4.0
0xccf2  ldloc.2
0xccf3  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0xccf8  stelem.ref
0xccf9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xccfe  rethrow
0xcd00  stloc.s  4
0xcd02  ldloc.s  4
0xcd04  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0xcd09  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_ErrorCode()
0xcd0e  stloc.s  5
0xcd10  ldloc.s  5
0xcd12  ldc.i4   0x80044165
0xcd17  beq.s    loc_CD2B
0xcd19  ldloc.s  5
0xcd1b  ldc.i4   0x80044166
0xcd20  beq.s    loc_CD2B
0xcd22  ldloc.s  5
0xcd24  ldc.i4   0x80044162
0xcd29  bne.un.s loc_CD6D
0xcd2b  ldarg.0
0xcd2c  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xcd31  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xcd36  ldc.i4.s 0x18
0xcd38  ldstr    aChildJobWithId// "Child job with Id"
0xcd3d  ldarga.s 1
0xcd3f  constrained. [mscorlib]System.Guid
0xcd45  callvirt instance string [mscorlib]System.Object::ToString()
0xcd4a  ldstr    aCouldNotBeMove// " could not be moved to Ready State | {0"...
0xcd4f  call     string [mscorlib]System.String::Concat(string, string, string)
0xcd54  ldc.i4.1
0xcd55  newarr   [mscorlib]System.Object
0xcd5a  dup
0xcd5b  ldc.i4.0
0xcd5c  ldloc.s  4
0xcd5e  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0xcd63  stelem.ref
0xcd64  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xcd69  ldc.i4.0
0xcd6a  stloc.3
0xcd6b  leave.s  loc_CDB1
0xcd6d  ldloc.s  4
0xcd6f  ldarg.0
0xcd70  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xcd75  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xcd7a  ldc.i4.s 0x18
0xcd7c  ldstr    aChildJobWithId// "Child job with Id"
0xcd81  ldarga.s 1
0xcd83  constrained. [mscorlib]System.Guid
0xcd89  callvirt instance string [mscorlib]System.Object::ToString()
0xcd8e  ldstr    aCouldNotBeMove// " could not be moved to Ready State | {0"...
0xcd93  call     string [mscorlib]System.String::Concat(string, string, string)
0xcd98  ldc.i4.1
0xcd99  newarr   [mscorlib]System.Object
0xcd9e  dup
0xcd9f  ldc.i4.0
0xcda0  ldloc.s  4
0xcda2  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0xcda7  stelem.ref
0xcda8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xcdad  rethrow
0xcdaf  ldc.i4.1
0xcdb0  ret
0xcdb1  ldloc.3
0xcdb2  ret
```
