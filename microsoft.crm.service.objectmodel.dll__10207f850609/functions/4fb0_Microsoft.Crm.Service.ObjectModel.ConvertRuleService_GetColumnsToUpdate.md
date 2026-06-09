# Microsoft.Crm.Service.ObjectModel.ConvertRuleService::GetColumnsToUpdate

- ea: `0x4fb0`
- end: `0x4fd7`
- name: `Microsoft.Crm.Service.ObjectModel.ConvertRuleService::GetColumnsToUpdate`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## string_xrefs

- `0x4fd0`: `responsetemplateid`

## pseudocode

```c

```

## disassembly

```asm
0x4fb0  ldc.i4.4
0x4fb1  newarr   [mscorlib]System.String
0x4fb6  dup
0x4fb7  ldc.i4.0
0x4fb8  ldstr    aQueueid// "queueid"
0x4fbd  stelem.ref
0x4fbe  dup
0x4fbf  ldc.i4.1
0x4fc0  ldstr    aSourcetypecode// "sourcetypecode"
0x4fc5  stelem.ref
0x4fc6  dup
0x4fc7  ldc.i4.2
0x4fc8  ldstr    aSendautomaticr// "sendautomaticresponse"
0x4fcd  stelem.ref
0x4fce  dup
0x4fcf  ldc.i4.3
0x4fd0  ldstr    aResponsetempla// "responsetemplateid"
0x4fd5  stelem.ref
0x4fd6  ret
```
