# Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignResponseRecordPageHandler::ChangeState

- ea: `0x2430`
- end: `0x2449`
- name: `Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignResponseRecordPageHandler::ChangeState`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x2430  ldc.i4.0
0x2431  stloc.1
0x2432  ldloca.s 1
0x2434  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.CampaignResponseState
0x243a  callvirt instance string [mscorlib]System.Object::ToString()
0x243f  stloc.0
0x2440  ldarg.0
0x2441  ldloc.0
0x2442  ldc.i4.m1
0x2443  callvirt instance void [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::ChangeState(string, int32)
0x2448  ret
```
