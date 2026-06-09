# RegisteredEnvironment::.cctor

- ea: `0x15680`
- end: `0x157a9`
- name: `RegisteredEnvironment::.cctor`
- size: `297`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x155a0`
- `0x155c0`
- `0x15670`

## string_xrefs

- `0x15691`: `Invalid Configuration`
- `0x1575d`: `https://graph.chinacloudapi.cn/`
- `0x1578b`: `.msods.msol-nova.com/`

## pseudocode

```c

```

## disassembly

```asm
0x15680  newobj   instance void RegisteredEnvironment::.ctor()
0x15685  dup
0x15686  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1568b  callvirt instance void RegisteredEnvironment::set_TenantId(valuetype [mscorlib]System.Guid value)
0x15690  dup
0x15691  ldstr    aInvalidConfigu// "Invalid Configuration"
0x15696  callvirt instance void RegisteredEnvironment::set_GraphUrl(string value)
0x1569b  dup
0x1569c  ldc.i4.0
0x1569d  stfld    bool RegisteredEnvironment::Allowed
0x156a2  dup
0x156a3  ldc.i4.0
0x156a4  stfld    bool RegisteredEnvironment::PassThrough
0x156a9  stsfld   class RegisteredEnvironment RegisteredEnvironment::InvalidConfiguredTenant
0x156ae  newobj   instance void RegisteredEnvironment::.ctor()
0x156b3  dup
0x156b4  ldstr    aF8cdef31A31e4b// "f8cdef31-a31e-4b4a-93e4-5f571e91255a"
0x156b9  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x156be  callvirt instance void RegisteredEnvironment::set_TenantId(valuetype [mscorlib]System.Guid value)
0x156c3  dup
0x156c4  ldstr    aHttpsGraphWind// "https://graph.windows.net/"
0x156c9  callvirt instance void RegisteredEnvironment::set_GraphUrl(string value)
0x156ce  dup
0x156cf  ldc.i4.1
0x156d0  stfld    bool RegisteredEnvironment::Allowed
0x156d5  dup
0x156d6  ldc.i4.0
0x156d7  stfld    bool RegisteredEnvironment::PassThrough
0x156dc  stsfld   class RegisteredEnvironment RegisteredEnvironment::ProductionTenant
0x156e1  newobj   instance void RegisteredEnvironment::.ctor()
0x156e6  dup
0x156e7  ldstr    aEa8a4392515e48// "ea8a4392-515e-481f-879e-6571ff2a8a36"
0x156ec  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x156f1  callvirt instance void RegisteredEnvironment::set_TenantId(valuetype [mscorlib]System.Guid value)
0x156f6  dup
0x156f7  ldstr    aHttpsGraphPpeW// "https://graph.ppe.windows.net/"
0x156fc  callvirt instance void RegisteredEnvironment::set_GraphUrl(string value)
0x15701  dup
0x15702  ldc.i4.1
0x15703  stfld    bool RegisteredEnvironment::Allowed
0x15708  dup
0x15709  ldc.i4.0
0x1570a  stfld    bool RegisteredEnvironment::PassThrough
0x1570f  stsfld   class RegisteredEnvironment RegisteredEnvironment::PreProductionTenant
0x15714  newobj   instance void RegisteredEnvironment::.ctor()
0x15719  dup
0x1571a  ldstr    aF8cdef31A31e4b// "f8cdef31-a31e-4b4a-93e4-5f571e91255a"
0x1571f  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x15724  callvirt instance void RegisteredEnvironment::set_TenantId(valuetype [mscorlib]System.Guid value)
0x15729  dup
0x1572a  ldstr    aHttpsGraphWind// "https://graph.windows.net/"
0x1572f  callvirt instance void RegisteredEnvironment::set_GraphUrl(string value)
0x15734  dup
0x15735  ldc.i4.1
0x15736  stfld    bool RegisteredEnvironment::Allowed
0x1573b  dup
0x1573c  ldc.i4.0
0x1573d  stfld    bool RegisteredEnvironment::PassThrough
0x15742  stsfld   class RegisteredEnvironment RegisteredEnvironment::NationalTenant
0x15747  newobj   instance void RegisteredEnvironment::.ctor()
0x1574c  dup
0x1574d  ldstr    a0b4a31a2C1a047// "0b4a31a2-c1a0-475d-b363-5f26668660a3"
0x15752  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x15757  callvirt instance void RegisteredEnvironment::set_TenantId(valuetype [mscorlib]System.Guid value)
0x1575c  dup
0x1575d  ldstr    aHttpsGraphChin// "https://graph.chinacloudapi.cn/"
0x15762  callvirt instance void RegisteredEnvironment::set_GraphUrl(string value)
0x15767  dup
0x15768  ldc.i4.1
0x15769  stfld    bool RegisteredEnvironment::Allowed
0x1576e  dup
0x1576f  ldc.i4.0
0x15770  stfld    bool RegisteredEnvironment::PassThrough
0x15775  stsfld   class RegisteredEnvironment RegisteredEnvironment::CnNationalTenant
0x1577a  newobj   instance void RegisteredEnvironment::.ctor()
0x1577f  dup
0x15780  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x15785  callvirt instance void RegisteredEnvironment::set_TenantId(valuetype [mscorlib]System.Guid value)
0x1578a  dup
0x1578b  ldstr    aMsodsMsolNovaC// ".msods.msol-nova.com/"
0x15790  callvirt instance void RegisteredEnvironment::set_GraphUrl(string value)
0x15795  dup
0x15796  ldc.i4.1
0x15797  stfld    bool RegisteredEnvironment::Allowed
0x1579c  dup
0x1579d  ldc.i4.1
0x1579e  stfld    bool RegisteredEnvironment::PassThrough
0x157a3  stsfld   class RegisteredEnvironment RegisteredEnvironment::NovaTenant
0x157a8  ret
```
