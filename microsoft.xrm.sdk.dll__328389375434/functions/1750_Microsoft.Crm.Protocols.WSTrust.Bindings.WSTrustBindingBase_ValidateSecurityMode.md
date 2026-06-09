# Microsoft.Crm.Protocols.WSTrust.Bindings.WSTrustBindingBase::ValidateSecurityMode

- ea: `0x1750`
- end: `0x1784`
- name: `Microsoft.Crm.Protocols.WSTrust.Bindings.WSTrustBindingBase::ValidateSecurityMode`
- size: `52`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x15b0`
- `0x1800`

## callees

- `0x1750`
- `0x1850`

## string_xrefs

- `0x175f`: `securityMode`
- `0x176d`: `ID3224: SecurityMode cannot be SecurityMode.None.`

## pseudocode

```c

```

## disassembly

```asm
0x1750  ldarg.0
0x1751  brfalse.s loc_176A
0x1753  ldarg.0
0x1754  ldc.i4.2
0x1755  beq.s    loc_176A
0x1757  ldarg.0
0x1758  ldc.i4.1
0x1759  beq.s    loc_176A
0x175b  ldarg.0
0x175c  ldc.i4.3
0x175d  beq.s    loc_176A
0x175f  ldstr    aSecuritymode// "securityMode"
0x1764  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x1769  throw
0x176a  ldarg.0
0x176b  brtrue.s loc_1783
0x176d  ldstr    aId3224Security// "ID3224: SecurityMode cannot be Security"...
0x1772  ldc.i4.0
0x1773  newarr   [mscorlib]System.Object
0x1778  call     string Microsoft.Crm.Protocols.WSTrust.Bindings.ClientExceptionHelper::GetString(string value, object[] args)
0x177d  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1782  throw
0x1783  ret
```
