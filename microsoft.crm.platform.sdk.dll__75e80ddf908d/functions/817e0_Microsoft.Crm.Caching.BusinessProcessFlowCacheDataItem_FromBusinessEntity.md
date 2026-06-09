# Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::FromBusinessEntity

- ea: `0x817e0`
- end: `0x81b56`
- name: `Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::FromBusinessEntity`
- size: `886`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x814b0`
- `0x81590`

## callees

- `0x817e0`
- `0x81f50`
- `0x81f60`

## string_xrefs

- `0x819f8`: `triggeroncreate`
- `0x81a06`: `triggeroncreate`
- `0x81a1b`: `triggerondelete`
- `0x81a29`: `triggerondelete`
- `0x81a3e`: `triggeronupdateattributelist`
- `0x81a4c`: `triggeronupdateattributelist`

## pseudocode

```c

```

## disassembly

```asm
0x817e0  ldarg.1
0x817e1  ldstr    aBusinessproces// "businessprocesstype"
0x817e6  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x817eb  brtrue.s loc_81803
0x817ed  ldarg.0
0x817ee  ldarg.1
0x817ef  ldstr    aBusinessproces// "businessprocesstype"
0x817f4  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x817f9  unbox.any [mscorlib]System.Int32
0x817fe  stfld    int32 Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::_businessProcessType
0x81803  ldarg.1
0x81804  ldstr    aClientdata// "clientdata"
0x81809  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x8180e  brtrue.s loc_81826
0x81810  ldarg.0
0x81811  ldarg.1
0x81812  ldstr    aClientdata// "clientdata"
0x81817  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x8181c  castclass [mscorlib]System.String
0x81821  stfld    string Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::_clientData
0x81826  ldarg.1
0x81827  ldstr    aDescription// "description"
0x8182c  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x81831  brtrue.s loc_81849
0x81833  ldarg.0
0x81834  ldarg.1
0x81835  ldstr    aDescription// "description"
0x8183a  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x8183f  castclass [mscorlib]System.String
0x81844  stfld    string Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::_description
0x81849  ldarg.1
0x8184a  ldstr    aMode// "mode"
0x8184f  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x81854  brtrue.s loc_8186C
0x81856  ldarg.0
0x81857  ldarg.1
0x81858  ldstr    aMode// "mode"
0x8185d  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x81862  unbox.any [mscorlib]System.Int32
0x81867  stfld    int32 Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::_mode
0x8186c  ldarg.1
0x8186d  ldstr    aName_0// "name"
0x81872  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x81877  brtrue.s loc_8188F
0x81879  ldarg.0
0x8187a  ldarg.1
0x8187b  ldstr    aName_0// "name"
0x81880  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x81885  castclass [mscorlib]System.String
0x8188a  stfld    string Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::_name
0x8188f  ldarg.1
0x81890  ldstr    aOndemand// "ondemand"
0x81895  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x8189a  brtrue.s loc_818B2
0x8189c  ldarg.0
0x8189d  ldarg.1
0x8189e  ldstr    aOndemand// "ondemand"
0x818a3  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x818a8  unbox.any [mscorlib]System.Boolean
0x818ad  stfld    bool Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::_onDemand
0x818b2  ldarg.1
0x818b3  ldstr    aOwnerid// "ownerid"
0x818b8  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x818bd  brtrue.s loc_818D5
0x818bf  ldarg.0
0x818c0  ldarg.1
0x818c1  ldstr    aOwnerid// "ownerid"
0x818c6  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x818cb  unbox.any [mscorlib]System.Guid
0x818d0  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::_ownerId
0x818d5  ldarg.1
0x818d6  ldstr    aOwneridtype// "owneridtype"
0x818db  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x818e0  brtrue.s loc_818F8
0x818e2  ldarg.0
0x818e3  ldarg.1
0x818e4  ldstr    aOwneridtype// "owneridtype"
0x818e9  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x818ee  unbox.any [mscorlib]System.Int32
0x818f3  stfld    int32 Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::_ownerIdType
0x818f8  ldarg.1
0x818f9  ldstr    aOwningbusiness// "owningbusinessunit"
0x818fe  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x81903  brtrue.s loc_81920
0x81905  ldarg.0
0x81906  ldarg.1
0x81907  ldstr    aOwningbusiness// "owningbusinessunit"
0x8190c  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x81911  unbox.any [mscorlib]System.Guid
0x81916  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x8191b  stfld    valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::_owningBusinessUnit
0x81920  ldarg.1
0x81921  ldstr    aPrimaryentity_0// "primaryentity"
0x81926  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x8192b  brtrue.s loc_81943
0x8192d  ldarg.0
0x8192e  ldarg.1
0x8192f  ldstr    aPrimaryentity_0// "primaryentity"
0x81934  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x81939  unbox.any [mscorlib]System.Int32
0x8193e  stfld    int32 Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::_primaryEntity
0x81943  ldarg.1
0x81944  ldstr    aProcessorder// "processorder"
0x81949  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x8194e  brtrue.s loc_8196B
0x81950  ldarg.0
0x81951  ldarg.1
0x81952  ldstr    aProcessorder// "processorder"
0x81957  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x8195c  unbox.any [mscorlib]System.Int32
0x81961  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x81966  stfld    valuetype [mscorlib]System.Nullable`1<int32> Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::_processOrder
0x8196b  ldarg.1
0x8196c  ldstr    aProcessroleass// "processroleassignment"
0x81971  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x81976  brtrue.s loc_8198E
0x81978  ldarg.0
0x81979  ldarg.1
0x8197a  ldstr    aProcessroleass// "processroleassignment"
0x8197f  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x81984  castclass [mscorlib]System.String
0x81989  stfld    string Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::_processRolesAssignment
0x8198e  ldarg.1
0x8198f  ldstr    aScope// "scope"
0x81994  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x81999  brtrue.s loc_819B1
0x8199b  ldarg.0
0x8199c  ldarg.1
0x8199d  ldstr    aScope// "scope"
0x819a2  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x819a7  unbox.any [mscorlib]System.Int32
0x819ac  stfld    int32 Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::_scope
0x819b1  ldarg.1
0x819b2  ldstr    aStatecode// "statecode"
0x819b7  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x819bc  brtrue.s loc_819D4
0x819be  ldarg.0
0x819bf  ldarg.1
0x819c0  ldstr    aStatecode// "statecode"
0x819c5  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x819ca  unbox.any [mscorlib]System.Int32
0x819cf  stfld    int32 Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::_stateCode
0x819d4  ldarg.1
0x819d5  ldstr    aSubprocess// "subprocess"
0x819da  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x819df  brtrue.s loc_819F7
0x819e1  ldarg.0
0x819e2  ldarg.1
0x819e3  ldstr    aSubprocess// "subprocess"
0x819e8  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x819ed  unbox.any [mscorlib]System.Boolean
0x819f2  stfld    bool Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::_subprocess
0x819f7  ldarg.1
0x819f8  ldstr    aTriggeroncreat// "triggeroncreate"
0x819fd  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x81a02  brtrue.s loc_81A1A
0x81a04  ldarg.0
0x81a05  ldarg.1
0x81a06  ldstr    aTriggeroncreat// "triggeroncreate"
0x81a0b  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x81a10  unbox.any [mscorlib]System.Boolean
0x81a15  stfld    bool Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::_triggerOnCreate
0x81a1a  ldarg.1
0x81a1b  ldstr    aTriggerondelet// "triggerondelete"
0x81a20  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x81a25  brtrue.s loc_81A3D
0x81a27  ldarg.0
0x81a28  ldarg.1
0x81a29  ldstr    aTriggerondelet// "triggerondelete"
0x81a2e  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x81a33  unbox.any [mscorlib]System.Boolean
0x81a38  stfld    bool Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::_triggerOnDelete
0x81a3d  ldarg.1
0x81a3e  ldstr    aTriggeronupdat// "triggeronupdateattributelist"
0x81a43  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x81a48  brtrue.s loc_81A60
0x81a4a  ldarg.0
0x81a4b  ldarg.1
0x81a4c  ldstr    aTriggeronupdat// "triggeronupdateattributelist"
0x81a51  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x81a56  castclass [mscorlib]System.String
0x81a5b  stfld    string Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::_triggerOnUpdateAttributeList
0x81a60  ldarg.1
0x81a61  ldstr    aType// "type"
0x81a66  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x81a6b  brtrue.s loc_81A83
0x81a6d  ldarg.0
0x81a6e  ldarg.1
0x81a6f  ldstr    aType// "type"
0x81a74  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x81a79  unbox.any [mscorlib]System.Int32
0x81a7e  stfld    int32 Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::_type
0x81a83  ldarg.1
0x81a84  ldstr    aUidata// "uidata"
0x81a89  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x81a8e  brtrue.s loc_81AA6
0x81a90  ldarg.0
0x81a91  ldarg.1
0x81a92  ldstr    aUidata// "uidata"
0x81a97  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x81a9c  castclass [mscorlib]System.String
0x81aa1  stfld    string Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::_uIData
0x81aa6  ldarg.1
0x81aa7  ldstr    aUniquename_1// "uniquename"
0x81aac  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x81ab1  brtrue.s loc_81AC9
0x81ab3  ldarg.0
0x81ab4  ldarg.1
0x81ab5  ldstr    aUniquename_1// "uniquename"
0x81aba  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x81abf  castclass [mscorlib]System.String
0x81ac4  stfld    string Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::_uniqueName
0x81ac9  ldarg.1
0x81aca  ldstr    aVersionnumber// "versionnumber"
0x81acf  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x81ad4  brtrue.s loc_81AEC
0x81ad6  ldarg.0
0x81ad7  ldarg.1
0x81ad8  ldstr    aVersionnumber// "versionnumber"
0x81add  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x81ae2  unbox.any [mscorlib]System.Int64
0x81ae7  stfld    int64 Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::_versionNumber
0x81aec  ldarg.1
0x81aed  ldstr    aWorkflowid// "workflowid"
0x81af2  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x81af7  brtrue.s loc_81B0F
0x81af9  ldarg.0
0x81afa  ldarg.1
0x81afb  ldstr    aWorkflowid// "workflowid"
0x81b00  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x81b05  unbox.any [mscorlib]System.Guid
0x81b0a  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::_workflowId
0x81b0f  ldarg.1
0x81b10  ldstr    aCategory// "category"
0x81b15  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x81b1a  brtrue.s loc_81B32
0x81b1c  ldarg.0
0x81b1d  ldarg.1
0x81b1e  ldstr    aCategory// "category"
0x81b23  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x81b28  unbox.any [mscorlib]System.Int32
0x81b2d  stfld    int32 Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::_category
0x81b32  ldarg.1
0x81b33  ldstr    aXaml// "xaml"
0x81b38  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x81b3d  brtrue.s loc_81B55
0x81b3f  ldarg.0
0x81b40  ldarg.1
0x81b41  ldstr    aXaml// "xaml"
0x81b46  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x81b4b  castclass [mscorlib]System.String
0x81b50  stfld    string Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::_xaml
0x81b55  ret
```
