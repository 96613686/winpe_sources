# Microsoft.Crm.Sdk.Messages.Internal.RetrievePrivilegeMaxDepthFromTeamRolesResponse::get_RolePrivileges

- ea: `0x148f0`
- end: `0x1491a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.RetrievePrivilegeMaxDepthFromTeamRolesResponse::get_RolePrivileges`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x148f0`

## string_xrefs

- `0x148f6`: `RolePrivileges`
- `0x14908`: `RolePrivileges`

## pseudocode

```c

```

## disassembly

```asm
0x148f0  ldarg.0
0x148f1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x148f6  ldstr    aRoleprivileges// "RolePrivileges"
0x148fb  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x14900  brfalse.s loc_14918
0x14902  ldarg.0
0x14903  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x14908  ldstr    aRoleprivileges// "RolePrivileges"
0x1490d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x14912  castclass class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.RolePrivilege[]
0x14917  ret
0x14918  ldnull
0x14919  ret
```
