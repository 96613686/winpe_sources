# Microsoft.Crm.Application.Utility.ActiveDirectoryUtility::FindUser

- ea: `0x37b20`
- end: `0x37d69`
- name: `Microsoft.Crm.Application.Utility.ActiveDirectoryUtility::FindUser`
- size: `585`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x38200`

## callees

- `0x2fb90`
- `0x2fbc0`
- `0x37ad0`
- `0x37b20`
- `0x380e0`
- `0x385f0`
- `0x47920`
- `0x47940`

## string_xrefs

- `0x37b5f`: `d:\dbs\sh\dccm2\1101_190851\cmd\20\src\Core\Application\WebPlatform\Utility\ActiveDirectoryUtility.cs`
- `0x37d46`: `Unable to find user {0} under the AD root path {1}`

## pseudocode

```c

```

## disassembly

```asm
0x37b20  ldnull
0x37b21  stloc.0
0x37b22  ldsfld   string [mscorlib]System.String::Empty
0x37b27  stloc.1
0x37b28  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.AutoReimpersonator::.ctor()
0x37b2d  stloc.2
0x37b2e  ldarg.0
0x37b2f  ldloca.s 3
0x37b31  ldloca.s 4
0x37b33  call     bool Microsoft.Crm.Application.Utility.ActiveDirectoryUtility::SeparateDomainAccount(string domainAccountName, [out] string& domainName, [out] string& accountName)
0x37b38  brfalse.s loc_37B41
0x37b3a  ldloc.3
0x37b3b  call     string Microsoft.Crm.Application.Utility.ActiveDirectoryUtility::GetDomainPath(string netBiosName)
0x37b40  stloc.1
0x37b41  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0x37b46  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x37b4b  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x37b50  call     string [Microsoft.Crm]Microsoft.Crm.ApplicationConfig::get_UserRootPath()
0x37b55  ldc.i4   0x112
0x37b5a  ldstr    aFinduser// "FindUser"
0x37b5f  ldstr    aDDbsShDccm2110_0// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\2"...
0x37b64  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider::GetOrganizationSetting(valuetype [mscorlib]System.Guid, string, int32, string, string)
0x37b69  castclass [mscorlib]System.String
0x37b6e  stloc.s  5
0x37b70  ldloc.s  5
0x37b72  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x37b77  brtrue.s loc_37B7C
0x37b79  ldloc.s  5
0x37b7b  stloc.1
0x37b7c  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::.ctor()
0x37b81  stloc.s  6
0x37b83  ldnull
0x37b84  stloc.s  7
0x37b86  newobj   instance void [System.DirectoryServices]System.DirectoryServices.DirectoryEntry::.ctor()
0x37b8b  stloc.s  8
0x37b8d  call     class [System.DirectoryServices]System.DirectoryServices.ActiveDirectory.Domain [System.DirectoryServices]System.DirectoryServices.ActiveDirectory.Domain::GetComputerDomain()
0x37b92  stloc.s  9
0x37b94  ldloc.s  9
0x37b96  callvirt instance class [System.DirectoryServices]System.DirectoryServices.ActiveDirectory.Forest [System.DirectoryServices]System.DirectoryServices.ActiveDirectory.Domain::get_Forest()
0x37b9b  stloc.s  0xA
0x37b9d  br       loc_37CA4
0x37ba2  nop
0x37ba3  ldloc.s  7
0x37ba5  brtrue.s loc_37BB2
0x37ba7  ldloc.s  0xA
0x37ba9  callvirt instance class [System.DirectoryServices]System.DirectoryServices.ActiveDirectory.GlobalCatalog [System.DirectoryServices]System.DirectoryServices.ActiveDirectory.Forest::FindGlobalCatalog()
0x37bae  stloc.s  7
0x37bb0  br.s     loc_37BBD
0x37bb2  ldloc.s  0xA
0x37bb4  ldc.i4.1
0x37bb5  conv.i8
0x37bb6  callvirt instance class [System.DirectoryServices]System.DirectoryServices.ActiveDirectory.GlobalCatalog [System.DirectoryServices]System.DirectoryServices.ActiveDirectory.Forest::FindGlobalCatalog(valuetype [System.DirectoryServices]System.DirectoryServices.ActiveDirectory.LocatorOptions)
0x37bbb  stloc.s  7
0x37bbd  ldloc.s  6
0x37bbf  ldloc.s  7
0x37bc1  callvirt instance string [System.DirectoryServices]System.DirectoryServices.ActiveDirectory.DirectoryServer::get_Name()
0x37bc6  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::ContainsKey(var<u1>)
0x37bcb  brfalse.s loc_37BD2
0x37bcd  leave    loc_37CAA
0x37bd2  ldloc.s  6
0x37bd4  ldloc.s  7
0x37bd6  callvirt instance string [System.DirectoryServices]System.DirectoryServices.ActiveDirectory.DirectoryServer::get_Name()
0x37bdb  ldc.i4.1
0x37bdc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::Add(var<u1>, !!T0)
0x37be1  ldloc.s  7
0x37be3  callvirt instance class [System.DirectoryServices]System.DirectoryServices.DirectorySearcher [System.DirectoryServices]System.DirectoryServices.ActiveDirectory.DomainController::GetDirectorySearcher()
0x37be8  stloc.s  0xB
0x37bea  ldloc.1
0x37beb  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x37bf0  brtrue.s loc_37C03
0x37bf2  ldloc.s  8
0x37bf4  ldloc.1
0x37bf5  callvirt instance void [System.DirectoryServices]System.DirectoryServices.DirectoryEntry::set_Path(string)
0x37bfa  ldloc.s  0xB
0x37bfc  ldloc.s  8
0x37bfe  callvirt instance void [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::set_SearchRoot(class [System.DirectoryServices]System.DirectoryServices.DirectoryEntry)
0x37c03  ldloc.s  0xB
0x37c05  ldc.i4.2
0x37c06  callvirt instance void [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::set_SizeLimit(int32)
0x37c0b  ldloc.s  0xB
0x37c0d  ldc.i4.0
0x37c0e  callvirt instance void [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::set_CacheResults(bool)
0x37c13  ldloc.s  0xB
0x37c15  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x37c1a  ldstr    aSamaccountname// "(&(sAMAccountName={0})(&(objectClass=us"...
0x37c1f  ldc.i4.1
0x37c20  newarr   [mscorlib]System.Object
0x37c25  dup
0x37c26  ldc.i4.0
0x37c27  ldloc.s  4
0x37c29  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmLdapSearchFilterEncode(string)
0x37c2e  stelem.ref
0x37c2f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x37c34  callvirt instance void [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::set_Filter(string)
0x37c39  ldloc.s  0xB
0x37c3b  ldc.i4.0
0x37c3c  callvirt instance void [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::set_ReferralChasing(valuetype [System.DirectoryServices]System.DirectoryServices.ReferralChasingOption)
0x37c41  ldloc.s  0xB
0x37c43  ldc.i4.2
0x37c44  callvirt instance void [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::set_SearchScope(valuetype [System.DirectoryServices]System.DirectoryServices.SearchScope)
0x37c49  ldloc.s  0xB
0x37c4b  call     void Microsoft.Crm.Application.Utility.ActiveDirectoryUtility::AddCommonProperties(class [System.DirectoryServices]System.DirectoryServices.DirectorySearcher searcher)
0x37c50  ldloc.s  0xB
0x37c52  callvirt instance class [System.DirectoryServices]System.DirectoryServices.SearchResult [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::FindOne()
0x37c57  stloc.0
0x37c58  leave.s  loc_37C66
0x37c5a  ldloc.s  0xB
0x37c5c  brfalse.s loc_37C65
0x37c5e  ldloc.s  0xB
0x37c60  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x37c65  endfinally
0x37c66  leave.s  loc_37C96
0x37c68  stloc.s  0xC
0x37c6a  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x37c6f  ldc.i4.s 0x14
0x37c71  ldstr    aErrorWhileFind// "Error while finding user {0} in GC {1}."...
0x37c76  ldc.i4.3
0x37c77  newarr   [mscorlib]System.Object
0x37c7c  dup
0x37c7d  ldc.i4.0
0x37c7e  ldarg.0
0x37c7f  stelem.ref
0x37c80  dup
0x37c81  ldc.i4.1
0x37c82  ldloc.s  7
0x37c84  callvirt instance string [System.DirectoryServices]System.DirectoryServices.ActiveDirectory.DirectoryServer::get_Name()
0x37c89  stelem.ref
0x37c8a  dup
0x37c8b  ldc.i4.2
0x37c8c  ldloc.s  0xC
0x37c8e  stelem.ref
0x37c8f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x37c94  leave.s  loc_37C96
0x37c96  leave.s  loc_37CA4
0x37c98  ldloc.s  7
0x37c9a  brfalse.s loc_37CA3
0x37c9c  ldloc.s  7
0x37c9e  callvirt instance void [System.DirectoryServices]System.DirectoryServices.ActiveDirectory.DirectoryServer::Dispose()
0x37ca3  endfinally
0x37ca4  ldloc.0
0x37ca5  brfalse  loc_37BA2
0x37caa  leave.s  loc_37CB8
0x37cac  ldloc.s  0xA
0x37cae  brfalse.s loc_37CB7
0x37cb0  ldloc.s  0xA
0x37cb2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x37cb7  endfinally
0x37cb8  leave.s  loc_37CC6
0x37cba  ldloc.s  9
0x37cbc  brfalse.s loc_37CC5
0x37cbe  ldloc.s  9
0x37cc0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x37cc5  endfinally
0x37cc6  leave.s  loc_37CD4
0x37cc8  ldloc.s  8
0x37cca  brfalse.s loc_37CD3
0x37ccc  ldloc.s  8
0x37cce  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x37cd3  endfinally
0x37cd4  leave.s  loc_37CE0
0x37cd6  ldloc.2
0x37cd7  brfalse.s loc_37CDF
0x37cd9  ldloc.2
0x37cda  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x37cdf  endfinally
0x37ce0  leave.s  loc_37D26
0x37ce2  stloc.s  0xD
0x37ce4  ldloc.s  0xD
0x37ce6  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Utility.Util::get_TraceOrganizationId()
0x37ceb  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x37cf0  ldstr    a0// "{0}"
0x37cf5  ldc.i4.1
0x37cf6  newarr   [mscorlib]System.Object
0x37cfb  dup
0x37cfc  ldc.i4.0
0x37cfd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x37d02  ldstr    aUnableToGetFin// "Unable to get find user {0}: {1}"
0x37d07  ldc.i4.2
0x37d08  newarr   [mscorlib]System.Object
0x37d0d  dup
0x37d0e  ldc.i4.0
0x37d0f  ldarg.0
0x37d10  stelem.ref
0x37d11  dup
0x37d12  ldc.i4.1
0x37d13  ldloc.s  0xD
0x37d15  stelem.ref
0x37d16  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x37d1b  stelem.ref
0x37d1c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x37d21  ldnull
0x37d22  stloc.s  0xE
0x37d24  leave.s  loc_37D66
0x37d26  ldloc.0
0x37d27  brtrue.s loc_37D64
0x37d29  ldnull
0x37d2a  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Utility.Util::get_TraceOrganizationId()
0x37d2f  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x37d34  ldstr    a0// "{0}"
0x37d39  ldc.i4.1
0x37d3a  newarr   [mscorlib]System.Object
0x37d3f  dup
0x37d40  ldc.i4.0
0x37d41  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x37d46  ldstr    aUnableToFindUs// "Unable to find user {0} under the AD ro"...
0x37d4b  ldc.i4.2
0x37d4c  newarr   [mscorlib]System.Object
0x37d51  dup
0x37d52  ldc.i4.0
0x37d53  ldarg.0
0x37d54  stelem.ref
0x37d55  dup
0x37d56  ldc.i4.1
0x37d57  ldloc.1
0x37d58  stelem.ref
0x37d59  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x37d5e  stelem.ref
0x37d5f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x37d64  ldloc.0
0x37d65  ret
0x37d66  ldloc.s  0xE
0x37d68  ret
```
