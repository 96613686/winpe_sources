# Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::UpdateVariableInternal

- ea: `0x33600`
- end: `0x33629`
- name: `Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::UpdateVariableInternal`
- size: `41`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x33580`
- `0x335c0`

## callees

- `0x28e30`
- `0x28fa0`

## string_xrefs

- `0x33607`: `The variable (with name {0}) to be updated does not exist`

## pseudocode

```c

```

## disassembly

```asm
0x33600  ldarg.1
0x33601  ldarg.2
0x33602  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x33607  ldstr    aTheVariableWit_0// "The variable (with name {0}) to be upda"...
0x3360c  ldc.i4.1
0x3360d  newarr   [mscorlib]System.Object
0x33612  dup
0x33613  ldc.i4.0
0x33614  ldarg.2
0x33615  stelem.ref
0x33616  call     string Microsoft.Crm.Workflow.Utils.StringUtility::FormatInvariant(string message, object[] parameters)
0x3361b  call     void Microsoft.Crm.Workflow.Utils.ExceptionUtility::Assert(bool condition, string message)
0x33620  ldarg.1
0x33621  ldarg.2
0x33622  ldarg.3
0x33623  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x33628  ret
```
