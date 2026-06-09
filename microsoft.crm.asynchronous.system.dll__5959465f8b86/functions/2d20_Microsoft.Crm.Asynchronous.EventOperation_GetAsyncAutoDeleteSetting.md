# Microsoft.Crm.Asynchronous.EventOperation::GetAsyncAutoDeleteSetting

- ea: `0x2d20`
- end: `0x2d74`
- name: `Microsoft.Crm.Asynchronous.EventOperation::GetAsyncAutoDeleteSetting`
- size: `84`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x3150`

## callees

- `0x2d20`

## string_xrefs

- `0x2d26`: `AsyncAutoDeleteOverride`
- `0x2d3d`: `Invalid auto delete setting`

## pseudocode

```c

```

## disassembly

```asm
0x2d20  ldarg.1
0x2d21  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext::get_SharedVariables()
0x2d26  ldstr    aAsyncautodelet// "AsyncAutoDeleteOverride"
0x2d2b  ldloca.s 0
0x2d2d  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::TryGetValue(var<u1>, !!T0)
0x2d32  brfalse.s loc_2D4E
0x2d34  ldloc.0
0x2d35  isinst   [mscorlib]System.Boolean
0x2d3a  ldnull
0x2d3b  cgt.un
0x2d3d  ldstr    aInvalidAutoDel// "Invalid auto delete setting"
0x2d42  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x2d47  ldloc.0
0x2d48  unbox.any [mscorlib]System.Boolean
0x2d4d  ret
0x2d4e  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.StepDescriptionCache [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.StepDescriptionCache::get_Instance()
0x2d53  ldarg.1
0x2d54  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext::get_OwningExtension()
0x2d59  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x2d5e  ldarg.1
0x2d5f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext::get_OrganizationId()
0x2d64  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x2d69  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.StepDescription>::LookupEntry(void, var<u1>)
0x2d6e  callvirt instance bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.StepDescription::get_AsyncAutoDelete()
0x2d73  ret
```
