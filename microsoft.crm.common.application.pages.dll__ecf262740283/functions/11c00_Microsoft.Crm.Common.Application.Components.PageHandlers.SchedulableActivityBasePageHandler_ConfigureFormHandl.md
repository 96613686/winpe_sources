# Microsoft.Crm.Common.Application.Components.PageHandlers.SchedulableActivityBasePageHandler::ConfigureFormHandler

- ea: `0x11c00`
- end: `0x11c7b`
- name: `Microsoft.Crm.Common.Application.Components.PageHandlers.SchedulableActivityBasePageHandler::ConfigureFormHandler`
- size: `123`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x10d00`

## callees

- `0x11510`
- `0x11550`
- `0x11c00`
- `0x11c80`
- `0x11cd0`
- `0x11df0`

## pseudocode

```c

```

## disassembly

```asm
0x11c00  ldarg.0
0x11c01  call     instance class [System.Web]System.Web.HttpRequest [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_Request()
0x11c06  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x11c0b  ldstr    aMode// "mode"
0x11c10  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x11c15  ldstr    aReactivate// "reactivate"
0x11c1a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x11c1f  brfalse.s loc_11C62
0x11c21  ldloca.s 0
0x11c23  ldarg.0
0x11c24  call     instance class [System.Web]System.Web.HttpRequest [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_Request()
0x11c29  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x11c2e  ldstr    aId// "id"
0x11c33  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x11c38  call     instance void [mscorlib]System.Guid::.ctor(string)
0x11c3d  ldarg.0
0x11c3e  call     instance class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.ActivityBase Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::get_CurrentActivity()
0x11c43  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_EntityName()
0x11c48  ldloc.0
0x11c49  ldc.i4.0
0x11c4a  stloc.1
0x11c4b  ldloca.s 1
0x11c4d  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.ActivityPointerState
0x11c53  callvirt instance string [mscorlib]System.Object::ToString()
0x11c58  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x11c5d  call     void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.ActivityBase::SetState(string, valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x11c62  ldarg.0
0x11c63  call     instance void Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::ConfigureFormHandler()
0x11c68  ldarg.0
0x11c69  call     instance void Microsoft.Crm.Common.Application.Components.PageHandlers.SchedulableActivityBasePageHandler::SetIsAllDay()
0x11c6e  ldarg.0
0x11c6f  call     instance void Microsoft.Crm.Common.Application.Components.PageHandlers.SchedulableActivityBasePageHandler::RestrictStatusCodes()
0x11c74  ldarg.0
0x11c75  call     instance void Microsoft.Crm.Common.Application.Components.PageHandlers.SchedulableActivityBasePageHandler::PopulateTimesFromQueryString()
0x11c7a  ret
```
