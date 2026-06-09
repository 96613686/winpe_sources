# Microsoft.Crm.LegacyFeatureCheck.LegacyFeatureCheckDriver::Run

- ea: `0x590`
- end: `0x802`
- name: `Microsoft.Crm.LegacyFeatureCheck.LegacyFeatureCheckDriver::Run`
- size: `626`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, broker_com_uri`

## callers

- `0xbe80`

## callees

- `0x590`
- `0x810`
- `0x9e0`
- `0xa80`
- `0xb90`
- `0xbb0`
- `0xc00`
- `0xe80`
- `0xe90`
- `0xea0`
- `0xeb0`
- `0xec0`
- `0xed0`
- `0xef0`
- `0xf00`
- `0xf10`
- `0xf20`
- `0x1280`
- `0x1460`
- `0x1aa0`
- `0x1ae0`
- `0x1b80`
- `0x1ca0`
- `0x1d80`

## string_xrefs

- `0x65f`: `The Microsoft Dynamics CRM configuration database (MSCRM_CONFIG) can't be accessed. Make sure that the person running the tool has read access to these databases.`
- `0x786`: `The Microsoft Dynamics CRM organization database ({0}) can't be accessed. Make sure that the person running the tool has read access to these databases.`

## pseudocode

```c

```

## disassembly

