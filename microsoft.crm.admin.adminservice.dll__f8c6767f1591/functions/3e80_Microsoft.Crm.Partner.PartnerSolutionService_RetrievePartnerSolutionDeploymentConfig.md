# Microsoft.Crm.Partner.PartnerSolutionService::RetrievePartnerSolutionDeploymentConfig

- ea: `0x3e80`
- end: `0x3f98`
- name: `Microsoft.Crm.Partner.PartnerSolutionService::RetrievePartnerSolutionDeploymentConfig`
- size: `280`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x33f0`
- `0x3410`
- `0x3470`
- `0x3480`
- `0x3490`
- `0x34a0`
- `0x3510`
- `0x3520`
- `0x3d60`
- `0x3e80`
- `0x41e0`

## string_xrefs

- `0x3e92`: `DeploymentXml`
- `0x3ead`: `DeploymentXml`
- `0x3f7d`: `RetrievePartnerSolutionDeploymentConfig: partner solution with id {0} not found.`

## pseudocode

```c

```

## disassembly

```asm
0x3e80  ldarg.0
0x3e81  ldarg.1
0x3e82  ldc.i4.3
0x3e83  newarr   [mscorlib]System.String
0x3e88  dup
0x3e89  ldc.i4.0
0x3e8a  ldstr    aId// "Id"
0x3e8f  stelem.ref
0x3e90  dup
0x3e91  ldc.i4.1
0x3e92  ldstr    aDeploymentxml// "DeploymentXml"
0x3e97  stelem.ref
0x3e98  dup
0x3e99  ldc.i4.2
0x3e9a  ldstr    aLocalizeddata// "LocalizedData"
0x3e9f  stelem.ref
0x3ea0  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Partner.PartnerSolutionService::RetrieveById(valuetype [mscorlib]System.Guid partnerSolutionId, string[] columns)
0x3ea5  stloc.0
0x3ea6  ldloc.0
0x3ea7  brfalse  loc_3F76
0x3eac  ldloc.0
0x3ead  ldstr    aDeploymentxml// "DeploymentXml"
0x3eb2  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x3eb7  castclass [mscorlib]System.String
0x3ebc  call     T0x2B00000C
0x3ec1  stloc.1
0x3ec2  ldloc.0
0x3ec3  ldstr    aLocalizeddata// "LocalizedData"
0x3ec8  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x3ecd  castclass [mscorlib]System.String
0x3ed2  call     T0x2B00000D
0x3ed7  stloc.2
0x3ed8  ldloc.2
0x3ed9  brfalse  loc_3F74
0x3ede  ldarg.0
0x3edf  ldarg.2
0x3ee0  ldloc.2
0x3ee1  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Partner.PartnerSolutionService::GetLocalizedItemsForLanguage(int32 languageCode, class Microsoft.Crm.Partner.PartnerSolutionLocalizedData localizedData)
0x3ee6  stloc.3
0x3ee7  ldloc.3
0x3ee8  ldloc.1
0x3ee9  callvirt instance class Microsoft.Crm.Partner.PartnerSolutionDeploymentConfigCrmUser Microsoft.Crm.Partner.PartnerSolutionDeploymentConfig::get_CrmUser()
0x3eee  callvirt instance string Microsoft.Crm.Partner.PartnerSolutionDeploymentConfigCrmUser::get_FirstName()
0x3ef3  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x3ef8  brfalse.s loc_3F16
0x3efa  ldloc.1
0x3efb  callvirt instance class Microsoft.Crm.Partner.PartnerSolutionDeploymentConfigCrmUser Microsoft.Crm.Partner.PartnerSolutionDeploymentConfig::get_CrmUser()
0x3f00  ldloc.3
0x3f01  ldloc.1
0x3f02  callvirt instance class Microsoft.Crm.Partner.PartnerSolutionDeploymentConfigCrmUser Microsoft.Crm.Partner.PartnerSolutionDeploymentConfig::get_CrmUser()
0x3f07  callvirt instance string Microsoft.Crm.Partner.PartnerSolutionDeploymentConfigCrmUser::get_FirstName()
0x3f0c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x3f11  callvirt instance void Microsoft.Crm.Partner.PartnerSolutionDeploymentConfigCrmUser::set_FirstName(string value)
0x3f16  ldloc.3
0x3f17  ldloc.1
0x3f18  callvirt instance class Microsoft.Crm.Partner.PartnerSolutionDeploymentConfigCrmUser Microsoft.Crm.Partner.PartnerSolutionDeploymentConfig::get_CrmUser()
0x3f1d  callvirt instance string Microsoft.Crm.Partner.PartnerSolutionDeploymentConfigCrmUser::get_LastName()
0x3f22  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x3f27  brfalse.s loc_3F45
0x3f29  ldloc.1
0x3f2a  callvirt instance class Microsoft.Crm.Partner.PartnerSolutionDeploymentConfigCrmUser Microsoft.Crm.Partner.PartnerSolutionDeploymentConfig::get_CrmUser()
0x3f2f  ldloc.3
0x3f30  ldloc.1
0x3f31  callvirt instance class Microsoft.Crm.Partner.PartnerSolutionDeploymentConfigCrmUser Microsoft.Crm.Partner.PartnerSolutionDeploymentConfig::get_CrmUser()
0x3f36  callvirt instance string Microsoft.Crm.Partner.PartnerSolutionDeploymentConfigCrmUser::get_LastName()
0x3f3b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x3f40  callvirt instance void Microsoft.Crm.Partner.PartnerSolutionDeploymentConfigCrmUser::set_LastName(string value)
0x3f45  ldloc.3
0x3f46  ldloc.1
0x3f47  callvirt instance class Microsoft.Crm.Partner.PartnerSolutionDeploymentConfigCrmUserRole Microsoft.Crm.Partner.PartnerSolutionDeploymentConfig::get_CrmUserRole()
0x3f4c  callvirt instance string Microsoft.Crm.Partner.PartnerSolutionDeploymentConfigCrmUserRole::get_Name()
0x3f51  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x3f56  brfalse.s loc_3F74
0x3f58  ldloc.1
0x3f59  callvirt instance class Microsoft.Crm.Partner.PartnerSolutionDeploymentConfigCrmUserRole Microsoft.Crm.Partner.PartnerSolutionDeploymentConfig::get_CrmUserRole()
0x3f5e  ldloc.3
0x3f5f  ldloc.1
0x3f60  callvirt instance class Microsoft.Crm.Partner.PartnerSolutionDeploymentConfigCrmUserRole Microsoft.Crm.Partner.PartnerSolutionDeploymentConfig::get_CrmUserRole()
0x3f65  callvirt instance string Microsoft.Crm.Partner.PartnerSolutionDeploymentConfigCrmUserRole::get_Name()
0x3f6a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x3f6f  callvirt instance void Microsoft.Crm.Partner.PartnerSolutionDeploymentConfigCrmUserRole::set_Name(string value)
0x3f74  ldloc.1
0x3f75  ret
0x3f76  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x3f7b  ldc.i4.s 0x14
0x3f7d  ldstr    aRetrievepartne_0// "RetrievePartnerSolutionDeploymentConfig"...
0x3f82  ldc.i4.1
0x3f83  newarr   [mscorlib]System.Object
0x3f88  dup
0x3f89  ldc.i4.0
0x3f8a  ldarg.1
0x3f8b  box      [mscorlib]System.Guid
0x3f90  stelem.ref
0x3f91  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3f96  ldnull
0x3f97  ret
```
