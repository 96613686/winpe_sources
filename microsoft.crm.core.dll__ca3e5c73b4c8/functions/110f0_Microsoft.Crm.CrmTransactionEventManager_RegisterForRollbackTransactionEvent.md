# Microsoft.Crm.CrmTransactionEventManager::RegisterForRollbackTransactionEvent

- ea: `0x110f0`
- end: `0x11116`
- name: `Microsoft.Crm.CrmTransactionEventManager::RegisterForRollbackTransactionEvent`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x110b0`
- `0x110f0`
- `0x11250`
- `0x1b5d0`

## string_xrefs

- `0x11105`: ` is already registered. Cannot register duplicate handlers.`
- `0x110fa`: `The RollbackTransactionEventHandler `

## pseudocode

```c

```

## disassembly

```asm
0x110f0  ldarg.0
0x110f1  ldarg.1
0x110f2  ldarg.2
0x110f3  call     instance bool Microsoft.Crm.CrmTransactionEventManager::TryRegisterForRollbackTransactionEvent(class RollbackTransactionEventHandler eventHandler, object parameter)
0x110f8  brtrue.s loc_11115
0x110fa  ldstr    aTheRollbacktra// "The RollbackTransactionEventHandler "
0x110ff  ldarg.1
0x11100  call     string Microsoft.Crm.CrmTransactionEventManager::GetMethodFullName(class [mscorlib]System.Delegate prospectiveEventHandler)
0x11105  ldstr    aIsAlreadyRegis// " is already registered. Cannot register"...
0x1110a  call     string [mscorlib]System.String::Concat(string, string, string)
0x1110f  newobj   instance void Microsoft.Crm.CrmInvalidOperationException::.ctor(string message)
0x11114  throw
0x11115  ret
```
