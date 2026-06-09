# Microsoft.Crm.Sdk.Messages.Internal.GetTrackingServiceDeploymentStatusResponse::get_TrackingServiceDeploymentStatus

- ea: `0x7010`
- end: `0x703a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.GetTrackingServiceDeploymentStatusResponse::get_TrackingServiceDeploymentStatus`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x7010`

## string_xrefs

- `0x7016`: `TrackingServiceDeploymentStatus`
- `0x7028`: `TrackingServiceDeploymentStatus`

## pseudocode

```c

```

## disassembly

```asm
0x7010  ldarg.0
0x7011  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x7016  ldstr    aTrackingservic// "TrackingServiceDeploymentStatus"
0x701b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x7020  brfalse.s loc_7038
0x7022  ldarg.0
0x7023  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x7028  ldstr    aTrackingservic// "TrackingServiceDeploymentStatus"
0x702d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x7032  castclass [mscorlib]System.String
0x7037  ret
0x7038  ldnull
0x7039  ret
```
