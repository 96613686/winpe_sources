# Microsoft.Crm.Application.Utility.ActiveDirectoryUtility::GetSerializedSystemUsers

- ea: `0x382d0`
- end: `0x385ad`
- name: `Microsoft.Crm.Application.Utility.ActiveDirectoryUtility::GetSerializedSystemUsers`
- size: `733`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x9dfb0`

## callees

- `0x2fb90`
- `0x2fbc0`
- `0x37ad0`
- `0x38050`
- `0x380e0`
- `0x38260`
- `0x382a0`
- `0x382d0`
- `0x385b0`
- `0x385f0`
- `0x38630`
- `0x387b0`
- `0x47920`
- `0x47940`

## string_xrefs

- `0x3831c`: `d:\dbs\sh\dccm2\1101_190851\cmd\20\src\Core\Application\WebPlatform\Utility\ActiveDirectoryUtility.cs`
- `0x382d1`: `ldapPath`

## pseudocode

```c

```

## disassembly

```asm
0x382d0  ldarg.0
0x382d1  ldstr    aLdappath// "ldapPath"
0x382d6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x382db  call     void Microsoft.Crm.Application.Utility.ActiveDirectoryUtility::ThrowExceptionForUnsupportedOperation()
0x382e0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.AutoReimpersonator::.ctor()
0x382e5  stloc.0
0x382e6  ldarg.0
0x382e7  stloc.3
0x382e8  ldarg.1
0x382e9  ldloca.s 1
0x382eb  ldloca.s 2
0x382ed  call     bool Microsoft.Crm.Application.Utility.ActiveDirectoryUtility::SeparateDomainAccount(string domainAccountName, [out] string& domainName, [out] string& accountName)
0x382f2  brfalse.s loc_38339
0x382f4  ldloc.1
0x382f5  call     string Microsoft.Crm.Application.Utility.ActiveDirectoryUtility::GetDomainPath(string netBiosName)
0x382fa  stloc.3
0x382fb  ldloc.2
0x382fc  starg.s  1
0x382fe  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0x38303  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x38308  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x3830d  call     string [Microsoft.Crm]Microsoft.Crm.ApplicationConfig::get_UserRootPath()
0x38312  ldc.i4   0x330
0x38317  ldstr    aGetserializeds// "GetSerializedSystemUsers"
0x3831c  ldstr    aDDbsShDccm2110_0// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\2"...
0x38321  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider::GetOrganizationSetting(valuetype [mscorlib]System.Guid, string, int32, string, string)
0x38326  castclass [mscorlib]System.String
0x3832b  stloc.s  4
0x3832d  ldloc.s  4
0x3832f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x38334  brtrue.s loc_38339
0x38336  ldloc.s  4
0x38338  stloc.3
0x38339  nop
0x3833a  ldloc.3
0x3833b  newobj   instance void [System.DirectoryServices]System.DirectoryServices.DirectoryEntry::.ctor(string)
0x38340  stloc.s  5
0x38342  ldloc.s  5
0x38344  newobj   instance void [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::.ctor(class [System.DirectoryServices]System.DirectoryServices.DirectoryEntry)
0x38349  stloc.s  6
0x3834b  ldloc.s  6
0x3834d  ldc.i4.0
0x3834e  callvirt instance void [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::set_CacheResults(bool)
0x38353  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x38358  stloc.s  7
0x3835a  ldloc.s  7
0x3835c  ldstr    aObjectclassUse// "(&(&(objectClass=user)(objectCategory=P"...
0x38361  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x38366  pop
0x38367  ldarg.1
0x38368  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3836d  brtrue.s loc_383BA
0x3836f  ldarg.1
0x38370  ldstr    asc_C4190// "*"
0x38375  ldc.i4.4
0x38376  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x3837b  brtrue.s loc_3838A
0x3837d  ldarg.1
0x3837e  ldstr    asc_C4190// "*"
0x38383  call     string [mscorlib]System.String::Concat(string, string)
0x38388  br.s     loc_3838B
0x3838a  ldarg.1
0x3838b  stloc.s  0xB
0x3838d  ldloc.s  7
0x3838f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x38394  ldstr    aName0Givenname// "(|(name={0})(givenName={0})(sn={0})(sAM"...
0x38399  ldc.i4.1
0x3839a  newarr   [mscorlib]System.Object
0x3839f  dup
0x383a0  ldc.i4.0
0x383a1  ldloc.s  0xB
0x383a3  ldc.i4.1
0x383a4  newarr   [mscorlib]System.Char
0x383a9  dup
0x383aa  ldc.i4.0
0x383ab  ldc.i4.s 0x2A
0x383ad  stelem.i2
0x383ae  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmLdapSearchFilterEncode(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<char>)
0x383b3  stelem.ref
0x383b4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x383b9  pop
0x383ba  ldloc.s  7
0x383bc  ldstr    asc_C4206// ")"
0x383c1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x383c6  pop
0x383c7  ldloc.s  6
0x383c9  ldloc.s  7
0x383cb  callvirt instance string [mscorlib]System.Object::ToString()
0x383d0  callvirt instance void [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::set_Filter(string)
0x383d5  ldloc.s  6
0x383d7  ldc.i4.s 0x60
0x383d9  callvirt instance void [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::set_ReferralChasing(valuetype [System.DirectoryServices]System.DirectoryServices.ReferralChasingOption)
0x383de  ldloc.s  6
0x383e0  ldc.i4.2
0x383e1  callvirt instance void [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::set_SearchScope(valuetype [System.DirectoryServices]System.DirectoryServices.SearchScope)
0x383e6  newobj   instance void [System.DirectoryServices]System.DirectoryServices.SortOption::.ctor()
0x383eb  stloc.s  8
0x383ed  ldloc.s  8
0x383ef  ldstr    aName// "name"
0x383f4  callvirt instance void [System.DirectoryServices]System.DirectoryServices.SortOption::set_PropertyName(string)
0x383f9  ldloc.s  8
0x383fb  ldc.i4.0
0x383fc  callvirt instance void [System.DirectoryServices]System.DirectoryServices.SortOption::set_Direction(valuetype [System.DirectoryServices]System.DirectoryServices.SortDirection)
0x38401  ldloc.s  6
0x38403  ldloc.s  8
0x38405  callvirt instance void [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::set_Sort(class [System.DirectoryServices]System.DirectoryServices.SortOption)
0x3840a  ldloc.s  6
0x3840c  call     void Microsoft.Crm.Application.Utility.ActiveDirectoryUtility::AddCommonProperties(class [System.DirectoryServices]System.DirectoryServices.DirectorySearcher searcher)
0x38411  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x38416  stloc.s  9
0x38418  newobj   instance void [System.Xml]System.Xml.XmlWriterSettings::.ctor()
0x3841d  stloc.s  0xA
0x3841f  ldloc.s  0xA
0x38421  ldc.i4.1
0x38422  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_OmitXmlDeclaration(bool)
0x38427  ldloc.s  9
0x38429  ldloc.s  0xA
0x3842b  call     class [System.Xml]System.Xml.XmlWriter [System.Xml]System.Xml.XmlWriter::Create(class [mscorlib]System.Text.StringBuilder, class [System.Xml]System.Xml.XmlWriterSettings)
0x38430  stloc.s  0xC
0x38432  ldloc.s  0xC
0x38434  ldstr    aSystemusers// "systemusers"
0x38439  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x3843e  ldloc.s  6
0x38440  callvirt instance class [System.DirectoryServices]System.DirectoryServices.SearchResultCollection [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::FindAll()
0x38445  stloc.s  0xD
0x38447  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x3844c  stloc.s  0xE
0x3844e  ldloc.s  0xD
0x38450  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.DirectoryServices]System.DirectoryServices.SearchResultCollection::GetEnumerator()
0x38455  stloc.s  0xF
0x38457  br       loc_384E4
0x3845c  ldloc.s  0xF
0x3845e  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x38463  castclass [System.DirectoryServices]System.DirectoryServices.SearchResult
0x38468  stloc.s  0x10
0x3846a  ldloc.s  0x10
0x3846c  ldstr    aDistinguishedn// "distinguishedName"
0x38471  call     string Microsoft.Crm.Application.Utility.ActiveDirectoryUtility::TryGetStringProperty(class [System.DirectoryServices]System.DirectoryServices.SearchResult result, string propertyName)
0x38476  call     string Microsoft.Crm.Application.Utility.ActiveDirectoryUtility::StripDistinguishedNameToDomain(string distinguishedName)
0x3847b  stloc.s  0x11
0x3847d  ldloc.s  0xE
0x3847f  ldloc.s  0x11
0x38481  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::ContainsKey(var<u1>)
0x38486  brtrue.s loc_38498
0x38488  ldloc.s  0xE
0x3848a  ldloc.s  0x11
0x3848c  ldloc.s  0x11
0x3848e  call     string Microsoft.Crm.Application.Utility.ActiveDirectoryUtility::GetDomainNetBiosName(string distinguishedName)
0x38493  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::Add(var<u1>, !!T0)
0x38498  ldloc.s  0xE
0x3849a  ldloc.s  0x11
0x3849c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::get_Item(void)
0x384a1  stloc.s  0x12
0x384a3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x384a8  ldstr    a01_3// "{0}\\{1}"
0x384ad  ldc.i4.2
0x384ae  newarr   [mscorlib]System.Object
0x384b3  dup
0x384b4  ldc.i4.0
0x384b5  ldloc.s  0x12
0x384b7  stelem.ref
0x384b8  dup
0x384b9  ldc.i4.1
0x384ba  ldloc.s  0x10
0x384bc  ldstr    aSamaccountname_0// "sAMAccountName"
0x384c1  call     string Microsoft.Crm.Application.Utility.ActiveDirectoryUtility::TryGetStringProperty(class [System.DirectoryServices]System.DirectoryServices.SearchResult result, string propertyName)
0x384c6  stelem.ref
0x384c7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x384cc  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x384d1  call     bool Microsoft.Crm.Application.Utility.ActiveDirectoryUtility::IsCrmUser(string domainLogonName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x384d6  brtrue.s loc_384E4
0x384d8  ldloc.s  0x10
0x384da  ldloc.s  0x12
0x384dc  ldc.i4.1
0x384dd  ldloc.s  0xC
0x384df  call     void Microsoft.Crm.Application.Utility.ActiveDirectoryUtility::SerializeSystemUserSearchResult(class [System.DirectoryServices]System.DirectoryServices.SearchResult user, string domainName, bool forLookup, class [System.Xml]System.Xml.XmlWriter writer)
0x384e4  ldloc.s  0xF
0x384e6  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x384eb  brtrue   loc_3845C
0x384f0  leave.s  loc_38507
0x384f2  ldloc.s  0xF
0x384f4  isinst   [mscorlib]System.IDisposable
0x384f9  stloc.s  0x13
0x384fb  ldloc.s  0x13
0x384fd  brfalse.s loc_38506
0x384ff  ldloc.s  0x13
0x38501  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x38506  endfinally
0x38507  leave.s  loc_38515
0x38509  ldloc.s  0xD
0x3850b  brfalse.s loc_38514
0x3850d  ldloc.s  0xD
0x3850f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x38514  endfinally
0x38515  ldloc.s  0xC
0x38517  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x3851c  ldloc.s  0xC
0x3851e  callvirt instance void [System.Xml]System.Xml.XmlWriter::Flush()
0x38523  leave.s  loc_38531
0x38525  ldloc.s  0xC
0x38527  brfalse.s loc_38530
0x38529  ldloc.s  0xC
0x3852b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x38530  endfinally
0x38531  ldloc.s  9
0x38533  callvirt instance string [mscorlib]System.Object::ToString()
0x38538  stloc.s  0x14
0x3853a  leave.s  loc_385AA
0x3853c  ldloc.s  6
0x3853e  brfalse.s loc_38547
0x38540  ldloc.s  6
0x38542  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x38547  endfinally
0x38548  ldloc.s  5
0x3854a  brfalse.s loc_38553
0x3854c  ldloc.s  5
0x3854e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x38553  endfinally
0x38554  stloc.s  0x15
0x38556  ldloc.s  0x15
0x38558  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Utility.Util::get_TraceOrganizationId()
0x3855d  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x38562  ldstr    a0// "{0}"
0x38567  ldc.i4.1
0x38568  newarr   [mscorlib]System.Object
0x3856d  dup
0x3856e  ldc.i4.0
0x3856f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x38574  ldstr    aExceptionSearc// "Exception searching for {0} in {1}: {2}"
0x38579  ldc.i4.3
0x3857a  newarr   [mscorlib]System.Object
0x3857f  dup
0x38580  ldc.i4.0
0x38581  ldarg.1
0x38582  stelem.ref
0x38583  dup
0x38584  ldc.i4.1
0x38585  ldloc.3
0x38586  stelem.ref
0x38587  dup
0x38588  ldc.i4.2
0x38589  ldloc.s  0x15
0x3858b  stelem.ref
0x3858c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x38591  stelem.ref
0x38592  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x38597  ldstr    aSystemusersSys// "<systemusers></systemusers>"
0x3859c  stloc.s  0x14
0x3859e  leave.s  loc_385AA
0x385a0  ldloc.0
0x385a1  brfalse.s loc_385A9
0x385a3  ldloc.0
0x385a4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x385a9  endfinally
0x385aa  ldloc.s  0x14
0x385ac  ret
```
