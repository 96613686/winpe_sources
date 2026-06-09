# Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::SubmitImportJob

- ea: `0x4ac0`
- end: `0x4b44`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::SubmitImportJob`
- size: `132`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x4ac0`
- `0x4b50`
- `0x4d90`
- `0x4df0`
- `0x4ea0`

## pseudocode

```c

```

## disassembly

```asm
0x4ac0  ldarg.1
0x4ac1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4ac6  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportWizardState::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4acb  stloc.0
0x4acc  ldloc.0
0x4acd  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportWizardState::MakeImportMapXmlConformToSchema()
0x4ad2  ldstr    aImportfile// "importfile"
0x4ad7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4adc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4ae1  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportFile::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x4ae6  stloc.1
0x4ae7  ldloc.0
0x4ae8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportWizardState::get_ImportMapId()
0x4aed  stloc.2
0x4aee  ldloc.0
0x4aef  ldarg.0
0x4af0  ldloc.0
0x4af1  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::CreateInProcessImportMap(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportWizardState wizardState)
0x4af6  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportWizardState::set_ImportMapId(valuetype [mscorlib]System.Guid)
0x4afb  ldarg.0
0x4afc  ldloc.2
0x4afd  ldloc.0
0x4afe  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportWizardState::get_ImportMapId()
0x4b03  call     instance void Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::CreateOwnermappings(valuetype [mscorlib]System.Guid baseImportMapId, valuetype [mscorlib]System.Guid newImportMapId)
0x4b08  ldarg.0
0x4b09  ldloc.0
0x4b0a  ldarg.1
0x4b0b  ldloc.1
0x4b0c  call     instance void Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::UpdateImportFiles(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportWizardState wizardState, string originalWizardDataXml, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportFile service)
0x4b11  ldloc.0
0x4b12  callvirt instance valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportWizardState::get_ImportType()
0x4b17  ldc.i4.4
0x4b18  bne.un.s loc_4B22
0x4b1a  ldarg.0
0x4b1b  ldloc.0
0x4b1c  ldloc.1
0x4b1d  call     instance void Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::RemapDocuments(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportWizardState wizardState, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportFile service)
0x4b22  ldloc.1
0x4b23  ldloc.0
0x4b24  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportWizardState::get_ImportId()
0x4b29  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportFile::SubmitImportJob(valuetype [mscorlib]System.Guid)
0x4b2e  ldloc.0
0x4b2f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportWizardState::get_ImportMapId()
0x4b34  stloc.3
0x4b35  leave.s  loc_4B42
0x4b37  stloc.s  4
0x4b39  ldarg.0
0x4b3a  ldloc.s  4
0x4b3c  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x4b41  throw
0x4b42  ldloc.3
0x4b43  ret
```
