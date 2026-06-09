# Microsoft.Crm.Application.Platform.Notifications.NotifiationGenerators.RecordDisabledMergedNotificationGenerator::AddNotificationIfNecessary

- ea: `0x81e10`
- end: `0x81f39`
- name: `Microsoft.Crm.Application.Platform.Notifications.NotifiationGenerators.RecordDisabledMergedNotificationGenerator::AddNotificationIfNecessary`
- size: `297`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x11760`
- `0x30260`
- `0x30e50`
- `0x30e70`
- `0x3a980`
- `0x5b890`
- `0x5bab0`
- `0x5be20`
- `0x6a2e0`
- `0x81e10`

## string_xrefs

- `0x81e71`: `<span class="ms-crm-Lookup-Item" onclick="openObj({0},this.getAttribute('oid'))" oid="{1}">{2}</span>`
- `0x81f1e`: `Merged_Record_Warning_Master_Deleted`

## pseudocode

```c

```

## disassembly

```asm
0x81e10  ldarg.1
0x81e11  callvirt instance bool Microsoft.Crm.Application.Platform.EntityBase::get_Disabled()
0x81e16  brfalse  loc_81F38
0x81e1b  ldarg.1
0x81e1c  ldstr    aMerged// "merged"
0x81e21  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x81e26  unbox.any [mscorlib]System.Boolean
0x81e2b  brfalse  loc_81F38
0x81e30  ldarg.1
0x81e31  ldstr    aMasterid// "masterid"
0x81e36  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x81e3b  castclass Microsoft.Crm.Application.Types.LookupValue
0x81e40  stloc.0
0x81e41  ldloc.0
0x81e42  brfalse  loc_81F19
0x81e47  ldloc.0
0x81e48  callvirt instance string Microsoft.Crm.Application.Types.LookupValue::get_Name()
0x81e4d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x81e52  brfalse.s loc_81E65
0x81e54  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x81e59  ldstr    aFormTitleUnkno// "Form_Title_Unknown"
0x81e5e  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x81e63  br.s     loc_81E6B
0x81e65  ldloc.0
0x81e66  callvirt instance string Microsoft.Crm.Application.Types.LookupValue::get_Name()
0x81e6b  stloc.1
0x81e6c  call     class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x81e71  ldstr    aSpanClassMsCrm_1// "<span class=\"ms-crm-Lookup-Item\" oncl"...
0x81e76  ldc.i4.3
0x81e77  newarr   [mscorlib]System.Object
0x81e7c  dup
0x81e7d  ldc.i4.0
0x81e7e  ldarg.1
0x81e7f  callvirt instance class Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x81e84  callvirt instance int32 Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0x81e89  stloc.s  7
0x81e8b  ldloca.s 7
0x81e8d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x81e92  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x81e97  stelem.ref
0x81e98  dup
0x81e99  ldc.i4.1
0x81e9a  ldloc.0
0x81e9b  callvirt instance string Microsoft.Crm.Application.Types.LookupValue::get_ID()
0x81ea0  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x81ea5  stelem.ref
0x81ea6  dup
0x81ea7  ldc.i4.2
0x81ea8  ldloc.1
0x81ea9  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x81eae  stelem.ref
0x81eaf  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x81eb4  stloc.2
0x81eb5  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x81eba  ldstr    aMergedRecordWa// "Merged_Record_Warning"
0x81ebf  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x81ec4  stloc.3
0x81ec5  call     class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x81eca  ldloc.3
0x81ecb  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x81ed0  ldc.i4.1
0x81ed1  newarr   [mscorlib]System.Object
0x81ed6  dup
0x81ed7  ldc.i4.0
0x81ed8  ldloc.2
0x81ed9  stelem.ref
0x81eda  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x81edf  stloc.s  4
0x81ee1  call     class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x81ee6  ldloc.3
0x81ee7  ldc.i4.1
0x81ee8  newarr   [mscorlib]System.Object
0x81eed  dup
0x81eee  ldc.i4.0
0x81eef  ldloc.1
0x81ef0  stelem.ref
0x81ef1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x81ef6  stloc.s  5
0x81ef8  ldc.i4.2
0x81ef9  ldloc.s  4
0x81efb  ldloc.s  5
0x81efd  call     class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification::CreateHtmlNotification(int32, string, string)
0x81f02  stloc.s  6
0x81f04  ldloc.s  6
0x81f06  ldstr    aRecorddisabled// "RecordDisabledMergedNotification"
0x81f0b  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification::Id
0x81f10  ldarg.2
0x81f11  ldloc.s  6
0x81f13  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification>::Add(var<u1>)
0x81f18  ret
0x81f19  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x81f1e  ldstr    aMergedRecordWa_0// "Merged_Record_Warning_Master_Deleted"
0x81f23  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x81f28  stloc.s  8
0x81f2a  ldarg.2
0x81f2b  ldc.i4.2
0x81f2c  ldloc.s  8
0x81f2e  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification::.ctor(int32, string)
0x81f33  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.Platform.Notifications.Notification>::Add(var<u1>)
0x81f38  ret
```
