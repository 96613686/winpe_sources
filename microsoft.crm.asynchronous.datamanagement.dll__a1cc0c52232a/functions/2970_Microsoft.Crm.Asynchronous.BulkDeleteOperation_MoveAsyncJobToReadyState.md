# Microsoft.Crm.Asynchronous.BulkDeleteOperation::MoveAsyncJobToReadyState

- ea: `0x2970`
- end: `0x2a69`
- name: `Microsoft.Crm.Asynchronous.BulkDeleteOperation::MoveAsyncJobToReadyState`
- size: `249`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2930`

## callees

- `0x2970`

## string_xrefs

- `0x2a01`: ` could not be moved to Ready State | {0}`
- `0x2a44`: ` could not be moved to Ready State | {0}`

## pseudocode

```c

```

## disassembly

```asm
0x2970  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor()
0x2975  stloc.0
0x2976  ldloc.0
0x2977  ldstr    aAsyncoperation_0// "asyncoperation"
0x297c  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_LogicalName(string)
0x2981  ldloc.0
0x2982  ldarg.1
0x2983  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Id(valuetype [mscorlib]System.Guid)
0x2988  ldloc.0
0x2989  ldstr    aStatecode// "statecode"
0x298e  ldc.i4.0
0x298f  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x2994  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x2999  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.UpdateRequest::.ctor()
0x299e  stloc.1
0x299f  ldloc.1
0x29a0  ldloc.0
0x29a1  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.UpdateRequest::set_Target(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x29a6  ldarg.0
0x29a7  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.BulkDeleteOperation::_crmService
0x29ac  ldloc.1
0x29ad  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x29b2  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.UpdateResponse
0x29b7  pop
0x29b8  leave    loc_2A64
0x29bd  stloc.2
0x29be  ldloc.2
0x29bf  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x29c4  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_ErrorCode()
0x29c9  stloc.3
0x29ca  ldloc.3
0x29cb  ldc.i4   0x80044165
0x29d0  beq.s    loc_29E2
0x29d2  ldloc.3
0x29d3  ldc.i4   0x80044166
0x29d8  beq.s    loc_29E2
0x29da  ldloc.3
0x29db  ldc.i4   0x80044162
0x29e0  bne.un.s loc_2A24
0x29e2  ldarg.0
0x29e3  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0x29e8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x29ed  ldc.i4.s 0x18
0x29ef  ldstr    aChildJobWithId// "Child job with Id"
0x29f4  ldarga.s 1
0x29f6  constrained. [mscorlib]System.Guid
0x29fc  callvirt instance string [mscorlib]System.Object::ToString()
0x2a01  ldstr    aCouldNotBeMove// " could not be moved to Ready State | {0"...
0x2a06  call     string [mscorlib]System.String::Concat(string, string, string)
0x2a0b  ldc.i4.1
0x2a0c  newarr   [mscorlib]System.Object
0x2a11  dup
0x2a12  ldc.i4.0
0x2a13  ldloc.2
0x2a14  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x2a19  stelem.ref
0x2a1a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2a1f  ldc.i4.0
0x2a20  stloc.s  4
0x2a22  leave.s  loc_2A66
0x2a24  ldloc.2
0x2a25  ldarg.0
0x2a26  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0x2a2b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x2a30  ldc.i4.s 0x18
0x2a32  ldstr    aChildJobWithId// "Child job with Id"
0x2a37  ldarga.s 1
0x2a39  constrained. [mscorlib]System.Guid
0x2a3f  callvirt instance string [mscorlib]System.Object::ToString()
0x2a44  ldstr    aCouldNotBeMove// " could not be moved to Ready State | {0"...
0x2a49  call     string [mscorlib]System.String::Concat(string, string, string)
0x2a4e  ldc.i4.1
0x2a4f  newarr   [mscorlib]System.Object
0x2a54  dup
0x2a55  ldc.i4.0
0x2a56  ldloc.2
0x2a57  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x2a5c  stelem.ref
0x2a5d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2a62  rethrow
0x2a64  ldc.i4.1
0x2a65  ret
0x2a66  ldloc.s  4
0x2a68  ret
```
