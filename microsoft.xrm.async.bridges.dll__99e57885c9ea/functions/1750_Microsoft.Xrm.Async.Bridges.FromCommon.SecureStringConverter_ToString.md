# Microsoft.Xrm.Async.Bridges.FromCommon.SecureStringConverter::ToString

- ea: `0x1750`
- end: `0x1773`
- name: `Microsoft.Xrm.Async.Bridges.FromCommon.SecureStringConverter::ToString`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x1750  ldarg.1
0x1751  ldstr    aSecurestring// "secureString"
0x1756  call     T0x2B000026
0x175b  call     T0x2B000027
0x1760  pop
0x1761  newobj   instance void [System]System.Net.NetworkCredential::.ctor()
0x1766  dup
0x1767  ldarg.1
0x1768  callvirt instance void [System]System.Net.NetworkCredential::set_SecurePassword(class [mscorlib]System.Security.SecureString)
0x176d  callvirt instance string [System]System.Net.NetworkCredential::get_Password()
0x1772  ret
```
