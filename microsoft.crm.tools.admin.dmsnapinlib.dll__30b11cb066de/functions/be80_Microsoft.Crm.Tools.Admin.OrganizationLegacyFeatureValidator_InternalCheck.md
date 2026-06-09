# Microsoft.Crm.Tools.Admin.OrganizationLegacyFeatureValidator::InternalCheck

- ea: `0xbe80`
- end: `0xc034`
- name: `Microsoft.Crm.Tools.Admin.OrganizationLegacyFeatureValidator::InternalCheck`
- size: `436`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x590`
- `0xab0`
- `0xad0`
- `0x22e0`
- `0x84f0`
- `0x8630`
- `0x8670`
- `0x86e0`
- `0x8720`
- `0x8bf0`
- `0x8cd0`
- `0xbdd0`
- `0xbe80`
- `0xc040`

## string_xrefs

- `0xbeb2`: `LegacyFeatureCheck.xml`
- `0xbfd0`: `OrganizationLegacyPluginCustomActivityValidator.Failure`

## pseudocode

```c

```

## disassembly

```asm
0xbe80  ldarg.0
0xbe81  call     instance bool Microsoft.Crm.Tools.Admin.OrganizationValidator::Perform2007EndpointCheck()
0xbe86  brtrue.s loc_BE9F
0xbe88  ldstr    aTheOrganizatio_0// "The OrganizationLegacyFeatureValidator "...
0xbe8d  ldc.i4.0
0xbe8e  newarr   [mscorlib]System.Object
0xbe93  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0xbe98  ldc.i4.3
0xbe99  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult)
0xbe9e  ret
0xbe9f  ldarg.1
0xbea0  newobj   instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::.ctor(class [mscorlib]System.Collections.IDictionary data)
0xbea5  stloc.0
0xbea6  ldc.i4.s 0x1A
0xbea8  call     string [mscorlib]System.Environment::GetFolderPath(valuetype [mscorlib]System.Environment/SpecialFolder)
0xbead  ldstr    aMicrosoftMscrm// "Microsoft\\MSCRM\\Logs"
0xbeb2  ldstr    aLegacyfeaturec// "LegacyFeatureCheck.xml"
0xbeb7  call     string [mscorlib]System.IO.Path::Combine(string, string, string)
0xbebc  stloc.1
0xbebd  newobj   instance void Microsoft.Crm.LegacyFeatureCheck.Parameters::.ctor()
0xbec2  stloc.2
0xbec3  ldloc.2
0xbec4  ldloc.0
0xbec5  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_SqlServerName()
0xbeca  stfld    string Microsoft.Crm.LegacyFeatureCheck.Parameters::ServerName
0xbecf  ldloc.2
0xbed0  ldloc.0
0xbed1  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationUniqueName()
0xbed6  stfld    string Microsoft.Crm.LegacyFeatureCheck.Parameters::OrgUniqueName
0xbedb  ldloc.2
0xbedc  ldloc.0
0xbedd  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationFriendlyName()
0xbee2  stfld    string Microsoft.Crm.LegacyFeatureCheck.Parameters::OrgFriendlyName
0xbee7  ldloc.2
0xbee8  ldloc.0
0xbee9  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0xbeee  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.LegacyFeatureCheck.Parameters::OrganizationId
0xbef3  ldloc.2
0xbef4  ldloc.0
0xbef5  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_ConnectionString()
0xbefa  stfld    string Microsoft.Crm.LegacyFeatureCheck.Parameters::ConnectionString
0xbeff  ldloc.2
0xbf00  ldloc.0
0xbf01  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_DatabaseName()
0xbf06  stfld    string Microsoft.Crm.LegacyFeatureCheck.Parameters::DatabaseName
0xbf0b  ldloc.2
0xbf0c  ldc.i4.1
0xbf0d  stfld    bool Microsoft.Crm.LegacyFeatureCheck.Parameters::Verbose
0xbf12  ldloc.2
0xbf13  ldc.i4.1
0xbf14  stfld    bool Microsoft.Crm.LegacyFeatureCheck.Parameters::IncludeDisabled
0xbf19  ldloc.2
0xbf1a  ldnull
0xbf1b  stfld    string Microsoft.Crm.LegacyFeatureCheck.Parameters::IISLogsPath
0xbf20  ldloc.2
0xbf21  ldloc.1
0xbf22  stfld    string Microsoft.Crm.LegacyFeatureCheck.Parameters::OutputFile
0xbf27  newobj   instance void Microsoft.Crm.LegacyFeatureCheck.LegacyFeatureCheckDriver::.ctor()
0xbf2c  ldloc.2
0xbf2d  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.LegacyFeatureCheck.VerificationResult> Microsoft.Crm.LegacyFeatureCheck.LegacyFeatureCheckDriver::Run(class Microsoft.Crm.LegacyFeatureCheck.Parameters parameters)
0xbf32  stloc.3
0xbf33  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbf38  ldstr    aLegacyfeaturec_0// "LegacyFeatureCheck log file is {0}"
0xbf3d  ldc.i4.1
0xbf3e  newarr   [mscorlib]System.Object
0xbf43  dup
0xbf44  ldc.i4.0
0xbf45  ldloc.2
0xbf46  ldfld    string Microsoft.Crm.LegacyFeatureCheck.Parameters::OutputFile
0xbf4b  stelem.ref
0xbf4c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xbf51  ldc.i4.0
0xbf52  newarr   [mscorlib]System.Object
0xbf57  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0xbf5c  ldarg.0
0xbf5d  ldloc.3
0xbf5e  call     instance class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.Crm.LegacyFeatureCheck.Common.ComponentName> Microsoft.Crm.Tools.Admin.OrganizationLegacyFeatureValidator::RetrieveInvalidComponentsFromVerificationResults(class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.LegacyFeatureCheck.VerificationResult> verificationResults)
0xbf63  stloc.s  4
0xbf65  ldloc.s  4
0xbf67  brfalse.s loc_BF72
0xbf69  ldloc.s  4
0xbf6b  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.Crm.LegacyFeatureCheck.Common.ComponentName>::get_Count()
0xbf70  brtrue.s loc_BF79
0xbf72  ldc.i4.0
0xbf73  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult)
0xbf78  ret
0xbf79  ldsfld   string [mscorlib]System.String::Empty
0xbf7e  stloc.s  5
0xbf80  ldloc.s  4
0xbf82  ldc.i4.3
0xbf83  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.Crm.LegacyFeatureCheck.Common.ComponentName>::Contains(var<u1>)
0xbf88  brfalse.s loc_BFA3
0xbf8a  ldloc.s  5
0xbf8c  ldstr    aOrganizationle_0// "OrganizationLegacyWebResourceValidator."...
0xbf91  ldc.i4.0
0xbf92  newarr   [mscorlib]System.Object
0xbf97  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0xbf9c  call     string [mscorlib]System.String::Concat(string, string)
0xbfa1  stloc.s  5
0xbfa3  ldloc.s  4
0xbfa5  ldc.i4.2
0xbfa6  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.Crm.LegacyFeatureCheck.Common.ComponentName>::Contains(var<u1>)
0xbfab  brtrue.s loc_BFB7
0xbfad  ldloc.s  4
0xbfaf  ldc.i4.1
0xbfb0  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.Crm.LegacyFeatureCheck.Common.ComponentName>::Contains(var<u1>)
0xbfb5  brfalse.s loc_BFE7
0xbfb7  ldloc.s  5
0xbfb9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xbfbe  brtrue.s loc_BFCE
0xbfc0  ldloc.s  5
0xbfc2  call     string [mscorlib]System.Environment::get_NewLine()
0xbfc7  call     string [mscorlib]System.String::Concat(string, string)
0xbfcc  stloc.s  5
0xbfce  ldloc.s  5
0xbfd0  ldstr    aOrganizationle_1// "OrganizationLegacyPluginCustomActivityV"...
0xbfd5  ldc.i4.0
0xbfd6  newarr   [mscorlib]System.Object
0xbfdb  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0xbfe0  call     string [mscorlib]System.String::Concat(string, string)
0xbfe5  stloc.s  5
0xbfe7  ldloc.s  5
0xbfe9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xbfee  brtrue.s loc_BFFE
0xbff0  ldloc.s  5
0xbff2  call     string [mscorlib]System.Environment::get_NewLine()
0xbff7  call     string [mscorlib]System.String::Concat(string, string)
0xbffc  stloc.s  5
0xbffe  ldloc.s  5
0xc000  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc005  ldstr    aOrganizationle_2// "OrganizationLegacyGeneralValidator.Fail"...
0xc00a  ldc.i4.0
0xc00b  newarr   [mscorlib]System.Object
0xc010  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0xc015  ldc.i4.1
0xc016  newarr   [mscorlib]System.Object
0xc01b  dup
0xc01c  ldc.i4.0
0xc01d  ldloc.1
0xc01e  stelem.ref
0xc01f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xc024  call     string [mscorlib]System.String::Concat(string, string)
0xc029  stloc.s  5
0xc02b  ldc.i4.2
0xc02c  ldloc.s  5
0xc02e  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0xc033  ret
```
