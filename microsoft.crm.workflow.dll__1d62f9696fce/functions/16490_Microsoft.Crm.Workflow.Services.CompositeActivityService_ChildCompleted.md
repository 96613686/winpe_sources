# Microsoft.Crm.Workflow.Services.CompositeActivityService::ChildCompleted

- ea: `0x16490`
- end: `0x16509`
- name: `Microsoft.Crm.Workflow.Services.CompositeActivityService::ChildCompleted`
- size: `121`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x14860`
- `0x14930`
- `0x149c0`
- `0x16490`
- `0x2d170`
- `0x2d1d0`

## pseudocode

```c

```

## disassembly

```asm
0x16490  ldarg.s  4
0x16492  ldarg.1
0x16493  callvirt instance var<u1> class [System.Activities]System.Activities.Variable`1<int32>::Get(!!T0)
0x16498  stloc.0
0x16499  ldloc.0
0x1649a  ldc.i4.1
0x1649b  add
0x1649c  stloc.0
0x1649d  ldloc.0
0x1649e  ldarg.2
0x1649f  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.Activities.Composite::get_Activities()
0x164a4  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::get_Count()
0x164a9  bge.s    loc_164D8
0x164ab  ldarg.2
0x164ac  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.Activities.Composite::get_Activities()
0x164b1  ldloc.0
0x164b2  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::get_Item(!!T0)
0x164b7  stloc.1
0x164b8  ldarg.0
0x164b9  ldloc.1
0x164ba  call     instance void Microsoft.Crm.Workflow.Services.ActivityServiceBase::CreateLogForStopWorkflowStep(class [System.Activities]System.Activities.Activity activity)
0x164bf  ldarg.1
0x164c0  ldloc.1
0x164c1  ldarg.2
0x164c2  callvirt instance class [System.Activities]System.Activities.CompletionCallback Microsoft.Crm.Workflow.Activities.Composite::get_OnChildComplete()
0x164c7  ldnull
0x164c8  callvirt instance class [System.Activities]System.Activities.ActivityInstance [System.Activities]System.Activities.NativeActivityContext::ScheduleActivity(class [System.Activities]System.Activities.Activity, class [System.Activities]System.Activities.CompletionCallback, class [System.Activities]System.Activities.FaultCallback)
0x164cd  pop
0x164ce  ldarg.s  4
0x164d0  ldarg.1
0x164d1  ldloc.0
0x164d2  callvirt instance void class [System.Activities]System.Activities.Variable`1<int32>::Set(class [System.Activities]System.Activities.ActivityContext, var<u1>)
0x164d7  ret
0x164d8  ldarg.0
0x164d9  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.Services.CompositeActivityService::_logId
0x164de  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x164e3  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x164e8  brtrue.s loc_164F2
0x164ea  ldarg.0
0x164eb  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.Services.CompositeActivityService::_logId
0x164f0  br.s     loc_164F9
0x164f2  ldarg.0
0x164f3  ldarg.2
0x164f4  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.Services.ActivityServiceBase::CreateLog(class [System.Activities]System.Activities.Activity activity)
0x164f9  stloc.2
0x164fa  ldarg.0
0x164fb  ldloc.2
0x164fc  ldc.i4.0
0x164fd  ldsfld   string [mscorlib]System.String::Empty
0x16502  ldc.i4.2
0x16503  call     instance void Microsoft.Crm.Workflow.Services.ActivityServiceBase::UpdateLog(valuetype [mscorlib]System.Guid logId, int32 errorCode, string errorMessage, int32 status)
0x16508  ret
```
