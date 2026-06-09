# Microsoft.Crm.Tools.Admin.ADUserMappingHelper::FindUserByLdapPathOrPrincipalName

- ea: `0x130e0`
- end: `0x13192`
- name: `Microsoft.Crm.Tools.Admin.ADUserMappingHelper::FindUserByLdapPathOrPrincipalName`
- size: `178`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x130d0`

## callees

- `0x12fc0`
- `0x130e0`
- `0x131a0`
- `0x13380`
- `0x135c0`

## string_xrefs

- `0x13164`: `Failed while trying to find user by LDAP path or principal name`

## pseudocode

```c

```

## disassembly

```asm
0x130e0  ldarg.0
0x130e1  newobj   instance void [System.DirectoryServices]System.DirectoryServices.DirectoryEntry::.ctor(string)
0x130e6  stloc.0
0x130e7  ldloc.0
0x130e8  newobj   instance void [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::.ctor(class [System.DirectoryServices]System.DirectoryServices.DirectoryEntry)
0x130ed  stloc.1
0x130ee  ldloc.1
0x130ef  ldc.i4   0x3E8
0x130f4  callvirt instance void [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::set_PageSize(int32)
0x130f9  ldloc.1
0x130fa  ldc.i4.0
0x130fb  callvirt instance void [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::set_SearchScope(valuetype [System.DirectoryServices]System.DirectoryServices.SearchScope)
0x13100  ldloc.1
0x13101  ldstr    aObjectclassUse_1// "(&(objectClass=user)(objectCategory=Per"...
0x13106  callvirt instance void [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::set_Filter(string)
0x1310b  ldloc.1
0x1310c  call     void Microsoft.Crm.Tools.Admin.ADUserMappingHelper::AddPropertiesToLoadToDirectorySearcher(class [System.DirectoryServices]System.DirectoryServices.DirectorySearcher searcher)
0x13111  ldloc.1
0x13112  callvirt instance class [System.DirectoryServices]System.DirectoryServices.SearchResultCollection [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::FindAll()
0x13117  stloc.2
0x13118  leave.s  loc_13171
0x1311a  stloc.3
0x1311b  ldloc.3
0x1311c  isinst   [System.DirectoryServices]System.DirectoryServices.DirectoryServicesCOMException
0x13121  brfalse.s loc_1313A
0x13123  ldarg.1
0x13124  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x13129  brtrue.s loc_1313A
0x1312b  ldarg.1
0x1312c  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.DomainAccount Microsoft.Crm.Tools.Admin.ADUserMappingHelper::ConvertPrincipalNameToDomainAccountName(string principalName)
0x13131  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.SearchUserResult Microsoft.Crm.Tools.Admin.ADUserMappingHelper::GetUserSidAndGuidByDomainAccount(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.DomainAccount domainAccount)
0x13136  stloc.s  4
0x13138  leave.s  loc_1318F
0x1313a  ldloc.3
0x1313b  isinst   [mscorlib]System.InvalidOperationException
0x13140  brtrue.s loc_1315A
0x13142  ldloc.3
0x13143  isinst   [mscorlib]System.NotSupportedException
0x13148  brtrue.s loc_1315A
0x1314a  ldloc.3
0x1314b  isinst   [System.DirectoryServices]System.DirectoryServices.DirectoryServicesCOMException
0x13150  brtrue.s loc_1315A
0x13152  ldloc.3
0x13153  isinst   [mscorlib]System.Runtime.InteropServices.COMException
0x13158  brfalse.s loc_13164
0x1315a  ldloc.3
0x1315b  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.SearchExceptionError::.ctor(class [mscorlib]System.Exception)
0x13160  stloc.s  4
0x13162  leave.s  loc_1318F
0x13164  ldstr    aFailedWhileTry_0// "Failed while trying to find user by LDA"...
0x13169  ldloc.3
0x1316a  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteError(string, class [mscorlib]System.Exception)
0x1316f  rethrow
0x13171  ldloc.2
0x13172  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.SearchUserResult Microsoft.Crm.Tools.Admin.ADUserMappingHelper::GetUserFromSearchResult(class [System.DirectoryServices]System.DirectoryServices.SearchResultCollection src)
0x13177  stloc.s  4
0x13179  leave.s  loc_1318F
0x1317b  ldloc.1
0x1317c  brfalse.s loc_13184
0x1317e  ldloc.1
0x1317f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x13184  endfinally
0x13185  ldloc.0
0x13186  brfalse.s loc_1318E
0x13188  ldloc.0
0x13189  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1318e  endfinally
0x1318f  ldloc.s  4
0x13191  ret
```
