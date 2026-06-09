# Microsoft.Crm.BusinessEntities.DllMethodActionsUtility::CreateExecutionContextForSolutionDelete

- ea: `0x68650`
- end: `0x68746`
- name: `Microsoft.Crm.BusinessEntities.DllMethodActionsUtility::CreateExecutionContextForSolutionDelete`
- size: `246`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x66530`
- `0x66ae0`
- `0x66c20`
- `0x66c30`
- `0x66c40`
- `0x66c50`
- `0x66ff0`
- `0x67610`
- `0x67630`
- `0x68650`

## string_xrefs

- `0x686e6`: `isDeleteAndPromote`
- `0x686f8`: `isDeleteAndPromote`
- `0x68703`: `isDeleteAndPromote`

## pseudocode

```c

```

## disassembly

```asm
0x68650  ldarg.0
0x68651  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x68656  ldc.i4.0
0x68657  ldc.i4.0
0x68658  newobj   instance void Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid organizationId, [opt] bool isReader, [opt] valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority priority)
0x6865d  stloc.0
0x6865e  ldloc.0
0x6865f  ldarg.0
0x68660  callvirt instance bool Microsoft.Crm.BusinessEntities.ExecutionContext::get_IsDependencyCalculationEnabled()
0x68665  callvirt instance void Microsoft.Crm.BusinessEntities.ExecutionContext::set_IsDependencyCalculationEnabled(bool value)
0x6866a  ldloc.0
0x6866b  ldarg.0
0x6866c  callvirt instance bool Microsoft.Crm.BusinessEntities.ExecutionContext::get_IsInDBUpdateOperation()
0x68671  callvirt instance void Microsoft.Crm.BusinessEntities.ExecutionContext::set_IsInDBUpdateOperation(bool value)
0x68676  ldloc.0
0x68677  ldarg.0
0x68678  callvirt instance bool Microsoft.Crm.BusinessEntities.ExecutionContext::get_IsInSandboxSolutionDeleteOperation()
0x6867d  callvirt instance void Microsoft.Crm.BusinessEntities.ExecutionContext::set_IsInSandboxSolutionDeleteOperation(bool value)
0x68682  ldloc.0
0x68683  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x68688  ldarg.0
0x68689  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x6868e  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.AddRootsOption [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_AddRootsOption()
0x68693  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::set_AddRootsOption(valuetype [Microsoft.Crm.Core]Microsoft.Crm.AddRootsOption)
0x68698  ldloc.0
0x68699  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x6869e  ldarg.0
0x6869f  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x686a4  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_IsDeletionValidated()
0x686a9  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::set_IsDeletionValidated(bool)
0x686ae  ldarg.0
0x686af  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x686b4  ldstr    aUpgradeaction// "UpgradeAction"
0x686b9  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x686be  brfalse.s loc_686E0
0x686c0  ldloc.0
0x686c1  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x686c6  ldstr    aUpgradeaction// "UpgradeAction"
0x686cb  ldarg.0
0x686cc  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x686d1  ldstr    aUpgradeaction// "UpgradeAction"
0x686d6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x686db  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x686e0  ldarg.0
0x686e1  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x686e6  ldstr    aIsdeleteandpro// "isDeleteAndPromote"
0x686eb  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x686f0  brfalse.s loc_68712
0x686f2  ldloc.0
0x686f3  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x686f8  ldstr    aIsdeleteandpro// "isDeleteAndPromote"
0x686fd  ldarg.0
0x686fe  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x68703  ldstr    aIsdeleteandpro// "isDeleteAndPromote"
0x68708  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x6870d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x68712  ldarg.0
0x68713  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x68718  ldstr    aHandlertype// "handlerType"
0x6871d  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x68722  brfalse.s loc_68744
0x68724  ldloc.0
0x68725  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x6872a  ldstr    aHandlertype// "handlerType"
0x6872f  ldarg.0
0x68730  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x68735  ldstr    aHandlertype// "handlerType"
0x6873a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x6873f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x68744  ldloc.0
0x68745  ret
```
