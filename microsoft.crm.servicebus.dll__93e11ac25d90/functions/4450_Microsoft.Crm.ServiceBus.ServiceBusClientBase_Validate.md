# Microsoft.Crm.ServiceBus.ServiceBusClientBase::Validate

- ea: `0x4450`
- end: `0x44f4`
- name: `Microsoft.Crm.ServiceBus.ServiceBusClientBase::Validate`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x4120`

## callees

- `0x1430`
- `0x2600`
- `0x4450`
- `0x5590`
- `0x55a0`

## string_xrefs

- `0x4480`: `net.windows.servicebus.action`
- `0x448d`: `net.windows.servicebus.action`

## pseudocode

```c

```

## disassembly

```asm
0x4450  ldarg.1
0x4451  newobj   instance void Microsoft.Crm.ServiceBus.TokenProvider::.ctor(class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation endpointInfo)
0x4456  stloc.0
0x4457  ldarg.1
0x4458  callvirt instance bool Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_IsFederatedMode()
0x445d  brfalse.s loc_4467
0x445f  ldloc.0
0x4460  ldc.i4.0
0x4461  callvirt instance string Microsoft.Crm.ServiceBus.TokenProvider::RetrieveEndpointToken(bool fromServiceBusScope)
0x4466  pop
0x4467  ldc.i4.0
0x4468  stloc.1
0x4469  ldloc.0
0x446a  ldc.i4.1
0x446b  callvirt instance string Microsoft.Crm.ServiceBus.TokenProvider::RetrieveEndpointToken(bool fromServiceBusScope)
0x4470  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.ServiceBus.ServiceBusUtility::ExtractClaims(string tokenString)
0x4475  stloc.2
0x4476  ldloc.2
0x4477  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Count()
0x447c  ldc.i4.0
0x447d  ble.s    loc_44E0
0x447f  ldloc.2
0x4480  ldstr    aNetWindowsServ// "net.windows.servicebus.action"
0x4485  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x448a  brfalse.s loc_44E0
0x448c  ldloc.2
0x448d  ldstr    aNetWindowsServ// "net.windows.servicebus.action"
0x4492  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x4497  ldc.i4.1
0x4498  newarr   [mscorlib]System.String
0x449d  dup
0x449e  ldc.i4.0
0x449f  ldstr    asc_A41E// ","
0x44a4  stelem.ref
0x44a5  ldc.i4.1
0x44a6  callvirt instance string[] [mscorlib]System.String::Split(string[], valuetype [mscorlib]System.StringSplitOptions)
0x44ab  stloc.3
0x44ac  ldc.i4.0
0x44ad  stloc.s  4
0x44af  br.s     loc_44D9
0x44b1  ldloc.3
0x44b2  ldloc.s  4
0x44b4  ldelem.ref
0x44b5  stloc.s  5
0x44b7  ldloc.s  5
0x44b9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x44be  brtrue.s loc_44D3
0x44c0  ldloc.s  5
0x44c2  ldstr    aSend// "Send"
0x44c7  ldc.i4.5
0x44c8  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x44cd  brfalse.s loc_44D3
0x44cf  ldc.i4.1
0x44d0  stloc.1
0x44d1  br.s     loc_44E0
0x44d3  ldloc.s  4
0x44d5  ldc.i4.1
0x44d6  add
0x44d7  stloc.s  4
0x44d9  ldloc.s  4
0x44db  ldloc.3
0x44dc  ldlen
0x44dd  conv.i4
0x44de  blt.s    loc_44B1
0x44e0  ldloc.1
0x44e1  brtrue.s loc_44F3
0x44e3  ldstr    aDidNotFindTheS// "Did not find the send claim"
0x44e8  ldc.i4   0x80044178
0x44ed  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x44f2  throw
0x44f3  ret
```
