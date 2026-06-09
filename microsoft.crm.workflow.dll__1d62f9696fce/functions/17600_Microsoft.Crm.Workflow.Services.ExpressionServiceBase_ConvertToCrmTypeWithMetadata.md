# Microsoft.Crm.Workflow.Services.ExpressionServiceBase::ConvertToCrmTypeWithMetadata

- ea: `0x17600`
- end: `0x17690`
- name: `Microsoft.Crm.Workflow.Services.ExpressionServiceBase::ConvertToCrmTypeWithMetadata`
- size: `144`
- prototype: ``
- caller_count: `6`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x16cd0`
- `0x16ee0`
- `0x17340`
- `0x17690`
- `0x17f60`
- `0x18090`

## callees

- `0x8e70`
- `0x12770`
- `0x13ad0`
- `0x14770`
- `0x17600`
- `0x186d0`

## pseudocode

```c

```

## disassembly

```asm
0x17600  ldarg.1
0x17601  ldtoken  [mscorlib]System.String
0x17606  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1760b  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x17610  brfalse.s loc_1762B
0x17612  ldarg.s  6
0x17614  brfalse.s loc_1762B
0x17616  ldarg.s  6
0x17618  ldarg.s  4
0x1761a  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, string>::Contains(var<u1>)
0x1761f  brfalse.s loc_1762B
0x17621  ldarg.s  6
0x17623  ldarg.s  4
0x17625  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, string>::get_Item(void)
0x1762a  ret
0x1762b  ldarg.2
0x1762c  brfalse.s loc_17672
0x1762e  ldarg.2
0x1762f  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x17634  ldarg.0
0x17635  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x1763a  newobj   instance void Microsoft.Crm.Workflow.WorkflowUserContext::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext workflowContext)
0x1763f  call     class Microsoft.Crm.Workflow.ValueConverters.ValueConverterBase Microsoft.Crm.Workflow.ValueConverters.ValueConverterFactory::CreateConverter(class [mscorlib]System.Type type, class Microsoft.Crm.Workflow.WorkflowUserContext userContext)
0x17644  stloc.0
0x17645  ldloc.0
0x17646  brfalse.s loc_17672
0x17648  ldarg.s  5
0x1764a  brfalse.s loc_17666
0x1764c  call     class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Type> Microsoft.Crm.Workflow.Services.ExpressionServiceBase::get_CrmToXrmWorkflowTypes()
0x17651  ldarg.1
0x17652  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Type>::ContainsKey(var<u1>)
0x17657  brfalse.s loc_17666
0x17659  call     class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Type> Microsoft.Crm.Workflow.Services.ExpressionServiceBase::get_CrmToXrmWorkflowTypes()
0x1765e  ldarg.1
0x1765f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Type>::get_Item(void)
0x17664  starg.s  1
0x17666  ldloc.0
0x17667  ldarg.1
0x17668  ldarg.2
0x17669  ldarg.3
0x1766a  ldarg.s  4
0x1766c  callvirt instance object Microsoft.Crm.Workflow.ValueConverters.ValueConverterBase::ConvertTo(class [mscorlib]System.Type targetType, object sourceValue, string entityName, string attributeName)
0x17671  ret
0x17672  ldarg.2
0x17673  brfalse.s loc_1768E
0x17675  ldarg.1
0x17676  ldtoken  [mscorlib]System.String
0x1767b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17680  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x17685  brfalse.s loc_1768E
0x17687  ldarg.2
0x17688  callvirt instance string [mscorlib]System.Object::ToString()
0x1768d  ret
0x1768e  ldarg.2
0x1768f  ret
```
