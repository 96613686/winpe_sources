# Microsoft.Crm.Sdk.Messages.Internal.PublishKnowledgeArticleRequest::get_CopyRelatedProductFromAssociatedPrimary

- ea: `0x2540`
- end: `0x256a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.PublishKnowledgeArticleRequest::get_CopyRelatedProductFromAssociatedPrimary`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x2540`

## string_xrefs

- `0x2546`: `CopyRelatedProductFromAssociatedPrimary`
- `0x2558`: `CopyRelatedProductFromAssociatedPrimary`

## pseudocode

```c

```

## disassembly

```asm
0x2540  ldarg.0
0x2541  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x2546  ldstr    aCopyrelatedpro// "CopyRelatedProductFromAssociatedPrimary"
0x254b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x2550  brfalse.s loc_2568
0x2552  ldarg.0
0x2553  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x2558  ldstr    aCopyrelatedpro// "CopyRelatedProductFromAssociatedPrimary"
0x255d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x2562  unbox.any [mscorlib]System.Boolean
0x2567  ret
0x2568  ldc.i4.0
0x2569  ret
```
