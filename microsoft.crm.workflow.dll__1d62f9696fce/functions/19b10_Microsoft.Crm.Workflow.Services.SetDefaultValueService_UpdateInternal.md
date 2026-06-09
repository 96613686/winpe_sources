# Microsoft.Crm.Workflow.Services.SetDefaultValueService::UpdateInternal

- ea: `0x19b10`
- end: `0x19c34`
- name: `Microsoft.Crm.Workflow.Services.SetDefaultValueService::UpdateInternal`
- size: `292`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x19ae0`

## callees

- `0x109a0`
- `0x14770`
- `0x14ea0`
- `0x14ee0`
- `0x19b10`
- `0x19c40`
- `0x19cd0`

## string_xrefs

- `0x19b27`: `Cannot find record to be updated`

## pseudocode

```c

```

## disassembly

```asm
0x19b10  ldarg.1
0x19b11  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x19b16  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x19b1b  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x19b20  brfalse.s loc_19B42
0x19b22  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x19b27  ldstr    aCannotFindReco_2// "Cannot find record to be updated"
0x19b2c  ldc.i4.0
0x19b2d  newarr   [mscorlib]System.Object
0x19b32  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x19b37  ldc.i4   0x80045031
0x19b3c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x19b41  throw
0x19b42  ldarg.0
0x19b43  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x19b48  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InputParameters()
0x19b4d  ldstr    aTarget// "Target"
0x19b52  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x19b57  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity
0x19b5c  stloc.0
0x19b5d  ldarg.1
0x19b5e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x19b63  stloc.1
0x19b64  ldloca.s 1
0x19b66  ldloc.0
0x19b67  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x19b6c  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0x19b71  brfalse  loc_19C29
0x19b76  ldnull
0x19b77  stloc.2
0x19b78  ldarg.0
0x19b79  call     instance bool Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_IsSynchronousWorkflowRuntime()
0x19b7e  brfalse.s loc_19B93
0x19b80  ldarg.0
0x19b81  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x19b86  castclass Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowContext
0x19b8b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowContext::get_ExecutionContext()
0x19b90  stloc.2
0x19b91  br.s     loc_19BA6
0x19b93  ldarg.0
0x19b94  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x19b99  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x19b9e  ldc.i4.0
0x19b9f  ldc.i4.0
0x19ba0  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x19ba5  stloc.2
0x19ba6  ldc.i4.0
0x19ba7  stloc.3
0x19ba8  ldarg.0
0x19ba9  call     instance bool Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_IsSynchronousWorkflowRuntime()
0x19bae  brfalse.s loc_19BB9
0x19bb0  ldarg.0
0x19bb1  call     instance bool Microsoft.Crm.Workflow.Services.ActivityServiceBase::PreImageExists()
0x19bb6  stloc.3
0x19bb7  br.s     loc_19BD0
0x19bb9  ldarg.0
0x19bba  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x19bbf  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityImageCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_PreEntityImages()
0x19bc4  callvirt instance int32 class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x19bc9  brtrue.s loc_19BCE
0x19bcb  ldc.i4.0
0x19bcc  br.s     loc_19BCF
0x19bce  ldc.i4.1
0x19bcf  stloc.3
0x19bd0  ldloc.3
0x19bd1  brtrue.s loc_19C18
0x19bd3  ldarg.1
0x19bd4  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x19bd9  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0>> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::GetEnumerator()
0x19bde  stloc.s  4
0x19be0  br.s     loc_19C01
0x19be2  ldloc.s  4
0x19be4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>>::get_Current()
0x19be9  stloc.s  5
0x19beb  ldarg.0
0x19bec  ldloc.0
0x19bed  ldloca.s 5
0x19bef  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Key()
0x19bf4  ldloca.s 5
0x19bf6  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Value()
0x19bfb  ldloc.2
0x19bfc  call     instance void Microsoft.Crm.Workflow.Services.SetDefaultValueService::TrySetInputEntityPropertyValue(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity TargetEntity, string propertyName, object value, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x19c01  ldloc.s  4
0x19c03  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x19c08  brtrue.s loc_19BE2
0x19c0a  leave.s  loc_19C18
0x19c0c  ldloc.s  4
0x19c0e  brfalse.s loc_19C17
0x19c10  ldloc.s  4
0x19c12  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x19c17  endfinally
0x19c18  ldarg.0
0x19c19  call     instance bool Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_IsSynchronousWorkflowRuntime()
0x19c1e  brtrue.s loc_19C32
0x19c20  ldarg.0
0x19c21  ldloc.0
0x19c22  call     instance void Microsoft.Crm.Workflow.Services.SetDefaultValueService::UpdateRelatedEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity)
0x19c27  br.s     loc_19C32
0x19c29  ldarg.0
0x19c2a  ldarg.1
0x19c2b  call     instance void Microsoft.Crm.Workflow.Services.SetDefaultValueService::UpdateRelatedEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity)
0x19c30  ldarg.1
0x19c31  stloc.0
0x19c32  ldloc.0
0x19c33  ret
```
