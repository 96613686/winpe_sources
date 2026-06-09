# Microsoft.Crm.Sdk.Messages.Internal.AddEditAppModuleRequest::get_RetainAppModuleComponents

- ea: `0xf8a0`
- end: `0xf8ca`
- name: `Microsoft.Crm.Sdk.Messages.Internal.AddEditAppModuleRequest::get_RetainAppModuleComponents`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xf8a0`

## string_xrefs

- `0xf8a6`: `RetainAppModuleComponents`
- `0xf8b8`: `RetainAppModuleComponents`

## pseudocode

```c

```

## disassembly

```asm
0xf8a0  ldarg.0
0xf8a1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0xf8a6  ldstr    aRetainappmodul// "RetainAppModuleComponents"
0xf8ab  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0xf8b0  brfalse.s loc_F8C8
0xf8b2  ldarg.0
0xf8b3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0xf8b8  ldstr    aRetainappmodul// "RetainAppModuleComponents"
0xf8bd  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xf8c2  unbox.any [mscorlib]System.Boolean
0xf8c7  ret
0xf8c8  ldc.i4.0
0xf8c9  ret
```
