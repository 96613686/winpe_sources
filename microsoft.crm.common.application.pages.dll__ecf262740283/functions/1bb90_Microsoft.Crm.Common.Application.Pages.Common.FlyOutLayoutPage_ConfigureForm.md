# Microsoft.Crm.Common.Application.Pages.Common.FlyOutLayoutPage::ConfigureForm

- ea: `0x1bb90`
- end: `0x1bbe7`
- name: `Microsoft.Crm.Common.Application.Pages.Common.FlyOutLayoutPage::ConfigureForm`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1bb90`

## string_xrefs

- `0x1bbdb`: `ReadForm does not support ActivityPointer or Resource.  You must send the underlying entity type instead.`

## pseudocode

```c

```

## disassembly

```asm
0x1bb90  ldarg.0
0x1bb91  ldarg.0
0x1bb92  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1bb97  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1bb9c  ldstr    aEtc// "etc"
0x1bba1  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1bba6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1bbab  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1bbb0  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::set_CurrentType(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x1bbb5  ldarg.0
0x1bbb6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentType()
0x1bbbb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x1bbc0  stloc.0
0x1bbc1  ldloc.0
0x1bbc2  ldstr    aActivitypointe// "activitypointer"
0x1bbc7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1bbcc  brtrue.s loc_1BBDB
0x1bbce  ldloc.0
0x1bbcf  ldstr    aResource// "resource"
0x1bbd4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1bbd9  brfalse.s loc_1BBE6
0x1bbdb  ldstr    aReadformDoesNo// "ReadForm does not support ActivityPoint"...
0x1bbe0  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1bbe5  throw
0x1bbe6  ret
```
