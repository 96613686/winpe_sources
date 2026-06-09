# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write442_annualfiscalcalendar

- ea: `0x2cfb0`
- end: `0x2d16f`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write442_annualfiscalcalendar`
- size: `447`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x37f60`
- `0x574d0`

## callees

- `0x5cf0`
- `0x5e50`
- `0x150d0`
- `0x15180`
- `0x153c0`
- `0x15430`
- `0x2cfb0`

## string_xrefs

- `0x2cff5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2d005`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2d01d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2d035`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2d04d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2d065`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2d07d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2d095`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2d0ad`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2d0c5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2d0dd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2d0f5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2d10d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2d125`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2d13d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2d155`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2d048`: `createdby`
- `0x2d060`: `createdon`

## pseudocode

```c

```

## disassembly

```asm
0x2cfb0  ldarg.3
0x2cfb1  brtrue.s loc_2CFC0
0x2cfb3  ldarg.s  4
0x2cfb5  brfalse.s loc_2CFBF
0x2cfb7  ldarg.0
0x2cfb8  ldarg.1
0x2cfb9  ldarg.2
0x2cfba  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x2cfbf  ret
0x2cfc0  ldarg.s  5
0x2cfc2  brtrue.s loc_2CFE0
0x2cfc4  ldarg.3
0x2cfc5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2cfca  stloc.0
0x2cfcb  ldloc.0
0x2cfcc  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.annualfiscalcalendar
0x2cfd1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2cfd6  beq.s    loc_2CFE0
0x2cfd8  ldarg.0
0x2cfd9  ldarg.3
0x2cfda  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x2cfdf  throw
0x2cfe0  ldarg.0
0x2cfe1  ldarg.1
0x2cfe2  ldarg.2
0x2cfe3  ldarg.3
0x2cfe4  ldc.i4.0
0x2cfe5  ldnull
0x2cfe6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x2cfeb  ldarg.s  5
0x2cfed  brfalse.s loc_2CFFF
0x2cfef  ldarg.0
0x2cff0  ldstr    aAnnualfiscalca// "annualfiscalcalendar"
0x2cff5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2cffa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x2cfff  ldarg.0
0x2d000  ldstr    aAnnual// "annual"
0x2d005  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2d00a  ldarg.3
0x2d00b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.annualfiscalcalendar::get_annual()
0x2d010  ldc.i4.0
0x2d011  ldc.i4.0
0x2d012  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x2d017  ldarg.0
0x2d018  ldstr    aAnnualBase// "annual_base"
0x2d01d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2d022  ldarg.3
0x2d023  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.annualfiscalcalendar::get_annual_base()
0x2d028  ldc.i4.0
0x2d029  ldc.i4.0
0x2d02a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x2d02f  ldarg.0
0x2d030  ldstr    aBusinessunitid// "businessunitid"
0x2d035  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2d03a  ldarg.3
0x2d03b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.annualfiscalcalendar::get_businessunitid()
0x2d040  ldc.i4.0
0x2d041  ldc.i4.0
0x2d042  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2d047  ldarg.0
0x2d048  ldstr    aCreatedby// "createdby"
0x2d04d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2d052  ldarg.3
0x2d053  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.annualfiscalcalendar::get_createdby()
0x2d058  ldc.i4.0
0x2d059  ldc.i4.0
0x2d05a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2d05f  ldarg.0
0x2d060  ldstr    aCreatedon// "createdon"
0x2d065  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2d06a  ldarg.3
0x2d06b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.annualfiscalcalendar::get_createdon()
0x2d070  ldc.i4.0
0x2d071  ldc.i4.0
0x2d072  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2d077  ldarg.0
0x2d078  ldstr    aEffectiveon// "effectiveon"
0x2d07d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2d082  ldarg.3
0x2d083  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.annualfiscalcalendar::get_effectiveon()
0x2d088  ldc.i4.0
0x2d089  ldc.i4.0
0x2d08a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2d08f  ldarg.0
0x2d090  ldstr    aExchangerate// "exchangerate"
0x2d095  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2d09a  ldarg.3
0x2d09b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.annualfiscalcalendar::get_exchangerate()
0x2d0a0  ldc.i4.0
0x2d0a1  ldc.i4.0
0x2d0a2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write137_CrmDecimal(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal o, bool isNullable, bool needType)
0x2d0a7  ldarg.0
0x2d0a8  ldstr    aFiscalperiodty// "fiscalperiodtype"
0x2d0ad  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2d0b2  ldarg.3
0x2d0b3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.annualfiscalcalendar::get_fiscalperiodtype()
0x2d0b8  ldc.i4.0
0x2d0b9  ldc.i4.0
0x2d0ba  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2d0bf  ldarg.0
0x2d0c0  ldstr    aModifiedby// "modifiedby"
0x2d0c5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2d0ca  ldarg.3
0x2d0cb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.annualfiscalcalendar::get_modifiedby()
0x2d0d0  ldc.i4.0
0x2d0d1  ldc.i4.0
0x2d0d2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2d0d7  ldarg.0
0x2d0d8  ldstr    aModifiedon// "modifiedon"
0x2d0dd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2d0e2  ldarg.3
0x2d0e3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.annualfiscalcalendar::get_modifiedon()
0x2d0e8  ldc.i4.0
0x2d0e9  ldc.i4.0
0x2d0ea  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2d0ef  ldarg.0
0x2d0f0  ldstr    aSalespersonid// "salespersonid"
0x2d0f5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2d0fa  ldarg.3
0x2d0fb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.annualfiscalcalendar::get_salespersonid()
0x2d100  ldc.i4.0
0x2d101  ldc.i4.0
0x2d102  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2d107  ldarg.0
0x2d108  ldstr    aTimezoneruleve// "timezoneruleversionnumber"
0x2d10d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2d112  ldarg.3
0x2d113  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.annualfiscalcalendar::get_timezoneruleversionnumber()
0x2d118  ldc.i4.0
0x2d119  ldc.i4.0
0x2d11a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2d11f  ldarg.0
0x2d120  ldstr    aTransactioncur_0// "transactioncurrencyid"
0x2d125  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2d12a  ldarg.3
0x2d12b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.annualfiscalcalendar::get_transactioncurrencyid()
0x2d130  ldc.i4.0
0x2d131  ldc.i4.0
0x2d132  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2d137  ldarg.0
0x2d138  ldstr    aUserfiscalcale// "userfiscalcalendarid"
0x2d13d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2d142  ldarg.3
0x2d143  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.annualfiscalcalendar::get_userfiscalcalendarid()
0x2d148  ldc.i4.0
0x2d149  ldc.i4.0
0x2d14a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x2d14f  ldarg.0
0x2d150  ldstr    aUtcconversiont// "utcconversiontimezonecode"
0x2d155  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2d15a  ldarg.3
0x2d15b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.annualfiscalcalendar::get_utcconversiontimezonecode()
0x2d160  ldc.i4.0
0x2d161  ldc.i4.0
0x2d162  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2d167  ldarg.0
0x2d168  ldarg.3
0x2d169  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x2d16e  ret
```
