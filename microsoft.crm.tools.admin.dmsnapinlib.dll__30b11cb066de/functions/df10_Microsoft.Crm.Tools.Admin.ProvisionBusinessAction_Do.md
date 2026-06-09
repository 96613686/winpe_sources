# Microsoft.Crm.Tools.Admin.ProvisionBusinessAction::Do

- ea: `0xdf10`
- end: `0xe018`
- name: `Microsoft.Crm.Tools.Admin.ProvisionBusinessAction::Do`
- size: `264`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callees

- `0x71e0`
- `0x7270`
- `0x84f0`
- `0x8630`
- `0x86e0`
- `0x8bf0`
- `0x8f80`
- `0x8fc0`
- `0x9010`
- `0x9060`
- `0x90b0`
- `0x9120`
- `0xdf10`

## string_xrefs

- `0xdf72`: `9\FeatureSet\FeatureSet.xml`
- `0xdfa7`: `BusinessConfigurator.BusinessResult`

## pseudocode

```c

```

## disassembly

```asm
0xdf10  ldarg.1
0xdf11  newobj   instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::.ctor(class [mscorlib]System.Collections.IDictionary data)
0xdf16  stloc.0
0xdf17  ldarg.1
0xdf18  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.SystemInfo::.ctor(class [mscorlib]System.Collections.IDictionary)
0xdf1d  stloc.1
0xdf1e  ldnull
0xdf1f  stloc.2
0xdf20  ldnull
0xdf21  stloc.3
0xdf22  ldnull
0xdf23  stloc.s  4
0xdf25  ldnull
0xdf26  stloc.s  5
0xdf28  ldloc.0
0xdf29  callvirt instance class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.UserProperties Microsoft.Crm.Tools.Admin.OrganizationInfo::get_InitialUser()
0xdf2e  stloc.s  6
0xdf30  ldloc.s  6
0xdf32  brfalse.s loc_DF66
0xdf34  ldloc.s  6
0xdf36  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.UserProperties::get_DomainName()
0xdf3b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xdf40  brtrue.s loc_DF4A
0xdf42  ldloc.s  6
0xdf44  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.UserProperties::get_DomainName()
0xdf49  stloc.2
0xdf4a  ldloc.s  6
0xdf4c  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.UserProperties::get_FirstName()
0xdf51  stloc.3
0xdf52  ldloc.s  6
0xdf54  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.UserProperties::get_LastName()
0xdf59  stloc.s  4
0xdf5b  ldloc.s  6
0xdf5d  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.UserProperties::get_Email()
0xdf62  stloc.s  5
0xdf64  br.s     loc_DF71
0xdf66  call     class [mscorlib]System.Security.Principal.WindowsIdentity [mscorlib]System.Security.Principal.WindowsIdentity::GetCurrent()
0xdf6b  callvirt instance string [mscorlib]System.Security.Claims.ClaimsIdentity::get_Name()
0xdf70  stloc.2
0xdf71  ldarg.0
0xdf72  ldstr    a9FeaturesetFea// "9\\FeatureSet\\FeatureSet.xml"
0xdf77  call     instance string Microsoft.Crm.Tools.Admin.OrganizationAction::ConstructPathForSqlFile(string relativePath)
0xdf7c  stloc.s  7
0xdf7e  ldloc.0
0xdf7f  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_SqlServerName()
0xdf84  ldloc.1
0xdf85  callvirt instance string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.SystemInfo::get_MachineName()
0xdf8a  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0xdf8f  brfalse.s loc_DFA3
0xdf91  ldloc.0
0xdf92  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_SqlServerName()
0xdf97  ldstr    asc_1EC48// "."
0xdf9c  call     bool [mscorlib]System.String::op_Equality(string, string)
0xdfa1  br.s     loc_DFA4
0xdfa3  ldc.i4.1
0xdfa4  stloc.s  8
0xdfa6  ldarg.1
0xdfa7  ldstr    aBusinessconfig// "BusinessConfigurator.BusinessResult"
0xdfac  ldarg.0
0xdfad  ldfld    bool Microsoft.Crm.Tools.Admin.ProvisionBusinessAction::isXrm
0xdfb2  ldloc.0
0xdfb3  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0xdfb8  stloc.s  9
0xdfba  ldloca.s 9
0xdfbc  ldstr    aB// "B"
0xdfc1  call     instance string [mscorlib]System.Guid::ToString(string)
0xdfc6  ldloc.0
0xdfc7  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationFriendlyName()
0xdfcc  ldloc.2
0xdfcd  ldloc.3
0xdfce  ldloc.s  4
0xdfd0  ldloc.s  5
0xdfd2  ldloc.s  7
0xdfd4  ldloc.0
0xdfd5  callvirt instance int32 Microsoft.Crm.Tools.Admin.OrganizationInfo::get_BaseLanguageCode()
0xdfda  stloc.s  0xA
0xdfdc  ldloca.s 0xA
0xdfde  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xdfe3  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xdfe8  ldloc.0
0xdfe9  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_PrivUserGroup()
0xdfee  ldloc.0
0xdfef  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_SqlAccessGroup()
0xdff4  ldloc.0
0xdff5  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_ReportingGroup()
0xdffa  ldloc.0
0xdffb  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_PrivReportingGroup()
0xe000  ldloc.s  8
0xe002  ldarg.0
0xe003  call     instance class [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.OrganizationResourceHelper Microsoft.Crm.Tools.Admin.OrganizationAction::get_OrganizationResourceHelper()
0xe008  call     valuetype [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.BusinessResult [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.NewOrgUtility::OrganizationCreateNew(bool, string, string, string, string, string, string, string, string, string, string, string, string, bool, class [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.OrganizationResourceHelper)
0xe00d  box      [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.BusinessResult
0xe012  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0xe017  ret
```
