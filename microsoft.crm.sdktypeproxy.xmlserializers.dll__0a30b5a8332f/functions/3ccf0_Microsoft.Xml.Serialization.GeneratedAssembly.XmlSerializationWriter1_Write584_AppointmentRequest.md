# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write584_AppointmentRequest

- ea: `0x3ccf0`
- end: `0x3d003`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write584_AppointmentRequest`
- size: `787`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x3cc30`

## callees

- `0x5cf0`
- `0x181f0`
- `0x18240`
- `0x182d0`
- `0x18370`
- `0x18400`
- `0x3ccf0`

## string_xrefs

- `0x3cd35`: `http://schemas.microsoft.com/crm/2006/Scheduling`
- `0x3cd45`: `http://schemas.microsoft.com/crm/2006/Scheduling`
- `0x3cd60`: `http://schemas.microsoft.com/crm/2006/Scheduling`
- `0x3cd7b`: `http://schemas.microsoft.com/crm/2006/Scheduling`
- `0x3cd96`: `http://schemas.microsoft.com/crm/2006/Scheduling`
- `0x3cdb1`: `http://schemas.microsoft.com/crm/2006/Scheduling`
- `0x3cdd6`: `http://schemas.microsoft.com/crm/2006/Scheduling`
- `0x3cdec`: `http://schemas.microsoft.com/crm/2006/Scheduling`
- `0x3ce1b`: `http://schemas.microsoft.com/crm/2006/Scheduling`
- `0x3ce32`: `http://schemas.microsoft.com/crm/2006/Scheduling`
- `0x3ce5b`: `http://schemas.microsoft.com/crm/2006/Scheduling`
- `0x3ce73`: `http://schemas.microsoft.com/crm/2006/Scheduling`
- `0x3ce8b`: `http://schemas.microsoft.com/crm/2006/Scheduling`
- `0x3cea3`: `http://schemas.microsoft.com/crm/2006/Scheduling`
- `0x3ceb9`: `http://schemas.microsoft.com/crm/2006/Scheduling`
- `0x3cee0`: `http://schemas.microsoft.com/crm/2006/Scheduling`
- `0x3cef7`: `http://schemas.microsoft.com/crm/2006/Scheduling`
- `0x3cf2e`: `http://schemas.microsoft.com/crm/2006/Scheduling`
- `0x3cf45`: `http://schemas.microsoft.com/crm/2006/Scheduling`
- `0x3cf70`: `http://schemas.microsoft.com/crm/2006/Scheduling`
- `0x3cf8c`: `http://schemas.microsoft.com/crm/2006/Scheduling`
- `0x3cfb3`: `http://schemas.microsoft.com/crm/2006/Scheduling`
- `0x3cfca`: `http://schemas.microsoft.com/crm/2006/Scheduling`
- `0x3cd40`: `ServiceId`

## pseudocode

```c

```

## disassembly

