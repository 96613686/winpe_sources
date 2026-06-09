# Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControlProcessLayoutCache::.ctor

- ea: `0x5fe0`
- end: `0x5ff7`
- name: `Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControlProcessLayoutCache::.ctor`
- size: `23`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x60b0`

## string_xrefs

- `0x5fe1`: `ProcessControlLayoutCache`

## pseudocode

```c

```

## disassembly

```asm
0x5fe0  ldarg.0
0x5fe1  ldstr    aProcesscontrol_50// "ProcessControlLayoutCache"
0x5fe6  ldc.i4.1
0x5fe7  newarr   [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType
0x5fec  dup
0x5fed  ldc.i4.0
0x5fee  ldc.i4.s 0x4F
0x5ff0  stelem.i4
0x5ff1  call     instance void class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCache`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControlInnerCacheKey, class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControlLayout>>::.ctor(string, valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType[])
0x5ff6  ret
```
