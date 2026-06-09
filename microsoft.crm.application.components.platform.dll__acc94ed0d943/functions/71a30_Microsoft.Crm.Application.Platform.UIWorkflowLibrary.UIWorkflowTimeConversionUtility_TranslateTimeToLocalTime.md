# Microsoft.Crm.Application.Platform.UIWorkflowLibrary.UIWorkflowTimeConversionUtility::TranslateTimeToLocalTime

- ea: `0x71a30`
- end: `0x71aeb`
- name: `Microsoft.Crm.Application.Platform.UIWorkflowLibrary.UIWorkflowTimeConversionUtility::TranslateTimeToLocalTime`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x71af0`

## callees

- `0xfd20`
- `0x5be20`
- `0x5be40`
- `0x71a30`

## string_xrefs

- `0x71a73`: `createdon`
- `0x71a80`: `createdon`
- `0x71a90`: `createdon`
- `0x71aaf`: `completedon`
- `0x71abc`: `completedon`
- `0x71acc`: `completedon`

## pseudocode

```c

```

## disassembly

```asm
0x71a30  ldarg.0
0x71a31  brfalse  loc_71AEA
0x71a36  ldarg.0
0x71a37  ldstr    aStartedon// "startedon"
0x71a3c  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x71a41  brfalse.s loc_71A72
0x71a43  ldarg.0
0x71a44  ldstr    aStartedon// "startedon"
0x71a49  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser Microsoft.Crm.Security.User::get_Current()
0x71a4e  callvirt instance class [mscorlib]System.TimeZone [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_TimeZone()
0x71a53  ldarg.0
0x71a54  ldstr    aStartedon// "startedon"
0x71a59  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x71a5e  unbox.any [mscorlib]System.DateTime
0x71a63  callvirt instance valuetype [mscorlib]System.DateTime [mscorlib]System.TimeZone::ToLocalTime(valuetype [mscorlib]System.DateTime)
0x71a68  box      [mscorlib]System.DateTime
0x71a6d  callvirt instance void Microsoft.Crm.Application.Platform.EntityBase::set_Item(string name, object value)
0x71a72  ldarg.0
0x71a73  ldstr    aCreatedon// "createdon"
0x71a78  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x71a7d  brfalse.s loc_71AAE
0x71a7f  ldarg.0
0x71a80  ldstr    aCreatedon// "createdon"
0x71a85  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser Microsoft.Crm.Security.User::get_Current()
0x71a8a  callvirt instance class [mscorlib]System.TimeZone [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_TimeZone()
0x71a8f  ldarg.0
0x71a90  ldstr    aCreatedon// "createdon"
0x71a95  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x71a9a  unbox.any [mscorlib]System.DateTime
0x71a9f  callvirt instance valuetype [mscorlib]System.DateTime [mscorlib]System.TimeZone::ToLocalTime(valuetype [mscorlib]System.DateTime)
0x71aa4  box      [mscorlib]System.DateTime
0x71aa9  callvirt instance void Microsoft.Crm.Application.Platform.EntityBase::set_Item(string name, object value)
0x71aae  ldarg.0
0x71aaf  ldstr    aCompletedon// "completedon"
0x71ab4  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x71ab9  brfalse.s loc_71AEA
0x71abb  ldarg.0
0x71abc  ldstr    aCompletedon// "completedon"
0x71ac1  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser Microsoft.Crm.Security.User::get_Current()
0x71ac6  callvirt instance class [mscorlib]System.TimeZone [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_TimeZone()
0x71acb  ldarg.0
0x71acc  ldstr    aCompletedon// "completedon"
0x71ad1  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x71ad6  unbox.any [mscorlib]System.DateTime
0x71adb  callvirt instance valuetype [mscorlib]System.DateTime [mscorlib]System.TimeZone::ToLocalTime(valuetype [mscorlib]System.DateTime)
0x71ae0  box      [mscorlib]System.DateTime
0x71ae5  callvirt instance void Microsoft.Crm.Application.Platform.EntityBase::set_Item(string name, object value)
0x71aea  ret
```
