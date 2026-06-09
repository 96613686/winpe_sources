# Microsoft.Crm.Sdk.Messages.Internal.GetEmailLinkTrackingUrlsRequest::get_EmailLinkUrls

- ea: `0x7390`
- end: `0x73ba`
- name: `Microsoft.Crm.Sdk.Messages.Internal.GetEmailLinkTrackingUrlsRequest::get_EmailLinkUrls`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x7390`

## string_xrefs

- `0x7396`: `EmailLinkUrls`
- `0x73a8`: `EmailLinkUrls`

## pseudocode

```c

```

## disassembly

```asm
0x7390  ldarg.0
0x7391  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x7396  ldstr    aEmaillinkurls// "EmailLinkUrls"
0x739b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x73a0  brfalse.s loc_73B8
0x73a2  ldarg.0
0x73a3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x73a8  ldstr    aEmaillinkurls// "EmailLinkUrls"
0x73ad  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x73b2  castclass string[]
0x73b7  ret
0x73b8  ldnull
0x73b9  ret
```
