# Microsoft.Crm.Workflow.Services.ActivityServiceBase::CreateLog

- ea: `0x14930`
- end: `0x14966`
- name: `Microsoft.Crm.Workflow.Services.ActivityServiceBase::CreateLog`
- size: `54`
- prototype: ``
- caller_count: `21`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x14860`
- `0x15bc0`
- `0x15df0`
- `0x16040`
- `0x16410`
- `0x16490`
- `0x165e0`
- `0x168d0`
- `0x16b10`
- `0x188b0`
- `0x18d00`
- `0x19020`
- `0x191f0`
- `0x19360`
- `0x19520`
- `0x19640`
- `0x198e0`
- `0x19ac0`
- `0x19d20`
- `0x19e60`
- `0x1a410`

## callees

- `0x147d0`
- `0x14820`
- `0x14840`
- `0x14970`

## pseudocode

```c

```

## disassembly

```asm
0x14930  ldarg.0
0x14931  ldarg.1
0x14932  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x14937  call     instance string Microsoft.Crm.Workflow.Services.ActivityServiceBase::FindStepId(string stepIdAndDescription)
0x1493c  stloc.0
0x1493d  ldarg.0
0x1493e  ldarg.1
0x1493f  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x14944  call     instance string Microsoft.Crm.Workflow.Services.ActivityServiceBase::FindStepDescription(string stepIdAndDescription)
0x14949  stloc.1
0x1494a  ldarg.0
0x1494b  ldloc.0
0x1494c  call     instance string Microsoft.Crm.Workflow.Services.ActivityServiceBase::FindStepName(string stepId)
0x14951  stloc.2
0x14952  ldarg.0
0x14953  ldloc.0
0x14954  ldstr    aStep_0// "_step"
0x14959  call     string [mscorlib]System.String::Concat(string, string)
0x1495e  ldloc.2
0x1495f  ldloc.1
0x14960  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.Services.ActivityServiceBase::CreateLog(string activityName, string stepName, string description)
0x14965  ret
```
