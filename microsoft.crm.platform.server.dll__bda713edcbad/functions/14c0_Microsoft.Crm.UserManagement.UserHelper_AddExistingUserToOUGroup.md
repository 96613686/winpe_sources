# Microsoft.Crm.UserManagement.UserHelper::AddExistingUserToOUGroup

- ea: `0x14c0`
- end: `0x16bc`
- name: `Microsoft.Crm.UserManagement.UserHelper::AddExistingUserToOUGroup`
- size: `508`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1480`

## callees

- `0xe40`
- `0x1230`
- `0x1270`
- `0x1350`
- `0x1370`
- `0x13b0`
- `0x14c0`
- `0x85d50`

## string_xrefs

- `0x14cc`: `adOUGroupNameLDAPPath`
- `0x14e6`: `Update Active Directory properties for entry `
- `0x162d`: `Attempting to add user using distinguished name. DN = {0}, Account Name = {1}`
- `0x16a4`: `Update completed`

## pseudocode

```c

```

## disassembly

```asm
0x14c0  ldarg.1
0x14c1  ldstr    aUser// "user"
0x14c6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x14cb  ldarg.2
0x14cc  ldstr    aAdougroupnamel// "adOUGroupNameLDAPPath"
0x14d1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x14d6  ldarg.2
0x14d7  newobj   instance void [System.DirectoryServices]System.DirectoryServices.DirectoryEntry::.ctor(string)
0x14dc  stloc.0
0x14dd  newobj   instance void <>c__DisplayClass1_0::.ctor()
0x14e2  stloc.1
0x14e3  ldarg.0
0x14e4  ldc.i4.s 0x14
0x14e6  ldstr    aUpdateActiveDi// "Update Active Directory properties for "...
0x14eb  ldc.i4.1
0x14ec  newarr   [mscorlib]System.Object
0x14f1  dup
0x14f2  ldc.i4.0
0x14f3  ldloc.0
0x14f4  callvirt instance string [System.DirectoryServices]System.DirectoryServices.DirectoryEntry::get_Path()
0x14f9  stelem.ref
0x14fa  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x14ff  ldarg.0
0x1500  ldc.i4.s 0x14
0x1502  ldstr    a0// "{0}"
0x1507  ldc.i4.1
0x1508  newarr   [mscorlib]System.Object
0x150d  dup
0x150e  ldc.i4.0
0x150f  ldstr    aPopulateWithUs// "Populate with user"
0x1514  stelem.ref
0x1515  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x151a  ldarg.0
0x151b  ldc.i4.s 0x14
0x151d  ldstr    a0// "{0}"
0x1522  ldc.i4.1
0x1523  newarr   [mscorlib]System.Object
0x1528  dup
0x1529  ldc.i4.0
0x152a  ldstr    aUpdatingMember// "Updating membership"
0x152f  stelem.ref
0x1530  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1535  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x153a  stloc.2
0x153b  ldloc.0
0x153c  callvirt instance class [System.DirectoryServices]System.DirectoryServices.PropertyCollection [System.DirectoryServices]System.DirectoryServices.DirectoryEntry::get_Properties()
0x1541  ldstr    aMember// "member"
0x1546  callvirt instance class [System.DirectoryServices]System.DirectoryServices.PropertyValueCollection [System.DirectoryServices]System.DirectoryServices.PropertyCollection::get_Item(string)
0x154b  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x1550  stloc.s  5
0x1552  br.s     loc_156A
0x1554  ldloc.s  5
0x1556  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x155b  castclass [mscorlib]System.String
0x1560  stloc.s  6
0x1562  ldloc.2
0x1563  ldloc.s  6
0x1565  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x156a  ldloc.s  5
0x156c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1571  brtrue.s loc_1554
0x1573  leave.s  loc_158A
0x1575  ldloc.s  5
0x1577  isinst   [mscorlib]System.IDisposable
0x157c  stloc.s  7
0x157e  ldloc.s  7
0x1580  brfalse.s loc_1589
0x1582  ldloc.s  7
0x1584  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1589  endfinally
0x158a  ldarg.1
0x158b  callvirt instance class Microsoft.Crm.UserManagement.DomainAccount Microsoft.Crm.UserManagement.User::get_DBDomainName()
0x1590  callvirt instance string Microsoft.Crm.UserManagement.DomainAccount::get_DomainAndAccount()
0x1595  stloc.3
0x1596  ldarg.1
0x1597  callvirt instance class Microsoft.Crm.UserManagement.DomainAccount Microsoft.Crm.UserManagement.User::get_ADDomainAccount()
0x159c  callvirt instance string Microsoft.Crm.UserManagement.DomainAccount::get_DomainAndAccount()
0x15a1  stloc.s  4
0x15a3  ldarg.0
0x15a4  ldc.i4.s 0x14
0x15a6  ldstr    aOldAccount// "Old account "
0x15ab  ldc.i4.1
0x15ac  newarr   [mscorlib]System.Object
0x15b1  dup
0x15b2  ldc.i4.0
0x15b3  ldloc.3
0x15b4  stelem.ref
0x15b5  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x15ba  ldarg.0
0x15bb  ldc.i4.s 0x14
0x15bd  ldstr    aAddingNewAccou// "Adding new account "
0x15c2  ldc.i4.1
0x15c3  newarr   [mscorlib]System.Object
0x15c8  dup
0x15c9  ldc.i4.0
0x15ca  ldloc.s  4
0x15cc  stelem.ref
0x15cd  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x15d2  ldloc.1
0x15d3  ldarg.1
0x15d4  callvirt instance string Microsoft.Crm.UserManagement.User::get_ADDistinguishedName()
0x15d9  stfld    string <>c__DisplayClass1_0::dn
0x15de  ldarg.0
0x15df  ldc.i4.s 0x14
0x15e1  ldstr    aFoundDn// "Found dn "
0x15e6  ldc.i4.1
0x15e7  newarr   [mscorlib]System.Object
0x15ec  dup
0x15ed  ldc.i4.0
0x15ee  ldloc.1
0x15ef  ldfld    string <>c__DisplayClass1_0::dn
0x15f4  stelem.ref
0x15f5  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x15fa  ldloc.1
0x15fb  ldfld    string <>c__DisplayClass1_0::dn
0x1600  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1605  brtrue.s loc_161B
0x1607  ldloc.2
0x1608  ldloc.1
0x1609  ldftn    instance bool <>c__DisplayClass1_0::<AddExistingUserToOUGroup>b__0(string existingMember)
0x160f  newobj   instance void class [mscorlib]System.Predicate`1<string>::.ctor(object, native int)
0x1614  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Exists(class [mscorlib]System.Predicate`1<var<u1>>)
0x1619  br.s     loc_161C
0x161b  ldc.i4.0
0x161c  brtrue.s loc_1694
0x161e  ldloc.2
0x161f  ldloc.1
0x1620  ldfld    string <>c__DisplayClass1_0::dn
0x1625  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x162a  ldarg.0
0x162b  ldc.i4.s 0x14
0x162d  ldstr    aAttemptingToAd// "Attempting to add user using distinguis"...
0x1632  ldc.i4.2
0x1633  newarr   [mscorlib]System.Object
0x1638  dup
0x1639  ldc.i4.0
0x163a  ldloc.1
0x163b  ldfld    string <>c__DisplayClass1_0::dn
0x1640  stelem.ref
0x1641  dup
0x1642  ldc.i4.1
0x1643  ldloc.s  4
0x1645  stelem.ref
0x1646  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x164b  ldarg.1
0x164c  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.UserManagement.User::get_ADObjectGuid()
0x1651  ldarg.1
0x1652  callvirt instance class [mscorlib]System.Security.Principal.SecurityIdentifier Microsoft.Crm.UserManagement.User::get_UserSid()
0x1657  stloc.s  8
0x1659  ldloc.s  8
0x165b  ldloc.0
0x165c  callvirt instance valuetype [mscorlib]System.Guid [System.DirectoryServices]System.DirectoryServices.DirectoryEntry::get_Guid()
0x1661  call     void [Microsoft.Crm.ADUtility]Microsoft.Crm.SecurityUtils::AddPrincipalToGroup(valuetype [mscorlib]System.Guid, class [mscorlib]System.Security.Principal.SecurityIdentifier, valuetype [mscorlib]System.Guid)
0x1666  leave.s  loc_1694
0x1668  stloc.s  9
0x166a  ldloc.s  9
0x166c  ldarg.0
0x166d  ldc.i4.s 0x14
0x166f  ldstr    aFailedToAddUse// "Failed to add user using the Distinguis"...
0x1674  ldc.i4.3
0x1675  newarr   [mscorlib]System.Object
0x167a  dup
0x167b  ldc.i4.0
0x167c  ldloc.1
0x167d  ldfld    string <>c__DisplayClass1_0::dn
0x1682  stelem.ref
0x1683  dup
0x1684  ldc.i4.1
0x1685  ldloc.s  4
0x1687  stelem.ref
0x1688  dup
0x1689  ldc.i4.2
0x168a  ldloc.s  9
0x168c  stelem.ref
0x168d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1692  rethrow
0x1694  ldarg.0
0x1695  ldc.i4.s 0x14
0x1697  ldstr    a0// "{0}"
0x169c  ldc.i4.1
0x169d  newarr   [mscorlib]System.Object
0x16a2  dup
0x16a3  ldc.i4.0
0x16a4  ldstr    aUpdateComplete// "Update completed"
0x16a9  stelem.ref
0x16aa  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x16af  leave.s  loc_16BB
0x16b1  ldloc.0
0x16b2  brfalse.s loc_16BA
0x16b4  ldloc.0
0x16b5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x16ba  endfinally
0x16bb  ret
```
