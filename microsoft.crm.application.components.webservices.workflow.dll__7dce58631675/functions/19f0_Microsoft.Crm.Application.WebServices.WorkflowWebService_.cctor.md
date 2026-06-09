# Microsoft.Crm.Application.WebServices.WorkflowWebService::.cctor

- ea: `0x19f0`
- end: `0x1a7a`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::.cctor`
- size: `138`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x19f0  ldc.i4.6
0x19f1  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Type>::.ctor(int32)
0x19f6  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Type> Microsoft.Crm.Application.WebServices.WorkflowWebService::SupportedVariableTypes
0x19fb  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Type> Microsoft.Crm.Application.WebServices.WorkflowWebService::SupportedVariableTypes
0x1a00  ldc.i4.0
0x1a01  ldtoken  [mscorlib]System.String
0x1a06  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a0b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Type>::Add(var<u1>, !!T0)
0x1a10  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Type> Microsoft.Crm.Application.WebServices.WorkflowWebService::SupportedVariableTypes
0x1a15  ldc.i4.1
0x1a16  ldtoken  [mscorlib]System.Int32
0x1a1b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a20  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Type>::Add(var<u1>, !!T0)
0x1a25  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Type> Microsoft.Crm.Application.WebServices.WorkflowWebService::SupportedVariableTypes
0x1a2a  ldc.i4.2
0x1a2b  ldtoken  [mscorlib]System.Double
0x1a30  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a35  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Type>::Add(var<u1>, !!T0)
0x1a3a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Type> Microsoft.Crm.Application.WebServices.WorkflowWebService::SupportedVariableTypes
0x1a3f  ldc.i4.5
0x1a40  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x1a45  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a4a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Type>::Add(var<u1>, !!T0)
0x1a4f  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Type> Microsoft.Crm.Application.WebServices.WorkflowWebService::SupportedVariableTypes
0x1a54  ldc.i4.3
0x1a55  ldtoken  [mscorlib]System.DateTime
0x1a5a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a5f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Type>::Add(var<u1>, !!T0)
0x1a64  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Type> Microsoft.Crm.Application.WebServices.WorkflowWebService::SupportedVariableTypes
0x1a69  ldc.i4.4
0x1a6a  ldtoken  [mscorlib]System.DateTime
0x1a6f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a74  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Type>::Add(var<u1>, !!T0)
0x1a79  ret
```
