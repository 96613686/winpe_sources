# Microsoft.Crm.Caching.SavedQueryData::Initialize

- ea: `0x8ea60`
- end: `0x8eafb`
- name: `Microsoft.Crm.Caching.SavedQueryData::Initialize`
- size: `155`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x8eb10`
- `0x8eb30`
- `0x8eb50`
- `0x8eb70`
- `0x8eb90`
- `0x8ebb0`
- `0x8ec10`
- `0x9c500`

## string_xrefs

- `0x8eae6`: `componentstate`
- `0x8ea78`: `fetchxml`
- `0x8ea8e`: `layoutxml`

## pseudocode

```c

```

## disassembly

```asm
0x8ea60  ldarg.0
0x8ea61  ldarg.1
0x8ea62  ldstr    aSavedqueryid// "savedqueryid"
0x8ea67  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x8ea6c  unbox.any [mscorlib]System.Guid
0x8ea71  call     instance void Microsoft.Crm.Caching.SavedQueryData::set_SavedQueryId(valuetype [mscorlib]System.Guid value)
0x8ea76  ldarg.0
0x8ea77  ldarg.1
0x8ea78  ldstr    aFetchxml// "fetchxml"
0x8ea7d  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x8ea82  castclass [mscorlib]System.String
0x8ea87  call     instance void Microsoft.Crm.Caching.SavedQueryData::set_FetchXml(string value)
0x8ea8c  ldarg.0
0x8ea8d  ldarg.1
0x8ea8e  ldstr    aLayoutxml// "layoutxml"
0x8ea93  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x8ea98  castclass [mscorlib]System.String
0x8ea9d  call     instance void Microsoft.Crm.Caching.SavedQueryData::set_LayoutXml(string value)
0x8eaa2  ldarg.0
0x8eaa3  ldarg.1
0x8eaa4  ldstr    aReturnedtypeco// "returnedtypecode"
0x8eaa9  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x8eaae  unbox.any [mscorlib]System.Int32
0x8eab3  call     instance void Microsoft.Crm.Caching.SavedQueryData::set_ReturnedTypeCode(int32 value)
0x8eab8  ldarg.0
0x8eab9  ldarg.1
0x8eaba  ldstr    aSolutionid_0// "solutionid"
0x8eabf  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x8eac4  unbox.any [mscorlib]System.Guid
0x8eac9  call     instance void Microsoft.Crm.Caching.SavedQueryData::set_SolutionId(valuetype [mscorlib]System.Guid value)
0x8eace  ldarg.0
0x8eacf  ldarg.1
0x8ead0  ldstr    aIscustomizable_0// "iscustomizable"
0x8ead5  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x8eada  unbox.any [mscorlib]System.Boolean
0x8eadf  call     instance void Microsoft.Crm.Caching.SavedQueryData::set_IsCustomizable(bool value)
0x8eae4  ldarg.0
0x8eae5  ldarg.1
0x8eae6  ldstr    aComponentstate_1// "componentstate"
0x8eaeb  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x8eaf0  unbox.any Microsoft.Crm.Platform.ComponentState
0x8eaf5  call     instance void Microsoft.Crm.Caching.SavedQueryData::set_ComponentState(valuetype Microsoft.Crm.Platform.ComponentState value)
0x8eafa  ret
```
