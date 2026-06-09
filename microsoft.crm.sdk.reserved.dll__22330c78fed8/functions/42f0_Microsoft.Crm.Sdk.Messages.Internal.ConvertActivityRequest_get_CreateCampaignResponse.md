# Microsoft.Crm.Sdk.Messages.Internal.ConvertActivityRequest::get_CreateCampaignResponse

- ea: `0x42f0`
- end: `0x431a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.ConvertActivityRequest::get_CreateCampaignResponse`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x42f0`

## string_xrefs

- `0x42f6`: `CreateCampaignResponse`
- `0x4308`: `CreateCampaignResponse`

## pseudocode

```c

```

## disassembly

```asm
0x42f0  ldarg.0
0x42f1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x42f6  ldstr    aCreatecampaign// "CreateCampaignResponse"
0x42fb  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x4300  brfalse.s loc_4318
0x4302  ldarg.0
0x4303  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x4308  ldstr    aCreatecampaign// "CreateCampaignResponse"
0x430d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x4312  unbox.any [mscorlib]System.Boolean
0x4317  ret
0x4318  ldc.i4.0
0x4319  ret
```
