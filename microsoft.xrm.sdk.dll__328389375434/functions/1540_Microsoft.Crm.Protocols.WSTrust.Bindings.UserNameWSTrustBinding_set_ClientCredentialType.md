# Microsoft.Crm.Protocols.WSTrust.Bindings.UserNameWSTrustBinding::set_ClientCredentialType

- ea: `0x1540`
- end: `0x158b`
- name: `Microsoft.Crm.Protocols.WSTrust.Bindings.UserNameWSTrustBinding::set_ClientCredentialType`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1510`
- `0x1540`
- `0x17f0`
- `0x1850`

## string_xrefs

- `0x1564`: `ID3225: UserNameWSTrustBinding in SecurityMode.Transport SecurityMode, clientCredentialType must be Digest or Basic. But actual value is '{0}'`

## pseudocode

```c

```

## disassembly

```asm
0x1540  ldarg.1
0x1541  call     bool Microsoft.Crm.Protocols.WSTrust.Bindings.UserNameWSTrustBinding::IsHttpClientCredentialTypeDefined(valuetype [System.ServiceModel]System.ServiceModel.HttpClientCredentialType value)
0x1546  brtrue.s loc_1553
0x1548  ldstr    aValue// "value"
0x154d  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x1552  throw
0x1553  ldc.i4.1
0x1554  ldarg.0
0x1555  call     instance valuetype [System.ServiceModel]System.ServiceModel.SecurityMode Microsoft.Crm.Protocols.WSTrust.Bindings.WSTrustBindingBase::get_SecurityMode()
0x155a  bne.un.s loc_1583
0x155c  ldc.i4.2
0x155d  ldarg.1
0x155e  beq.s    loc_1583
0x1560  ldc.i4.1
0x1561  ldarg.1
0x1562  beq.s    loc_1583
0x1564  ldstr    aId3225Username// "ID3225: UserNameWSTrustBinding in Secur"...
0x1569  ldc.i4.1
0x156a  newarr   [mscorlib]System.Object
0x156f  dup
0x1570  ldc.i4.0
0x1571  ldarg.1
0x1572  box      [System.ServiceModel]System.ServiceModel.HttpClientCredentialType
0x1577  stelem.ref
0x1578  call     string Microsoft.Crm.Protocols.WSTrust.Bindings.ClientExceptionHelper::GetString(string value, object[] args)
0x157d  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1582  throw
0x1583  ldarg.0
0x1584  ldarg.1
0x1585  stfld    valuetype [System.ServiceModel]System.ServiceModel.HttpClientCredentialType Microsoft.Crm.Protocols.WSTrust.Bindings.UserNameWSTrustBinding::_clientCredentialType
0x158a  ret
```
