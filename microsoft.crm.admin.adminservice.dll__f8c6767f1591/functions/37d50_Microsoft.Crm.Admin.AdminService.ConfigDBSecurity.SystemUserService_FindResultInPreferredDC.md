# Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserService::FindResultInPreferredDC

- ea: `0x37d50`
- end: `0x37f05`
- name: `Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserService::FindResultInPreferredDC`
- size: `437`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x37850`

## callees

- `0x37d50`
- `0x37f10`
- `0x37f90`

## string_xrefs

- `0x37ddb`: `LDAP path to search into: {0}`
- `0x37ec1`: `ThreadAbort Exception in FindResultInPreferredDC {0}`

## pseudocode

```c

```

## disassembly

```asm
0x37d50  ldnull
0x37d51  stloc.0
0x37d52  ldarg.0
0x37d53  call     instance string Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserService::get_PreferredDc()
0x37d58  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x37d5d  brtrue   loc_37F03
0x37d62  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x37d67  ldc.i4.s 0x39
0x37d69  ldstr    aSearchInThePre// "Search in the PreferredDc: {0}"
0x37d6e  ldc.i4.1
0x37d6f  newarr   [mscorlib]System.Object
0x37d74  dup
0x37d75  ldc.i4.0
0x37d76  ldarg.0
0x37d77  call     instance string Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserService::get_PreferredDc()
0x37d7c  stelem.ref
0x37d7d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x37d82  ldstr    aDefaultnamingc// "defaultNamingContext"
0x37d87  stloc.1
0x37d88  ldarg.0
0x37d89  ldstr    aRootdse// "rootDSE"
0x37d8e  call     instance string Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserService::BuildLdapPath(string distinguishedName)
0x37d93  newobj   instance void [System.DirectoryServices]System.DirectoryServices.DirectoryEntry::.ctor(string)
0x37d98  stloc.2
0x37d99  ldloc.2
0x37d9a  callvirt instance class [System.DirectoryServices]System.DirectoryServices.PropertyCollection [System.DirectoryServices]System.DirectoryServices.DirectoryEntry::get_Properties()
0x37d9f  ldloc.1
0x37da0  callvirt instance class [System.DirectoryServices]System.DirectoryServices.PropertyValueCollection [System.DirectoryServices]System.DirectoryServices.PropertyCollection::get_Item(string)
0x37da5  callvirt instance object [System.DirectoryServices]System.DirectoryServices.PropertyValueCollection::get_Value()
0x37daa  isinst   [mscorlib]System.String
0x37daf  stloc.3
0x37db0  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x37db5  ldc.i4.s 0x39
0x37db7  ldstr    aSearchInTheDef// "Search in the 'defaultNamingContext' th"...
0x37dbc  ldc.i4.1
0x37dbd  newarr   [mscorlib]System.Object
0x37dc2  dup
0x37dc3  ldc.i4.0
0x37dc4  ldloc.3
0x37dc5  stelem.ref
0x37dc6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x37dcb  ldarg.0
0x37dcc  ldloc.3
0x37dcd  call     instance string Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserService::BuildLdapPath(string distinguishedName)
0x37dd2  stloc.s  4
0x37dd4  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x37dd9  ldc.i4.s 0x39
0x37ddb  ldstr    aLdapPathToSear// "LDAP path to search into: {0}"
0x37de0  ldc.i4.1
0x37de1  newarr   [mscorlib]System.Object
0x37de6  dup
0x37de7  ldc.i4.0
0x37de8  ldloc.s  4
0x37dea  stelem.ref
0x37deb  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x37df0  ldloc.s  4
0x37df2  newobj   instance void [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::.ctor(string)
0x37df7  stloc.s  5
0x37df9  ldloc.s  5
0x37dfb  ldc.i4.0
0x37dfc  callvirt instance void [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::set_CacheResults(bool)
0x37e01  ldloc.s  5
0x37e03  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x37e08  ldstr    aSamaccountname_1// "(SAMAccountName={0})"
0x37e0d  ldc.i4.1
0x37e0e  newarr   [mscorlib]System.Object
0x37e13  dup
0x37e14  ldc.i4.0
0x37e15  ldarg.1
0x37e16  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmLdapSearchFilterEncode(string)
0x37e1b  stelem.ref
0x37e1c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x37e21  callvirt instance void [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::set_Filter(string)
0x37e26  ldloc.s  5
0x37e28  callvirt instance class [System]System.Collections.Specialized.StringCollection [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::get_PropertiesToLoad()
0x37e2d  ldstr    aSamaccountname_0// "samaccountname"
0x37e32  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x37e37  pop
0x37e38  ldloc.s  5
0x37e3a  ldc.i4.s 0x60
0x37e3c  callvirt instance void [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::set_ReferralChasing(valuetype [System.DirectoryServices]System.DirectoryServices.ReferralChasingOption)
0x37e41  ldloc.s  5
0x37e43  ldc.i4.2
0x37e44  callvirt instance void [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::set_SearchScope(valuetype [System.DirectoryServices]System.DirectoryServices.SearchScope)
0x37e49  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x37e4e  ldc.i4.s 0x39
0x37e50  ldstr    aSearchingWithF// "Searching with filter: {0}"
0x37e55  ldc.i4.1
0x37e56  newarr   [mscorlib]System.Object
0x37e5b  dup
0x37e5c  ldc.i4.0
0x37e5d  ldloc.s  5
0x37e5f  callvirt instance string [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::get_Filter()
0x37e64  stelem.ref
0x37e65  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x37e6a  ldloc.s  5
0x37e6c  callvirt instance class [System.DirectoryServices]System.DirectoryServices.SearchResult [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::FindOne()
0x37e71  stloc.0
0x37e72  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x37e77  ldc.i4.s 0x39
0x37e79  ldstr    aSearchWas0Succ// "Search was {0}successful."
0x37e7e  ldc.i4.1
0x37e7f  newarr   [mscorlib]System.Object
0x37e84  dup
0x37e85  ldc.i4.0
0x37e86  ldloc.0
0x37e87  brtrue.s loc_37E90
0x37e89  ldstr    aNot// "NOT "
0x37e8e  br.s     loc_37E95
0x37e90  ldsfld   string [mscorlib]System.String::Empty
0x37e95  stelem.ref
0x37e96  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x37e9b  leave.s  loc_37EA9
0x37e9d  ldloc.s  5
0x37e9f  brfalse.s loc_37EA8
0x37ea1  ldloc.s  5
0x37ea3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x37ea8  endfinally
0x37ea9  leave.s  loc_37EB5
0x37eab  ldloc.2
0x37eac  brfalse.s loc_37EB4
0x37eae  ldloc.2
0x37eaf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x37eb4  endfinally
0x37eb5  leave.s  loc_37F03
0x37eb7  stloc.s  6
0x37eb9  ldloc.s  6
0x37ebb  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x37ec0  ldc.i4.6
0x37ec1  ldstr    aThreadabortExc_0// "ThreadAbort Exception in FindResultInPr"...
0x37ec6  ldc.i4.1
0x37ec7  newarr   [mscorlib]System.Object
0x37ecc  dup
0x37ecd  ldc.i4.0
0x37ece  ldloc.s  6
0x37ed0  callvirt instance string [mscorlib]System.Exception::get_Message()
0x37ed5  stelem.ref
0x37ed6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x37edb  rethrow
0x37edd  stloc.s  7
0x37edf  ldloc.s  7
0x37ee1  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x37ee6  ldc.i4.6
0x37ee7  ldstr    aExceptionInFin_0// "Exception in FindResultInPreferredDC: {"...
0x37eec  ldc.i4.1
0x37eed  newarr   [mscorlib]System.Object
0x37ef2  dup
0x37ef3  ldc.i4.0
0x37ef4  ldloc.s  7
0x37ef6  callvirt instance string [mscorlib]System.Exception::get_Message()
0x37efb  stelem.ref
0x37efc  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x37f01  leave.s  loc_37F03
0x37f03  ldloc.0
0x37f04  ret
```
