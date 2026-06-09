# Microsoft.Crm.Asynchronous.AvgResourceCountPerServiceAppointmentCollector::GetTotalResourceParticipantCount

- ea: `0x49f0`
- end: `0x4b3f`
- name: `Microsoft.Crm.Asynchronous.AvgResourceCountPerServiceAppointmentCollector::GetTotalResourceParticipantCount`
- size: `335`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x4990`

## callees

- `0x4310`
- `0x49f0`
- `0x5030`

## string_xrefs

- `0x4a97`: `<link-entity name='activitypointer' from='activityid' to='activityid' alias='activitypointer'>`
- `0x4adf`: `</link-entity>`

## pseudocode

```c

```

## disassembly

```asm
0x49f0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x49f5  stloc.0
0x49f6  ldloc.0
0x49f7  ldstr    aFetchAggregate// "<fetch aggregate='true'>"
0x49fc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4a01  pop
0x4a02  ldloc.0
0x4a03  ldstr    aEntityNameActi// "<entity name='activityparty'>"
0x4a08  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4a0d  pop
0x4a0e  ldloc.0
0x4a0f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4a14  ldstr    aAttributeNameA_0// "<attribute name='activitypartyid' aggre"...
0x4a19  ldc.i4.0
0x4a1a  newarr   [mscorlib]System.Object
0x4a1f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x4a24  pop
0x4a25  ldloc.0
0x4a26  ldstr    aFilterTypeAnd// "<filter type='and'>"
0x4a2b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4a30  pop
0x4a31  ldloc.0
0x4a32  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4a37  ldstr    aConditionAttri_5// "<condition attribute='participationtype"...
0x4a3c  ldc.i4.1
0x4a3d  newarr   [mscorlib]System.Object
0x4a42  dup
0x4a43  ldc.i4.0
0x4a44  ldc.i4.s 0xA
0x4a46  box      [mscorlib]System.Int32
0x4a4b  stelem.ref
0x4a4c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x4a51  pop
0x4a52  ldloc.0
0x4a53  ldstr    aFilter// "</filter>"
0x4a58  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4a5d  pop
0x4a5e  ldloc.0
0x4a5f  ldstr    aFilterTypeAnd// "<filter type='and'>"
0x4a64  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4a69  pop
0x4a6a  ldloc.0
0x4a6b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4a70  ldstr    aConditionAttri_6// "<condition attribute='partyobjecttypeco"...
0x4a75  ldc.i4.1
0x4a76  newarr   [mscorlib]System.Object
0x4a7b  dup
0x4a7c  ldc.i4.0
0x4a7d  ldarg.1
0x4a7e  box      [mscorlib]System.Int32
0x4a83  stelem.ref
0x4a84  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x4a89  pop
0x4a8a  ldloc.0
0x4a8b  ldstr    aFilter// "</filter>"
0x4a90  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4a95  pop
0x4a96  ldloc.0
0x4a97  ldstr    aLinkEntityName// "<link-entity name='activitypointer' fro"...
0x4a9c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4aa1  pop
0x4aa2  ldloc.0
0x4aa3  ldstr    aFilterTypeAnd// "<filter type='and'>"
0x4aa8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4aad  pop
0x4aae  ldloc.0
0x4aaf  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4ab4  ldstr    aConditionAttri_7// "<condition attribute='activitytypecode'"...
0x4ab9  ldc.i4.1
0x4aba  newarr   [mscorlib]System.Object
0x4abf  dup
0x4ac0  ldc.i4.0
0x4ac1  ldc.i4   0x1076
0x4ac6  box      [mscorlib]System.Int32
0x4acb  stelem.ref
0x4acc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x4ad1  pop
0x4ad2  ldloc.0
0x4ad3  ldstr    aFilter// "</filter>"
0x4ad8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4add  pop
0x4ade  ldloc.0
0x4adf  ldstr    aLinkEntity// "</link-entity>"
0x4ae4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4ae9  pop
0x4aea  ldloc.0
0x4aeb  ldstr    aEntity_0// "</entity>"
0x4af0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4af5  pop
0x4af6  ldloc.0
0x4af7  ldstr    aFetch// "</fetch>"
0x4afc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4b01  pop
0x4b02  ldarg.0
0x4b03  call     instance class Microsoft.Crm.Asynchronous.PlatformCollectorHelper Microsoft.Crm.Asynchronous.SqmCollectorBase::get_PlatformCollectorHelper()
0x4b08  ldloc.0
0x4b09  callvirt instance string [mscorlib]System.Object::ToString()
0x4b0e  ldarg.0
0x4b0f  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.AvgResourceCountPerServiceAppointmentCollector::_configuration
0x4b14  callvirt instance string Microsoft.Crm.Asynchronous.PlatformCollectorHelper::ExecuteFetch(string fetchSpecification, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration configuration)
0x4b19  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x4b1e  ldstr    aResultsetResul_0// "/resultset/result/EntityCount"
0x4b23  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x4b28  stloc.1
0x4b29  ldloc.1
0x4b2a  brtrue.s loc_4B2E
0x4b2c  ldc.i4.0
0x4b2d  ret
0x4b2e  ldloc.1
0x4b2f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x4b34  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4b39  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x4b3e  ret
```
