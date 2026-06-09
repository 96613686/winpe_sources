# Microsoft.Crm.ServiceBus.RouterClientManagerExternal::get_InvitationWebServiceUrl

- ea: `0x500`
- end: `0x562`
- name: `Microsoft.Crm.ServiceBus.RouterClientManagerExternal::get_InvitationWebServiceUrl`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x570`

## callees

- `0x500`

## string_xrefs

- `0x505`: `InvitationWebService`
- `0x51e`: `ExternalRouterService`
- `0x53a`: `Unable to find External router service URL setting.`

## pseudocode

```c

```

## disassembly

```asm
0x500  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x505  ldstr    aInvitationwebs// "InvitationWebService"
0x50a  ldc.i4.0
0x50b  callvirt T0x2B000001
0x510  stloc.0
0x511  ldloc.0
0x512  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x517  brfalse.s loc_55B
0x519  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x51e  ldstr    aExternalrouter// "ExternalRouterService"
0x523  ldc.i4.0
0x524  callvirt T0x2B000001
0x529  stloc.0
0x52a  ldloc.0
0x52b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x530  brfalse.s loc_55B
0x532  ldnull
0x533  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x538  ldc.i4.s 0x2F
0x53a  ldstr    aUnableToFindEx// "Unable to find External router service "...
0x53f  ldc.i4.0
0x540  newarr   [mscorlib]System.Object
0x545  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x54a  ldc.i4   0x8004D204
0x54f  ldc.i4.0
0x550  newarr   [mscorlib]System.Object
0x555  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x55a  throw
0x55b  ldloc.0
0x55c  newobj   instance void [System]System.Uri::.ctor(string)
0x561  ret
```
