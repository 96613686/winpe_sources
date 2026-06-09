# Microsoft.Crm.Sdk.Messages.Internal.NavigateToNextEntityRequest::get_NewTraversedPath

- ea: `0xeff0`
- end: `0xf01a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.NavigateToNextEntityRequest::get_NewTraversedPath`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xeff0`

## string_xrefs

- `0xeff6`: `NewTraversedPath`
- `0xf008`: `NewTraversedPath`

## pseudocode

```c

```

## disassembly

```asm
0xeff0  ldarg.0
0xeff1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0xeff6  ldstr    aNewtraversedpa// "NewTraversedPath"
0xeffb  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0xf000  brfalse.s loc_F018
0xf002  ldarg.0
0xf003  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0xf008  ldstr    aNewtraversedpa// "NewTraversedPath"
0xf00d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xf012  castclass [mscorlib]System.String
0xf017  ret
0xf018  ldnull
0xf019  ret
```
