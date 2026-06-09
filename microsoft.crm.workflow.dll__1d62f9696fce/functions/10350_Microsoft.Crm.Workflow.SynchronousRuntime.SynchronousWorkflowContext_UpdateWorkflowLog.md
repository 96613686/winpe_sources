# Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowContext::UpdateWorkflowLog

- ea: `0x10350`
- end: `0x10411`
- name: `Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowContext::UpdateWorkflowLog`
- size: `193`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x10350`

## string_xrefs

- `0x103de`: `completedon`

## pseudocode

```c

```

## disassembly

```asm
0x10350  ldarg.1
0x10351  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x10356  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1035b  brfalse  loc_10410
0x10360  ldarg.0
0x10361  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity> Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowContext::workflowLogs
0x10366  ldarg.1
0x10367  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>::get_Item(void)
0x1036c  stloc.0
0x1036d  ldloc.0
0x1036e  ldstr    aStatus// "status"
0x10373  ldarg.s  4
0x10375  box      [mscorlib]System.Int32
0x1037a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1037f  ldarg.0
0x10380  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference Microsoft.Crm.Workflow.WorkflowContextBase::_stepRegardingRecord
0x10385  brfalse.s loc_103A4
0x10387  ldloc.0
0x10388  ldstr    aRegardingobjec_0// "regardingobjectid"
0x1038d  ldarg.0
0x1038e  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference Microsoft.Crm.Workflow.WorkflowContextBase::_stepRegardingRecord
0x10393  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x10398  box      [mscorlib]System.Guid
0x1039d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x103a2  br.s     loc_103B0
0x103a4  ldloc.0
0x103a5  ldstr    aRegardingobjec_0// "regardingobjectid"
0x103aa  ldnull
0x103ab  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x103b0  ldarg.0
0x103b1  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.WorkflowContextBase::_childWorkflowInstanceId
0x103b6  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x103bb  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x103c0  brfalse.s loc_103D8
0x103c2  ldloc.0
0x103c3  ldstr    aChildworkflowi// "childworkflowinstanceid"
0x103c8  ldarg.0
0x103c9  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.WorkflowContextBase::_childWorkflowInstanceId
0x103ce  box      [mscorlib]System.Guid
0x103d3  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x103d8  ldarg.s  4
0x103da  ldc.i4.2
0x103db  bne.un.s loc_103ED
0x103dd  ldloc.0
0x103de  ldstr    aCompletedon// "completedon"
0x103e3  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_UniversalNow()
0x103e8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x103ed  ldarg.3
0x103ee  brfalse.s loc_103FC
0x103f0  ldloc.0
0x103f1  ldstr    aMessage// "message"
0x103f6  ldarg.3
0x103f7  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x103fc  ldarg.2
0x103fd  brfalse.s loc_10410
0x103ff  ldloc.0
0x10400  ldstr    aErrorcode// "errorcode"
0x10405  ldarg.2
0x10406  box      [mscorlib]System.Int32
0x1040b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x10410  ret
```
