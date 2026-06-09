# Microsoft.Crm.ObjectModel.AuthInfoCrmOnlineProvider::GetValidAuthInfo

- ea: `0x58580`
- end: `0x588a9`
- name: `Microsoft.Crm.ObjectModel.AuthInfoCrmOnlineProvider::GetValidAuthInfo`
- size: `809`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x58580`
- `0x5e950`
- `0x5e960`
- `0x5ea90`
- `0x5ead0`
- `0x5eb20`

## string_xrefs

- `0x585e2`: `DirectoryObjectId`
- `0x58631`: `DirectoryObjectId`
- `0x5863e`: `DirectoryObjectId`
- `0x585fa`: `LastAccessServer`
- `0x5869d`: `LastAccessServer`
- `0x586aa`: `LastAccessServer`
- `0x58602`: `LastAccessTime`
- `0x586c1`: `LastAccessTime`
- `0x586ce`: `LastAccessTime`
- `0x5860a`: `IsDeleted`
- `0x586f5`: `IsDeleted`
- `0x58702`: `IsDeleted`
- `0x58618`: `D:\a\1\s\src\Core\ObjectModel\Services\AuthenticationProviders\AuthInfoProviders.cs`
- `0x587a6`: `D:\a\1\s\src\Core\ObjectModel\Services\AuthenticationProviders\AuthInfoProviders.cs`

## pseudocode

```c

