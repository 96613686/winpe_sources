# Microsoft.Crm.Common.Application.Commands.ApplicationCommand::IsOneQualifyState

- ea: `0x2570`
- end: `0x2585`
- name: `Microsoft.Crm.Common.Application.Commands.ApplicationCommand::IsOneQualifyState`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x25b0`

## pseudocode

```c

```

## disassembly

```asm
0x2570  ldc.i4.1
0x2571  stloc.0
0x2572  ldloca.s 0
0x2574  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.LeadState
0x257a  callvirt instance string [mscorlib]System.Object::ToString()
0x257f  call     bool Microsoft.Crm.Common.Application.Commands.ApplicationCommand::IsOnlyOneState(string LeadState)
0x2584  ret
```
