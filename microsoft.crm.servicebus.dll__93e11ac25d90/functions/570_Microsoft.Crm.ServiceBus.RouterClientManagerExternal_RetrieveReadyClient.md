# Microsoft.Crm.ServiceBus.RouterClientManagerExternal::RetrieveReadyClient

- ea: `0x570`
- end: `0x636`
- name: `Microsoft.Crm.ServiceBus.RouterClientManagerExternal::RetrieveReadyClient`
- size: `198`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x100`
- `0x1f0`
- `0x230`
- `0x350`
- `0x500`
- `0x570`

## pseudocode

```c

```

## disassembly

```asm
0x570  ldarg.0
0x571  ldfld    class Microsoft.Crm.ServiceBus.RouterClient Microsoft.Crm.ServiceBus.RouterClientManagerExternal::_readyClient
0x576  brfalse.s loc_58D
0x578  ldarg.0
0x579  ldfld    class Microsoft.Crm.ServiceBus.RouterClient Microsoft.Crm.ServiceBus.RouterClientManagerExternal::_readyClient
0x57e  callvirt instance valuetype Microsoft.Crm.ServiceBus.ClientStatus Microsoft.Crm.ServiceBus.RouterClient::get_Status()
0x583  ldc.i4.1
0x584  bne.un.s loc_58D
0x586  ldarg.0
0x587  ldfld    class Microsoft.Crm.ServiceBus.RouterClient Microsoft.Crm.ServiceBus.RouterClientManagerExternal::_readyClient
0x58c  ret
0x58d  ldsfld   object Microsoft.Crm.ServiceBus.RouterClientManagerExternal::_lockObject
0x592  stloc.0
0x593  ldc.i4.0
0x594  stloc.1
0x595  ldloc.0
0x596  ldloca.s 1
0x598  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x59d  ldarg.0
0x59e  ldfld    class Microsoft.Crm.ServiceBus.RouterClient Microsoft.Crm.ServiceBus.RouterClientManagerExternal::_readyClient
0x5a3  brfalse.s loc_5C7
0x5a5  ldarg.0
0x5a6  ldfld    class Microsoft.Crm.ServiceBus.RouterClient Microsoft.Crm.ServiceBus.RouterClientManagerExternal::_readyClient
0x5ab  callvirt instance valuetype Microsoft.Crm.ServiceBus.ClientStatus Microsoft.Crm.ServiceBus.RouterClient::get_Status()
0x5b0  ldc.i4.1
0x5b1  bne.un.s loc_5BC
0x5b3  ldarg.0
0x5b4  ldfld    class Microsoft.Crm.ServiceBus.RouterClient Microsoft.Crm.ServiceBus.RouterClientManagerExternal::_readyClient
0x5b9  stloc.3
0x5ba  leave.s  loc_634
0x5bc  ldarg.0
0x5bd  ldfld    class Microsoft.Crm.ServiceBus.RouterClient Microsoft.Crm.ServiceBus.RouterClientManagerExternal::_readyClient
0x5c2  callvirt instance void Microsoft.Crm.ServiceBus.RouterClient::Close()
0x5c7  newobj   instance void Microsoft.Crm.ServiceBus.RouterClient::.ctor()
0x5cc  stloc.2
0x5cd  ldloc.2
0x5ce  ldarg.0
0x5cf  call     instance class [System]System.Uri Microsoft.Crm.ServiceBus.RouterClientManagerExternal::get_InvitationWebServiceUrl()
0x5d4  callvirt instance string [System]System.Uri::get_Host()
0x5d9  callvirt instance void Microsoft.Crm.ServiceBus.RouterClient::Start(string endpointHostName)
0x5de  ldloc.2
0x5df  callvirt instance valuetype Microsoft.Crm.ServiceBus.ClientStatus Microsoft.Crm.ServiceBus.RouterClient::get_Status()
0x5e4  ldc.i4.1
0x5e5  beq.s    loc_61A
0x5e7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5ec  ldstr    aInvalidClientS// "Invalid client state after start: {0}"
0x5f1  ldc.i4.1
0x5f2  newarr   [mscorlib]System.Object
0x5f7  dup
0x5f8  ldc.i4.0
0x5f9  ldloc.2
0x5fa  callvirt instance valuetype Microsoft.Crm.ServiceBus.ClientStatus Microsoft.Crm.ServiceBus.RouterClient::get_Status()
0x5ff  stloc.s  4
0x601  ldloca.s 4
0x603  constrained. Microsoft.Crm.ServiceBus.ClientStatus
0x609  callvirt instance string [mscorlib]System.Object::ToString()
0x60e  stelem.ref
0x60f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x614  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x619  throw
0x61a  ldarg.0
0x61b  ldloc.2
0x61c  stfld    class Microsoft.Crm.ServiceBus.RouterClient Microsoft.Crm.ServiceBus.RouterClientManagerExternal::_readyClient
0x621  leave.s  loc_62D
0x623  ldloc.1
0x624  brfalse.s loc_62C
0x626  ldloc.0
0x627  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x62c  endfinally
0x62d  ldarg.0
0x62e  ldfld    class Microsoft.Crm.ServiceBus.RouterClient Microsoft.Crm.ServiceBus.RouterClientManagerExternal::_readyClient
0x633  ret
0x634  ldloc.3
0x635  ret
```
