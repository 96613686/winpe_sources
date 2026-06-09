# Microsoft.Crm.Sandbox.SandboxListener`2::IsServiceHostStarted

- ea: `0x5bb0`
- end: `0x5bc9`
- name: `Microsoft.Crm.Sandbox.SandboxListener`2::IsServiceHostStarted`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x5bb0`

## pseudocode

```c

```

## disassembly

```asm
0x5bb0  ldarg.0
0x5bb1  ldfld    class [System.ServiceModel]System.ServiceModel.ServiceHost class Microsoft.Crm.Sandbox.SandboxListener`2<var<u1>, !!T0>::_serviceHost
0x5bb6  brfalse.s loc_5BC7
0x5bb8  ldarg.0
0x5bb9  ldfld    class [System.ServiceModel]System.ServiceModel.ServiceHost class Microsoft.Crm.Sandbox.SandboxListener`2<var<u1>, !!T0>::_serviceHost
0x5bbe  callvirt instance valuetype [System.ServiceModel]System.ServiceModel.CommunicationState [System.ServiceModel]System.ServiceModel.Channels.CommunicationObject::get_State()
0x5bc3  ldc.i4.2
0x5bc4  ceq
0x5bc6  ret
0x5bc7  ldc.i4.0
0x5bc8  ret
```
