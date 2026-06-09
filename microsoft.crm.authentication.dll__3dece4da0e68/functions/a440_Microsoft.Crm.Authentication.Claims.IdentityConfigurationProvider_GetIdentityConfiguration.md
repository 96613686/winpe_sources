# Microsoft.Crm.Authentication.Claims.IdentityConfigurationProvider::GetIdentityConfiguration

- ea: `0xa440`
- end: `0xa46a`
- name: `Microsoft.Crm.Authentication.Claims.IdentityConfigurationProvider::GetIdentityConfiguration`
- size: `42`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0xdab0`
- `0xea20`
- `0xf480`
- `0xf650`
- `0x148c0`

## callees

- `0xa340`
- `0xa440`

## pseudocode

```c

```

## disassembly

```asm
0xa440  ldsfld   class [mscorlib]System.Action <>c::<>9__9_0
0xa445  dup
0xa446  brtrue.s loc_A45F
0xa448  pop
0xa449  ldsfld   class <>c <>c::<>9
0xa44e  ldftn    instance void <>c::<GetIdentityConfiguration>b__9_0()
0xa454  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0xa459  dup
0xa45a  stsfld   class [mscorlib]System.Action <>c::<>9__9_0
0xa45f  call     void Microsoft.Crm.Authentication.Claims.IdentityConfigurationProvider::InitializeConfiguration(class [mscorlib]System.Action action)
0xa464  ldsfld   class [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration Microsoft.Crm.Authentication.Claims.IdentityConfigurationProvider::_identityConfiguration
0xa469  ret
```
