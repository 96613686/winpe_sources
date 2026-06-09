# Microsoft.Crm.Sandbox.SandboxAppDomainHelper::ChaosFailure

- ea: `0xe60`
- end: `0xe6f`
- name: `Microsoft.Crm.Sandbox.SandboxAppDomainHelper::ChaosFailure`
- size: `15`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x7b0`
- `0x1240`

## callees

- `0xe60`

## string_xrefs

- `0xe63`: `Chaos failure agent. This should not affect this transaction, contact CRM Developer Experience Team <crmdevexp@microsoft.com> if this is breaking any scenario.`

## pseudocode

```c

```

## disassembly

```asm
0xe60  ldarg.0
0xe61  brfalse.s loc_E6E
0xe63  ldstr    aChaosFailureAg// "Chaos failure agent. This should not af"...
0xe68  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0xe6d  throw
0xe6e  ret
```
