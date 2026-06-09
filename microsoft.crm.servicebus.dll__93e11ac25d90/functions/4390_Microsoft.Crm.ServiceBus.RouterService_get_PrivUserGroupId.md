# Microsoft.Crm.ServiceBus.RouterService::get_PrivUserGroupId

- ea: `0x4390`
- end: `0x43e3`
- name: `Microsoft.Crm.ServiceBus.RouterService::get_PrivUserGroupId`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x4340`
- `0x4390`

## pseudocode

```c

```

## disassembly

```asm
0x4390  ldarg.0
0x4391  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.RouterService::_privUserGroupId
0x4396  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x439b  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x43a0  brfalse.s loc_43DC
0x43a2  ldsfld   object Microsoft.Crm.ServiceBus.RouterService::_lock
0x43a7  stloc.0
0x43a8  ldc.i4.0
0x43a9  stloc.1
0x43aa  ldloc.0
0x43ab  ldloca.s 1
0x43ad  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x43b2  ldarg.0
0x43b3  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.RouterService::_privUserGroupId
0x43b8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x43bd  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x43c2  brfalse.s loc_43D0
0x43c4  ldarg.0
0x43c5  ldarg.0
0x43c6  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.RouterService::RetrievePrivilegeUserGroupId()
0x43cb  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.RouterService::_privUserGroupId
0x43d0  leave.s  loc_43DC
0x43d2  ldloc.1
0x43d3  brfalse.s loc_43DB
0x43d5  ldloc.0
0x43d6  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x43db  endfinally
0x43dc  ldarg.0
0x43dd  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.RouterService::_privUserGroupId
0x43e2  ret
```
