# Microsoft.Crm.Protocols.WSTrust.Bindings.UserNameWSTrustBinding::.ctor_1

- ea: `0x1480`
- end: `0x14cd`
- name: `Microsoft.Crm.Protocols.WSTrust.Bindings.UserNameWSTrustBinding::.ctor_1`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1450`

## callees

- `0x1480`
- `0x1510`
- `0x15a0`
- `0x1850`

## string_xrefs

- `0x14a6`: `ID3225: UserNameWSTrustBinding in SecurityMode.Transport SecurityMode, clientCredentialType must be Digest or Basic. But actual value is '{0}'`

## pseudocode

```c

```

## disassembly

```asm
0x1480  ldarg.0
0x1481  ldarg.1
0x1482  call     instance void Microsoft.Crm.Protocols.WSTrust.Bindings.WSTrustBindingBase::.ctor(valuetype [System.ServiceModel]System.ServiceModel.SecurityMode securityMode)
0x1487  ldarg.2
0x1488  call     bool Microsoft.Crm.Protocols.WSTrust.Bindings.UserNameWSTrustBinding::IsHttpClientCredentialTypeDefined(valuetype [System.ServiceModel]System.ServiceModel.HttpClientCredentialType value)
0x148d  brtrue.s loc_149A
0x148f  ldstr    aClientcredenti// "clientCredentialType"
0x1494  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x1499  throw
0x149a  ldc.i4.1
0x149b  ldarg.1
0x149c  bne.un.s loc_14C5
0x149e  ldc.i4.2
0x149f  ldarg.2
0x14a0  beq.s    loc_14C5
0x14a2  ldc.i4.1
0x14a3  ldarg.2
0x14a4  beq.s    loc_14C5
0x14a6  ldstr    aId3225Username// "ID3225: UserNameWSTrustBinding in Secur"...
0x14ab  ldc.i4.1
0x14ac  newarr   [mscorlib]System.Object
0x14b1  dup
0x14b2  ldc.i4.0
0x14b3  ldarg.2
0x14b4  box      [System.ServiceModel]System.ServiceModel.HttpClientCredentialType
0x14b9  stelem.ref
0x14ba  call     string Microsoft.Crm.Protocols.WSTrust.Bindings.ClientExceptionHelper::GetString(string value, object[] args)
0x14bf  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x14c4  throw
0x14c5  ldarg.0
0x14c6  ldarg.2
0x14c7  stfld    valuetype [System.ServiceModel]System.ServiceModel.HttpClientCredentialType Microsoft.Crm.Protocols.WSTrust.Bindings.UserNameWSTrustBinding::_clientCredentialType
0x14cc  ret
```
