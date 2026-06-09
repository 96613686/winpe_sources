# Microsoft.Crm.Extensibility.ExtensiblePlatformMessageDispatcher::GetDefaultEntityStateFromContext

- ea: `0x5be0`
- end: `0x5c36`
- name: `Microsoft.Crm.Extensibility.ExtensiblePlatformMessageDispatcher::GetDefaultEntityStateFromContext`
- size: `86`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x5b70`
- `0x5bb0`

## callees

- `0x5be0`

## string_xrefs

- `0x5c26`: `Update`
- `0x5c12`: `Create`

## pseudocode

```c

```

## disassembly

```asm
0x5be0  ldarg.s  4
0x5be2  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_RootPluginContext()
0x5be7  isinst   [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext
0x5bec  stloc.0
0x5bed  ldloc.0
0x5bee  brfalse.s loc_5C34
0x5bf0  ldloc.0
0x5bf1  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PrimaryEntityName()
0x5bf6  ldarg.2
0x5bf7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5bfc  brfalse.s loc_5C34
0x5bfe  ldloc.0
0x5bff  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_MessageName()
0x5c04  ldarg.3
0x5c05  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5c0a  brfalse.s loc_5C34
0x5c0c  ldloc.0
0x5c0d  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_MessageName()
0x5c12  ldstr    aCreate// "Create"
0x5c17  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5c1c  brfalse.s loc_5C20
0x5c1e  ldc.i4.1
0x5c1f  ret
0x5c20  ldloc.0
0x5c21  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_MessageName()
0x5c26  ldstr    aUpdate// "Update"
0x5c2b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5c30  brfalse.s loc_5C34
0x5c32  ldc.i4.2
0x5c33  ret
0x5c34  ldarg.1
0x5c35  ret
```
