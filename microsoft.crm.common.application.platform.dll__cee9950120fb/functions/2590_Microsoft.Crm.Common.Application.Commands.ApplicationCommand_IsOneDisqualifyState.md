# Microsoft.Crm.Common.Application.Commands.ApplicationCommand::IsOneDisqualifyState

- ea: `0x2590`
- end: `0x25a5`
- name: `Microsoft.Crm.Common.Application.Commands.ApplicationCommand::IsOneDisqualifyState`
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
0x2590  ldc.i4.2
0x2591  stloc.0
0x2592  ldloca.s 0
0x2594  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.LeadState
0x259a  callvirt instance string [mscorlib]System.Object::ToString()
0x259f  call     bool Microsoft.Crm.Common.Application.Commands.ApplicationCommand::IsOnlyOneState(string LeadState)
0x25a4  ret
```
