# Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl

- ea: `0x142c0`
- end: `0x14302`
- name: `Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl`
- size: `66`
- prototype: ``
- caller_count: `22`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x3ae0`
- `0x7b90`
- `0x90b0`
- `0x9480`
- `0x97b0`
- `0xcf10`
- `0xf7b0`
- `0x101a0`
- `0x10990`
- `0x11d80`
- `0x133a0`
- `0x140d0`
- `0x14310`
- `0x143b0`
- `0x16260`
- `0x1c230`
- `0x1df00`
- `0x1fdf0`
- `0x227b0`
- `0x23440`
- `0x24a50`
- `0x24eb0`

## callees

- `0x14200`
- `0x14290`
- `0x142c0`

## string_xrefs

- `0x142e4`: `Error occured while computing the status of CDN feature: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x142c0  call     bool Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::ShouldUseCDN()
0x142c5  brtrue.s loc_142CF
0x142c7  ldsfld   string [mscorlib]System.String::Empty
0x142cc  stloc.0
0x142cd  leave.s  loc_14300
0x142cf  call     string Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::BuildCDNUrl()
0x142d4  stloc.0
0x142d5  leave.s  loc_14300
0x142d7  stloc.1
0x142d8  ldloc.1
0x142d9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x142de  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x142e3  ldc.i4.6
0x142e4  ldstr    aErrorOccuredWh// "Error occured while computing the statu"...
0x142e9  ldc.i4.1
0x142ea  newarr   [mscorlib]System.Object
0x142ef  dup
0x142f0  ldc.i4.0
0x142f1  ldloc.1
0x142f2  stelem.ref
0x142f3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x142f8  ldsfld   string [mscorlib]System.String::Empty
0x142fd  stloc.0
0x142fe  leave.s  loc_14300
0x14300  ldloc.0
0x14301  ret
```
