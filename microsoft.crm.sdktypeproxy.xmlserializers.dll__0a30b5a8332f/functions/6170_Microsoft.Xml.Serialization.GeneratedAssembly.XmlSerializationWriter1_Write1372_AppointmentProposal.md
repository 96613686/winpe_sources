# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1372_AppointmentProposal

- ea: `0x6170`
- end: `0x626d`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1372_AppointmentProposal`
- size: `253`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1940`
- `0x6ac0`
- `0x5ecd0`

## callees

- `0x5cf0`
- `0x6170`
- `0x6270`

## string_xrefs

- `0x61b5`: `http://schemas.microsoft.com/crm/2006/Scheduling`
- `0x61c5`: `http://schemas.microsoft.com/crm/2006/Scheduling`
- `0x61dd`: `http://schemas.microsoft.com/crm/2006/Scheduling`
- `0x61f5`: `http://schemas.microsoft.com/crm/2006/Scheduling`
- `0x6210`: `http://schemas.microsoft.com/crm/2006/Scheduling`
- `0x6230`: `http://schemas.microsoft.com/crm/2006/Scheduling`
- `0x6246`: `http://schemas.microsoft.com/crm/2006/Scheduling`

## pseudocode

```c

```

## disassembly

```asm
0x6170  ldarg.3
0x6171  brtrue.s loc_6180
0x6173  ldarg.s  4
0x6175  brfalse.s loc_617F
0x6177  ldarg.0
0x6178  ldarg.1
0x6179  ldarg.2
0x617a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x617f  ret
0x6180  ldarg.s  5
0x6182  brtrue.s loc_61A0
0x6184  ldarg.3
0x6185  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x618a  stloc.0
0x618b  ldloc.0
0x618c  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AppointmentProposal
0x6191  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6196  beq.s    loc_61A0
0x6198  ldarg.0
0x6199  ldarg.3
0x619a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x619f  throw
0x61a0  ldarg.0
0x61a1  ldarg.1
0x61a2  ldarg.2
0x61a3  ldarg.3
0x61a4  ldc.i4.0
0x61a5  ldnull
0x61a6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x61ab  ldarg.s  5
0x61ad  brfalse.s loc_61BF
0x61af  ldarg.0
0x61b0  ldstr    aAppointmentpro// "AppointmentProposal"
0x61b5  ldstr    aHttpSchemasMic_4// "http://schemas.microsoft.com/crm/2006/S"...
0x61ba  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x61bf  ldarg.0
0x61c0  ldstr    aStart// "Start"
0x61c5  ldstr    aHttpSchemasMic_4// "http://schemas.microsoft.com/crm/2006/S"...
0x61ca  ldarg.3
0x61cb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AppointmentProposal::get_Start()
0x61d0  ldc.i4.0
0x61d1  ldc.i4.0
0x61d2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x61d7  ldarg.0
0x61d8  ldstr    aEnd// "End"
0x61dd  ldstr    aHttpSchemasMic_4// "http://schemas.microsoft.com/crm/2006/S"...
0x61e2  ldarg.3
0x61e3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AppointmentProposal::get_End()
0x61e8  ldc.i4.0
0x61e9  ldc.i4.0
0x61ea  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x61ef  ldarg.0
0x61f0  ldstr    aSiteid// "SiteId"
0x61f5  ldstr    aHttpSchemasMic_4// "http://schemas.microsoft.com/crm/2006/S"...
0x61fa  ldarg.3
0x61fb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AppointmentProposal::get_SiteId()
0x6200  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x6205  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x620a  ldarg.0
0x620b  ldstr    aSitename// "SiteName"
0x6210  ldstr    aHttpSchemasMic_4// "http://schemas.microsoft.com/crm/2006/S"...
0x6215  ldarg.3
0x6216  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AppointmentProposal::get_SiteName()
0x621b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x6220  ldarg.3
0x6221  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.ProposalParty[] [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AppointmentProposal::get_ProposalParties()
0x6226  stloc.1
0x6227  ldloc.1
0x6228  brfalse.s loc_6265
0x622a  ldarg.0
0x622b  ldstr    aProposalpartie// "ProposalParties"
0x6230  ldstr    aHttpSchemasMic_4// "http://schemas.microsoft.com/crm/2006/S"...
0x6235  ldnull
0x6236  ldc.i4.0
0x6237  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x623c  ldc.i4.0
0x623d  stloc.2
0x623e  br.s     loc_6259
0x6240  ldarg.0
0x6241  ldstr    aProposalparty// "ProposalParty"
0x6246  ldstr    aHttpSchemasMic_4// "http://schemas.microsoft.com/crm/2006/S"...
0x624b  ldloc.1
0x624c  ldloc.2
0x624d  ldelem.ref
0x624e  ldc.i4.1
0x624f  ldc.i4.0
0x6250  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1371_ProposalParty(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.ProposalParty o, bool isNullable, bool needType)
0x6255  ldloc.2
0x6256  ldc.i4.1
0x6257  add
0x6258  stloc.2
0x6259  ldloc.2
0x625a  ldloc.1
0x625b  ldlen
0x625c  conv.i4
0x625d  blt.s    loc_6240
0x625f  ldarg.0
0x6260  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x6265  ldarg.0
0x6266  ldarg.3
0x6267  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x626c  ret
```
