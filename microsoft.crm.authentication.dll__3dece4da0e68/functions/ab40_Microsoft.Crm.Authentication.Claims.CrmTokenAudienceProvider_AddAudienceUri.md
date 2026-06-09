# Microsoft.Crm.Authentication.Claims.CrmTokenAudienceProvider::AddAudienceUri

- ea: `0xab40`
- end: `0xab51`
- name: `Microsoft.Crm.Authentication.Claims.CrmTokenAudienceProvider::AddAudienceUri`
- size: `17`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xa9b0`
- `0xaa50`
- `0xaaa0`

## callees

- `0xab40`

## pseudocode

```c

```

## disassembly

```asm
0xab40  ldarg.0
0xab41  ldarg.1
0xab42  callvirt instance bool class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System]System.Uri>::Contains(var<u1>)
0xab47  brtrue.s loc_AB50
0xab49  ldarg.0
0xab4a  ldarg.1
0xab4b  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System]System.Uri>::Add(var<u1>)
0xab50  ret
```
