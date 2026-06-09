# Microsoft.Crm.Application.Components.UI.AppointmentCalendar::RenderItem

- ea: `0x14aa0`
- end: `0x14d57`
- name: `Microsoft.Crm.Application.Components.UI.AppointmentCalendar::RenderItem`
- size: `695`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0xab0`
- `0x97b0`
- `0xbfe0`

## callees

- `0xa160`
- `0xa180`
- `0xa1a0`
- `0xa220`
- `0xa2a0`
- `0x14aa0`
- `0x14ea0`
- `0x14eb0`

## string_xrefs

- `0x14ae2`: ` onclick='openObj(this.getAttribute("atc"),this.getAttribute("oid"));`
- `0x14b0c`: ` onclick='Mscrm.AppointmentCalHelper.openAppt(this.getAttribute("atc"),this.getAttribute("oid"));`
- `0x14b71`: `<table class ='ms-crm-Cal-DeleteIcon'><tr><td>`
- `0x14c1a`: `'><a class='ms-crm-Link' onclick='new Sys.UI.DomEvent(event).preventDefault();' href='javascript:onclick();' target='_self'>`
- `0x14cc2`: `</td><td class='ms-crm-Cal-DeleteIconCell'>`
- `0x14cd2`: `<div oid='{0}' onclick='Mscrm.AppointmentCalHelper.deleteRecAppt(this.getAttribute("atc"), this.getAttribute("oid"));'`
- `0x14d08`: `><a class='ms-crm-Link' onclick='new Sys.UI.DomEvent(event).preventDefault();' href='javascript:onclick();' target='_self'>`
- `0x14d2a`: `Appointment.Calendar.DeleteIconAlt`

## pseudocode

```c

```

## disassembly

