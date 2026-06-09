# Microsoft.Crm.Workflow.Services.SetAttributeValueService::UpdateInternal

- ea: `0x19930`
- end: `0x19a0a`
- name: `Microsoft.Crm.Workflow.Services.SetAttributeValueService::UpdateInternal`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x19900`

## callees

- `0x109a0`
- `0x14770`
- `0x14ee0`
- `0x19930`
- `0x19a10`
- `0x19a70`

## string_xrefs

- `0x19947`: `Cannot find record to be updated`

## pseudocode

```c

```

## disassembly

```asm
0x19930  ldarg.1
0x19931  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x19936  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1993b  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x19940  brfalse.s loc_19962
0x19942  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x19947  ldstr    aCannotFindReco_2// "Cannot find record to be updated"
0x1994c  ldc.i4.0
0x1994d  newarr   [mscorlib]System.Object
0x19952  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x19957  ldc.i4   0x80045031
0x1995c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x19961  throw
0x19962  ldarg.0
0x19963  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x19968  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InputParameters()
0x1996d  ldstr    aTarget// "Target"
0x19972  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x19977  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity
0x1997c  stloc.0
0x1997d  ldarg.1
0x1997e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x19983  stloc.1
0x19984  ldloca.s 1
0x19986  ldloc.0
0x19987  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x1998c  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0x19991  brfalse.s loc_199FF
0x19993  ldnull
0x19994  stloc.2
0x19995  ldarg.0
0x19996  call     instance bool Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_IsSynchronousWorkflowRuntime()
0x1999b  brfalse.s loc_199AE
0x1999d  ldarg.0
0x1999e  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x199a3  castclass Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowContext
0x199a8  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowContext::get_ExecutionContext()
0x199ad  stloc.2
0x199ae  ldarg.1
0x199af  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x199b4  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0>> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::GetEnumerator()
0x199b9  stloc.3
0x199ba  br.s     loc_199DA
0x199bc  ldloc.3
0x199bd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>>::get_Current()
0x199c2  stloc.s  4
0x199c4  ldarg.0
0x199c5  ldloc.0
0x199c6  ldloca.s 4
0x199c8  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Key()
0x199cd  ldloca.s 4
0x199cf  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Value()
0x199d4  ldloc.2
0x199d5  call     instance void Microsoft.Crm.Workflow.Services.SetAttributeValueService::TrySetInputEntityPropertyValue(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity TargetEntity, string propertyName, object value, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x199da  ldloc.3
0x199db  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x199e0  brtrue.s loc_199BC
0x199e2  leave.s  loc_199EE
0x199e4  ldloc.3
0x199e5  brfalse.s loc_199ED
0x199e7  ldloc.3
0x199e8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x199ed  endfinally
0x199ee  ldarg.0
0x199ef  call     instance bool Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_IsSynchronousWorkflowRuntime()
0x199f4  brtrue.s loc_19A08
0x199f6  ldarg.0
0x199f7  ldloc.0
0x199f8  call     instance void Microsoft.Crm.Workflow.Services.SetAttributeValueService::UpdateRelatedEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity)
0x199fd  br.s     loc_19A08
0x199ff  ldarg.0
0x19a00  ldarg.1
0x19a01  call     instance void Microsoft.Crm.Workflow.Services.SetAttributeValueService::UpdateRelatedEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity)
0x19a06  ldarg.1
0x19a07  stloc.0
0x19a08  ldloc.0
0x19a09  ret
```
