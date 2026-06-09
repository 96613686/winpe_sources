# Microsoft.Crm.Sdk.Messages.Internal.GetTrackingServiceBaseUrlResponse::get_TrackingServiceBaseUrl

- ea: `0x7090`
- end: `0x70ba`
- name: `Microsoft.Crm.Sdk.Messages.Internal.GetTrackingServiceBaseUrlResponse::get_TrackingServiceBaseUrl`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x7090`

## string_xrefs

- `0x7096`: `TrackingServiceBaseUrl`
- `0x70a8`: `TrackingServiceBaseUrl`

## pseudocode

```c

```

## disassembly

```asm
0x7090  ldarg.0
0x7091  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x7096  ldstr    aTrackingservic_0// "TrackingServiceBaseUrl"
0x709b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x70a0  brfalse.s loc_70B8
0x70a2  ldarg.0
0x70a3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x70a8  ldstr    aTrackingservic_0// "TrackingServiceBaseUrl"
0x70ad  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x70b2  castclass [mscorlib]System.String
0x70b7  ret
0x70b8  ldnull
0x70b9  ret
```
