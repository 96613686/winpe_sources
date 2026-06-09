# Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::PublishCustomizations

- ea: `0x6900`
- end: `0x6957`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::PublishCustomizations`
- size: `87`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x57e0`

## callees

- `0x6880`
- `0x6900`
- `0x69b0`

## pseudocode

```c

```

## disassembly

```asm
0x6900  ldarg.1
0x6901  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x6906  brtrue.s loc_6909
0x6908  ret
0x6909  nop
0x690a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x690f  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.SystemCustomizationSecurity::CheckPublishPrivileges(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6914  brfalse.s loc_6922
0x6916  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x691b  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.SystemCustomizationSecurity::CheckPublishCustomizationsPrivileges(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6920  brtrue.s loc_6933
0x6922  ldc.i4   0x80040277
0x6927  ldc.i4.0
0x6928  newarr   [mscorlib]System.Object
0x692d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x6932  throw
0x6933  ldarg.0
0x6934  ldarg.1
0x6935  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::CreatePublishXml(class [mscorlib]System.Collections.Generic.List`1<string> entitiesToPublish)
0x693a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x693f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6944  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::PublishXml(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6949  leave.s  loc_6956
0x694b  stloc.0
0x694c  ldarg.0
0x694d  ldarg.2
0x694e  ldloc.0
0x694f  call     instance void Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::UpdateMapXmlForPublishFailure(class [System.Xml]System.Xml.XmlDocument mapDoc, class [Microsoft.Crm.Core]Microsoft.Crm.CrmException ex)
0x6954  rethrow
0x6956  ret
```
