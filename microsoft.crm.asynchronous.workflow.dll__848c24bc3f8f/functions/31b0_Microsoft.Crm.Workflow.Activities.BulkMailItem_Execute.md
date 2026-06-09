# Microsoft.Crm.Workflow.Activities.BulkMailItem::Execute

- ea: `0x31b0`
- end: `0x33c3`
- name: `Microsoft.Crm.Workflow.Activities.BulkMailItem::Execute`
- size: `531`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x31b0`
- `0x33d0`
- `0x33f0`
- `0x3410`

## string_xrefs

- `0x32a5`: `TemplateId`

## pseudocode

```c

```

## disassembly

```asm
0x31b0  ldarg.1
0x31b1  callvirt T0x2B000004
0x31b6  stloc.0
0x31b7  ldarg.1
0x31b8  callvirt instance class [System.Activities]System.Activities.ExecutionProperties [System.Activities]System.Activities.NativeActivityContext::get_Properties()
0x31bd  ldtoken  [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.BulkMailListProperty
0x31c2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x31c7  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x31cc  callvirt instance object [System.Activities]System.Activities.ExecutionProperties::Find(string)
0x31d1  stloc.1
0x31d2  ldloc.1
0x31d3  brfalse.s loc_31EC
0x31d5  ldloc.1
0x31d6  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x31db  ldtoken  [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.BulkMailListProperty
0x31e0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x31e5  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x31ea  brfalse.s loc_31F7
0x31ec  ldstr    aInvalidValueFo// "Invalid value for BulkMailListProperty"
0x31f1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x31f6  throw
0x31f7  ldloc.1
0x31f8  castclass [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.BulkMailListProperty
0x31fd  callvirt instance class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.BulkMailListProperty::get_Receipients()
0x3202  stloc.2
0x3203  ldloc.2
0x3204  ldarg.0
0x3205  call     instance class [System.Activities]System.Activities.InArgument`1<int32> Microsoft.Crm.Workflow.Activities.BulkMailItem::get_Count()
0x320a  ldarg.1
0x320b  callvirt instance var<u1> class [System.Activities]System.Activities.InArgument`1<int32>::Get(!!T0)
0x3210  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Item(!!T0)
0x3215  stloc.3
0x3216  ldloc.0
0x3217  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InputParameters()
0x321c  ldstr    aSender// "Sender"
0x3221  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x3226  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x322b  stloc.s  4
0x322d  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.SendTemplateRequest::.ctor()
0x3232  stloc.s  5
0x3234  ldloc.s  5
0x3236  ldc.i4.1
0x3237  newarr   [mscorlib]System.Guid
0x323c  dup
0x323d  ldc.i4.0
0x323e  ldloc.3
0x323f  stelem   [mscorlib]System.Guid
0x3244  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.SendTemplateRequest::set_RecipientIds(valuetype [mscorlib]System.Guid[])
0x3249  ldloc.s  5
0x324b  ldarg.0
0x324c  call     instance class [System.Activities]System.Activities.InArgument`1<string> Microsoft.Crm.Workflow.Activities.BulkMailItem::get_EntityName()
0x3251  ldarg.1
0x3252  callvirt instance var<u1> class [System.Activities]System.Activities.InArgument`1<string>::Get(!!T0)
0x3257  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.SendTemplateRequest::set_RecipientType(string)
0x325c  ldloc.s  5
0x325e  ldloc.0
0x325f  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InputParameters()
0x3264  ldstr    aRegardingid// "RegardingId"
0x3269  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x326e  unbox.any [mscorlib]System.Guid
0x3273  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.SendTemplateRequest::set_RegardingId(valuetype [mscorlib]System.Guid)
0x3278  ldloc.s  5
0x327a  ldloc.0
0x327b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InputParameters()
0x3280  ldstr    aRegardingtype// "RegardingType"
0x3285  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x328a  castclass [mscorlib]System.String
0x328f  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.SendTemplateRequest::set_RegardingType(string)
0x3294  ldloc.s  5
0x3296  ldloc.s  4
0x3298  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.SendTemplateRequest::set_Sender(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference)
0x329d  ldloc.s  5
0x329f  ldloc.0
0x32a0  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InputParameters()
0x32a5  ldstr    aTemplateid// "TemplateId"
0x32aa  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x32af  unbox.any [mscorlib]System.Guid
0x32b4  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.SendTemplateRequest::set_TemplateId(valuetype [mscorlib]System.Guid)
0x32b9  ldloc.s  5
0x32bb  ldc.i4.0
0x32bc  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x32c1  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.SendTemplateRequest::set_DeliveryPriorityCode(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue)
0x32c6  ldloc.0
0x32c7  ldc.i4.0
0x32c8  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext::CreateSdkService(bool)
0x32cd  ldloc.s  5
0x32cf  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x32d4  pop
0x32d5  leave.s  loc_3341
0x32d7  stloc.s  6
0x32d9  ldarg.0
0x32da  call     instance class [System.Activities]System.Activities.InOutArgument`1<int32> Microsoft.Crm.Workflow.Activities.BulkMailItem::get_Failures()
0x32df  ldarg.1
0x32e0  ldarg.0
0x32e1  call     instance class [System.Activities]System.Activities.InOutArgument`1<int32> Microsoft.Crm.Workflow.Activities.BulkMailItem::get_Failures()
0x32e6  ldarg.1
0x32e7  callvirt instance var<u1> class [System.Activities]System.Activities.InOutArgument`1<int32>::Get(!!T0)
0x32ec  ldc.i4.1
0x32ed  add
0x32ee  callvirt instance void class [System.Activities]System.Activities.InOutArgument`1<int32>::Set(class [System.Activities]System.Activities.ActivityContext, var<u1>)
0x32f3  ldloc.s  6
0x32f5  ldloc.0
0x32f6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x32fb  ldc.i4.s 0x1E
0x32fd  ldstr    a0// "{0}"
0x3302  ldc.i4.1
0x3303  newarr   [mscorlib]System.Object
0x3308  dup
0x3309  ldc.i4.0
0x330a  ldloc.s  6
0x330c  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x3311  stelem.ref
0x3312  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3317  leave.s  loc_3341
0x3319  stloc.s  7
0x331b  ldloc.s  7
0x331d  ldloc.0
0x331e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x3323  ldc.i4.s 0x1E
0x3325  ldstr    a0// "{0}"
0x332a  ldc.i4.1
0x332b  newarr   [mscorlib]System.Object
0x3330  dup
0x3331  ldc.i4.0
0x3332  ldloc.s  7
0x3334  callvirt instance string [mscorlib]System.Exception::get_Message()
0x3339  stelem.ref
0x333a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x333f  rethrow
0x3341  ldarg.0
0x3342  call     instance class [System.Activities]System.Activities.InArgument`1<int32> Microsoft.Crm.Workflow.Activities.BulkMailItem::get_Count()
0x3347  ldarg.1
0x3348  callvirt instance var<u1> class [System.Activities]System.Activities.InArgument`1<int32>::Get(!!T0)
0x334d  ldloc.2
0x334e  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x3353  ldc.i4.1
0x3354  sub
0x3355  bne.un.s loc_33C2
0x3357  ldarg.0
0x3358  call     instance class [System.Activities]System.Activities.InOutArgument`1<int32> Microsoft.Crm.Workflow.Activities.BulkMailItem::get_Failures()
0x335d  ldarg.1
0x335e  callvirt instance var<u1> class [System.Activities]System.Activities.InOutArgument`1<int32>::Get(!!T0)
0x3363  ldc.i4.0
0x3364  ble.s    loc_33C2
0x3366  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x336b  ldc.i4   0x8004502D
0x3370  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0x3375  ldc.i4.1
0x3376  newarr   [mscorlib]System.Object
0x337b  dup
0x337c  ldc.i4.0
0x337d  ldarg.0
0x337e  call     instance class [System.Activities]System.Activities.InOutArgument`1<int32> Microsoft.Crm.Workflow.Activities.BulkMailItem::get_Failures()
0x3383  ldarg.1
0x3384  callvirt instance var<u1> class [System.Activities]System.Activities.InOutArgument`1<int32>::Get(!!T0)
0x3389  box      [mscorlib]System.Int32
0x338e  stelem.ref
0x338f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3394  stloc.s  8
0x3396  ldnull
0x3397  ldloc.0
0x3398  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x339d  ldc.i4.s 0x1E
0x339f  ldstr    a0// "{0}"
0x33a4  ldc.i4.1
0x33a5  newarr   [mscorlib]System.Object
0x33aa  dup
0x33ab  ldc.i4.0
0x33ac  ldloc.s  8
0x33ae  stelem.ref
0x33af  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x33b4  ldc.i4.2
0x33b5  ldc.i4   0x8004502D
0x33ba  ldloc.s  8
0x33bc  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Workflow.Activities.StopWorkflowException::.ctor(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Workflow.Activities.WorkflowCompletionStatus, int32, string)
0x33c1  throw
0x33c2  ret
```
