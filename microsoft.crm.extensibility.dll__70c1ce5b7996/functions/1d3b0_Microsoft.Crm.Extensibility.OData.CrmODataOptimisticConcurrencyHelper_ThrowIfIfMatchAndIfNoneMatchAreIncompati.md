# Microsoft.Crm.Extensibility.OData.CrmODataOptimisticConcurrencyHelper::ThrowIfIfMatchAndIfNoneMatchAreIncompatible

- ea: `0x1d3b0`
- end: `0x1d474`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataOptimisticConcurrencyHelper::ThrowIfIfMatchAndIfNoneMatchAreIncompatible`
- size: `196`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1d0f0`
- `0x1d220`
- `0x1d2a0`
- `0x1d320`

## callees

- `0x19a60`
- `0x19a80`
- `0x1d3b0`
- `0x1d480`
- `0x24e60`

## string_xrefs

- `0x1d3ee`: `The specified combination of If-Match and If-None-Match conditions isn't  valid.`
- `0x1d42d`: `The specified combination of If-Match and If-None-Match conditions isn't valid.`

## pseudocode

```c

```

## disassembly

```asm
0x1d3b0  ldarg.0
0x1d3b1  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x1d3b6  callvirt instance class [System.Net.Http]System.Net.Http.Headers.EntityTagHeaderValue Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_IfMatch()
0x1d3bb  brfalse  loc_1D444
0x1d3c0  ldarg.0
0x1d3c1  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x1d3c6  callvirt instance class [System.Net.Http]System.Net.Http.Headers.EntityTagHeaderValue Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_IfMatch()
0x1d3cb  callvirt instance string [System.Net.Http]System.Net.Http.Headers.EntityTagHeaderValue::get_Tag()
0x1d3d0  ldstr    asc_383DE// "*"
0x1d3d5  callvirt instance bool [mscorlib]System.String::Equals(string)
0x1d3da  brfalse.s loc_1D3FF
0x1d3dc  ldarg.0
0x1d3dd  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x1d3e2  callvirt instance class [System.Net.Http]System.Net.Http.Headers.EntityTagHeaderValue Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_IfNoneMatch()
0x1d3e7  brfalse.s loc_1D444
0x1d3e9  ldc.i4   0x190
0x1d3ee  ldstr    aTheSpecifiedCo// "The specified combination of If-Match a"...
0x1d3f3  ldc.i4.0
0x1d3f4  newarr   [mscorlib]System.Object
0x1d3f9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0x1d3fe  throw
0x1d3ff  ldarg.0
0x1d400  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x1d405  callvirt instance class [System.Net.Http]System.Net.Http.Headers.EntityTagHeaderValue Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_IfNoneMatch()
0x1d40a  brfalse.s loc_1D43E
0x1d40c  ldarg.0
0x1d40d  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x1d412  callvirt instance class [System.Net.Http]System.Net.Http.Headers.EntityTagHeaderValue Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_IfNoneMatch()
0x1d417  callvirt instance string [System.Net.Http]System.Net.Http.Headers.EntityTagHeaderValue::get_Tag()
0x1d41c  ldstr    asc_383DE// "*"
0x1d421  callvirt instance bool [mscorlib]System.String::Equals(string)
0x1d426  brfalse.s loc_1D43E
0x1d428  ldc.i4   0x190
0x1d42d  ldstr    aTheSpecifiedCo_0// "The specified combination of If-Match a"...
0x1d432  ldc.i4.0
0x1d433  newarr   [mscorlib]System.Object
0x1d438  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0x1d43d  throw
0x1d43e  ldarg.1
0x1d43f  call     void Microsoft.Crm.Extensibility.OData.CrmODataOptimisticConcurrencyHelper::ThrowIfOptimisticConcurrencyIsDisabled(string entityLogicalName)
0x1d444  ldarg.0
0x1d445  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x1d44a  callvirt instance class [System.Net.Http]System.Net.Http.Headers.EntityTagHeaderValue Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_IfNoneMatch()
0x1d44f  brfalse.s loc_1D473
0x1d451  ldarg.0
0x1d452  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x1d457  callvirt instance class [System.Net.Http]System.Net.Http.Headers.EntityTagHeaderValue Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_IfNoneMatch()
0x1d45c  callvirt instance string [System.Net.Http]System.Net.Http.Headers.EntityTagHeaderValue::get_Tag()
0x1d461  ldstr    asc_383DE// "*"
0x1d466  callvirt instance bool [mscorlib]System.String::Equals(string)
0x1d46b  brtrue.s loc_1D473
0x1d46d  ldarg.1
0x1d46e  call     void Microsoft.Crm.Extensibility.OData.CrmODataOptimisticConcurrencyHelper::ThrowIfOptimisticConcurrencyIsDisabled(string entityLogicalName)
0x1d473  ret
```
