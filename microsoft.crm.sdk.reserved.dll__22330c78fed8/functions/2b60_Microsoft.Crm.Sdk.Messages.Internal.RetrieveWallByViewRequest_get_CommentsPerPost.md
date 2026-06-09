# Microsoft.Crm.Sdk.Messages.Internal.RetrieveWallByViewRequest::get_CommentsPerPost

- ea: `0x2b60`
- end: `0x2b8a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.RetrieveWallByViewRequest::get_CommentsPerPost`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x2b60`

## string_xrefs

- `0x2b66`: `CommentsPerPost`
- `0x2b78`: `CommentsPerPost`

## pseudocode

```c

```

## disassembly

```asm
0x2b60  ldarg.0
0x2b61  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x2b66  ldstr    aCommentsperpos// "CommentsPerPost"
0x2b6b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x2b70  brfalse.s loc_2B88
0x2b72  ldarg.0
0x2b73  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x2b78  ldstr    aCommentsperpos// "CommentsPerPost"
0x2b7d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x2b82  unbox.any [mscorlib]System.Int32
0x2b87  ret
0x2b88  ldc.i4.0
0x2b89  ret
```