```asm
0x14aa0  ldarg.2
0x14aa1  callvirt instance valuetype [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeBlock Microsoft.Crm.Application.Components.UI.ScheduledBlock::get_TimeBlockInternal()
0x14aa6  stloc.s  8
0x14aa8  ldloca.s 8
0x14aaa  call     instance class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.ITimeMetadata [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeBlock::get_Metadata()
0x14aaf  isinst   Microsoft.Crm.Controls.CalendarRowData
0x14ab4  stloc.0
0x14ab5  ldloc.0
0x14ab6  callvirt instance string Microsoft.Crm.Controls.CalendarRowData::get_Type()
0x14abb  stloc.1
0x14abc  ldloc.0
0x14abd  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Controls.CalendarRowData::get_ObjectId()
0x14ac2  stloc.2
0x14ac3  ldloc.0
0x14ac4  callvirt instance int32 Microsoft.Crm.Controls.CalendarRowData::get_InstanceType()
0x14ac9  ldc.i4.2
0x14aca  beq.s    loc_14AE0
0x14acc  ldloc.0
0x14acd  callvirt instance int32 Microsoft.Crm.Controls.CalendarRowData::get_InstanceType()
0x14ad2  ldc.i4.3
0x14ad3  beq.s    loc_14AE0
0x14ad5  ldloc.0
0x14ad6  callvirt instance int32 Microsoft.Crm.Controls.CalendarRowData::get_InstanceType()
0x14adb  ldc.i4.4
0x14adc  ceq
0x14ade  br.s     loc_14AE1
0x14ae0  ldc.i4.1
0x14ae1  stloc.3
0x14ae2  ldstr    aOnclickOpenobj// " onclick='openObj(this.getAttribute(\"a"...
0x14ae7  stloc.s  4
0x14ae9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x14aee  ldstr    aImgAltSrcImgsI// "<img alt='' src='/_imgs/ico_16_{0}.gif'"...
0x14af3  ldc.i4.1
0x14af4  newarr   [mscorlib]System.Object
0x14af9  dup
0x14afa  ldc.i4.0
0x14afb  ldloc.1
0x14afc  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x14b01  stelem.ref
0x14b02  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x14b07  stloc.s  5
0x14b09  ldloc.3
0x14b0a  brfalse.s loc_14B7B
0x14b0c  ldstr    aOnclickMscrmAp// " onclick='Mscrm.AppointmentCalHelper.op"...
0x14b11  stloc.s  4
0x14b13  ldloc.0
0x14b14  callvirt instance int32 Microsoft.Crm.Controls.CalendarRowData::get_InstanceType()
0x14b19  ldc.i4.3
0x14b1a  beq.s    loc_14B25
0x14b1c  ldloc.0
0x14b1d  callvirt instance int32 Microsoft.Crm.Controls.CalendarRowData::get_InstanceType()
0x14b22  ldc.i4.4
0x14b23  bne.un.s loc_14B47
0x14b25  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x14b2a  ldstr    aImgAltSrcImgsI_0// "<img alt='' src='/_imgs/ico_16_{0}_re.p"...
0x14b2f  ldc.i4.1
0x14b30  newarr   [mscorlib]System.Object
0x14b35  dup
0x14b36  ldc.i4.0
0x14b37  ldloc.1
0x14b38  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x14b3d  stelem.ref
0x14b3e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x14b43  stloc.s  5
0x14b45  br.s     loc_14B70
0x14b47  ldloc.0
0x14b48  callvirt instance int32 Microsoft.Crm.Controls.CalendarRowData::get_InstanceType()
0x14b4d  ldc.i4.2
0x14b4e  bne.un.s loc_14B70
0x14b50  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x14b55  ldstr    aImgAltSrcImgsI_1// "<img alt='' src='/_imgs/ico_16_{0}_ri.p"...
0x14b5a  ldc.i4.1
0x14b5b  newarr   [mscorlib]System.Object
0x14b60  dup
0x14b61  ldc.i4.0
0x14b62  ldloc.1
0x14b63  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x14b68  stelem.ref
0x14b69  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x14b6e  stloc.s  5
0x14b70  ldarg.1
0x14b71  ldstr    aTableClassMsCr_1// "<table class ='ms-crm-Cal-DeleteIcon'><"...
0x14b76  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x14b7b  ldarg.2
0x14b7c  callvirt instance bool Microsoft.Crm.Application.Components.UI.ScheduledBlock::get_HasConflict()
0x14b81  brfalse.s loc_14B90
0x14b83  ldarg.1
0x14b84  ldstr    aDivClassMsCrmC_8// "<div class='ms-crm-Cal-Appointment ms-c"...
0x14b89  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x14b8e  br.s     loc_14B9B
0x14b90  ldarg.1
0x14b91  ldstr    aDivClassMsCrmC_9// "<div class='ms-crm-Cal-Appointment' oid"...
0x14b96  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x14b9b  ldarg.1
0x14b9c  ldloca.s 2
0x14b9e  ldstr    aD_1// "D"
0x14ba3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x14ba8  call     instance string [mscorlib]System.Guid::ToString(string, class [mscorlib]System.IFormatProvider)
0x14bad  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x14bb2  ldarg.1
0x14bb3  ldstr    asc_42CDA// "'"
0x14bb8  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x14bbd  ldstr    aAtc// "atc"
0x14bc2  ldloc.1
0x14bc3  ldarg.1
0x14bc4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x14bc9  ldloc.0
0x14bca  callvirt instance string Microsoft.Crm.Controls.CalendarRowData::get_Title()
0x14bcf  dup
0x14bd0  brtrue.s loc_14BD8
0x14bd2  pop
0x14bd3  ldstr    asc_3280A// ""
0x14bd8  stloc.s  6
0x14bda  ldstr    aTitle_2// "title"
0x14bdf  ldloc.s  6
0x14be1  ldarg.1
0x14be2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x14be7  ldarg.1
0x14be8  ldloc.s  4
0x14bea  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x14bef  ldloc.0
0x14bf0  callvirt instance string Microsoft.Crm.Controls.CalendarRowData::get_RgbColor()
0x14bf5  callvirt instance int32 [mscorlib]System.String::get_Length()
0x14bfa  ldc.i4.0
0x14bfb  ble.s    loc_14C19
0x14bfd  ldarg.1
0x14bfe  ldstr    aStyleBackgroun_0// "' style='background-color:"
0x14c03  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x14c08  ldarg.1
0x14c09  ldloc.0
0x14c0a  callvirt instance string Microsoft.Crm.Controls.CalendarRowData::get_RgbColor()
0x14c0f  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x14c14  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x14c19  ldarg.1
0x14c1a  ldstr    aAClassMsCrmLin// "'><a class='ms-crm-Link' onclick='new S"...
0x14c1f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x14c24  ldarg.1
0x14c25  ldloc.s  5
0x14c27  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x14c2c  ldarg.2
0x14c2d  callvirt instance bool Microsoft.Crm.Application.Components.UI.ScheduledBlock::get_HasConflict()
0x14c32  brfalse.s loc_14C7E
0x14c34  ldarg.1
0x14c35  ldstr    aImgSrcImgsErro_0// "<img src='/_imgs/error/notif_icn_warn16"...
0x14c3a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x14c3f  ldstr    aAlt// "alt"
0x14c44  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x14c49  ldstr    aAppointmentCon// "Appointment_Conflict_Detected"
0x14c4e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x14c53  ldarg.1
0x14c54  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x14c59  ldstr    aTitle_2// "title"
0x14c5e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x14c63  ldstr    aAppointmentCon// "Appointment_Conflict_Detected"
0x14c68  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x14c6d  ldarg.1
0x14c6e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x14c73  ldarg.1
0x14c74  ldstr    asc_2B7B6// ">"
0x14c79  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x14c7e  ldloc.0
0x14c7f  callvirt instance string Microsoft.Crm.Controls.CalendarRowData::get_Title()
0x14c84  stloc.s  7
0x14c86  ldloc.s  7
0x14c88  brfalse.s loc_14C97
0x14c8a  ldarg.1
0x14c8b  ldloc.s  7
0x14c8d  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x14c92  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x14c97  ldarg.1
0x14c98  ldstr    aADiv// "</a></div>"
0x14c9d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x14ca2  ldloc.3
0x14ca3  brfalse  loc_14D56
0x14ca8  ldc.i4   0x1068
0x14cad  ldc.i4   0x10000
0x14cb2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x14cb7  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x14cbc  brfalse  loc_14D4B
0x14cc1  ldarg.1
0x14cc2  ldstr    aTdTdClassMsCrm// "</td><td class='ms-crm-Cal-DeleteIconCe"...
0x14cc7  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x14ccc  ldarg.1
0x14ccd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x14cd2  ldstr    aDivOid0Onclick// "<div oid='{0}' onclick='Mscrm.Appointme"...
0x14cd7  ldc.i4.1
0x14cd8  newarr   [mscorlib]System.Object
0x14cdd  dup
0x14cde  ldc.i4.0
0x14cdf  ldloca.s 2
0x14ce1  ldstr    aD_1// "D"
0x14ce6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x14ceb  call     instance string [mscorlib]System.Guid::ToString(string, class [mscorlib]System.IFormatProvider)
0x14cf0  stelem.ref
0x14cf1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x14cf6  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x14cfb  ldstr    aAtc// "atc"
0x14d00  ldloc.1
0x14d01  ldarg.1
0x14d02  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x14d07  ldarg.1
0x14d08  ldstr    aAClassMsCrmLin_0// "><a class='ms-crm-Link' onclick='new Sy"...
0x14d0d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x14d12  ldarg.1
0x14d13  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x14d18  ldstr    aImgAlt0Title0S// "<img alt='{0}' title='{0}' src='/_imgs/"...
0x14d1d  ldc.i4.1
0x14d1e  newarr   [mscorlib]System.Object
0x14d23  dup
0x14d24  ldc.i4.0
0x14d25  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x14d2a  ldstr    aAppointmentCal// "Appointment.Calendar.DeleteIconAlt"
0x14d2f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x14d34  stelem.ref
0x14d35  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x14d3a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x14d3f  ldarg.1
0x14d40  ldstr    aADivTdTrTable// "</a></div></td></tr></table>"
0x14d45  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x14d4a  ret
0x14d4b  ldarg.1
0x14d4c  ldstr    aTdTrTable// "</td></tr></table>"
0x14d51  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x14d56  ret
```
