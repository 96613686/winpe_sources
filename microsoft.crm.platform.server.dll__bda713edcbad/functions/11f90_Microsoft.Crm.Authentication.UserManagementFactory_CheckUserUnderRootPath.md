# Microsoft.Crm.Authentication.UserManagementFactory::CheckUserUnderRootPath

- ea: `0x11f90`
- end: `0x120d8`
- name: `Microsoft.Crm.Authentication.UserManagementFactory::CheckUserUnderRootPath`
- size: `328`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10d20`

## callees

- `0x11f90`

## string_xrefs

- `0x11fa5`: `CheckUserUnderRootPath`
- `0x120ae`: `	UserManagementFactory.CheckUserUnderRootPath for user '{0}' failed because it is not under the UserRootPath '{1}' specified by using the Deployment Configuration Tool.`

## pseudocode

```c

```

## disassembly

```asm
0x11f90  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0x11f95  ldarg.2
0x11f96  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x11f9b  call     string [Microsoft.Crm]Microsoft.Crm.ApplicationConfig::get_UserRootPath()
0x11fa0  ldc.i4   0x3FB
0x11fa5  ldstr    aCheckuserunder// "CheckUserUnderRootPath"
0x11faa  ldstr    aDA1SSrcManaged_1// "D:\\a\\1\\s\\src\\ManagedPlatform\\Serv"...
0x11faf  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider::GetOrganizationSetting(valuetype [mscorlib]System.Guid, string, int32, string, string)
0x11fb4  castclass [mscorlib]System.String
0x11fb9  stloc.0
0x11fba  ldloc.0
0x11fbb  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x11fc0  brtrue   loc_120D7
0x11fc5  ldnull
0x11fc6  stloc.1
0x11fc7  ldloc.0
0x11fc8  newobj   instance void [System.DirectoryServices]System.DirectoryServices.DirectoryEntry::.ctor(string)
0x11fcd  stloc.2
0x11fce  ldarg.1
0x11fcf  call     bool [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.FederatedUserInformation::ValidateUserPrincipalName(string)
0x11fd4  brfalse.s loc_12020
0x11fd6  ldloc.2
0x11fd7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x11fdc  ldstr    aObjectcategory// "(&(objectcategory=person)(objectclass=u"...
0x11fe1  ldc.i4.1
0x11fe2  newarr   [mscorlib]System.Object
0x11fe7  dup
0x11fe8  ldc.i4.0
0x11fe9  ldarg.1
0x11fea  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmLdapSearchFilterEncode(string)
0x11fef  stelem.ref
0x11ff0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x11ff5  ldc.i4.1
0x11ff6  newarr   [mscorlib]System.String
0x11ffb  dup
0x11ffc  ldc.i4.0
0x11ffd  ldstr    aUserprincipaln// "userprincipalname"
0x12002  stelem.ref
0x12003  ldc.i4.2
0x12004  newobj   instance void [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::.ctor(class [System.DirectoryServices]System.DirectoryServices.DirectoryEntry, string, string[], valuetype [System.DirectoryServices]System.DirectoryServices.SearchScope)
0x12009  stloc.3
0x1200a  ldloc.3
0x1200b  callvirt instance class [System.DirectoryServices]System.DirectoryServices.SearchResult [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::FindOne()
0x12010  stloc.1
0x12011  leave    loc_120A2
0x12016  ldloc.3
0x12017  brfalse.s loc_1201F
0x12019  ldloc.3
0x1201a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1201f  endfinally
0x12020  ldarg.1
0x12021  stloc.s  4
0x12023  ldarg.1
0x12024  ldc.i4.s 0x5C
0x12026  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x1202b  ldc.i4.0
0x1202c  ble.s    loc_12043
0x1202e  ldarg.1
0x1202f  ldc.i4.1
0x12030  newarr   [mscorlib]System.Char
0x12035  dup
0x12036  ldc.i4.0
0x12037  ldc.i4.s 0x5C
0x12039  stelem.i2
0x1203a  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x1203f  ldc.i4.1
0x12040  ldelem.ref
0x12041  stloc.s  4
0x12043  ldloc.2
0x12044  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x12049  ldstr    aObjectcategory_0// "(&(objectcategory=person)(objectclass=u"...
0x1204e  ldc.i4.2
0x1204f  newarr   [mscorlib]System.Object
0x12054  dup
0x12055  ldc.i4.0
0x12056  ldarg.1
0x12057  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmLdapSearchFilterEncode(string)
0x1205c  stelem.ref
0x1205d  dup
0x1205e  ldc.i4.1
0x1205f  ldloc.s  4
0x12061  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmLdapSearchFilterEncode(string)
0x12066  stelem.ref
0x12067  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1206c  ldc.i4.1
0x1206d  newarr   [mscorlib]System.String
0x12072  dup
0x12073  ldc.i4.0
0x12074  ldstr    aSamaccountname// "samaccountname"
0x12079  stelem.ref
0x1207a  ldc.i4.2
0x1207b  newobj   instance void [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::.ctor(class [System.DirectoryServices]System.DirectoryServices.DirectoryEntry, string, string[], valuetype [System.DirectoryServices]System.DirectoryServices.SearchScope)
0x12080  stloc.s  5
0x12082  ldloc.s  5
0x12084  callvirt instance class [System.DirectoryServices]System.DirectoryServices.SearchResult [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::FindOne()
0x12089  stloc.1
0x1208a  leave.s  loc_120A2
0x1208c  ldloc.s  5
0x1208e  brfalse.s loc_12097
0x12090  ldloc.s  5
0x12092  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12097  endfinally
0x12098  ldloc.2
0x12099  brfalse.s loc_120A1
0x1209b  ldloc.2
0x1209c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x120a1  endfinally
0x120a2  ldloc.1
0x120a3  brtrue.s loc_120D7
0x120a5  ldnull
0x120a6  ldarg.2
0x120a7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x120ac  ldc.i4.s 0x14
0x120ae  ldstr    aUsermanagement_6// "\tUserManagementFactory.CheckUserUnderR"...
0x120b3  ldc.i4.2
0x120b4  newarr   [mscorlib]System.Object
0x120b9  dup
0x120ba  ldc.i4.0
0x120bb  ldarg.1
0x120bc  stelem.ref
0x120bd  dup
0x120be  ldc.i4.1
0x120bf  ldloc.0
0x120c0  stelem.ref
0x120c1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x120c6  ldc.i4   0x8004021D
0x120cb  ldc.i4.0
0x120cc  newarr   [mscorlib]System.Object
0x120d1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x120d6  throw
0x120d7  ret
```
