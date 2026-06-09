# Microsoft.Crm.Sdk.Messages.Internal.CreateMiniCampaignRequest::get_TemplateId

- ea: `0x159d0`
- end: `0x15a02`
- name: `Microsoft.Crm.Sdk.Messages.Internal.CreateMiniCampaignRequest::get_TemplateId`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x159d0`

## string_xrefs

- `0x159d6`: `TemplateId`
- `0x159e8`: `TemplateId`

## pseudocode

```c

```

## disassembly

```asm
0x159d0  ldarg.0
0x159d1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x159d6  ldstr    aTemplateid// "TemplateId"
0x159db  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x159e0  brfalse.s loc_159F8
0x159e2  ldarg.0
0x159e3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x159e8  ldstr    aTemplateid// "TemplateId"
0x159ed  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x159f2  unbox.any [mscorlib]System.Guid
0x159f7  ret
0x159f8  ldloca.s 0
0x159fa  initobj  [mscorlib]System.Guid
0x15a00  ldloc.0
0x15a01  ret
```
