# Microsoft.Crm.Authentication.UserManagementFactory::MergeDirectoryData

- ea: `0x11850`
- end: `0x11913`
- name: `Microsoft.Crm.Authentication.UserManagementFactory::MergeDirectoryData`
- size: `195`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x11850`
- `0x11920`
- `0x11970`

## string_xrefs

- `0x11891`: `azureactivedirectoryobjectid`
- `0x1185c`: `directoryObjectData`

## pseudocode

```c

```

## disassembly

```asm
0x11850  ldarg.1
0x11851  ldstr    aSystemuser// "systemUser"
0x11856  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1185b  ldarg.2
0x1185c  ldstr    aDirectoryobjec_1// "directoryObjectData"
0x11861  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x11866  call     class [System]System.Collections.Concurrent.ConcurrentBag`1<class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.DirectoryObjectMap> [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.MSOnlineMapping::get_MSOnlineUserAttributeMapping()
0x1186b  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [System]System.Collections.Concurrent.ConcurrentBag`1<class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.DirectoryObjectMap>::GetEnumerator()
0x11870  stloc.0
0x11871  br       loc_118FA
0x11876  ldloc.0
0x11877  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.DirectoryObjectMap>::get_Current()
0x1187c  stloc.1
0x1187d  ldarg.2
0x1187e  ldloc.1
0x1187f  callvirt instance string [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.DirectoryObjectMap::get_CrmPropertyName()
0x11884  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0x11889  brfalse.s loc_118FA
0x1188b  ldloc.1
0x1188c  callvirt instance string [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.DirectoryObjectMap::get_CrmPropertyName()
0x11891  ldstr    aAzureactivedir// "azureactivedirectoryobjectid"
0x11896  ldc.i4.3
0x11897  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x1189c  brfalse.s loc_118B8
0x1189e  ldarg.1
0x1189f  ldloc.1
0x118a0  callvirt instance string [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.DirectoryObjectMap::get_CrmPropertyName()
0x118a5  ldarg.2
0x118a6  ldloc.1
0x118a7  callvirt instance string [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.DirectoryObjectMap::get_CrmPropertyName()
0x118ac  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x118b1  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x118b6  br.s     loc_118FA
0x118b8  ldarg.2
0x118b9  ldloc.1
0x118ba  callvirt instance string [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.DirectoryObjectMap::get_CrmPropertyName()
0x118bf  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x118c4  castclass [mscorlib]System.String
0x118c9  stloc.2
0x118ca  ldloc.1
0x118cb  callvirt instance bool [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.DirectoryObjectMap::get_Required()
0x118d0  brtrue.s loc_118E0
0x118d2  ldarg.1
0x118d3  ldloc.1
0x118d4  callvirt instance string [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.DirectoryObjectMap::get_CrmPropertyName()
0x118d9  ldloc.2
0x118da  call     string Microsoft.Crm.Authentication.UserManagementFactory::TruncateAttributeValue(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity systemUser, string attributeName, string value)
0x118df  stloc.2
0x118e0  ldloc.1
0x118e1  callvirt instance string [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.DirectoryObjectMap::get_OsdpPropertyName()
0x118e6  ldloc.2
0x118e7  call     string Microsoft.Crm.Authentication.UserManagementFactory::HandleSpecialAttribute(string osdpPropertyName, string osdpValue)
0x118ec  stloc.2
0x118ed  ldarg.1
0x118ee  ldloc.1
0x118ef  callvirt instance string [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.DirectoryObjectMap::get_CrmPropertyName()
0x118f4  ldloc.2
0x118f5  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x118fa  ldloc.0
0x118fb  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x11900  brtrue   loc_11876
0x11905  leave.s  loc_11911
0x11907  ldloc.0
0x11908  brfalse.s loc_11910
0x1190a  ldloc.0
0x1190b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11910  endfinally
0x11911  ldarg.1
0x11912  ret
```
