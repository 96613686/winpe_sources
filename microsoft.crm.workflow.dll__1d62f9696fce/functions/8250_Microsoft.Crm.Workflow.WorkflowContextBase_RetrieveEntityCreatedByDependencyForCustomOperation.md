# Microsoft.Crm.Workflow.WorkflowContextBase::RetrieveEntityCreatedByDependencyForCustomOperation

- ea: `0x8250`
- end: `0x833d`
- name: `Microsoft.Crm.Workflow.WorkflowContextBase::RetrieveEntityCreatedByDependencyForCustomOperation`
- size: `237`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x8090`

## callees

- `0x73f0`
- `0x7610`
- `0x77b0`
- `0x8250`
- `0x8840`

## pseudocode

```c

```

## disassembly

```asm
0x8250  ldarg.0
0x8251  callvirt instance int32 Microsoft.Crm.Workflow.WorkflowContextBase::get_WorkflowCategory()
0x8256  ldc.i4.3
0x8257  bne.un   loc_833C
0x825c  ldarg.0
0x825d  call     instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Sdk]Microsoft.Crm.Workflow.EntityDependencyBase> Microsoft.Crm.Workflow.WorkflowContextBase::get_EntityDependencies()
0x8262  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Sdk]Microsoft.Crm.Workflow.EntityDependencyBase>::GetEnumerator()
0x8267  stloc.0
0x8268  br       loc_8325
0x826d  ldloc.0
0x826e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Sdk]Microsoft.Crm.Workflow.EntityDependencyBase>::get_Current()
0x8273  stloc.1
0x8274  ldloc.1
0x8275  isinst   [Microsoft.Crm.Sdk]Microsoft.Crm.Workflow.EntityCreatedByDependency
0x827a  brfalse  loc_8325
0x827f  ldnull
0x8280  stloc.2
0x8281  ldloc.1
0x8282  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Workflow.ParameterDependencyBase::get_ParameterName()
0x8287  stloc.3
0x8288  ldsfld   string [mscorlib]System.String::Empty
0x828d  stloc.s  4
0x828f  ldsfld   string [mscorlib]System.String::Empty
0x8294  stloc.s  5
0x8296  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x829b  stloc.s  6
0x829d  ldloc.3
0x829e  ldc.i4.s 0x23
0x82a0  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x82a5  stloc.s  7
0x82a7  ldloc.s  7
0x82a9  ldc.i4.0
0x82aa  ble.s    loc_82B7
0x82ac  ldloc.3
0x82ad  ldc.i4.0
0x82ae  ldloc.s  7
0x82b0  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x82b5  stloc.s  4
0x82b7  ldarg.0
0x82b8  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection Microsoft.Crm.Workflow.WorkflowContextBase::get_InputParameters()
0x82bd  ldloc.s  4
0x82bf  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::ContainsKey(var<u1>)
0x82c4  brtrue.s loc_82C9
0x82c6  ldnull
0x82c7  br.s     loc_82DB
0x82c9  ldarg.0
0x82ca  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection Microsoft.Crm.Workflow.WorkflowContextBase::get_InputParameters()
0x82cf  ldloc.s  4
0x82d1  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x82d6  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x82db  stloc.s  8
0x82dd  ldloc.s  8
0x82df  brfalse.s loc_82F3
0x82e1  ldloc.s  8
0x82e3  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_LogicalName()
0x82e8  stloc.s  5
0x82ea  ldloc.s  8
0x82ec  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x82f1  stloc.s  6
0x82f3  ldarg.0
0x82f4  ldloc.s  5
0x82f6  ldloc.s  6
0x82f8  ldloc.1
0x82f9  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Workflow.EntityDependencyBase::get_EntityAttributes()
0x82fe  ldloc.1
0x82ff  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Workflow.ParameterDependencyBase::get_ParameterName()
0x8304  ldloca.s 2
0x8306  ldnull
0x8307  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Workflow.WorkflowContextHelper::TryRetrieveEntity(class Microsoft.Crm.Workflow.ICommonWorkflowContext context, string entityName, valuetype [mscorlib]System.Guid entityId, string entityAttributes, string dependencyParameterName, [out] class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>& faultException, [opt] class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet columnSet)
0x830c  stloc.s  9
0x830e  ldloc.s  9
0x8310  brfalse.s loc_831B
0x8312  ldarg.1
0x8313  ldloc.3
0x8314  ldloc.s  9
0x8316  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::set_Item(var<u1>, !!T0)
0x831b  leave.s  loc_8320
0x831d  pop
0x831e  leave.s  loc_8320
0x8320  ldloc.2
0x8321  brfalse.s loc_8325
0x8323  ldloc.2
0x8324  throw
0x8325  ldloc.0
0x8326  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x832b  brtrue   loc_826D
0x8330  leave.s  loc_833C
0x8332  ldloc.0
0x8333  brfalse.s loc_833B
0x8335  ldloc.0
0x8336  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x833b  endfinally
0x833c  ret
```
