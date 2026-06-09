# Microsoft.Crm.CrmTransactionEventManager::RegisterForPostCommitTransactionEvent

- ea: `0x10f50`
- end: `0x10f76`
- name: `Microsoft.Crm.CrmTransactionEventManager::RegisterForPostCommitTransactionEvent`
- size: `38`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x10b60`
- `0x10b70`

## callees

- `0x10f10`
- `0x10f50`
- `0x11250`
- `0x1b5d0`

## string_xrefs

- `0x10f65`: ` is already registered. Cannot register duplicate handlers.`
- `0x10f5a`: `The PostCommitTransactionEventHandler `

## pseudocode

```c

```

## disassembly

```asm
0x10f50  ldarg.0
0x10f51  ldarg.1
0x10f52  ldarg.2
0x10f53  call     instance bool Microsoft.Crm.CrmTransactionEventManager::TryRegisterForPostCommitTransactionEvent(class PostCommitTransactionEventHandler eventHandler, object parameter)
0x10f58  brtrue.s loc_10F75
0x10f5a  ldstr    aThePostcommitt// "The PostCommitTransactionEventHandler "
0x10f5f  ldarg.1
0x10f60  call     string Microsoft.Crm.CrmTransactionEventManager::GetMethodFullName(class [mscorlib]System.Delegate prospectiveEventHandler)
0x10f65  ldstr    aIsAlreadyRegis// " is already registered. Cannot register"...
0x10f6a  call     string [mscorlib]System.String::Concat(string, string, string)
0x10f6f  newobj   instance void Microsoft.Crm.CrmInvalidOperationException::.ctor(string message)
0x10f74  throw
0x10f75  ret
```
