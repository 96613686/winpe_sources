# Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_Uri

- ea: `0x98f0`
- end: `0x9923`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_Uri`
- size: `51`
- prototype: ``
- caller_count: `10`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xf60`
- `0x7230`
- `0x7e30`
- `0x8620`
- `0x8c60`
- `0x8c80`
- `0xa020`
- `0xa0f0`
- `0xa350`
- `0xcd60`

## pseudocode

```c

```

## disassembly

```asm
0x98f0  newobj   instance void [System]System.UriBuilder::.ctor()
0x98f5  dup
0x98f6  ldc.i4.5
0x98f7  ldstr    a127001// "127.0.0.1"
0x98fc  call     T0x2B000010
0x9901  callvirt instance void [System]System.UriBuilder::set_Host(string)
0x9906  dup
0x9907  ldarg.0
0x9908  ldfld    int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::WorkerPort
0x990d  callvirt instance void [System]System.UriBuilder::set_Port(int32)
0x9912  dup
0x9913  ldstr    aNetTcp// "net.tcp"
0x9918  callvirt instance void [System]System.UriBuilder::set_Scheme(string)
0x991d  callvirt instance class [System]System.Uri [System]System.UriBuilder::get_Uri()
0x9922  ret
```
