# Microsoft.Crm.Sdk.Messages.Internal.AddEditAppModuleRequest::get_AppModuleComponents

- ea: `0xf7b0`
- end: `0xf7da`
- name: `Microsoft.Crm.Sdk.Messages.Internal.AddEditAppModuleRequest::get_AppModuleComponents`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xf7b0`

## string_xrefs

- `0xf7b6`: `AppModuleComponents`
- `0xf7c8`: `AppModuleComponents`

## pseudocode

```c

```

## disassembly

```asm
0xf7b0  ldarg.0
0xf7b1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0xf7b6  ldstr    aAppmodulecompo// "AppModuleComponents"
0xf7bb  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0xf7c0  brfalse.s loc_F7D8
0xf7c2  ldarg.0
0xf7c3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0xf7c8  ldstr    aAppmodulecompo// "AppModuleComponents"
0xf7cd  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xf7d2  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection
0xf7d7  ret
0xf7d8  ldnull
0xf7d9  ret
```
