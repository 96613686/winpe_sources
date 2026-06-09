# Microsoft.Crm.CrmCacheUtility::IsInStagingContextAndStagedCacheEnabled

- ea: `0x1bc10`
- end: `0x1bc52`
- name: `Microsoft.Crm.CrmCacheUtility::IsInStagingContextAndStagedCacheEnabled`
- size: `66`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x22240`

## callees

- `0x1bc10`
- `0x1bc60`
- `0x1bc80`
- `0x1bca0`

## string_xrefs

- `0x1bc2e`: `AddStagedMetadataInCache`
- `0x1bc40`: `AddStagedMetadataInCache`

## pseudocode

```c

```

## disassembly

```asm
0x1bc10  ldarg.0
0x1bc11  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.CrmCacheUtility::TrygetSqlExecutionContext(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x1bc16  stloc.0
0x1bc17  ldloc.0
0x1bc18  brfalse.s loc_1BC50
0x1bc1a  call     bool Microsoft.Crm.CrmCacheUtility::IsRefreshableMetadataCacheEnabled()
0x1bc1f  brfalse.s loc_1BC50
0x1bc21  call     bool Microsoft.Crm.CrmCacheUtility::IsStagedMetadataCacheEnabled()
0x1bc26  brfalse.s loc_1BC50
0x1bc28  ldloc.0
0x1bc29  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::get_ContextStorage()
0x1bc2e  ldstr    aAddstagedmetad// "AddStagedMetadataInCache"
0x1bc33  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x1bc38  brfalse.s loc_1BC50
0x1bc3a  ldloc.0
0x1bc3b  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::get_ContextStorage()
0x1bc40  ldstr    aAddstagedmetad// "AddStagedMetadataInCache"
0x1bc45  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x1bc4a  unbox.any [mscorlib]System.Boolean
0x1bc4f  ret
0x1bc50  ldc.i4.0
0x1bc51  ret
```
