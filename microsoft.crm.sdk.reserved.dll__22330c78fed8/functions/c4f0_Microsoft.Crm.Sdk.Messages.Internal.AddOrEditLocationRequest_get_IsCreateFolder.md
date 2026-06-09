# Microsoft.Crm.Sdk.Messages.Internal.AddOrEditLocationRequest::get_IsCreateFolder

- ea: `0xc4f0`
- end: `0xc51a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.AddOrEditLocationRequest::get_IsCreateFolder`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xc4f0`

## string_xrefs

- `0xc4f6`: `IsCreateFolder`
- `0xc508`: `IsCreateFolder`

## pseudocode

```c

```

## disassembly

```asm
0xc4f0  ldarg.0
0xc4f1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0xc4f6  ldstr    aIscreatefolder// "IsCreateFolder"
0xc4fb  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0xc500  brfalse.s loc_C518
0xc502  ldarg.0
0xc503  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0xc508  ldstr    aIscreatefolder// "IsCreateFolder"
0xc50d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xc512  unbox.any [mscorlib]System.Boolean
0xc517  ret
0xc518  ldc.i4.0
0xc519  ret
```
