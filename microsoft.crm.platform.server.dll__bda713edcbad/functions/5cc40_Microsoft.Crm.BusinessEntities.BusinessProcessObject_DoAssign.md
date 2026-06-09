# Microsoft.Crm.BusinessEntities.BusinessProcessObject::DoAssign

- ea: `0x5cc40`
- end: `0x5ccf3`
- name: `Microsoft.Crm.BusinessEntities.BusinessProcessObject::DoAssign`
- size: `179`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x8c550`

## callees

- `0x1ab10`
- `0x5c430`
- `0x5c450`
- `0x5cc40`
- `0x5cd00`
- `0x66f10`
- `0x66ff0`
- `0x68390`

## string_xrefs

- `0x5cc9e`: `HasAssignUpdatedWithPipeline`
- `0x5ccb0`: `HasAssignUpdatedWithPipeline`
- `0x5cccc`: `HasAssignUpdatedWithPipeline`

## pseudocode

```c

```

## disassembly

```asm
0x5cc40  ldarg.1
0x5cc41  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PlatformName()
0x5cc46  ldarg.2
0x5cc47  newobj   instance void Microsoft.Crm.Query.FilterExpression::.ctor(string entityPlatformName, class Microsoft.Crm.BusinessEntities.ExecutionContext orgContext)
0x5cc4c  stloc.0
0x5cc4d  ldarg.2
0x5cc4e  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x5cc53  ldstr    aIscascadingass// "IsCascadingAssign"
0x5cc58  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x5cc5d  brfalse.s loc_5CCCB
0x5cc5f  ldarg.2
0x5cc60  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x5cc65  ldstr    aIscascadingass// "IsCascadingAssign"
0x5cc6a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x5cc6f  unbox.any [mscorlib]System.Boolean
0x5cc74  brtrue.s loc_5CCCB
0x5cc76  ldarg.0
0x5cc77  ldarg.2
0x5cc78  ldc.i4.1
0x5cc79  ldarg.1
0x5cc7a  call     instance bool Microsoft.Crm.BusinessEntities.BusinessProcessObject::IsOperationExecutedViaUpdatePipeline(class Microsoft.Crm.BusinessEntities.ExecutionContext context, valuetype Microsoft.Crm.Platform.Server.InternalOperationType operationType, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity)
0x5cc7f  brfalse.s loc_5CCCB
0x5cc81  ldarg.2
0x5cc82  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_PluginContext()
0x5cc87  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_MessageName()
0x5cc8c  ldstr    aAssign// "Assign"
0x5cc91  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x5cc96  brtrue.s loc_5CCC1
0x5cc98  ldarg.2
0x5cc99  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x5cc9e  ldstr    aHasassignupdat// "HasAssignUpdatedWithPipeline"
0x5cca3  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x5cca8  brfalse.s loc_5CCCB
0x5ccaa  ldarg.2
0x5ccab  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x5ccb0  ldstr    aHasassignupdat// "HasAssignUpdatedWithPipeline"
0x5ccb5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x5ccba  unbox.any [mscorlib]System.Boolean
0x5ccbf  brfalse.s loc_5CCCB
0x5ccc1  ldarg.0
0x5ccc2  ldarg.1
0x5ccc3  ldloc.0
0x5ccc4  ldarg.2
0x5ccc5  call     instance void Microsoft.Crm.BusinessEntities.BusinessProcessObject::DoUpdate(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class Microsoft.Crm.Query.FilterExpression filter, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5ccca  ret
0x5cccb  ldarg.2
0x5cccc  ldstr    aHasassignupdat// "HasAssignUpdatedWithPipeline"
0x5ccd1  ldc.i4.1
0x5ccd2  box      [mscorlib]System.Boolean
0x5ccd7  newobj   instance void Microsoft.Crm.BusinessEntities.SetVariableInContextModifier::.ctor(class Microsoft.Crm.BusinessEntities.ExecutionContext context, string key, object value)
0x5ccdc  stloc.1
0x5ccdd  ldarg.0
0x5ccde  ldarg.1
0x5ccdf  ldloc.0
0x5cce0  ldarg.2
0x5cce1  call     instance void Microsoft.Crm.BusinessEntities.BusinessProcessObject::UpdateWithPipeline(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class Microsoft.Crm.Query.FilterExpression filter, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5cce6  leave.s  loc_5CCF2
0x5cce8  ldloc.1
0x5cce9  brfalse.s loc_5CCF1
0x5cceb  ldloc.1
0x5ccec  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5ccf1  endfinally
0x5ccf2  ret
```
