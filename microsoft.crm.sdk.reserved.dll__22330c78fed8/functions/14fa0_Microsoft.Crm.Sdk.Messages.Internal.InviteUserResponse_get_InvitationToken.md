# Microsoft.Crm.Sdk.Messages.Internal.InviteUserResponse::get_InvitationToken

- ea: `0x14fa0`
- end: `0x14fca`
- name: `Microsoft.Crm.Sdk.Messages.Internal.InviteUserResponse::get_InvitationToken`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14fa0`

## string_xrefs

- `0x14fa6`: `InvitationToken`
- `0x14fb8`: `InvitationToken`

## pseudocode

```c

```

## disassembly

```asm
0x14fa0  ldarg.0
0x14fa1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x14fa6  ldstr    aInvitationtoke// "InvitationToken"
0x14fab  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x14fb0  brfalse.s loc_14FC8
0x14fb2  ldarg.0
0x14fb3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x14fb8  ldstr    aInvitationtoke// "InvitationToken"
0x14fbd  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x14fc2  castclass [mscorlib]System.String
0x14fc7  ret
0x14fc8  ldnull
0x14fc9  ret
```