```asm
0x590  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.LegacyFeatureCheck.VerificationResult>::.ctor()
0x595  stloc.0
0x596  call     void Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::PreLoadV4Assemblies()
0x59b  ldarg.1
0x59c  ldfld    string Microsoft.Crm.LegacyFeatureCheck.Parameters::OutputFile
0x5a1  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x5a6  brtrue.s loc_5BF
0x5a8  ldarg.0
0x5a9  ldarg.1
0x5aa  ldfld    string Microsoft.Crm.LegacyFeatureCheck.Parameters::OutputFile
0x5af  call     instance void Microsoft.Crm.LegacyFeatureCheck.LegacyFeatureCheckDriver::RemoveOutputFile(string outputFile)
0x5b4  ldarg.0
0x5b5  newobj   instance void Microsoft.Crm.LegacyFeatureCheck.Common.DeploymentVerificationResults::.ctor()
0x5ba  stfld    class Microsoft.Crm.LegacyFeatureCheck.Common.DeploymentVerificationResults Microsoft.Crm.LegacyFeatureCheck.LegacyFeatureCheckDriver::_resultsToWrite
0x5bf  nop
0x5c0  ldarg.1
0x5c1  ldfld    string Microsoft.Crm.LegacyFeatureCheck.Parameters::ServerName
0x5c6  newobj   instance void Microsoft.Crm.LegacyFeatureCheck.CrmDeployment::.ctor(string configDBServerName)
0x5cb  stloc.3
0x5cc  ldloc.3
0x5cd  ldarg.1
0x5ce  ldfld    string Microsoft.Crm.LegacyFeatureCheck.Parameters::OrgUniqueName
0x5d3  ldarg.1
0x5d4  ldfld    bool Microsoft.Crm.LegacyFeatureCheck.Parameters::IncludeDisabled
0x5d9  ldc.i4.0
0x5da  ceq
0x5dc  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.LegacyFeatureCheck.Organization> Microsoft.Crm.LegacyFeatureCheck.CrmDeployment::GetOrganizations(string orgName, bool enabledOrganizationsOnly)
0x5e1  stloc.1
0x5e2  ldarg.1
0x5e3  call     class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.LegacyFeatureCheck.Common.DeploymentVerificationAction> Microsoft.Crm.LegacyFeatureCheck.Common.VerificationActionFactory::CreateDefaultDeploymentActions(class Microsoft.Crm.LegacyFeatureCheck.Parameters parameters)
0x5e8  stloc.s  4
0x5ea  ldloc.3
0x5eb  ldloc.s  4
0x5ed  call     void Microsoft.Crm.LegacyFeatureCheck.Common.DeploymentVerificationAction::Execute(class Microsoft.Crm.LegacyFeatureCheck.CrmDeployment deployment, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.LegacyFeatureCheck.Common.DeploymentVerificationAction> actions)
0x5f2  ldarg.0
0x5f3  ldarg.1
0x5f4  ldfld    bool Microsoft.Crm.LegacyFeatureCheck.Parameters::Verbose
0x5f9  ldstr    aDeployment// "Deployment"
0x5fe  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x603  ldsfld   string [mscorlib]System.String::Empty
0x608  ldsfld   string [mscorlib]System.String::Empty
0x60d  ldloc.3
0x60e  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.LegacyFeatureCheck.VerificationResult> Microsoft.Crm.LegacyFeatureCheck.CrmDeployment::get_VerificationResults()
0x613  call     instance void Microsoft.Crm.LegacyFeatureCheck.LegacyFeatureCheckDriver::ProcessResults(bool verboseMode, string scope, valuetype [mscorlib]System.Guid orgId, string friendlyName, string uniqueName, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.LegacyFeatureCheck.VerificationResult> results)
0x618  ldloc.3
0x619  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.LegacyFeatureCheck.VerificationResult> Microsoft.Crm.LegacyFeatureCheck.CrmDeployment::get_VerificationResults()
0x61e  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.LegacyFeatureCheck.VerificationResult>::GetEnumerator()
0x623  stloc.s  5
0x625  br.s     loc_638
0x627  ldloca.s 5
0x629  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.LegacyFeatureCheck.VerificationResult>::get_Current()
0x62e  stloc.s  6
0x630  ldloc.0
0x631  ldloc.s  6
0x633  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.LegacyFeatureCheck.VerificationResult>::Add(var<u1>)
0x638  ldloca.s 5
0x63a  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.LegacyFeatureCheck.VerificationResult>::MoveNext()
0x63f  brtrue.s loc_627
0x641  leave.s  loc_651
0x643  ldloca.s 5
0x645  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.LegacyFeatureCheck.VerificationResult>
0x64b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x650  endfinally
0x651  leave.s  loc_673
0x653  callvirt instance int32 [System.Data]System.Data.SqlClient.SqlException::get_Number()
0x658  ldc.i4   0xFDC
0x65d  bne.un.s loc_671
0x65f  ldstr    aTheMicrosoftDy// "The Microsoft Dynamics CRM configuratio"...
0x664  call     void [mscorlib]System.Console::WriteLine(string)
0x669  ldloc.0
0x66a  stloc.s  7
0x66c  leave    loc_7FF
0x671  rethrow
0x673  ldloc.1
0x674  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.LegacyFeatureCheck.Organization>::get_Count()
0x679  brtrue.s loc_6D3
0x67b  ldarg.1
0x67c  ldfld    string Microsoft.Crm.LegacyFeatureCheck.Parameters::ConnectionString
0x681  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x686  brtrue.s loc_6D3
0x688  newobj   instance void Microsoft.Crm.LegacyFeatureCheck.Organization::.ctor()
0x68d  dup
0x68e  ldarg.1
0x68f  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.LegacyFeatureCheck.Parameters::OrganizationId
0x694  callvirt instance void Microsoft.Crm.LegacyFeatureCheck.Organization::set_Id(valuetype [mscorlib]System.Guid value)
0x699  dup
0x69a  ldarg.1
0x69b  ldfld    string Microsoft.Crm.LegacyFeatureCheck.Parameters::OrgFriendlyName
0x6a0  callvirt instance void Microsoft.Crm.LegacyFeatureCheck.Organization::set_FriendlyName(string value)
0x6a5  dup
0x6a6  ldarg.1
0x6a7  ldfld    string Microsoft.Crm.LegacyFeatureCheck.Parameters::OrgUniqueName
0x6ac  callvirt instance void Microsoft.Crm.LegacyFeatureCheck.Organization::set_UniqueName(string value)
0x6b1  dup
0x6b2  ldarg.1
0x6b3  ldfld    string Microsoft.Crm.LegacyFeatureCheck.Parameters::ConnectionString
0x6b8  callvirt instance void Microsoft.Crm.LegacyFeatureCheck.Organization::set_ConnectionString(string value)
0x6bd  dup
0x6be  ldarg.1
0x6bf  ldfld    string Microsoft.Crm.LegacyFeatureCheck.Parameters::DatabaseName
0x6c4  callvirt instance void Microsoft.Crm.LegacyFeatureCheck.Organization::set_DatabaseName(string value)
0x6c9  stloc.s  8
0x6cb  ldloc.1
0x6cc  ldloc.s  8
0x6ce  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.LegacyFeatureCheck.Organization>::Add(var<u1>)
0x6d3  call     class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.LegacyFeatureCheck.Common.OrganizationVerificationAction> Microsoft.Crm.LegacyFeatureCheck.Common.VerificationActionFactory::CreateDefaultOrganizationActions()
0x6d8  stloc.2
0x6d9  ldstr    aFound0Organiza// "Found {0} Organizations"
0x6de  ldloc.1
0x6df  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.LegacyFeatureCheck.Organization>::get_Count()
0x6e4  box      [mscorlib]System.Int32
0x6e9  call     void [mscorlib]System.Console::WriteLine(string, object)
0x6ee  ldloc.1
0x6ef  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.LegacyFeatureCheck.Organization>::GetEnumerator()
0x6f4  stloc.s  9
0x6f6  br       loc_7AB
0x6fb  ldloca.s 9
0x6fd  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.LegacyFeatureCheck.Organization>::get_Current()
0x702  stloc.s  0xA
0x704  ldloc.s  0xA
0x706  ldloc.2
0x707  call     void Microsoft.Crm.LegacyFeatureCheck.Common.OrganizationVerificationAction::Execute(class Microsoft.Crm.LegacyFeatureCheck.Organization organization, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.LegacyFeatureCheck.Common.OrganizationVerificationAction> actions)
0x70c  ldarg.0
0x70d  ldarg.1
0x70e  ldfld    bool Microsoft.Crm.LegacyFeatureCheck.Parameters::Verbose
0x713  ldstr    aOrganization// "Organization"
0x718  ldloc.s  0xA
0x71a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.LegacyFeatureCheck.Organization::get_Id()
0x71f  ldloc.s  0xA
0x721  callvirt instance string Microsoft.Crm.LegacyFeatureCheck.Organization::get_FriendlyName()
0x726  ldloc.s  0xA
0x728  callvirt instance string Microsoft.Crm.LegacyFeatureCheck.Organization::get_UniqueName()
0x72d  ldloc.s  0xA
0x72f  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.LegacyFeatureCheck.VerificationResult> Microsoft.Crm.LegacyFeatureCheck.Organization::get_VerificationResults()
0x734  call     instance void Microsoft.Crm.LegacyFeatureCheck.LegacyFeatureCheckDriver::ProcessResults(bool verboseMode, string scope, valuetype [mscorlib]System.Guid orgId, string friendlyName, string uniqueName, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.LegacyFeatureCheck.VerificationResult> results)
0x739  ldloc.s  0xA
0x73b  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.LegacyFeatureCheck.VerificationResult> Microsoft.Crm.LegacyFeatureCheck.Organization::get_VerificationResults()
0x740  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.LegacyFeatureCheck.VerificationResult>::GetEnumerator()
0x745  stloc.s  5
0x747  br.s     loc_75A
0x749  ldloca.s 5
0x74b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.LegacyFeatureCheck.VerificationResult>::get_Current()
0x750  stloc.s  0xB
0x752  ldloc.0
0x753  ldloc.s  0xB
0x755  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.LegacyFeatureCheck.VerificationResult>::Add(var<u1>)
0x75a  ldloca.s 5
0x75c  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.LegacyFeatureCheck.VerificationResult>::MoveNext()
0x761  brtrue.s loc_749
0x763  leave.s  loc_773
0x765  ldloca.s 5
0x767  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.LegacyFeatureCheck.VerificationResult>
0x76d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x772  endfinally
0x773  leave.s  loc_7AB
0x775  callvirt instance int32 [System.Data]System.Data.SqlClient.SqlException::get_Number()
0x77a  ldc.i4   0xFDC
0x77f  bne.un.s loc_7A7
0x781  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x786  ldstr    aTheMicrosoftDy_0// "The Microsoft Dynamics CRM organization"...
0x78b  ldc.i4.1
0x78c  newarr   [mscorlib]System.Object
0x791  dup
0x792  ldc.i4.0
0x793  ldloc.s  0xA
0x795  callvirt instance string Microsoft.Crm.LegacyFeatureCheck.Organization::get_DatabaseName()
0x79a  stelem.ref
0x79b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7a0  call     void [mscorlib]System.Console::WriteLine(string)
0x7a5  br.s     loc_7A9
0x7a7  rethrow
0x7a9  leave.s  loc_7AB
0x7ab  ldloca.s 9
0x7ad  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.LegacyFeatureCheck.Organization>::MoveNext()
0x7b2  brtrue   loc_6FB
0x7b7  leave.s  loc_7C7
0x7b9  ldloca.s 9
0x7bb  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.LegacyFeatureCheck.Organization>
0x7c1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7c6  endfinally
0x7c7  leave.s  loc_7F1
0x7c9  stloc.s  0xC
0x7cb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7d0  ldstr    aError0// "Error: {0}"
0x7d5  ldc.i4.1
0x7d6  newarr   [mscorlib]System.Object
0x7db  dup
0x7dc  ldc.i4.0
0x7dd  ldloc.s  0xC
0x7df  callvirt instance string [mscorlib]System.Object::ToString()
0x7e4  stelem.ref
0x7e5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7ea  call     void [mscorlib]System.Console::WriteLine(string)
0x7ef  leave.s  loc_7F1
0x7f1  ldarg.0
0x7f2  ldarg.1
0x7f3  ldfld    string Microsoft.Crm.LegacyFeatureCheck.Parameters::OutputFile
0x7f8  call     instance void Microsoft.Crm.LegacyFeatureCheck.LegacyFeatureCheckDriver::WriteResults(string outputFile)
0x7fd  ldloc.0
0x7fe  ret
0x7ff  ldloc.s  7
0x801  ret
```
