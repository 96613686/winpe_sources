# Microsoft.Crm.Asynchronous.EmailConnector.CrmServiceAppointment::SetApptStateStatusFromStatus

- ea: `0x64590`
- end: `0x64713`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.CrmServiceAppointment::SetApptStateStatusFromStatus`
- size: `387`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x56a30`
- `0x64590`
- `0x6e1b0`
- `0x6e420`
- `0x6e600`
- `0x6e620`
- `0x70120`
- `0x70170`
- `0x701d0`
- `0x702a0`
- `0x70300`
- `0x70330`
- `0x70460`
- `0x704a0`

## string_xrefs

- `0x64598`: `crmxml`

## pseudocode

```c

```

## disassembly

```asm
0x64590  ldc.i4.0
0x64591  stloc.0
0x64592  ldarg.0
0x64593  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_InputSyncItem()
0x64598  ldstr    aCrmxml// "crmxml"
0x6459d  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::GetProperty(string propertyName)
0x645a2  stloc.1
0x645a3  ldloc.1
0x645a4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x645a9  brtrue   loc_64631
0x645ae  ldarg.0
0x645af  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPropertiesMapping Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_SyncPropertiesMapping()
0x645b4  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPropertiesMapping::get_CrmPropertyList()
0x645b9  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0x645be  stloc.s  4
0x645c0  ldarg.0
0x645c1  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_Context()
0x645c6  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties::.ctor(class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context)
0x645cb  dup
0x645cc  ldloc.1
0x645cd  ldloc.s  4
0x645cf  ldarg.0
0x645d0  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_ItemObjectType()
0x645d5  stloc.s  6
0x645d7  ldloca.s 6
0x645d9  constrained. [Microsoft.Crm]Microsoft.Crm.ItemObjectType
0x645df  callvirt instance string [mscorlib]System.Object::ToString()
0x645e4  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x645e9  ldarg.0
0x645ea  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_FromCrmId()
0x645ef  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties::Initialize(string xml, class [mscorlib]System.Collections.ObjectModel.Collection`1<string> columnSetCollection, string name, string crmId)
0x645f4  dup
0x645f5  ldstr    aStatuscode// "statuscode"
0x645fa  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties::GetProperty(string propertyName)
0x645ff  stloc.s  5
0x64601  ldstr    aStatuscode// "statuscode"
0x64606  ldloc.s  5
0x64608  ldnull
0x64609  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties::IsPropertyChanged(string propertyName, string newValue, [opt] class Microsoft.Crm.Asynchronous.EmailConnector.PropertyCompare comparer)
0x6460e  brfalse.s loc_64621
0x64610  ldarg.0
0x64611  ldstr    aStatuscode// "statuscode"
0x64616  ldloc.s  5
0x64618  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::SetPropertyValue(string propertyName, string propertyValue)
0x6461d  ldc.i4.1
0x6461e  stloc.0
0x6461f  br.s     loc_64631
0x64621  ldarg.0
0x64622  ldstr    aStatuscode// "statuscode"
0x64627  ldsfld   string [mscorlib]System.String::Empty
0x6462c  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::SetPropertyValue(string propertyName, string propertyValue)
0x64631  ldarg.0
0x64632  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_InputSyncItem()
0x64637  ldstr    aGetstatuscode// "getstatuscode"
0x6463c  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::GetProperty(string propertyName)
0x64641  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x64646  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x6464b  stloc.2
0x6464c  ldstr    a0// "0"
0x64651  stloc.3
0x64652  ldloc.2
0x64653  switch   loc_6466A, loc_646C7, loc_646D5, loc_646D5
0x64668  br.s     loc_646E3
0x6466a  ldarg.0
0x6466b  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_OriginalProperties()
0x64670  ldstr    aStatecode// "statecode"
0x64675  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties::GetProperty(string propertyName)
0x6467a  stloc.s  7
0x6467c  ldloc.s  7
0x6467e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x64683  brfalse.s loc_6468C
0x64685  ldstr    a0// "0"
0x6468a  stloc.s  7
0x6468c  ldloc.s  7
0x6468e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x64693  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x64698  stloc.s  8
0x6469a  ldloc.s  7
0x6469c  stloc.3
0x6469d  ldloc.s  8
0x6469f  ldc.i4.1
0x646a0  bne.un.s loc_646AB
0x646a2  ldstr    a1// "1"
0x646a7  stloc.s  7
0x646a9  br.s     loc_646EF
0x646ab  ldloc.s  8
0x646ad  ldc.i4.2
0x646ae  bne.un.s loc_646B9
0x646b0  ldstr    a2// "2"
0x646b5  stloc.s  7
0x646b7  br.s     loc_646EF
0x646b9  ldc.i4.0
0x646ba  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x646bf  call     string [mscorlib]System.Convert::ToString(int32, class [mscorlib]System.IFormatProvider)
0x646c4  stloc.3
0x646c5  br.s     loc_646EF
0x646c7  ldc.i4.0
0x646c8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x646cd  call     string [mscorlib]System.Convert::ToString(int32, class [mscorlib]System.IFormatProvider)
0x646d2  stloc.3
0x646d3  br.s     loc_646EF
0x646d5  ldc.i4.3
0x646d6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x646db  call     string [mscorlib]System.Convert::ToString(int32, class [mscorlib]System.IFormatProvider)
0x646e0  stloc.3
0x646e1  br.s     loc_646EF
0x646e3  ldc.i4.0
0x646e4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x646e9  call     string [mscorlib]System.Convert::ToString(int32, class [mscorlib]System.IFormatProvider)
0x646ee  stloc.3
0x646ef  ldarg.0
0x646f0  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_OriginalProperties()
0x646f5  ldstr    aStatecode// "statecode"
0x646fa  ldloc.3
0x646fb  ldnull
0x646fc  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties::IsPropertyChanged(string propertyName, string newValue, [opt] class Microsoft.Crm.Asynchronous.EmailConnector.PropertyCompare comparer)
0x64701  brfalse.s loc_64711
0x64703  ldarg.0
0x64704  ldstr    aStatecode// "statecode"
0x64709  ldloc.3
0x6470a  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::SetPropertyValue(string propertyName, string propertyValue)
0x6470f  ldc.i4.1
0x64710  stloc.0
0x64711  ldloc.0
0x64712  ret
```
