# Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::InstallSampleBusinessProcesses

- ea: `0x4cb0`
- end: `0x4cfd`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::InstallSampleBusinessProcesses`
- size: `77`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x4cb0`
- `0x4d00`

## string_xrefs

- `0x4cd7`: `Error while installing sample business processes`

## pseudocode

```c

```

## disassembly

```asm
0x4cb0  ldarg.0
0x4cb1  call     instance unsigned int8[] Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::GetSolutionFileBuffer()
0x4cb6  ldc.i4.1
0x4cb7  ldc.i4.0
0x4cb8  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x4cbd  ldc.i4.1
0x4cbe  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4cc3  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::ImportSolution(unsigned int8[], bool, bool, valuetype [mscorlib]System.Guid, bool, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4cc8  leave.s  loc_4CFC
0x4cca  stloc.0
0x4ccb  ldloc.0
0x4ccc  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x4cd1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0x4cd6  ldc.i4.0
0x4cd7  ldstr    aErrorWhileInst// "Error while installing sample business "...
0x4cdc  ldc.i4.2
0x4cdd  newarr   [mscorlib]System.Object
0x4ce2  dup
0x4ce3  ldc.i4.0
0x4ce4  ldloc.0
0x4ce5  callvirt instance string [mscorlib]System.Exception::get_Message()
0x4cea  stelem.ref
0x4ceb  dup
0x4cec  ldc.i4.1
0x4ced  ldloc.0
0x4cee  stelem.ref
0x4cef  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4cf4  ldarg.0
0x4cf5  ldloc.0
0x4cf6  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x4cfb  throw
0x4cfc  ret
```
