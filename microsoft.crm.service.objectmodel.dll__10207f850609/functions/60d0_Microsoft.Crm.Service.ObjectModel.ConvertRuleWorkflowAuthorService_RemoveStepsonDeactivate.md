# Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthorService::RemoveStepsonDeactivate

- ea: `0x60d0`
- end: `0x6152`
- name: `Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthorService::RemoveStepsonDeactivate`
- size: `130`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x60d0`
- `0x9300`
- `0x9460`
- `0x17e70`
- `0x18820`

## string_xrefs

- `0x6109`: `RemoveStepsonDeactivate`

## pseudocode

```c

```

## disassembly

```asm
0x60d0  ldarg.0
0x60d1  call     instance bool Microsoft.Crm.Service.ObjectModel.ServiceWorkflowAuthorService::get_UseReflection()
0x60d6  brfalse.s loc_6134
0x60d8  ldarg.0
0x60d9  call     instance class [mscorlib]System.Type Microsoft.Crm.Service.ObjectModel.ServiceWorkflowAuthorService::GetWorkflowAuthorType()
0x60de  stloc.0
0x60df  ldloc.0
0x60e0  ldc.i4.2
0x60e1  newarr   [mscorlib]System.Object
0x60e6  dup
0x60e7  ldc.i4.0
0x60e8  ldarg.0
0x60e9  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowAuthorServiceBase::get_Context()
0x60ee  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x60f3  box      [mscorlib]System.Guid
0x60f8  stelem.ref
0x60f9  dup
0x60fa  ldc.i4.1
0x60fb  ldc.i4.1
0x60fc  box      [mscorlib]System.Boolean
0x6101  stelem.ref
0x6102  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type, object[])
0x6107  stloc.1
0x6108  ldloc.0
0x6109  ldstr    aRemovestepsond// "RemoveStepsonDeactivate"
0x610e  ldc.i4   0x100
0x6113  ldnull
0x6114  ldloc.1
0x6115  ldc.i4.2
0x6116  newarr   [mscorlib]System.Object
0x611b  dup
0x611c  ldc.i4.0
0x611d  ldarg.1
0x611e  stelem.ref
0x611f  dup
0x6120  ldc.i4.1
0x6121  ldarg.0
0x6122  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowAuthorServiceBase::get_Context()
0x6127  stelem.ref
0x6128  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x612d  callvirt instance object [mscorlib]System.Type::InvokeMember(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, object, object[], class [mscorlib]System.Globalization.CultureInfo)
0x6132  pop
0x6133  ret
0x6134  ldarg.0
0x6135  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowAuthorServiceBase::get_Context()
0x613a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x613f  ldc.i4.1
0x6140  newobj   instance void Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::.ctor(valuetype [mscorlib]System.Guid organizationId, bool isSdkContext)
0x6145  ldarg.1
0x6146  ldarg.0
0x6147  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowAuthorServiceBase::get_Context()
0x614c  callvirt instance void Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::RemoveStepsonDeactivate(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection convertRuleItems, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext context)
0x6151  ret
```
