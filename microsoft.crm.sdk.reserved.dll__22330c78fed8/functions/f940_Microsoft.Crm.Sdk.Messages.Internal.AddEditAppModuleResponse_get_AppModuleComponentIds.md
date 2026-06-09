# Microsoft.Crm.Sdk.Messages.Internal.AddEditAppModuleResponse::get_AppModuleComponentIds

- ea: `0xf940`
- end: `0xf96a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.AddEditAppModuleResponse::get_AppModuleComponentIds`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xf940`

## string_xrefs

- `0xf946`: `AppModuleComponentIds`
- `0xf958`: `AppModuleComponentIds`

## pseudocode

```c

```

## disassembly

```asm
0xf940  ldarg.0
0xf941  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0xf946  ldstr    aAppmodulecompo_0// "AppModuleComponentIds"
0xf94b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0xf950  brfalse.s loc_F968
0xf952  ldarg.0
0xf953  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0xf958  ldstr    aAppmodulecompo_0// "AppModuleComponentIds"
0xf95d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xf962  castclass valuetype [mscorlib]System.Guid[]
0xf967  ret
0xf968  ldnull
0xf969  ret
```
