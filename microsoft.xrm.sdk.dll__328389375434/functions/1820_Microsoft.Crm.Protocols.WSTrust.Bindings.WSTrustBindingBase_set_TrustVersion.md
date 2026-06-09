# Microsoft.Crm.Protocols.WSTrust.Bindings.WSTrustBindingBase::set_TrustVersion

- ea: `0x1820`
- end: `0x183c`
- name: `Microsoft.Crm.Protocols.WSTrust.Bindings.WSTrustBindingBase::set_TrustVersion`
- size: `28`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18030`
- `0x19270`

## callees

- `0x1790`
- `0x1820`

## pseudocode

```c

```

## disassembly

```asm
0x1820  ldarg.1
0x1821  brtrue.s loc_182E
0x1823  ldstr    aValue// "value"
0x1828  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x182d  throw
0x182e  ldarg.1
0x182f  call     void Microsoft.Crm.Protocols.WSTrust.Bindings.WSTrustBindingBase::ValidateTrustVersion(class [System.ServiceModel]System.ServiceModel.Security.TrustVersion trustVersion)
0x1834  ldarg.0
0x1835  ldarg.1
0x1836  stfld    class [System.ServiceModel]System.ServiceModel.Security.TrustVersion Microsoft.Crm.Protocols.WSTrust.Bindings.WSTrustBindingBase::_trustVersion
0x183b  ret
```
