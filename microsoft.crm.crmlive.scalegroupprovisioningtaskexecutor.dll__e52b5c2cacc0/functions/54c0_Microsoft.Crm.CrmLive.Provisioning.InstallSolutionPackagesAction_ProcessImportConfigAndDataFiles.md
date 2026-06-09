# Microsoft.Crm.CrmLive.Provisioning.InstallSolutionPackagesAction::ProcessImportConfigAndDataFiles

- ea: `0x54c0`
- end: `0x5592`
- name: `Microsoft.Crm.CrmLive.Provisioning.InstallSolutionPackagesAction::ProcessImportConfigAndDataFiles`
- size: `210`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x51e0`

## callees

- `0x4f00`
- `0x4f40`
- `0x54c0`
- `0x64b0`
- `0x91b0`
- `0x151e0`
- `0x15ad0`
- `0x15bd0`

## string_xrefs

- `0x54d0`: `ImportConfig.xml`
- `0x54f7`: `Could not find ImportConfig.xml under a subdirectory in : `

## pseudocode

```c

```

## disassembly

```asm
0x54c0  ldnull
0x54c1  stloc.0
0x54c2  ldarg.1
0x54c3  call     string[] [mscorlib]System.IO.Directory::GetDirectories(string)
0x54c8  stloc.2
0x54c9  ldc.i4.0
0x54ca  stloc.3
0x54cb  br.s     loc_54EE
0x54cd  ldloc.2
0x54ce  ldloc.3
0x54cf  ldelem.ref
0x54d0  ldstr    aImportconfigXm// "ImportConfig.xml"
0x54d5  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x54da  stloc.s  4
0x54dc  ldloc.s  4
0x54de  call     bool [mscorlib]System.IO.File::Exists(string)
0x54e3  brfalse.s loc_54EA
0x54e5  ldloc.s  4
0x54e7  stloc.0
0x54e8  br.s     loc_54F4
0x54ea  ldloc.3
0x54eb  ldc.i4.1
0x54ec  add
0x54ed  stloc.3
0x54ee  ldloc.3
0x54ef  ldloc.2
0x54f0  ldlen
0x54f1  conv.i4
0x54f2  blt.s    loc_54CD
0x54f4  ldloc.0
0x54f5  brtrue.s loc_5508
0x54f7  ldstr    aCouldNotFindIm// "Could not find ImportConfig.xml under a"...
0x54fc  ldarg.1
0x54fd  call     string [mscorlib]System.String::Concat(string, string)
0x5502  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x5507  throw
0x5508  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x550d  stloc.1
0x550e  ldarg.2
0x550f  brfalse.s loc_5567
0x5511  ldarg.0
0x5512  call     instance bool Microsoft.Crm.CrmLive.Provisioning.InstallSolutionPackagesAction::get_SkipDemoUserCreation()
0x5517  brtrue.s loc_5567
0x5519  ldloc.0
0x551a  call     string[] Microsoft.Crm.CrmLive.Provisioning.SolutionPackageFixer::GetUsers(string importConfigXml)
0x551f  stloc.2
0x5520  ldc.i4.0
0x5521  stloc.3
0x5522  br.s     loc_555F
0x5524  ldloc.2
0x5525  ldloc.3
0x5526  ldelem.ref
0x5527  stloc.s  5
0x5529  ldloc.s  5
0x552b  call     bool [Microsoft.Crm]Microsoft.Crm.Data.DemoUserManager::IsDemoUserUpn(string)
0x5530  brfalse.s loc_555B
0x5532  ldarg.0
0x5533  ldstr    aCreatingDemous// "Creating DemoUser : "
0x5538  ldloc.s  5
0x553a  call     string [mscorlib]System.String::Concat(string, string)
0x553f  call     instance void Microsoft.Crm.CrmLive.Provisioning.InstallSolutionPackagesAction::Log(string log)
0x5544  ldarg.0
0x5545  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x554a  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x554f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x5554  ldloc.s  5
0x5556  call     void Microsoft.Crm.CrmLive.Provisioning.ProvisioningDemoUserManager::CreateDemoUser(valuetype [mscorlib]System.Guid orgId, string upn)
0x555b  ldloc.3
0x555c  ldc.i4.1
0x555d  add
0x555e  stloc.3
0x555f  ldloc.3
0x5560  ldloc.2
0x5561  ldlen
0x5562  conv.i4
0x5563  blt.s    loc_5524
0x5565  br.s     loc_557E
0x5567  ldarg.2
0x5568  brfalse.s loc_557E
0x556a  ldarg.0
0x556b  call     instance bool Microsoft.Crm.CrmLive.Provisioning.InstallSolutionPackagesAction::get_SkipDemoUserCreation()
0x5570  brfalse.s loc_557E
0x5572  ldloc.1
0x5573  ldstr    asc_37DAC// "*"
0x5578  ldarg.3
0x5579  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x557e  ldloc.0
0x557f  ldloc.1
0x5580  ldarg.0
0x5581  ldftn    instance void Microsoft.Crm.CrmLive.Provisioning.InstallSolutionPackagesAction::Log(string log)
0x5587  newobj   instance void class [mscorlib]System.Action`1<string>::.ctor(object, native int)
0x558c  call     class Microsoft.Crm.CrmLive.Provisioning.SolutionPackageDataReport Microsoft.Crm.CrmLive.Provisioning.SolutionPackageFixer::ProcessDataAndMappingFiles(string importConfigXml, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> specificUpnMappingsToUse, class [mscorlib]System.Action`1<string> logger)
0x5591  ret
```
