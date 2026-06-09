# Microsoft.Crm.Partner.PartnerSolutionService::Create

- ea: `0x3a90`
- end: `0x3b88`
- name: `Microsoft.Crm.Partner.PartnerSolutionService::Create`
- size: `248`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x31f0`
- `0x3210`
- `0x3230`
- `0x3250`
- `0x3270`
- `0x3290`
- `0x32b0`
- `0x3610`
- `0x39f0`
- `0x3a90`

## string_xrefs

- `0x3b65`: `Create`
- `0x3aec`: `DeploymentXml`
- `0x3b6a`: `D:\a\1\s\src\CrmLive\Admin\Partner\PartnerSolutionService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x3a90  newobj   instance void Microsoft.Crm.Partner.PartnerService::.ctor()
0x3a95  ldarg.1
0x3a96  callvirt instance string Microsoft.Crm.Partner.PartnerSolutionInfo::get_PartnerName()
0x3a9b  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Partner.PartnerService::GetIdFromName(string name)
0x3aa0  stloc.0
0x3aa1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x3aa6  stloc.1
0x3aa7  ldloc.1
0x3aa8  ldstr    aName// "Name"
0x3aad  ldarg.1
0x3aae  callvirt instance string Microsoft.Crm.Partner.PartnerSolutionInfo::get_SolutionName()
0x3ab3  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x3ab8  ldloc.1
0x3ab9  ldstr    aPartnerid// "PartnerId"
0x3abe  ldloc.0
0x3abf  box      [mscorlib]System.Guid
0x3ac4  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x3ac9  ldloc.1
0x3aca  ldstr    aDescription// "Description"
0x3acf  ldarg.1
0x3ad0  callvirt instance string Microsoft.Crm.Partner.PartnerSolutionInfo::get_Description()
0x3ad5  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x3ada  ldloc.1
0x3adb  ldstr    aApplicationred// "ApplicationRedirectUrl"
0x3ae0  ldarg.1
0x3ae1  callvirt instance string Microsoft.Crm.Partner.PartnerSolutionInfo::get_ApplicationRedirectUrl()
0x3ae6  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x3aeb  ldloc.1
0x3aec  ldstr    aDeploymentxml// "DeploymentXml"
0x3af1  ldarg.1
0x3af2  callvirt instance class Microsoft.Crm.Partner.PartnerSolutionDeploymentConfig Microsoft.Crm.Partner.PartnerSolutionInfo::get_DeploymentConfig()
0x3af7  call     T0x2B00000A
0x3afc  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x3b01  ldloc.1
0x3b02  ldstr    aLocalizeddata// "LocalizedData"
0x3b07  ldarg.1
0x3b08  callvirt instance class Microsoft.Crm.Partner.PartnerSolutionLocalizedData Microsoft.Crm.Partner.PartnerSolutionInfo::get_LocalizedData()
0x3b0d  call     T0x2B00000B
0x3b12  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x3b17  ldarg.1
0x3b18  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Partner.PartnerSolutionInfo::get_Id()
0x3b1d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3b22  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3b27  brfalse.s loc_3B41
0x3b29  ldloc.1
0x3b2a  ldstr    aId// "Id"
0x3b2f  ldarg.1
0x3b30  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Partner.PartnerSolutionInfo::get_Id()
0x3b35  box      [mscorlib]System.Guid
0x3b3a  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x3b3f  br.s     loc_3B56
0x3b41  ldloc.1
0x3b42  ldstr    aId// "Id"
0x3b47  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x3b4c  box      [mscorlib]System.Guid
0x3b51  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x3b56  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x3b5b  stloc.2
0x3b5c  ldloc.2
0x3b5d  ldstr    aPartnersolutio_2// "PartnerSolution"
0x3b62  ldloc.1
0x3b63  ldc.i4.s 0x75
0x3b65  ldstr    aCreate// "Create"
0x3b6a  ldstr    aDA1SSrcCrmlive_5// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Partn"...
0x3b6f  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x3b74  unbox.any [mscorlib]System.Guid
0x3b79  stloc.3
0x3b7a  leave.s  loc_3B86
0x3b7c  ldloc.2
0x3b7d  brfalse.s loc_3B85
0x3b7f  ldloc.2
0x3b80  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3b85  endfinally
0x3b86  ldloc.3
0x3b87  ret
```
