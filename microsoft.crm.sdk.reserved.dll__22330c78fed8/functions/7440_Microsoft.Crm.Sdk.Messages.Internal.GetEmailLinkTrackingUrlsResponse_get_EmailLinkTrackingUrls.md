# Microsoft.Crm.Sdk.Messages.Internal.GetEmailLinkTrackingUrlsResponse::get_EmailLinkTrackingUrls

- ea: `0x7440`
- end: `0x746a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.GetEmailLinkTrackingUrlsResponse::get_EmailLinkTrackingUrls`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x7440`

## string_xrefs

- `0x7446`: `EmailLinkTrackingUrls`
- `0x7458`: `EmailLinkTrackingUrls`

## pseudocode

```c

```

## disassembly

```asm
0x7440  ldarg.0
0x7441  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x7446  ldstr    aEmaillinktrack// "EmailLinkTrackingUrls"
0x744b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x7450  brfalse.s loc_7468
0x7452  ldarg.0
0x7453  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x7458  ldstr    aEmaillinktrack// "EmailLinkTrackingUrls"
0x745d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x7462  castclass string[]
0x7467  ret
0x7468  ldnull
0x7469  ret
```