```asm
0x3ccf0  ldarg.3
0x3ccf1  brtrue.s loc_3CD00
0x3ccf3  ldarg.s  4
0x3ccf5  brfalse.s loc_3CCFF
0x3ccf7  ldarg.0
0x3ccf8  ldarg.1
0x3ccf9  ldarg.2
0x3ccfa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x3ccff  ret
0x3cd00  ldarg.s  5
0x3cd02  brtrue.s loc_3CD20
0x3cd04  ldarg.3
0x3cd05  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3cd0a  stloc.0
0x3cd0b  ldloc.0
0x3cd0c  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AppointmentRequest
0x3cd11  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3cd16  beq.s    loc_3CD20
0x3cd18  ldarg.0
0x3cd19  ldarg.3
0x3cd1a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x3cd1f  throw
0x3cd20  ldarg.0
0x3cd21  ldarg.1
0x3cd22  ldarg.2
0x3cd23  ldarg.3
0x3cd24  ldc.i4.0
0x3cd25  ldnull
0x3cd26  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x3cd2b  ldarg.s  5
0x3cd2d  brfalse.s loc_3CD3F
0x3cd2f  ldarg.0
0x3cd30  ldstr    aAppointmentreq// "AppointmentRequest"
0x3cd35  ldstr    aHttpSchemasMic_4// "http://schemas.microsoft.com/crm/2006/S"...
0x3cd3a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x3cd3f  ldarg.0
0x3cd40  ldstr    aServiceid_0// "ServiceId"
0x3cd45  ldstr    aHttpSchemasMic_4// "http://schemas.microsoft.com/crm/2006/S"...
0x3cd4a  ldarg.3
0x3cd4b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AppointmentRequest::get_ServiceId()
0x3cd50  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x3cd55  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x3cd5a  ldarg.0
0x3cd5b  ldstr    aAnchoroffset_0// "AnchorOffset"
0x3cd60  ldstr    aHttpSchemasMic_4// "http://schemas.microsoft.com/crm/2006/S"...
0x3cd65  ldarg.3
0x3cd66  callvirt instance int32 [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AppointmentRequest::get_AnchorOffset()
0x3cd6b  call     string [System.Xml]System.Xml.XmlConvert::ToString(int32)
0x3cd70  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x3cd75  ldarg.0
0x3cd76  ldstr    aUsertimezoneco// "UserTimeZoneCode"
0x3cd7b  ldstr    aHttpSchemasMic_4// "http://schemas.microsoft.com/crm/2006/S"...
0x3cd80  ldarg.3
0x3cd81  callvirt instance int32 [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AppointmentRequest::get_UserTimeZoneCode()
0x3cd86  call     string [System.Xml]System.Xml.XmlConvert::ToString(int32)
0x3cd8b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x3cd90  ldarg.0
0x3cd91  ldstr    aRecurrencedura// "RecurrenceDuration"
0x3cd96  ldstr    aHttpSchemasMic_4// "http://schemas.microsoft.com/crm/2006/S"...
0x3cd9b  ldarg.3
0x3cd9c  callvirt instance int32 [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AppointmentRequest::get_RecurrenceDuration()
0x3cda1  call     string [System.Xml]System.Xml.XmlConvert::ToString(int32)
0x3cda6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x3cdab  ldarg.0
0x3cdac  ldstr    aRecurrencetime// "RecurrenceTimeZoneCode"
0x3cdb1  ldstr    aHttpSchemasMic_4// "http://schemas.microsoft.com/crm/2006/S"...
0x3cdb6  ldarg.3
0x3cdb7  callvirt instance int32 [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AppointmentRequest::get_RecurrenceTimeZoneCode()
0x3cdbc  call     string [System.Xml]System.Xml.XmlConvert::ToString(int32)
0x3cdc1  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x3cdc6  ldarg.3
0x3cdc7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AppointmentsToIgnore[] [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AppointmentRequest::get_AppointmentsToIgnore()
0x3cdcc  stloc.1
0x3cdcd  ldloc.1
0x3cdce  brfalse.s loc_3CE0B
0x3cdd0  ldarg.0
0x3cdd1  ldstr    aAppointmentsto// "AppointmentsToIgnore"
0x3cdd6  ldstr    aHttpSchemasMic_4// "http://schemas.microsoft.com/crm/2006/S"...
0x3cddb  ldnull
0x3cddc  ldc.i4.0
0x3cddd  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x3cde2  ldc.i4.0
0x3cde3  stloc.2
0x3cde4  br.s     loc_3CDFF
0x3cde6  ldarg.0
0x3cde7  ldstr    aAppointmentsto// "AppointmentsToIgnore"
0x3cdec  ldstr    aHttpSchemasMic_4// "http://schemas.microsoft.com/crm/2006/S"...
0x3cdf1  ldloc.1
0x3cdf2  ldloc.2
0x3cdf3  ldelem.ref
0x3cdf4  ldc.i4.1
0x3cdf5  ldc.i4.0
0x3cdf6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write579_AppointmentsToIgnore(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AppointmentsToIgnore o, bool isNullable, bool needType)
0x3cdfb  ldloc.2
0x3cdfc  ldc.i4.1
0x3cdfd  add
0x3cdfe  stloc.2
0x3cdff  ldloc.2
0x3ce00  ldloc.1
0x3ce01  ldlen
0x3ce02  conv.i4
0x3ce03  blt.s    loc_3CDE6
0x3ce05  ldarg.0
0x3ce06  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x3ce0b  ldarg.3
0x3ce0c  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RequiredResource[] [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AppointmentRequest::get_RequiredResources()
0x3ce11  stloc.3
0x3ce12  ldloc.3
0x3ce13  brfalse.s loc_3CE55
0x3ce15  ldarg.0
0x3ce16  ldstr    aRequiredresour_0// "RequiredResources"
0x3ce1b  ldstr    aHttpSchemasMic_4// "http://schemas.microsoft.com/crm/2006/S"...
0x3ce20  ldnull
0x3ce21  ldc.i4.0
0x3ce22  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x3ce27  ldc.i4.0
0x3ce28  stloc.s  4
0x3ce2a  br.s     loc_3CE48
0x3ce2c  ldarg.0
0x3ce2d  ldstr    aRequiredresour// "RequiredResource"
0x3ce32  ldstr    aHttpSchemasMic_4// "http://schemas.microsoft.com/crm/2006/S"...
0x3ce37  ldloc.3
0x3ce38  ldloc.s  4
0x3ce3a  ldelem.ref
0x3ce3b  ldc.i4.1
0x3ce3c  ldc.i4.0
0x3ce3d  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write580_RequiredResource(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RequiredResource o, bool isNullable, bool needType)
0x3ce42  ldloc.s  4
0x3ce44  ldc.i4.1
0x3ce45  add
0x3ce46  stloc.s  4
0x3ce48  ldloc.s  4
0x3ce4a  ldloc.3
0x3ce4b  ldlen
0x3ce4c  conv.i4
0x3ce4d  blt.s    loc_3CE2C
0x3ce4f  ldarg.0
0x3ce50  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x3ce55  ldarg.0
0x3ce56  ldstr    aSearchwindowst// "SearchWindowStart"
0x3ce5b  ldstr    aHttpSchemasMic_4// "http://schemas.microsoft.com/crm/2006/S"...
0x3ce60  ldarg.3
0x3ce61  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AppointmentRequest::get_SearchWindowStart()
0x3ce66  ldc.i4.0
0x3ce67  ldc.i4.0
0x3ce68  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x3ce6d  ldarg.0
0x3ce6e  ldstr    aSearchwindowen// "SearchWindowEnd"
0x3ce73  ldstr    aHttpSchemasMic_4// "http://schemas.microsoft.com/crm/2006/S"...
0x3ce78  ldarg.3
0x3ce79  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AppointmentRequest::get_SearchWindowEnd()
0x3ce7e  ldc.i4.0
0x3ce7f  ldc.i4.0
0x3ce80  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x3ce85  ldarg.0
0x3ce86  ldstr    aSearchrecurren// "SearchRecurrenceStart"
0x3ce8b  ldstr    aHttpSchemasMic_4// "http://schemas.microsoft.com/crm/2006/S"...
0x3ce90  ldarg.3
0x3ce91  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AppointmentRequest::get_SearchRecurrenceStart()
0x3ce96  ldc.i4.0
0x3ce97  ldc.i4.0
0x3ce98  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x3ce9d  ldarg.0
0x3ce9e  ldstr    aSearchrecurren_0// "SearchRecurrenceRule"
0x3cea3  ldstr    aHttpSchemasMic_4// "http://schemas.microsoft.com/crm/2006/S"...
0x3cea8  ldarg.3
0x3cea9  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AppointmentRequest::get_SearchRecurrenceRule()
0x3ceae  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x3ceb3  ldarg.0
0x3ceb4  ldstr    aDuration_0// "Duration"
0x3ceb9  ldstr    aHttpSchemasMic_4// "http://schemas.microsoft.com/crm/2006/S"...
0x3cebe  ldarg.3
0x3cebf  callvirt instance int32 [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AppointmentRequest::get_Duration()
0x3cec4  call     string [System.Xml]System.Xml.XmlConvert::ToString(int32)
0x3cec9  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x3cece  ldarg.3
0x3cecf  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.ConstraintRelation[] [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AppointmentRequest::get_Constraints()
0x3ced4  stloc.s  5
0x3ced6  ldloc.s  5
0x3ced8  brfalse.s loc_3CF1C
0x3ceda  ldarg.0
0x3cedb  ldstr    aConstraints// "Constraints"
0x3cee0  ldstr    aHttpSchemasMic_4// "http://schemas.microsoft.com/crm/2006/S"...
0x3cee5  ldnull
0x3cee6  ldc.i4.0
0x3cee7  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x3ceec  ldc.i4.0
0x3ceed  stloc.s  6
0x3ceef  br.s     loc_3CF0E
0x3cef1  ldarg.0
0x3cef2  ldstr    aConstraintrela// "ConstraintRelation"
0x3cef7  ldstr    aHttpSchemasMic_4// "http://schemas.microsoft.com/crm/2006/S"...
0x3cefc  ldloc.s  5
0x3cefe  ldloc.s  6
0x3cf00  ldelem.ref
0x3cf01  ldc.i4.1
0x3cf02  ldc.i4.0
0x3cf03  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write581_ConstraintRelation(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.ConstraintRelation o, bool isNullable, bool needType)
0x3cf08  ldloc.s  6
0x3cf0a  ldc.i4.1
0x3cf0b  add
0x3cf0c  stloc.s  6
0x3cf0e  ldloc.s  6
0x3cf10  ldloc.s  5
0x3cf12  ldlen
0x3cf13  conv.i4
0x3cf14  blt.s    loc_3CEF1
0x3cf16  ldarg.0
0x3cf17  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x3cf1c  ldarg.3
0x3cf1d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.ObjectiveRelation[] [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AppointmentRequest::get_Objectives()
0x3cf22  stloc.s  7
0x3cf24  ldloc.s  7
0x3cf26  brfalse.s loc_3CF6A
0x3cf28  ldarg.0
0x3cf29  ldstr    aObjectives// "Objectives"
0x3cf2e  ldstr    aHttpSchemasMic_4// "http://schemas.microsoft.com/crm/2006/S"...
0x3cf33  ldnull
0x3cf34  ldc.i4.0
0x3cf35  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x3cf3a  ldc.i4.0
0x3cf3b  stloc.s  8
0x3cf3d  br.s     loc_3CF5C
0x3cf3f  ldarg.0
0x3cf40  ldstr    aObjectiverelat// "ObjectiveRelation"
0x3cf45  ldstr    aHttpSchemasMic_4// "http://schemas.microsoft.com/crm/2006/S"...
0x3cf4a  ldloc.s  7
0x3cf4c  ldloc.s  8
0x3cf4e  ldelem.ref
0x3cf4f  ldc.i4.1
0x3cf50  ldc.i4.0
0x3cf51  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write582_ObjectiveRelation(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.ObjectiveRelation o, bool isNullable, bool needType)
0x3cf56  ldloc.s  8
0x3cf58  ldc.i4.1
0x3cf59  add
0x3cf5a  stloc.s  8
0x3cf5c  ldloc.s  8
0x3cf5e  ldloc.s  7
0x3cf60  ldlen
0x3cf61  conv.i4
0x3cf62  blt.s    loc_3CF3F
0x3cf64  ldarg.0
0x3cf65  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x3cf6a  ldarg.0
0x3cf6b  ldstr    aDirection// "Direction"
0x3cf70  ldstr    aHttpSchemasMic_4// "http://schemas.microsoft.com/crm/2006/S"...
0x3cf75  ldarg.0
0x3cf76  ldarg.3
0x3cf77  callvirt instance valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SearchDirection [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AppointmentRequest::get_Direction()
0x3cf7c  call     instance string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write583_SearchDirection(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SearchDirection v)
0x3cf81  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x3cf86  ldarg.0
0x3cf87  ldstr    aNumberofresult// "NumberOfResults"
0x3cf8c  ldstr    aHttpSchemasMic_4// "http://schemas.microsoft.com/crm/2006/S"...
0x3cf91  ldarg.3
0x3cf92  callvirt instance int32 [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AppointmentRequest::get_NumberOfResults()
0x3cf97  call     string [System.Xml]System.Xml.XmlConvert::ToString(int32)
0x3cf9c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x3cfa1  ldarg.3
0x3cfa2  callvirt instance valuetype [mscorlib]System.Guid[] [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AppointmentRequest::get_Sites()
0x3cfa7  stloc.s  9
0x3cfa9  ldloc.s  9
0x3cfab  brfalse.s loc_3CFFB
0x3cfad  ldarg.0
0x3cfae  ldstr    aSites// "Sites"
0x3cfb3  ldstr    aHttpSchemasMic_4// "http://schemas.microsoft.com/crm/2006/S"...
0x3cfb8  ldnull
0x3cfb9  ldc.i4.0
0x3cfba  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x3cfbf  ldc.i4.0
0x3cfc0  stloc.s  0xA
0x3cfc2  br.s     loc_3CFED
0x3cfc4  ldarg.0
0x3cfc5  ldstr    aGuid// "guid"
0x3cfca  ldstr    aHttpSchemasMic_4// "http://schemas.microsoft.com/crm/2006/S"...
0x3cfcf  ldloc.s  9
0x3cfd1  ldloc.s  0xA
0x3cfd3  ldelema  [mscorlib]System.Guid
0x3cfd8  ldobj    [mscorlib]System.Guid
0x3cfdd  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x3cfe2  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x3cfe7  ldloc.s  0xA
0x3cfe9  ldc.i4.1
0x3cfea  add
0x3cfeb  stloc.s  0xA
0x3cfed  ldloc.s  0xA
0x3cfef  ldloc.s  9
0x3cff1  ldlen
0x3cff2  conv.i4
0x3cff3  blt.s    loc_3CFC4
0x3cff5  ldarg.0
0x3cff6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x3cffb  ldarg.0
0x3cffc  ldarg.3
0x3cffd  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x3d002  ret
```
