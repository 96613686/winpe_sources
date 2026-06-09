# Microsoft.Crm.Common.Application.Platform.ActivityBase::GetRecipientsPartyStatusType

- ea: `0x2a90`
- end: `0x2b6d`
- name: `Microsoft.Crm.Common.Application.Platform.ActivityBase::GetRecipientsPartyStatusType`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x2a30`

## callees

- `0x2940`
- `0x2a90`

## pseudocode

```c

```

## disassembly

```asm
0x2a90  ldc.i4.0
0x2a91  stloc.0
0x2a92  ldarg.0
0x2a93  ldarg.2
0x2a94  call     valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PartyStatusType Microsoft.Crm.Common.Application.Platform.ActivityBase::CheckPartyStatus(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection parties, string activityLogicalName)
0x2a99  ldarg.0
0x2a9a  brfalse  loc_2B45
0x2a9f  ldarg.0
0x2aa0  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x2aa5  ldc.i4.1
0x2aa6  bne.un   loc_2B45
0x2aab  ldarg.1
0x2aac  ldstr    aFrom// "from"
0x2ab1  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x2ab6  brtrue   loc_2B45
0x2abb  ldarg.0
0x2abc  ldc.i4.0
0x2abd  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0x2ac2  ldstr    aPartyid// "partyid"
0x2ac7  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x2acc  brfalse.s loc_2B45
0x2ace  ldarg.0
0x2acf  ldc.i4.0
0x2ad0  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0x2ad5  ldstr    aPartyid// "partyid"
0x2ada  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x2adf  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0x2ae4  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_Type()
0x2ae9  ldc.i4.8
0x2aea  bne.un.s loc_2B45
0x2aec  ldloca.s 1
0x2aee  ldarg.0
0x2aef  ldc.i4.0
0x2af0  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0x2af5  ldstr    aPartyid// "partyid"
0x2afa  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x2aff  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0x2b04  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0x2b09  call     instance void [mscorlib]System.Guid::.ctor(string)
0x2b0e  ldloc.1
0x2b0f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2b14  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserId()
0x2b19  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2b1e  brfalse.s loc_2B45
0x2b20  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache::Instance()
0x2b25  ldloc.1
0x2b26  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2b2b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x2b30  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x2b35  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser>::LookupEntry(void, var<u1>)
0x2b3a  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_IsSendAsAllowed()
0x2b3f  brtrue.s loc_2B45
0x2b41  ldloc.0
0x2b42  ldc.i4.8
0x2b43  or
0x2b44  stloc.0
0x2b45  dup
0x2b46  ldc.i4.2
0x2b47  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x2b4c  brfalse.s loc_2B52
0x2b4e  ldloc.0
0x2b4f  ldc.i4.2
0x2b50  or
0x2b51  stloc.0
0x2b52  dup
0x2b53  ldc.i4.1
0x2b54  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x2b59  brfalse.s loc_2B5F
0x2b5b  ldloc.0
0x2b5c  ldc.i4.1
0x2b5d  or
0x2b5e  stloc.0
0x2b5f  ldc.i4.4
0x2b60  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x2b65  brfalse.s loc_2B6B
0x2b67  ldloc.0
0x2b68  ldc.i4.4
0x2b69  or
0x2b6a  stloc.0
0x2b6b  ldloc.0
0x2b6c  ret
```
