# Microsoft.Crm.Extensibility.OData.CrmODataOptimisticConcurrencyHelper::HandleDeleteMatchETags

- ea: `0x1d320`
- end: `0x1d3a9`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataOptimisticConcurrencyHelper::HandleDeleteMatchETags`
- size: `137`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1e930`

## callees

- `0x19a60`
- `0x19a80`
- `0x1d320`
- `0x1d3b0`
- `0x24e60`

## string_xrefs

- `0x1d380`: `The specified If-None-Match condition isn't valid for a DELETE request.`
- `0x1d396`: `The specified If-None-Match condition isn't supported for a DELETE request.`

## pseudocode

```c

```

## disassembly

```asm
0x1d320  ldarg.0
0x1d321  ldarg.1
0x1d322  call     void Microsoft.Crm.Extensibility.OData.CrmODataOptimisticConcurrencyHelper::ThrowIfIfMatchAndIfNoneMatchAreIncompatible(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, string entityLogicalName)
0x1d327  ldarg.0
0x1d328  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x1d32d  callvirt instance class [System.Net.Http]System.Net.Http.Headers.EntityTagHeaderValue Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_IfMatch()
0x1d332  brfalse.s loc_1D352
0x1d334  ldarg.0
0x1d335  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x1d33a  callvirt instance class [System.Net.Http]System.Net.Http.Headers.EntityTagHeaderValue Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_IfMatch()
0x1d33f  callvirt instance string [System.Net.Http]System.Net.Http.Headers.EntityTagHeaderValue::get_Tag()
0x1d344  ldstr    asc_383DE// "*"
0x1d349  callvirt instance bool [mscorlib]System.String::Equals(string)
0x1d34e  brtrue.s loc_1D352
0x1d350  ldc.i4.1
0x1d351  ret
0x1d352  ldarg.0
0x1d353  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x1d358  callvirt instance class [System.Net.Http]System.Net.Http.Headers.EntityTagHeaderValue Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_IfNoneMatch()
0x1d35d  brfalse.s loc_1D3A7
0x1d35f  ldarg.0
0x1d360  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x1d365  callvirt instance class [System.Net.Http]System.Net.Http.Headers.EntityTagHeaderValue Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_IfNoneMatch()
0x1d36a  callvirt instance string [System.Net.Http]System.Net.Http.Headers.EntityTagHeaderValue::get_Tag()
0x1d36f  ldstr    asc_383DE// "*"
0x1d374  callvirt instance bool [mscorlib]System.String::Equals(string)
0x1d379  brfalse.s loc_1D391
0x1d37b  ldc.i4   0x190
0x1d380  ldstr    aTheSpecifiedIf_3// "The specified If-None-Match condition i"...
0x1d385  ldc.i4.0
0x1d386  newarr   [mscorlib]System.Object
0x1d38b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0x1d390  throw
0x1d391  ldc.i4   0x190
0x1d396  ldstr    aTheSpecifiedIf_4// "The specified If-None-Match condition i"...
0x1d39b  ldc.i4.0
0x1d39c  newarr   [mscorlib]System.Object
0x1d3a1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0x1d3a6  throw
0x1d3a7  ldc.i4.0
0x1d3a8  ret
```
