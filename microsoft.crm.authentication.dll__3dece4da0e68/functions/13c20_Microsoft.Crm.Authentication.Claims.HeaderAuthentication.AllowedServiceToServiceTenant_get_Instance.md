# Microsoft.Crm.Authentication.Claims.HeaderAuthentication.AllowedServiceToServiceTenant::get_Instance

- ea: `0x13c20`
- end: `0x13c5a`
- name: `Microsoft.Crm.Authentication.Claims.HeaderAuthentication.AllowedServiceToServiceTenant::get_Instance`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xf230`

## callees

- `0x13c20`
- `0x13ca0`

## pseudocode

```c

```

## disassembly

```asm
0x13c20  ldsfld   class Microsoft.Crm.Authentication.Claims.HeaderAuthentication.IAllowedServiceToServiceTenant Microsoft.Crm.Authentication.Claims.HeaderAuthentication.AllowedServiceToServiceTenant::_instance
0x13c25  brtrue.s loc_13C54
0x13c27  ldsfld   object Microsoft.Crm.Authentication.Claims.HeaderAuthentication.AllowedServiceToServiceTenant::_staticLockObject
0x13c2c  stloc.0
0x13c2d  ldc.i4.0
0x13c2e  stloc.1
0x13c2f  ldloc.0
0x13c30  ldloca.s 1
0x13c32  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x13c37  ldsfld   class Microsoft.Crm.Authentication.Claims.HeaderAuthentication.IAllowedServiceToServiceTenant Microsoft.Crm.Authentication.Claims.HeaderAuthentication.AllowedServiceToServiceTenant::_instance
0x13c3c  brtrue.s loc_13C48
0x13c3e  newobj   instance void Microsoft.Crm.Authentication.Claims.HeaderAuthentication.AllowedServiceToServiceTenant::.ctor()
0x13c43  stsfld   class Microsoft.Crm.Authentication.Claims.HeaderAuthentication.IAllowedServiceToServiceTenant Microsoft.Crm.Authentication.Claims.HeaderAuthentication.AllowedServiceToServiceTenant::_instance
0x13c48  leave.s  loc_13C54
0x13c4a  ldloc.1
0x13c4b  brfalse.s loc_13C53
0x13c4d  ldloc.0
0x13c4e  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x13c53  endfinally
0x13c54  ldsfld   class Microsoft.Crm.Authentication.Claims.HeaderAuthentication.IAllowedServiceToServiceTenant Microsoft.Crm.Authentication.Claims.HeaderAuthentication.AllowedServiceToServiceTenant::_instance
0x13c59  ret
```
