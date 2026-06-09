# Microsoft.Crm.CrmTransactionEventManager::RegisterForPreCommitTransactionEvent

- ea: `0x10e00`
- end: `0x10e25`
- name: `Microsoft.Crm.CrmTransactionEventManager::RegisterForPreCommitTransactionEvent`
- size: `37`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x10b50`

## callees

- `0x10dd0`
- `0x10e00`
- `0x11250`
- `0x1b5d0`

## string_xrefs

- `0x10e09`: `The PreCommitTransactionEventHandler `
- `0x10e14`: ` is already registered. Cannot register duplicate handlers.`

## pseudocode

```c

```

## disassembly

```asm
0x10e00  ldarg.0
0x10e01  ldarg.1
0x10e02  call     instance bool Microsoft.Crm.CrmTransactionEventManager::TryRegisterForPreCommitTransactionEvent(class PreCommitTransactionEventHandler eventHandler)
0x10e07  brtrue.s loc_10E24
0x10e09  ldstr    aThePrecommittr// "The PreCommitTransactionEventHandler "
0x10e0e  ldarg.1
0x10e0f  call     string Microsoft.Crm.CrmTransactionEventManager::GetMethodFullName(class [mscorlib]System.Delegate prospectiveEventHandler)
0x10e14  ldstr    aIsAlreadyRegis// " is already registered. Cannot register"...
0x10e19  call     string [mscorlib]System.String::Concat(string, string, string)
0x10e1e  newobj   instance void Microsoft.Crm.CrmInvalidOperationException::.ctor(string message)
0x10e23  throw
0x10e24  ret
```
