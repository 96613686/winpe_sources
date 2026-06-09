# Microsoft.Crm.Protocols.WSTrust.Bindings.WSTrustBindingBase::.ctor_0

- ea: `0x15b0`
- end: `0x15f1`
- name: `Microsoft.Crm.Protocols.WSTrust.Bindings.WSTrustBindingBase::.ctor_0`
- size: `65`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0xe60`
- `0x15a0`

## callees

- `0x15b0`
- `0x1750`
- `0x1790`

## pseudocode

```c

```

## disassembly

```asm
0x15b0  ldarg.0
0x15b1  call     instance void [System.ServiceModel]System.ServiceModel.Channels.Binding::.ctor()
0x15b6  ldarg.0
0x15b7  ldc.i4.2
0x15b8  stfld    valuetype [System.ServiceModel]System.ServiceModel.SecurityMode Microsoft.Crm.Protocols.WSTrust.Bindings.WSTrustBindingBase::_securityMode
0x15bd  ldarg.0
0x15be  call     class [System.ServiceModel]System.ServiceModel.Security.TrustVersion [System.ServiceModel]System.ServiceModel.Security.TrustVersion::get_WSTrust13()
0x15c3  stfld    class [System.ServiceModel]System.ServiceModel.Security.TrustVersion Microsoft.Crm.Protocols.WSTrust.Bindings.WSTrustBindingBase::_trustVersion
0x15c8  ldarg.2
0x15c9  brtrue.s loc_15D6
0x15cb  ldstr    aTrustversion// "trustVersion"
0x15d0  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x15d5  throw
0x15d6  ldarg.2
0x15d7  call     void Microsoft.Crm.Protocols.WSTrust.Bindings.WSTrustBindingBase::ValidateTrustVersion(class [System.ServiceModel]System.ServiceModel.Security.TrustVersion trustVersion)
0x15dc  ldarg.1
0x15dd  call     void Microsoft.Crm.Protocols.WSTrust.Bindings.WSTrustBindingBase::ValidateSecurityMode(valuetype [System.ServiceModel]System.ServiceModel.SecurityMode securityMode)
0x15e2  ldarg.0
0x15e3  ldarg.1
0x15e4  stfld    valuetype [System.ServiceModel]System.ServiceModel.SecurityMode Microsoft.Crm.Protocols.WSTrust.Bindings.WSTrustBindingBase::_securityMode
0x15e9  ldarg.0
0x15ea  ldarg.2
0x15eb  stfld    class [System.ServiceModel]System.ServiceModel.Security.TrustVersion Microsoft.Crm.Protocols.WSTrust.Bindings.WSTrustBindingBase::_trustVersion
0x15f0  ret
```
