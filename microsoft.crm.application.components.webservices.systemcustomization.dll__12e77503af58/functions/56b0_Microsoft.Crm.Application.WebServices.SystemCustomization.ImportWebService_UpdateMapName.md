# Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::UpdateMapName

- ea: `0x56b0`
- end: `0x574d`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::UpdateMapName`
- size: `157`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x56b0`

## pseudocode

```c

```

## disassembly

```asm
0x56b0  ldstr    aImportmap// "importmap"
0x56b5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x56ba  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x56bf  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x56c4  stloc.0
0x56c5  ldloc.0
0x56c6  ldstr    aImportmapid// "importmapid"
0x56cb  ldarg.2
0x56cc  box      [mscorlib]System.Guid
0x56d1  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x56d6  ldloc.0
0x56d7  ldstr    aName// "name"
0x56dc  ldarg.1
0x56dd  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x56e2  ldloc.0
0x56e3  ldstr    aImportmaptype// "importmaptype"
0x56e8  ldc.i4.1
0x56e9  box      [mscorlib]System.Int32
0x56ee  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x56f3  ldloc.0
0x56f4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x56f9  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Update(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x56fe  leave.s  loc_574C
0x5700  stloc.1
0x5701  ldloc.1
0x5702  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x5707  isinst   [Microsoft.Crm.Core]Microsoft.Crm.CrmException
0x570c  stloc.2
0x570d  ldloc.2
0x570e  brfalse.s loc_5744
0x5710  ldloc.2
0x5711  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x5716  ldc.i4   0x80048443
0x571b  bne.un.s loc_5744
0x571d  ldloc.0
0x571e  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Properties()
0x5723  ldstr    aName// "name"
0x5728  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::Remove(var<u1>)
0x572d  pop
0x572e  ldloc.0
0x572f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x5734  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Update(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5739  leave.s  loc_5744
0x573b  stloc.3
0x573c  ldarg.0
0x573d  ldloc.3
0x573e  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x5743  throw
0x5744  ldarg.0
0x5745  ldloc.1
0x5746  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x574b  throw
0x574c  ret
```
