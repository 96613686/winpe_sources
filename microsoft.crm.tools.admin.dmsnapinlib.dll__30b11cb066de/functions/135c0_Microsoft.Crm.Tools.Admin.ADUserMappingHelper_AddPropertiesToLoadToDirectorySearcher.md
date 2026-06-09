# Microsoft.Crm.Tools.Admin.ADUserMappingHelper::AddPropertiesToLoadToDirectorySearcher

- ea: `0x135c0`
- end: `0x13649`
- name: `Microsoft.Crm.Tools.Admin.ADUserMappingHelper::AddPropertiesToLoadToDirectorySearcher`
- size: `137`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x12e70`
- `0x130e0`
- `0x13200`

## string_xrefs

- `0x1363d`: `objectSid`

## pseudocode

```c

```

## disassembly

```asm
0x135c0  ldarg.0
0x135c1  callvirt instance class [System]System.Collections.Specialized.StringCollection [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::get_PropertiesToLoad()
0x135c6  ldstr    aDistinguishedn// "distinguishedName"
0x135cb  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x135d0  pop
0x135d1  ldarg.0
0x135d2  callvirt instance class [System]System.Collections.Specialized.StringCollection [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::get_PropertiesToLoad()
0x135d7  ldstr    aDisplayname// "displayName"
0x135dc  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x135e1  pop
0x135e2  ldarg.0
0x135e3  callvirt instance class [System]System.Collections.Specialized.StringCollection [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::get_PropertiesToLoad()
0x135e8  ldstr    aSamaccountname_2// "samAccountName"
0x135ed  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x135f2  pop
0x135f3  ldarg.0
0x135f4  callvirt instance class [System]System.Collections.Specialized.StringCollection [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::get_PropertiesToLoad()
0x135f9  ldstr    aCn_0// "cn"
0x135fe  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x13603  pop
0x13604  ldarg.0
0x13605  callvirt instance class [System]System.Collections.Specialized.StringCollection [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::get_PropertiesToLoad()
0x1360a  ldstr    aObjectguid// "objectGuid"
0x1360f  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x13614  pop
0x13615  ldarg.0
0x13616  callvirt instance class [System]System.Collections.Specialized.StringCollection [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::get_PropertiesToLoad()
0x1361b  ldstr    aGivenname// "givenName"
0x13620  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x13625  pop
0x13626  ldarg.0
0x13627  callvirt instance class [System]System.Collections.Specialized.StringCollection [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::get_PropertiesToLoad()
0x1362c  ldstr    aSn// "sn"
0x13631  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x13636  pop
0x13637  ldarg.0
0x13638  callvirt instance class [System]System.Collections.Specialized.StringCollection [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::get_PropertiesToLoad()
0x1363d  ldstr    aObjectsid// "objectSid"
0x13642  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x13647  pop
0x13648  ret
```
