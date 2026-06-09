# Microsoft.Crm.BusinessEntities.RunAsCondition::GetInitiatingPluginExecutionContext

- ea: `0x7e0b0`
- end: `0x7e0ef`
- name: `Microsoft.Crm.BusinessEntities.RunAsCondition::GetInitiatingPluginExecutionContext`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x7e030`

## callees

- `0x7e0b0`

## string_xrefs

- `0x7e0da`: `Update`
- `0x7e0c8`: `Create`

## pseudocode

```c

```

## disassembly

```asm
0x7e0b0  ldarg.0
0x7e0b1  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext::get_ParentContext()
0x7e0b6  stloc.0
0x7e0b7  ldloc.0
0x7e0b8  brfalse.s loc_7E0ED
0x7e0ba  ldloc.0
0x7e0bb  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext::get_ParentContext()
0x7e0c0  brfalse.s loc_7E0ED
0x7e0c2  ldloc.0
0x7e0c3  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_MessageName()
0x7e0c8  ldstr    aCreate// "Create"
0x7e0cd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7e0d2  brtrue.s loc_7E0E6
0x7e0d4  ldloc.0
0x7e0d5  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_MessageName()
0x7e0da  ldstr    aUpdate// "Update"
0x7e0df  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7e0e4  brfalse.s loc_7E0ED
0x7e0e6  ldloc.0
0x7e0e7  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext::get_ParentContext()
0x7e0ec  stloc.0
0x7e0ed  ldloc.0
0x7e0ee  ret
```
