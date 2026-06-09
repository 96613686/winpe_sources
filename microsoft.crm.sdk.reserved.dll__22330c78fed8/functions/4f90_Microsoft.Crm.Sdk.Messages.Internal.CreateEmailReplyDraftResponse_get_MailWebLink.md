# Microsoft.Crm.Sdk.Messages.Internal.CreateEmailReplyDraftResponse::get_MailWebLink

- ea: `0x4f90`
- end: `0x4fba`
- name: `Microsoft.Crm.Sdk.Messages.Internal.CreateEmailReplyDraftResponse::get_MailWebLink`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x4f90`

## string_xrefs

- `0x4f96`: `MailWebLink`
- `0x4fa8`: `MailWebLink`

## pseudocode

```c

```

## disassembly

```asm
0x4f90  ldarg.0
0x4f91  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x4f96  ldstr    aMailweblink// "MailWebLink"
0x4f9b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x4fa0  brfalse.s loc_4FB8
0x4fa2  ldarg.0
0x4fa3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x4fa8  ldstr    aMailweblink// "MailWebLink"
0x4fad  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x4fb2  castclass [mscorlib]System.String
0x4fb7  ret
0x4fb8  ldnull
0x4fb9  ret
```
