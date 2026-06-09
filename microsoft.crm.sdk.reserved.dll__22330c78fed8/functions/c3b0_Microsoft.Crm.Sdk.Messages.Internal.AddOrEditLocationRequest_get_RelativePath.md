# Microsoft.Crm.Sdk.Messages.Internal.AddOrEditLocationRequest::get_RelativePath

- ea: `0xc3b0`
- end: `0xc3da`
- name: `Microsoft.Crm.Sdk.Messages.Internal.AddOrEditLocationRequest::get_RelativePath`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xc3b0`

## string_xrefs

- `0xc3b6`: `RelativePath`
- `0xc3c8`: `RelativePath`

## pseudocode

```c

```

## disassembly

```asm
0xc3b0  ldarg.0
0xc3b1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0xc3b6  ldstr    aRelativepath// "RelativePath"
0xc3bb  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0xc3c0  brfalse.s loc_C3D8
0xc3c2  ldarg.0
0xc3c3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0xc3c8  ldstr    aRelativepath// "RelativePath"
0xc3cd  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xc3d2  castclass [mscorlib]System.String
0xc3d7  ret
0xc3d8  ldnull
0xc3d9  ret
```
