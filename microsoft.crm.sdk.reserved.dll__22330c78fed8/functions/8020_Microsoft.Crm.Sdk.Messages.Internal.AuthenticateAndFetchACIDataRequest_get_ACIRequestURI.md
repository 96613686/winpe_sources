# Microsoft.Crm.Sdk.Messages.Internal.AuthenticateAndFetchACIDataRequest::get_ACIRequestURI

- ea: `0x8020`
- end: `0x804a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.AuthenticateAndFetchACIDataRequest::get_ACIRequestURI`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x8020`

## string_xrefs

- `0x8026`: `ACIRequestURI`
- `0x8038`: `ACIRequestURI`

## pseudocode

```c

```

## disassembly

```asm
0x8020  ldarg.0
0x8021  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x8026  ldstr    aAcirequesturi// "ACIRequestURI"
0x802b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x8030  brfalse.s loc_8048
0x8032  ldarg.0
0x8033  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x8038  ldstr    aAcirequesturi// "ACIRequestURI"
0x803d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x8042  castclass [mscorlib]System.String
0x8047  ret
0x8048  ldnull
0x8049  ret
```
