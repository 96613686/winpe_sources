# Microsoft.Crm.Sdk.Messages.Internal.PublishKnowledgeArticleRequest::get_CopyRelatedCategoryFromAssociatedPrimary

- ea: `0x2590`
- end: `0x25ba`
- name: `Microsoft.Crm.Sdk.Messages.Internal.PublishKnowledgeArticleRequest::get_CopyRelatedCategoryFromAssociatedPrimary`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x2590`

## string_xrefs

- `0x2596`: `CopyRelatedCategoryFromAssociatedPrimary`
- `0x25a8`: `CopyRelatedCategoryFromAssociatedPrimary`

## pseudocode

```c

```

## disassembly

```asm
0x2590  ldarg.0
0x2591  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x2596  ldstr    aCopyrelatedcat// "CopyRelatedCategoryFromAssociatedPrimar"...
0x259b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x25a0  brfalse.s loc_25B8
0x25a2  ldarg.0
0x25a3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x25a8  ldstr    aCopyrelatedcat// "CopyRelatedCategoryFromAssociatedPrimar"...
0x25ad  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x25b2  unbox.any [mscorlib]System.Boolean
0x25b7  ret
0x25b8  ldc.i4.0
0x25b9  ret
```
