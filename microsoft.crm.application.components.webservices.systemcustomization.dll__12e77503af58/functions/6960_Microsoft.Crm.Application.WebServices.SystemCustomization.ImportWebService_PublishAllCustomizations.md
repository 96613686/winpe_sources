# Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::PublishAllCustomizations

- ea: `0x6960`
- end: `0x69a1`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::PublishAllCustomizations`
- size: `65`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x5d20`

## callees

- `0x6880`
- `0x6960`

## pseudocode

```c

```

## disassembly

```asm
0x6960  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6965  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.SystemCustomizationSecurity::CheckPublishPrivileges(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x696a  brfalse.s loc_6978
0x696c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6971  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.SystemCustomizationSecurity::CheckPublishCustomizationsPrivileges(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6976  brtrue.s loc_6989
0x6978  ldc.i4   0x80040277
0x697d  ldc.i4.0
0x697e  newarr   [mscorlib]System.Object
0x6983  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x6988  throw
0x6989  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x698e  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::PublishAllXml(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6993  leave.s  loc_69A0
0x6995  stloc.0
0x6996  ldarg.0
0x6997  ldarg.1
0x6998  ldloc.0
0x6999  call     instance void Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::UpdateMapXmlForPublishFailure(class [System.Xml]System.Xml.XmlDocument mapDoc, class [Microsoft.Crm.Core]Microsoft.Crm.CrmException ex)
0x699e  rethrow
0x69a0  ret
```