```

## disassembly

```asm
0x58580  ldarg.2
0x58581  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x58586  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x5858b  brfalse  loc_5888A
0x58590  ldarg.1
0x58591  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x58596  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x5859b  brfalse  loc_5888A
0x585a0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x585a5  stloc.0
0x585a6  ldloc.0
0x585a7  ldstr    aCrmuserid// "CrmUserId"
0x585ac  ldarg.1
0x585ad  box      [mscorlib]System.Guid
0x585b2  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x585b7  ldloc.0
0x585b8  ldstr    aOrganizationid_5// "OrganizationId"
0x585bd  ldarg.2
0x585be  box      [mscorlib]System.Guid
0x585c3  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x585c8  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x585cd  ldstr    aSystemuserorga// "SystemUserOrganizations"
0x585d2  ldc.i4.7
0x585d3  newarr   [mscorlib]System.String
0x585d8  dup
0x585d9  ldc.i4.0
0x585da  ldstr    aUserid_0// "UserId"
0x585df  stelem.ref
0x585e0  dup
0x585e1  ldc.i4.1
0x585e2  ldstr    aDirectoryobjec// "DirectoryObjectId"
0x585e7  stelem.ref
0x585e8  dup
0x585e9  ldc.i4.2
0x585ea  ldstr    aIsdisabled_0// "IsDisabled"
0x585ef  stelem.ref
0x585f0  dup
0x585f1  ldc.i4.3
0x585f2  ldstr    aIslicensed// "IsLicensed"
0x585f7  stelem.ref
0x585f8  dup
0x585f9  ldc.i4.4
0x585fa  ldstr    aLastaccessserv// "LastAccessServer"
0x585ff  stelem.ref
0x58600  dup
0x58601  ldc.i4.5
0x58602  ldstr    aLastaccesstime// "LastAccessTime"
0x58607  stelem.ref
0x58608  dup
0x58609  ldc.i4.6
0x5860a  ldstr    aIsdeleted// "IsDeleted"
0x5860f  stelem.ref
0x58610  ldloc.0
0x58611  ldc.i4.s 0x4A
0x58613  ldstr    aGetvalidauthin// "GetValidAuthInfo"
0x58618  ldstr    aDA1SSrcCoreObj_9// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Se"...
0x5861d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::RetrieveSingleRow(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x58622  stloc.1
0x58623  ldloc.1
0x58624  brfalse  loc_58872
0x58629  call     class Microsoft.Crm.ObjectModel.AuthenticationProviderEventSource Microsoft.Crm.ObjectModel.AuthenticationProviderEventSource::get_Instance()
0x5862e  ldarg.2
0x5862f  ldarg.1
0x58630  ldloc.1
0x58631  ldstr    aDirectoryobjec// "DirectoryObjectId"
0x58636  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x5863b  brfalse.s loc_5864F
0x5863d  ldloc.1
0x5863e  ldstr    aDirectoryobjec// "DirectoryObjectId"
0x58643  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x58648  callvirt instance string [mscorlib]System.Object::ToString()
0x5864d  br.s     loc_58654
0x5864f  ldsfld   string [mscorlib]System.String::Empty
0x58654  ldloc.1
0x58655  ldstr    aIsdisabled_0// "IsDisabled"
0x5865a  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x5865f  brfalse.s loc_58673
0x58661  ldloc.1
0x58662  ldstr    aIsdisabled_0// "IsDisabled"
0x58667  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x5866c  callvirt instance string [mscorlib]System.Object::ToString()
0x58671  br.s     loc_58678
0x58673  ldsfld   string [mscorlib]System.String::Empty
0x58678  ldloc.1
0x58679  ldstr    aIslicensed// "IsLicensed"
0x5867e  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x58683  brfalse.s loc_58697
0x58685  ldloc.1
0x58686  ldstr    aIslicensed// "IsLicensed"
0x5868b  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x58690  callvirt instance string [mscorlib]System.Object::ToString()
0x58695  br.s     loc_5869C
0x58697  ldsfld   string [mscorlib]System.String::Empty
0x5869c  ldloc.1
0x5869d  ldstr    aLastaccessserv// "LastAccessServer"
0x586a2  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x586a7  brfalse.s loc_586BB
0x586a9  ldloc.1
0x586aa  ldstr    aLastaccessserv// "LastAccessServer"
0x586af  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x586b4  callvirt instance string [mscorlib]System.Object::ToString()
0x586b9  br.s     loc_586C0
0x586bb  ldsfld   string [mscorlib]System.String::Empty
0x586c0  ldloc.1
0x586c1  ldstr    aLastaccesstime// "LastAccessTime"
0x586c6  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x586cb  brfalse.s loc_586E7
0x586cd  ldloc.1
0x586ce  ldstr    aLastaccesstime// "LastAccessTime"
0x586d3  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x586d8  unbox.any [mscorlib]System.DateTime
0x586dd  stloc.3
0x586de  ldloca.s 3
0x586e0  call     instance string [mscorlib]System.DateTime::ToString()
0x586e5  br.s     loc_586F4
0x586e7  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x586ec  stloc.3
0x586ed  ldloca.s 3
0x586ef  call     instance string [mscorlib]System.DateTime::ToString()
0x586f4  ldloc.1
0x586f5  ldstr    aIsdeleted// "IsDeleted"
0x586fa  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x586ff  brfalse.s loc_58713
0x58701  ldloc.1
0x58702  ldstr    aIsdeleted// "IsDeleted"
0x58707  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x5870c  callvirt instance string [mscorlib]System.Object::ToString()
0x58711  br.s     loc_58718
0x58713  ldsfld   string [mscorlib]System.String::Empty
0x58718  ldloc.1
0x58719  ldstr    aUserid_0// "UserId"
0x5871e  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x58723  brfalse.s loc_58737
0x58725  ldloc.1
0x58726  ldstr    aUserid_0// "UserId"
0x5872b  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x58730  unbox.any [mscorlib]System.Guid
0x58735  br.s     loc_5873C
0x58737  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5873c  callvirt instance void Microsoft.Crm.ObjectModel.AuthenticationProviderEventSource::LogSystemUserOrganizationsInfo(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid CrmUserId, string DirectoryObjectId, string IsDisabled, string IsLicensed, string LastAccessServer, string LastAccessTime, string IsDeleted, valuetype [mscorlib]System.Guid UserId)
0x58741  ldloc.1
0x58742  ldstr    aUserid_0// "UserId"
0x58747  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x5874c  unbox.any [mscorlib]System.Guid
0x58751  stloc.2
0x58752  ldloca.s 2
0x58754  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x58759  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0x5875e  brtrue   loc_5885A
0x58763  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x58768  stloc.s  4
0x5876a  ldloc.s  4
0x5876c  ldstr    aUserid_0// "UserId"
0x58771  ldloc.2
0x58772  box      [mscorlib]System.Guid
0x58777  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x5877c  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x58781  ldstr    aSystemuserauth// "SystemUserAuthentication"
0x58786  ldc.i4.1
0x58787  newarr   [mscorlib]System.String
0x5878c  dup
0x5878d  ldc.i4.0
0x5878e  ldstr    aAuthinfo// "AuthInfo"
0x58793  stelem.ref
0x58794  ldc.i4.1
0x58795  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x5879a  dup
0x5879b  ldc.i4.0
0x5879c  ldloc.s  4
0x5879e  stelem.ref
0x5879f  ldc.i4.s 0x61
0x587a1  ldstr    aGetvalidauthin// "GetValidAuthInfo"
0x587a6  ldstr    aDA1SSrcCoreObj_9// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Se"...
0x587ab  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x587b0  stloc.s  5
0x587b2  ldloc.s  5
0x587b4  brfalse  loc_58842
0x587b9  call     class Microsoft.Crm.ObjectModel.AuthenticationProviderEventSource Microsoft.Crm.ObjectModel.AuthenticationProviderEventSource::get_Instance()
0x587be  ldarg.2
0x587bf  ldloc.s  5
0x587c1  ldc.i4.1
0x587c2  call     string [Newtonsoft.Json]Newtonsoft.Json.JsonConvert::SerializeObject(object, valuetype [Newtonsoft.Json]Newtonsoft.Json.Formatting)
0x587c7  ldloc.s  5
0x587c9  callvirt instance int32 class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Count()
0x587ce  callvirt instance void Microsoft.Crm.ObjectModel.AuthenticationProviderEventSource::LogSystemUserAuthenticationInfo(valuetype [mscorlib]System.Guid organizationId, string EventDetails, int32 Count)
0x587d3  ldloc.s  5
0x587d5  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x587da  stloc.s  6
0x587dc  ldloca.s 6
0x587de  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x587e3  brfalse.s loc_58832
0x587e5  ldloca.s 6
0x587e7  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x587ec  stloc.s  8
0x587ee  ldloca.s 8
0x587f0  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Value()
0x587f5  stloc.s  7
0x587f7  call     class Microsoft.Crm.ObjectModel.AuthenticationProviderEventSource Microsoft.Crm.ObjectModel.AuthenticationProviderEventSource::get_Instance()
0x587fc  ldarg.2
0x587fd  ldstr    aRetrieveauthin// "RetrieveAuthInfo"
0x58802  ldstr    aAuthentication_0// "Authentication Info"
0x58807  ldloc.s  7
0x58809  ldstr    aAuthinfo// "AuthInfo"
0x5880e  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x58813  castclass [mscorlib]System.String
0x58818  callvirt instance void Microsoft.Crm.ObjectModel.AuthenticationProviderEventSource::LogInformation(valuetype [mscorlib]System.Guid organizationId, string CallingMethod, string EventName, string EventDetails)
0x5881d  ldloc.s  7
0x5881f  ldstr    aAuthinfo// "AuthInfo"
0x58824  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x58829  castclass [mscorlib]System.String
0x5882e  stloc.s  9
0x58830  leave.s  loc_588A6
0x58832  leave.s  loc_588A0
0x58834  ldloca.s 6
0x58836  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x5883c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x58841  endfinally
0x58842  call     class Microsoft.Crm.ObjectModel.AuthenticationProviderEventSource Microsoft.Crm.ObjectModel.AuthenticationProviderEventSource::get_Instance()
0x58847  ldarg.2
0x58848  ldstr    aRetrieveauthin// "RetrieveAuthInfo"
0x5884d  ldc.i4.0
0x5884e  ldstr    aUseridIsEmpty// "UserId is Empty"
0x58853  callvirt instance void Microsoft.Crm.ObjectModel.AuthenticationProviderEventSource::LogError(valuetype [mscorlib]System.Guid organizationId, string CallingMethod, int32 CrmErrorCode, string ErrorDetails)
0x58858  br.s     loc_588A0
0x5885a  call     class Microsoft.Crm.ObjectModel.AuthenticationProviderEventSource Microsoft.Crm.ObjectModel.AuthenticationProviderEventSource::get_Instance()
0x5885f  ldarg.2
0x58860  ldstr    aRetrieveauthin// "RetrieveAuthInfo"
0x58865  ldc.i4.0
0x58866  ldstr    aUseridIsEmpty// "UserId is Empty"
0x5886b  callvirt instance void Microsoft.Crm.ObjectModel.AuthenticationProviderEventSource::LogError(valuetype [mscorlib]System.Guid organizationId, string CallingMethod, int32 CrmErrorCode, string ErrorDetails)
0x58870  br.s     loc_588A0
0x58872  call     class Microsoft.Crm.ObjectModel.AuthenticationProviderEventSource Microsoft.Crm.ObjectModel.AuthenticationProviderEventSource::get_Instance()
0x58877  ldarg.2
0x58878  ldstr    aRetrieveauthin// "RetrieveAuthInfo"
0x5887d  ldc.i4.0
0x5887e  ldstr    aSystemuserorga_0// "SystemUserOrganizations Property Bag is"...
0x58883  callvirt instance void Microsoft.Crm.ObjectModel.AuthenticationProviderEventSource::LogError(valuetype [mscorlib]System.Guid organizationId, string CallingMethod, int32 CrmErrorCode, string ErrorDetails)
0x58888  br.s     loc_588A0
0x5888a  call     class Microsoft.Crm.ObjectModel.AuthenticationProviderEventSource Microsoft.Crm.ObjectModel.AuthenticationProviderEventSource::get_Instance()
0x5888f  ldarg.2
0x58890  ldstr    aRetrieveauthin// "RetrieveAuthInfo"
0x58895  ldc.i4.0
0x58896  ldstr    aOrganizationid_6// "OrganizationId OR CallerId not present "...
0x5889b  callvirt instance void Microsoft.Crm.ObjectModel.AuthenticationProviderEventSource::LogError(valuetype [mscorlib]System.Guid organizationId, string CallingMethod, int32 CrmErrorCode, string ErrorDetails)
0x588a0  ldsfld   string [mscorlib]System.String::Empty
0x588a5  ret
0x588a6  ldloc.s  9
0x588a8  ret
```
