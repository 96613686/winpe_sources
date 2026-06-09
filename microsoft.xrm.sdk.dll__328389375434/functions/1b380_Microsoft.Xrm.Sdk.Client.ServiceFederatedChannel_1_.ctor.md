# Microsoft.Xrm.Sdk.Client.ServiceFederatedChannel`1::.ctor

- ea: `0x1b380`
- end: `0x1b39a`
- name: `Microsoft.Xrm.Sdk.Client.ServiceFederatedChannel`1::.ctor`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x7ca0`

## string_xrefs

- `0x1b388`: `token`

## pseudocode

```c

```

## disassembly

```asm
0x1b380  ldarg.0
0x1b381  ldarg.1
0x1b382  call     instance void class Microsoft.Xrm.Sdk.Client.ServiceChannel`1<var<u1>>::.ctor(class [System.ServiceModel]System.ServiceModel.ChannelFactory`1<var<u1>>)
0x1b387  ldarg.2
0x1b388  ldstr    aToken// "token"
0x1b38d  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x1b392  ldarg.0
0x1b393  ldarg.2
0x1b394  stfld    class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken class Microsoft.Xrm.Sdk.Client.ServiceFederatedChannel`1<var<u1>>::_token
0x1b399  ret
```
