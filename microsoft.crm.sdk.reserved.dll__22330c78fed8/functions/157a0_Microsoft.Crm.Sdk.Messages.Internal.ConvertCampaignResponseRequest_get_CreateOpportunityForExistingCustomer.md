# Microsoft.Crm.Sdk.Messages.Internal.ConvertCampaignResponseRequest::get_CreateOpportunityForExistingCustomer

- ea: `0x157a0`
- end: `0x157ca`
- name: `Microsoft.Crm.Sdk.Messages.Internal.ConvertCampaignResponseRequest::get_CreateOpportunityForExistingCustomer`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x157a0`

## string_xrefs

- `0x157a6`: `CreateOpportunityForExistingCustomer`
- `0x157b8`: `CreateOpportunityForExistingCustomer`

## pseudocode

```c

```

## disassembly

```asm
0x157a0  ldarg.0
0x157a1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x157a6  ldstr    aCreateopportun// "CreateOpportunityForExistingCustomer"
0x157ab  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x157b0  brfalse.s loc_157C8
0x157b2  ldarg.0
0x157b3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x157b8  ldstr    aCreateopportun// "CreateOpportunityForExistingCustomer"
0x157bd  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x157c2  unbox.any [mscorlib]System.Boolean
0x157c7  ret
0x157c8  ldc.i4.0
0x157c9  ret
```
