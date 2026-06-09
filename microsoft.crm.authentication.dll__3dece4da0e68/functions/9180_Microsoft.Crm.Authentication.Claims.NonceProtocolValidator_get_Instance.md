# Microsoft.Crm.Authentication.Claims.NonceProtocolValidator::get_Instance

- ea: `0x9180`
- end: `0x91b5`
- name: `Microsoft.Crm.Authentication.Claims.NonceProtocolValidator::get_Instance`
- size: `53`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xd2d0`
- `0x14d30`

## callees

- `0x9180`
- `0x91c0`

## pseudocode

```c

```

## disassembly

```asm
0x9180  ldsfld   class Microsoft.Crm.Authentication.Claims.INonceProtocolValidator Microsoft.Crm.Authentication.Claims.NonceProtocolValidator::_instance
0x9185  brtrue.s loc_91AF
0x9187  ldsfld   object Microsoft.Crm.Authentication.Claims.NonceProtocolValidator::_staticLockObject
0x918c  stloc.0
0x918d  ldc.i4.0
0x918e  stloc.1
0x918f  ldloc.0
0x9190  ldloca.s 1
0x9192  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x9197  ldsfld   class Microsoft.Crm.Authentication.Claims.INonceProtocolValidator Microsoft.Crm.Authentication.Claims.NonceProtocolValidator::_instance
0x919c  brtrue.s loc_91A3
0x919e  call     void Microsoft.Crm.Authentication.Claims.NonceProtocolValidator::InitializeInstance()
0x91a3  leave.s  loc_91AF
0x91a5  ldloc.1
0x91a6  brfalse.s loc_91AE
0x91a8  ldloc.0
0x91a9  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x91ae  endfinally
0x91af  ldsfld   class Microsoft.Crm.Authentication.Claims.INonceProtocolValidator Microsoft.Crm.Authentication.Claims.NonceProtocolValidator::_instance
0x91b4  ret
```
