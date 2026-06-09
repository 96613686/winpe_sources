# Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::ProvisionLanguagesWithJob

- ea: `0xb310`
- end: `0xb3a0`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::ProvisionLanguagesWithJob`
- size: `144`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xb310`
- `0xb3a0`
- `0xb3c0`

## string_xrefs

- `0xb36d`: `<importexportxml></importexportxml>`

## pseudocode

```c

```

## disassembly

```asm
0xb310  ldnull
0xb311  stloc.0
0xb312  ldarg.1
0xb313  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb318  brtrue.s loc_B324
0xb31a  ldarg.1
0xb31b  ldloca.s 1
0xb31d  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0xb322  brtrue.s loc_B32F
0xb324  ldstr    aInvalidImportj// "Invalid importjob id."
0xb329  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0xb32e  throw
0xb32f  ldarg.2
0xb330  brtrue.s loc_B33D
0xb332  ldstr    aInvalidData// "Invalid data."
0xb337  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0xb33c  throw
0xb33d  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_LanguageSettings()
0xb342  ldc.i4.3
0xb343  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb348  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb34d  brtrue.s loc_B360
0xb34f  ldc.i4   0x80040277
0xb354  ldc.i4.0
0xb355  newarr   [mscorlib]System.Object
0xb35a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0xb35f  throw
0xb360  newobj   instance void [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.ImportJobWebService::.ctor()
0xb365  stloc.2
0xb366  ldloc.2
0xb367  ldloc.1
0xb368  ldstr    aProvisionlangu// "ProvisionLanguages"
0xb36d  ldstr    aImportexportxm_0// "<importexportxml></importexportxml>"
0xb372  callvirt instance void [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.ImportJobWebService::CreateJob(valuetype [mscorlib]System.Guid, string, string)
0xb377  ldarg.0
0xb378  ldarg.2
0xb379  call     instance void Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::ProvisionLanguages(class [System.Xml]System.Xml.XmlNode data)
0xb37e  leave.s  loc_B39F
0xb380  stloc.3
0xb381  ldloc.3
0xb382  stloc.0
0xb383  ldarg.0
0xb384  ldloc.3
0xb385  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0xb38a  throw
0xb38b  ldarg.0
0xb38c  ldloc.1
0xb38d  ldloc.0
0xb38e  ldloc.2
0xb38f  call     instance void Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::UpdateImportJob(valuetype [mscorlib]System.Guid importJobId, class [mscorlib]System.Exception ex, class [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.ImportJobWebService importJobService)
0xb394  endfinally
0xb395  ldloc.2
0xb396  brfalse.s loc_B39E
0xb398  ldloc.2
0xb399  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb39e  endfinally
0xb39f  ret
```
