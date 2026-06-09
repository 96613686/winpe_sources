# Microsoft.Crm.Common.Application.Components.PageHandlers.SchedulableActivityBasePageHandler::ConfigureHeaderHandler

- ea: `0x11b90`
- end: `0x11bff`
- name: `Microsoft.Crm.Common.Application.Components.PageHandlers.SchedulableActivityBasePageHandler::ConfigureHeaderHandler`
- size: `111`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x10cd0`

## callees

- `0x11510`
- `0x11b00`
- `0x11b50`
- `0x11b60`

## pseudocode

```c

```

## disassembly

```asm
0x11b90  ldarg.0
0x11b91  call     instance void Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::ConfigureHeaderHandler()
0x11b96  ldarg.0
0x11b97  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0x11b9c  ldstr    aIactivitytypec// "_iActivityTypeCode"
0x11ba1  ldarg.0
0x11ba2  call     instance class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.ActivityBase Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::get_CurrentActivity()
0x11ba7  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x11bac  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0x11bb1  conv.i8
0x11bb2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x11bb7  ldarg.0
0x11bb8  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0x11bbd  ldstr    aBenableschedul// "_bEnableSchedulingDialog"
0x11bc2  ldarg.0
0x11bc3  call     instance bool Microsoft.Crm.Common.Application.Components.PageHandlers.SchedulableActivityBasePageHandler::get_EnableSchedulingDialog()
0x11bc8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x11bcd  ldarg.0
0x11bce  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0x11bd3  ldstr    aBallowschedule// "_bAllowSchedule"
0x11bd8  ldarg.0
0x11bd9  call     instance bool Microsoft.Crm.Common.Application.Components.PageHandlers.SchedulableActivityBasePageHandler::get_AllowSchedule()
0x11bde  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x11be3  ldc.i4   0x1068
0x11be8  call     class [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.EntityPageHeaders.IConfigHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.EntityPageHeaders.ConfigHeaderFactory::GetConfigHeader(int32)
0x11bed  ldarg.0
0x11bee  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0x11bf3  ldarg.0
0x11bf4  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0x11bf9  callvirt instance void [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.EntityPageHeaders.IConfigHeader::ConfigHeader(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity)
0x11bfe  ret
```
