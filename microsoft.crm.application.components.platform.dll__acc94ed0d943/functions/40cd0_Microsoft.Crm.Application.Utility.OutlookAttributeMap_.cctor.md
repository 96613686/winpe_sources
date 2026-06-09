# Microsoft.Crm.Application.Utility.OutlookAttributeMap::.cctor

- ea: `0x40cd0`
- end: `0x41555`
- name: `Microsoft.Crm.Application.Utility.OutlookAttributeMap::.cctor`
- size: `2181`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x40f5f`: `scheduledend`
- `0x41348`: `scheduledend`
- `0x40e10`: `scheduleddurationminutes`
- `0x40f37`: `scheduleddurationminutes`
- `0x4133d`: `scheduleddurationminutes`
- `0x41332`: `scheduledstart`
- `0x41466`: `isworkflowcreated`

## pseudocode

```c

```

## disassembly

```asm
0x40cd0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.IList`1<string>>::.ctor()
0x40cd5  stsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [mscorlib]System.Collections.Generic.IList`1<string>> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_crmAttributeList
0x40cda  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.IList`1<string>>::.ctor()
0x40cdf  stsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [mscorlib]System.Collections.Generic.IList`1<string>> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_outlookAttributeList
0x40ce4  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x40ce9  stsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_mapOutlookFieldToCrmField
0x40cee  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x40cf3  stsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_mapCrmFieldToOutlookField
0x40cf8  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x40cfd  stsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_mapOutlookRecurrenceFieldToCrmRecurrenceField
0x40d02  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x40d07  stsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_mapCrmRecurrenceFieldToOutlookRecurrenceField
0x40d0c  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.IList`1<string>>::.ctor()
0x40d11  stsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [mscorlib]System.Collections.Generic.IList`1<string>> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_crmAttributeSecondPageExcludeList
0x40d16  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_mapOutlookFieldToCrmField
0x40d1b  ldstr    aFrom_0// "From"
0x40d20  ldstr    aFrom// "from"
0x40d25  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x40d2a  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_mapOutlookFieldToCrmField
0x40d2f  ldstr    aTo_0// "To"
0x40d34  ldstr    aTo// "to"
0x40d39  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x40d3e  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_mapOutlookFieldToCrmField
0x40d43  ldstr    aCc// "CC"
0x40d48  ldstr    aCc_0// "cc"
0x40d4d  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x40d52  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_mapOutlookFieldToCrmField
0x40d57  ldstr    aBcc// "BCC"
0x40d5c  ldstr    aBcc_0// "bcc"
0x40d61  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x40d66  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_mapOutlookFieldToCrmField
0x40d6b  ldstr    aSubject_0// "Subject"
0x40d70  ldstr    aSubject// "subject"
0x40d75  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x40d7a  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_mapOutlookFieldToCrmField
0x40d7f  ldstr    aDescription_0// "description"
0x40d84  ldstr    aDescription_0// "description"
0x40d89  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x40d8e  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_mapOutlookFieldToCrmField
0x40d93  ldstr    aBody// "Body"
0x40d98  ldstr    aDescription_0// "description"
0x40d9d  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x40da2  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_mapOutlookFieldToCrmField
0x40da7  ldstr    aAlldayevent// "AllDayEvent"
0x40dac  ldstr    aIsalldayevent// "isalldayevent"
0x40db1  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x40db6  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_mapOutlookFieldToCrmField
0x40dbb  ldstr    aImportance// "Importance"
0x40dc0  ldstr    aPrioritycode// "prioritycode"
0x40dc5  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x40dca  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_mapOutlookFieldToCrmField
0x40dcf  ldstr    aOptionalattend// "OptionalAttendees"
0x40dd4  ldstr    aOptionalattend_0// "optionalattendees"
0x40dd9  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x40dde  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_mapOutlookFieldToCrmField
0x40de3  ldstr    aRequiredattend_0// "RequiredAttendees"
0x40de8  ldstr    aRequiredattend// "requiredattendees"
0x40ded  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x40df2  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_mapOutlookFieldToCrmField
0x40df7  ldstr    aLocation// "Location"
0x40dfc  ldstr    aLocation_0// "location"
0x40e01  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x40e06  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_mapOutlookFieldToCrmField
0x40e0b  ldstr    aDuration// "Duration"
0x40e10  ldstr    aScheduleddurat// "scheduleddurationminutes"
0x40e15  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x40e1a  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_mapOutlookFieldToCrmField
0x40e1f  ldstr    aBusystatus// "BusyStatus"
0x40e24  ldstr    aStatuscode// "statuscode"
0x40e29  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x40e2e  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_mapOutlookFieldToCrmField
0x40e33  ldstr    aCrmregardingid// "crmRegardingId"
0x40e38  ldstr    aRegardingobjec_0// "regardingobjectid"
0x40e3d  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x40e42  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_mapCrmFieldToOutlookField
0x40e47  ldstr    aFrom// "from"
0x40e4c  ldstr    aFrom_0// "From"
0x40e51  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x40e56  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_mapCrmFieldToOutlookField
0x40e5b  ldstr    aTo// "to"
0x40e60  ldstr    aTo_0// "To"
0x40e65  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x40e6a  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_mapCrmFieldToOutlookField
0x40e6f  ldstr    aCc_0// "cc"
0x40e74  ldstr    aCc// "CC"
0x40e79  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x40e7e  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_mapCrmFieldToOutlookField
0x40e83  ldstr    aBcc_0// "bcc"
0x40e88  ldstr    aBcc// "BCC"
0x40e8d  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x40e92  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_mapCrmFieldToOutlookField
0x40e97  ldstr    aSubject// "subject"
0x40e9c  ldstr    aSubject_0// "Subject"
0x40ea1  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x40ea6  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_mapCrmFieldToOutlookField
0x40eab  ldstr    aDescription_0// "description"
0x40eb0  ldstr    aBody// "Body"
0x40eb5  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x40eba  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_mapCrmFieldToOutlookField
0x40ebf  ldstr    aIsalldayevent// "isalldayevent"
0x40ec4  ldstr    aAlldayevent// "AllDayEvent"
0x40ec9  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x40ece  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_mapCrmFieldToOutlookField
0x40ed3  ldstr    aPrioritycode// "prioritycode"
0x40ed8  ldstr    aImportance// "Importance"
0x40edd  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x40ee2  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_mapCrmFieldToOutlookField
0x40ee7  ldstr    aOptionalattend_0// "optionalattendees"
0x40eec  ldstr    aOptionalattend// "OptionalAttendees"
0x40ef1  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x40ef6  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_mapCrmFieldToOutlookField
0x40efb  ldstr    aRequiredattend// "requiredattendees"
0x40f00  ldstr    aRequiredattend_0// "RequiredAttendees"
0x40f05  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x40f0a  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_mapCrmFieldToOutlookField
0x40f0f  ldstr    aLocation_0// "location"
0x40f14  ldstr    aLocation// "Location"
0x40f19  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x40f1e  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_mapCrmFieldToOutlookField
0x40f23  ldstr    aRecurrencepatt// "recurrencepatterntype"
0x40f28  ldstr    aRecurrencepatt_0// "RecurrencePattern"
0x40f2d  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x40f32  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_mapCrmFieldToOutlookField
0x40f37  ldstr    aScheduleddurat// "scheduleddurationminutes"
0x40f3c  ldstr    aDuration// "Duration"
0x40f41  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x40f46  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_mapCrmFieldToOutlookField
0x40f4b  ldstr    aStatuscode// "statuscode"
0x40f50  ldstr    aBusystatus// "BusyStatus"
0x40f55  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x40f5a  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_mapCrmFieldToOutlookField
0x40f5f  ldstr    aScheduledend// "scheduledend"
0x40f64  ldstr    aEnd// "End"
0x40f69  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x40f6e  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_mapCrmFieldToOutlookField
0x40f73  ldstr    aRegardingobjec_0// "regardingobjectid"
0x40f78  ldstr    aCrmregardingid// "crmRegardingId"
0x40f7d  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x40f82  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_mapOutlookRecurrenceFieldToCrmRecurrenceField
0x40f87  ldstr    aStart// "Start"
0x40f8c  ldstr    aPatternstartda// "patternstartdate"
0x40f91  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x40f96  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_mapOutlookRecurrenceFieldToCrmRecurrenceField
0x40f9b  ldstr    aEnd// "End"
0x40fa0  ldstr    aPatternenddate// "patternenddate"
0x40fa5  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x40faa  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_mapOutlookRecurrenceFieldToCrmRecurrenceField
0x40faf  ldstr    aStarttime// "StartTime"
0x40fb4  ldstr    aStarttime_0// "starttime"
0x40fb9  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x40fbe  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_mapOutlookRecurrenceFieldToCrmRecurrenceField
0x40fc3  ldstr    aEndtime// "EndTime"
0x40fc8  ldstr    aEndtime_0// "endtime"
0x40fcd  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x40fd2  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_mapOutlookRecurrenceFieldToCrmRecurrenceField
0x40fd7  ldstr    aRecurrencepatt_1// "RecurrencePatternType"
0x40fdc  ldstr    aRecurrencetype// "recurrenceType"
0x40fe1  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x40fe6  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_mapCrmRecurrenceFieldToOutlookRecurrenceField
0x40feb  ldstr    aPatternstartda// "patternstartdate"
0x40ff0  ldstr    aStart// "Start"
0x40ff5  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x40ffa  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_mapCrmRecurrenceFieldToOutlookRecurrenceField
0x40fff  ldstr    aPatternenddate// "patternenddate"
0x41004  ldstr    aEnd// "End"
0x41009  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x4100e  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_mapCrmRecurrenceFieldToOutlookRecurrenceField
0x41013  ldstr    aStarttime_0// "starttime"
0x41018  ldstr    aStarttime// "StartTime"
0x4101d  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x41022  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_mapCrmRecurrenceFieldToOutlookRecurrenceField
0x41027  ldstr    aEndtime_0// "endtime"
0x4102c  ldstr    aEndtime// "EndTime"
0x41031  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x41036  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_mapCrmRecurrenceFieldToOutlookRecurrenceField
0x4103b  ldstr    aRecurrencetype// "recurrenceType"
0x41040  ldstr    aRecurrencepatt_1// "RecurrencePatternType"
0x41045  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x4104a  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x4104f  stloc.0
0x41050  ldloc.0
0x41051  ldstr    aFrom_0// "From"
0x41056  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x4105b  ldloc.0
0x4105c  ldstr    aTo_0// "To"
0x41061  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x41066  ldloc.0
0x41067  ldstr    aCc// "CC"
0x4106c  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x41071  ldloc.0
0x41072  ldstr    aBcc// "BCC"
0x41077  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x4107c  ldloc.0
0x4107d  ldstr    aSubject_0// "Subject"
0x41082  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x41087  ldloc.0
0x41088  ldstr    aDescription_0// "description"
0x4108d  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x41092  ldloc.0
0x41093  ldstr    aCrmregardingid// "crmRegardingId"
0x41098  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x4109d  ldloc.0
0x4109e  ldstr    aRegarding_0// "Regarding"
0x410a3  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x410a8  ldloc.0
0x410a9  ldstr    aCrmregardingob// "crmRegardingObjectType"
0x410ae  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x410b3  ldloc.0
0x410b4  ldstr    aImportance// "Importance"
0x410b9  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x410be  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [mscorlib]System.Collections.Generic.IList`1<string>> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_outlookAttributeList
0x410c3  ldstr    aEmail// "email"
0x410c8  ldloc.0
0x410c9  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [mscorlib]System.Collections.Generic.IList`1<string>>::set_Item(var<u1>, !!T0)
0x410ce  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x410d3  stloc.0
0x410d4  ldloc.0
0x410d5  ldstr    aSubject_0// "Subject"
0x410da  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x410df  ldloc.0
0x410e0  ldstr    aBody// "Body"
0x410e5  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x410ea  ldloc.0
0x410eb  ldstr    aAlldayevent// "AllDayEvent"
0x410f0  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x410f5  ldloc.0
0x410f6  ldstr    aImportance// "Importance"
0x410fb  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x41100  ldloc.0
0x41101  ldstr    aOptionalattend// "OptionalAttendees"
0x41106  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x4110b  ldloc.0
0x4110c  ldstr    aRequiredattend_0// "RequiredAttendees"
0x41111  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x41116  ldloc.0
0x41117  ldstr    aLocation// "Location"
0x4111c  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x41121  ldloc.0
0x41122  ldstr    aCrmregardingid// "crmRegardingId"
0x41127  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x4112c  ldloc.0
0x4112d  ldstr    aRegarding_0// "Regarding"
0x41132  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x41137  ldloc.0
0x41138  ldstr    aCrmregardingob// "crmRegardingObjectType"
0x4113d  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x41142  ldloc.0
0x41143  ldstr    aDuration// "Duration"
0x41148  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x4114d  ldloc.0
0x4114e  ldstr    aBusystatus// "BusyStatus"
0x41153  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x41158  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [mscorlib]System.Collections.Generic.IList`1<string>> Microsoft.Crm.Application.Utility.OutlookAttributeMap::_outlookAttributeList
0x4115d  ldstr    aAppointment// "appointment"
0x41162  ldloc.0
0x41163  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [mscorlib]System.Collections.Generic.IList`1<string>>::set_Item(var<u1>, !!T0)
0x41168  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x4116d  stloc.0
0x4116e  ldloc.0
0x4116f  ldstr    aSubject_0// "Subject"
0x41174  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x41179  ldloc.0
0x4117a  ldstr    aBody// "Body"
0x4117f  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x41184  ldloc.0
0x41185  ldstr    aAlldayevent// "AllDayEvent"
0x4118a  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x4118f  ldloc.0
0x41190  ldstr    aImportance// "Importance"
0x41195  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x4119a  ldloc.0
0x4119b  ldstr    aOptionalattend// "OptionalAttendees"
0x411a0  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x411a5  ldloc.0
0x411a6  ldstr    aRequiredattend_0// "RequiredAttendees"
0x411ab  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x411b0  ldloc.0
0x411b1  ldstr    aLocation// "Location"
0x411b6  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x411bb  ldloc.0
0x411bc  ldstr    aRecurrencepatt_0// "RecurrencePattern"
0x411c1  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x411c6  ldloc.0
0x411c7  ldstr    aCrmregardingid// "crmRegardingId"
0x411cc  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x411d1  ldloc.0
0x411d2  ldstr    aRegarding_0// "Regarding"
0x411d7  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x411dc  ldloc.0
0x411dd  ldstr    aCrmregardingob// "crmRegardingObjectType"
0x411e2  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x411e7  ldloc.0
0x411e8  ldstr    aDuration// "Duration"
0x411ed  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x411f2  ldloc.0
0x411f3  ldstr    aBusystatus// "BusyStatus"
0x411f8  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x411fd  ldloc.0
0x411fe  ldstr    aStart// "Start"
0x41203  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
  ... truncated ...
```
