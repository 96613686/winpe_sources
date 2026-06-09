# Microsoft.Crm.Sdk.Messages.Internal.CanUserSendEmailResponse::get_HasPrivileges

- ea: `0x33a0`
- end: `0x33ca`
- name: `Microsoft.Crm.Sdk.Messages.Internal.CanUserSendEmailResponse::get_HasPrivileges`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x33a0`

## string_xrefs

- `0x33a6`: `HasPrivileges`
- `0x33b8`: `HasPrivileges`

## pseudocode

```c

```

## disassembly

```asm
0x33a0  ldarg.0
0x33a1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x33a6  ldstr    aHasprivileges// "HasPrivileges"
0x33ab  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x33b0  brfalse.s loc_33C8
0x33b2  ldarg.0
0x33b3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x33b8  ldstr    aHasprivileges// "HasPrivileges"
0x33bd  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x33c2  unbox.any [mscorlib]System.Boolean
0x33c7  ret
0x33c8  ldc.i4.0
0x33c9  ret
```
