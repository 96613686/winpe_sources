# Microsoft.Crm.Asynchronous.PublishDuplicateRuleOperation::InternalExecute

- ea: `0x1dc50`
- end: `0x1dd67`
- name: `Microsoft.Crm.Asynchronous.PublishDuplicateRuleOperation::InternalExecute`
- size: `279`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1dc50`
- `0x1dd70`
- `0x1ed50`
- `0x1f0e0`

## string_xrefs

- `0x1dcd4`: `Exception during rule publish async operation {0}: {1}`
- `0x1dd3b`: `Unpublish of a rule inside exception handler failed: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1dc50  ldarg.1
0x1dc51  ldstr    aAsyncevent// "asyncEvent"
0x1dc56  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1dc5b  ldarg.1
0x1dc5c  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OperationType()
0x1dc61  ldc.i4.7
0x1dc62  ceq
0x1dc64  ldstr    aOperationTypeM_7// "Operation type must be 'PublishDuplicat"...
0x1dc69  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x1dc6e  ldarg.1
0x1dc6f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_RegardingObject()
0x1dc74  ldstr    aRegardingobjec_3// "RegardingObjectId"
0x1dc79  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1dc7e  ldarg.1
0x1dc7f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_RegardingObject()
0x1dc84  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::get_Value()
0x1dc89  stloc.0
0x1dc8a  ldloc.0
0x1dc8b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1dc90  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1dc95  brfalse.s loc_1DCA2
0x1dc97  ldstr    aInvalidDuplica// "Invalid duplicateRuleId retrieved from "...
0x1dc9c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x1dca1  throw
0x1dca2  ldarg.1
0x1dca3  ldc.i4.1
0x1dca4  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService [Microsoft.Crm.Asynchronous.HandlerUtility]Microsoft.Crm.Asynchronous.SdkServiceFactory::CreateInstance(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent, bool)
0x1dca9  stloc.1
0x1dcaa  ldarg.0
0x1dcab  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0x1dcb0  newobj   instance void Microsoft.Crm.Asynchronous.DuplicateRuleDataAccess::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration config)
0x1dcb5  stloc.2
0x1dcb6  ldnull
0x1dcb7  stloc.3
0x1dcb8  ldarg.0
0x1dcb9  ldloc.0
0x1dcba  ldarg.1
0x1dcbb  ldloc.2
0x1dcbc  ldloc.1
0x1dcbd  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult Microsoft.Crm.Asynchronous.PublishDuplicateRuleOperation::DoPublish(valuetype [mscorlib]System.Guid duplicateRuleId, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent asyncEvent, class Microsoft.Crm.Asynchronous.DuplicateRuleDataAccess data, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService crmService)
0x1dcc2  stloc.3
0x1dcc3  leave    loc_1DD62
0x1dcc8  stloc.s  4
0x1dcca  ldloc.s  4
0x1dccc  ldarg.1
0x1dccd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x1dcd2  ldc.i4.s 0x15
0x1dcd4  ldstr    aExceptionDurin// "Exception during rule publish async ope"...
0x1dcd9  ldc.i4.2
0x1dcda  newarr   [mscorlib]System.Object
0x1dcdf  dup
0x1dce0  ldc.i4.0
0x1dce1  ldarg.1
0x1dce2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_EventId()
0x1dce7  box      [mscorlib]System.Guid
0x1dcec  stelem.ref
0x1dced  dup
0x1dcee  ldc.i4.1
0x1dcef  ldloc.s  4
0x1dcf1  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x1dcf6  stelem.ref
0x1dcf7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1dcfc  ldloc.s  4
0x1dcfe  isinst   class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>
0x1dd03  stloc.s  5
0x1dd05  ldloc.s  5
0x1dd07  brfalse.s loc_1DD1E
0x1dd09  ldloc.s  5
0x1dd0b  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x1dd10  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_ErrorCode()
0x1dd15  ldc.i4   0x8004A001
0x1dd1a  bne.un.s loc_1DD1E
0x1dd1c  rethrow
0x1dd1e  nop
0x1dd1f  ldloc.0
0x1dd20  ldloc.2
0x1dd21  ldarg.1
0x1dd22  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x1dd27  ldloc.1
0x1dd28  call     void Microsoft.Crm.Asynchronous.PublishDuplicateRuleOperation::UnpublishRule(valuetype [mscorlib]System.Guid ruleId, class Microsoft.Crm.Asynchronous.DuplicateRuleDataAccess data, valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService crmService)
0x1dd2d  leave.s  loc_1DD57
0x1dd2f  stloc.s  6
0x1dd31  ldloc.s  6
0x1dd33  ldarg.1
0x1dd34  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x1dd39  ldc.i4.s 0x15
0x1dd3b  ldstr    aUnpublishOfARu// "Unpublish of a rule inside exception ha"...
0x1dd40  ldc.i4.1
0x1dd41  newarr   [mscorlib]System.Object
0x1dd46  dup
0x1dd47  ldc.i4.0
0x1dd48  ldloc.s  6
0x1dd4a  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x1dd4f  stelem.ref
0x1dd50  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1dd55  leave.s  loc_1DD57
0x1dd57  ldloc.s  4
0x1dd59  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncFailedResult::.ctor(class [mscorlib]System.Exception)
0x1dd5e  stloc.s  7
0x1dd60  leave.s  loc_1DD64
0x1dd62  ldloc.3
0x1dd63  ret
0x1dd64  ldloc.s  7
0x1dd66  ret
```
