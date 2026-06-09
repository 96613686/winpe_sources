# Microsoft.Crm.Workflow.ValueConverters.ValueConverterFactory::CreateConverter

- ea: `0x13ad0`
- end: `0x13cad`
- name: `Microsoft.Crm.Workflow.ValueConverters.ValueConverterFactory::CreateConverter`
- size: `477`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0xa490`
- `0x17600`

## callees

- `0x12df0`
- `0x12ea0`
- `0x12f20`
- `0x12fd0`
- `0x13050`
- `0x13160`
- `0x13250`
- `0x132f0`
- `0x13360`
- `0x133c0`
- `0x13470`
- `0x134f0`
- `0x13570`
- `0x13630`
- `0x136e0`
- `0x13770`
- `0x13810`
- `0x138b0`
- `0x13950`
- `0x13ad0`

## pseudocode

```c

```

## disassembly

```asm
0x13ad0  ldarg.0
0x13ad1  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber
0x13ad6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13adb  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x13ae0  brfalse.s loc_13AE9
0x13ae2  ldarg.1
0x13ae3  newobj   instance void Microsoft.Crm.Workflow.ValueConverters.CrmNumberConverter::.ctor(class Microsoft.Crm.Workflow.WorkflowUserContext userContext)
0x13ae8  ret
0x13ae9  ldarg.0
0x13aea  ldtoken  [mscorlib]System.Int32
0x13aef  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13af4  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x13af9  brfalse.s loc_13B02
0x13afb  ldarg.1
0x13afc  newobj   instance void Microsoft.Crm.Workflow.ValueConverters.IntConverter::.ctor(class Microsoft.Crm.Workflow.WorkflowUserContext userContext)
0x13b01  ret
0x13b02  ldarg.0
0x13b03  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmFloat
0x13b08  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13b0d  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x13b12  brfalse.s loc_13B1B
0x13b14  ldarg.1
0x13b15  newobj   instance void Microsoft.Crm.Workflow.ValueConverters.CrmFloatConverter::.ctor(class Microsoft.Crm.Workflow.WorkflowUserContext userContext)
0x13b1a  ret
0x13b1b  ldarg.0
0x13b1c  ldtoken  [mscorlib]System.Double
0x13b21  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13b26  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x13b2b  brfalse.s loc_13B34
0x13b2d  ldarg.1
0x13b2e  newobj   instance void Microsoft.Crm.Workflow.ValueConverters.DoubleConverter::.ctor(class Microsoft.Crm.Workflow.WorkflowUserContext userContext)
0x13b33  ret
0x13b34  ldarg.0
0x13b35  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup
0x13b3a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13b3f  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x13b44  brfalse.s loc_13B4D
0x13b46  ldarg.1
0x13b47  newobj   instance void Microsoft.Crm.Workflow.ValueConverters.CrmLookupConverter::.ctor(class Microsoft.Crm.Workflow.WorkflowUserContext userContext)
0x13b4c  ret
0x13b4d  ldarg.0
0x13b4e  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x13b53  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13b58  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x13b5d  brfalse.s loc_13B66
0x13b5f  ldarg.1
0x13b60  newobj   instance void Microsoft.Crm.Workflow.ValueConverters.EntityReferenceConverter::.ctor(class Microsoft.Crm.Workflow.WorkflowUserContext userContext)
0x13b65  ret
0x13b66  ldarg.0
0x13b67  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney
0x13b6c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13b71  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x13b76  brfalse.s loc_13B7F
0x13b78  ldarg.1
0x13b79  newobj   instance void Microsoft.Crm.Workflow.ValueConverters.CrmMoneyConverter::.ctor(class Microsoft.Crm.Workflow.WorkflowUserContext userContext)
0x13b7e  ret
0x13b7f  ldarg.0
0x13b80  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Money
0x13b85  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13b8a  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x13b8f  brfalse.s loc_13B98
0x13b91  ldarg.1
0x13b92  newobj   instance void Microsoft.Crm.Workflow.ValueConverters.MoneyConverter::.ctor(class Microsoft.Crm.Workflow.WorkflowUserContext userContext)
0x13b97  ret
0x13b98  ldarg.0
0x13b99  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean
0x13b9e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13ba3  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x13ba8  brfalse.s loc_13BB1
0x13baa  ldarg.1
0x13bab  newobj   instance void Microsoft.Crm.Workflow.ValueConverters.CrmBooleanConverter::.ctor(class Microsoft.Crm.Workflow.WorkflowUserContext userContext)
0x13bb0  ret
0x13bb1  ldarg.0
0x13bb2  ldtoken  [mscorlib]System.Boolean
0x13bb7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13bbc  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x13bc1  brfalse.s loc_13BCA
0x13bc3  ldarg.1
0x13bc4  newobj   instance void Microsoft.Crm.Workflow.ValueConverters.BooleanConverter::.ctor(class Microsoft.Crm.Workflow.WorkflowUserContext userContext)
0x13bc9  ret
0x13bca  ldarg.0
0x13bcb  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal
0x13bd0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13bd5  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x13bda  brfalse.s loc_13BE3
0x13bdc  ldarg.1
0x13bdd  newobj   instance void Microsoft.Crm.Workflow.ValueConverters.CrmDecimalConverter::.ctor(class Microsoft.Crm.Workflow.WorkflowUserContext userContext)
0x13be2  ret
0x13be3  ldarg.0
0x13be4  ldtoken  [mscorlib]System.Decimal
0x13be9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13bee  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x13bf3  brfalse.s loc_13BFC
0x13bf5  ldarg.1
0x13bf6  newobj   instance void Microsoft.Crm.Workflow.ValueConverters.DecimalConverter::.ctor(class Microsoft.Crm.Workflow.WorkflowUserContext userContext)
0x13bfb  ret
0x13bfc  ldarg.0
0x13bfd  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime
0x13c02  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13c07  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x13c0c  brfalse.s loc_13C15
0x13c0e  ldarg.1
0x13c0f  newobj   instance void Microsoft.Crm.Workflow.ValueConverters.CrmDateTimeConverter::.ctor(class Microsoft.Crm.Workflow.WorkflowUserContext userContext)
0x13c14  ret
0x13c15  ldarg.0
0x13c16  ldtoken  [mscorlib]System.DateTime
0x13c1b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13c20  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x13c25  brfalse.s loc_13C2E
0x13c27  ldarg.1
0x13c28  newobj   instance void Microsoft.Crm.Workflow.ValueConverters.DateTimeConverter::.ctor(class Microsoft.Crm.Workflow.WorkflowUserContext userContext)
0x13c2d  ret
0x13c2e  ldarg.0
0x13c2f  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist
0x13c34  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13c39  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x13c3e  brfalse.s loc_13C47
0x13c40  ldarg.1
0x13c41  newobj   instance void Microsoft.Crm.Workflow.ValueConverters.PicklistConverter::.ctor(class Microsoft.Crm.Workflow.WorkflowUserContext userContext)
0x13c46  ret
0x13c47  ldarg.0
0x13c48  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status
0x13c4d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13c52  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x13c57  brfalse.s loc_13C60
0x13c59  ldarg.1
0x13c5a  newobj   instance void Microsoft.Crm.Workflow.ValueConverters.StatusConverter::.ctor(class Microsoft.Crm.Workflow.WorkflowUserContext userContext)
0x13c5f  ret
0x13c60  ldarg.0
0x13c61  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0x13c66  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13c6b  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x13c70  brfalse.s loc_13C79
0x13c72  ldarg.1
0x13c73  newobj   instance void Microsoft.Crm.Workflow.ValueConverters.OptionSetConverter::.ctor(class Microsoft.Crm.Workflow.WorkflowUserContext userContext)
0x13c78  ret
0x13c79  ldarg.0
0x13c7a  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection
0x13c7f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13c84  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x13c89  brfalse.s loc_13C92
0x13c8b  ldarg.1
0x13c8c  newobj   instance void Microsoft.Crm.Workflow.ValueConverters.PartyListConverter::.ctor(class Microsoft.Crm.Workflow.WorkflowUserContext userContext)
0x13c91  ret
0x13c92  ldarg.0
0x13c93  ldtoken  [mscorlib]System.Guid
0x13c98  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13c9d  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x13ca2  brfalse.s loc_13CAB
0x13ca4  ldarg.1
0x13ca5  newobj   instance void Microsoft.Crm.Workflow.ValueConverters.GuidConverter::.ctor(class Microsoft.Crm.Workflow.WorkflowUserContext userContext)
0x13caa  ret
0x13cab  ldnull
0x13cac  ret
```
