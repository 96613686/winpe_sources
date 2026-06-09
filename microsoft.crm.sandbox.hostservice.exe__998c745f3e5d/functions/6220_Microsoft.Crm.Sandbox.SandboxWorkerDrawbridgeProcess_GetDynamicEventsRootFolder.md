# Microsoft.Crm.Sandbox.SandboxWorkerDrawbridgeProcess::GetDynamicEventsRootFolder

- ea: `0x6220`
- end: `0x6244`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerDrawbridgeProcess::GetDynamicEventsRootFolder`
- size: `36`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x5c60`

## string_xrefs

- `0x6239`: `MonAgentDynamicEvents\CrmTrace`

## pseudocode

```c

```

## disassembly

```asm
0x6220  ldtoken  Microsoft.Crm.Sandbox.SandboxWorkerDrawbridgeProcess
0x6225  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x622a  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x622f  callvirt instance string [mscorlib]System.Reflection.Assembly::get_Location()
0x6234  call     string [mscorlib]System.IO.Path::GetPathRoot(string)
0x6239  ldstr    aMonagentdynami// "MonAgentDynamicEvents\\CrmTrace"
0x623e  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x6243  ret
```
