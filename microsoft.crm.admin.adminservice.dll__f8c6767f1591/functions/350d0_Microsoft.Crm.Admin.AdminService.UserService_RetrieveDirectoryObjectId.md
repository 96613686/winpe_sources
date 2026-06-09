# Microsoft.Crm.Admin.AdminService.UserService::RetrieveDirectoryObjectId

- ea: `0x350d0`
- end: `0x35221`
- name: `Microsoft.Crm.Admin.AdminService.UserService::RetrieveDirectoryObjectId`
- size: `337`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x350d0`

## string_xrefs

- `0x3511b`: `D:\a\1\s\src\CrmLive\Admin\Security\UserService.cs`
- `0x35194`: `D:\a\1\s\src\CrmLive\Admin\Security\UserService.cs`
- `0x35116`: `RetrieveDirectoryObjectId`
- `0x3518f`: `RetrieveDirectoryObjectId`
- `0x3517a`: `DirectoryObjectId`
- `0x351d4`: `DirectoryObjectId`
- `0x351e2`: `DirectoryObjectId`

## pseudocode

```c

```

## disassembly

```asm
0x350d0  ldarg.0
0x350d1  ldstr    aAuthinfo_0// "authInfo"
0x350d6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x350db  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x350e0  stloc.0
0x350e1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x350e6  stloc.1
0x350e7  ldloc.1
0x350e8  ldstr    aAuthinfo// "AuthInfo"
0x350ed  ldarg.0
0x350ee  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x350f3  ldloc.0
0x350f4  ldstr    aSystemuserauth// "SystemUserAuthentication"
0x350f9  ldc.i4.1
0x350fa  newarr   [mscorlib]System.String
0x350ff  dup
0x35100  ldc.i4.0
0x35101  ldstr    aUserid// "UserId"
0x35106  stelem.ref
0x35107  ldc.i4.1
0x35108  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x3510d  dup
0x3510e  ldc.i4.0
0x3510f  ldloc.1
0x35110  stelem.ref
0x35111  ldc.i4   0xA6
0x35116  ldstr    aRetrievedirect_0// "RetrieveDirectoryObjectId"
0x3511b  ldstr    aDA1SSrcCrmlive_62// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x35120  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x35125  stloc.2
0x35126  ldloc.2
0x35127  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection::IsNullOrEmpty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection)
0x3512c  brfalse.s loc_3513A
0x3512e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x35133  stloc.s  6
0x35135  leave    loc_3521E
0x3513a  ldloc.2
0x3513b  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x35140  call     T0x2B00005D
0x35145  ldstr    aUserid// "UserId"
0x3514a  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x3514f  unbox.any [mscorlib]System.Guid
0x35154  stloc.3
0x35155  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x3515a  stloc.1
0x3515b  ldloc.1
0x3515c  ldstr    aUserid// "UserId"
0x35161  ldloc.3
0x35162  box      [mscorlib]System.Guid
0x35167  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x3516c  ldloc.0
0x3516d  ldstr    aSystemuserorga// "SystemUserOrganizations"
0x35172  ldc.i4.1
0x35173  newarr   [mscorlib]System.String
0x35178  dup
0x35179  ldc.i4.0
0x3517a  ldstr    aDirectoryobjec_4// "DirectoryObjectId"
0x3517f  stelem.ref
0x35180  ldc.i4.1
0x35181  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x35186  dup
0x35187  ldc.i4.0
0x35188  ldloc.1
0x35189  stelem.ref
0x3518a  ldc.i4   0xB1
0x3518f  ldstr    aRetrievedirect_0// "RetrieveDirectoryObjectId"
0x35194  ldstr    aDA1SSrcCrmlive_62// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Secur"...
0x35199  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x3519e  stloc.s  4
0x351a0  ldloc.s  4
0x351a2  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection::IsNullOrEmpty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection)
0x351a7  brfalse.s loc_351B2
0x351a9  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x351ae  stloc.s  6
0x351b0  leave.s  loc_3521E
0x351b2  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x351b7  stloc.s  5
0x351b9  ldloc.s  4
0x351bb  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x351c0  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x351c5  stloc.s  7
0x351c7  br.s     loc_351F5
0x351c9  ldloca.s 7
0x351cb  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x351d0  stloc.s  8
0x351d2  ldloc.s  8
0x351d4  ldstr    aDirectoryobjec_4// "DirectoryObjectId"
0x351d9  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x351de  brfalse.s loc_351F5
0x351e0  ldloc.s  8
0x351e2  ldstr    aDirectoryobjec_4// "DirectoryObjectId"
0x351e7  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x351ec  unbox.any [mscorlib]System.Guid
0x351f1  stloc.s  5
0x351f3  leave.s  loc_3520E
0x351f5  ldloca.s 7
0x351f7  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x351fc  brtrue.s loc_351C9
0x351fe  leave.s  loc_3520E
0x35200  ldloca.s 7
0x35202  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x35208  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3520d  endfinally
0x3520e  ldloc.s  5
0x35210  stloc.s  6
0x35212  leave.s  loc_3521E
0x35214  ldloc.0
0x35215  brfalse.s loc_3521D
0x35217  ldloc.0
0x35218  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3521d  endfinally
0x3521e  ldloc.s  6
0x35220  ret
```
