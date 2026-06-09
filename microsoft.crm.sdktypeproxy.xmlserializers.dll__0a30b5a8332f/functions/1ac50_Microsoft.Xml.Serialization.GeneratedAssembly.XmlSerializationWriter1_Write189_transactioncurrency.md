# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write189_transactioncurrency

- ea: `0x1ac50`
- end: `0x1adf1`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write189_transactioncurrency`
- size: `417`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x35870`
- `0x56b30`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15180`
- `0x153c0`
- `0x15430`
- `0x16cb0`
- `0x1ac50`
- `0x1ae00`

## string_xrefs

- `0x1ac95`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1aca5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1acbd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1acd5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1aceb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ad01`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ad19`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ad31`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ad47`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ad5f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ad77`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ad8f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ada7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1adbf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1add7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1aca0`: `createdby`
- `0x1acb8`: `createdon`
- `0x1ad8a`: `overriddencreatedon`

## pseudocode

```c

```

## disassembly

```asm
0x1ac50  ldarg.3
0x1ac51  brtrue.s loc_1AC60
0x1ac53  ldarg.s  4
0x1ac55  brfalse.s loc_1AC5F
0x1ac57  ldarg.0
0x1ac58  ldarg.1
0x1ac59  ldarg.2
0x1ac5a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x1ac5f  ret
0x1ac60  ldarg.s  5
0x1ac62  brtrue.s loc_1AC80
0x1ac64  ldarg.3
0x1ac65  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1ac6a  stloc.0
0x1ac6b  ldloc.0
0x1ac6c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.transactioncurrency
0x1ac71  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1ac76  beq.s    loc_1AC80
0x1ac78  ldarg.0
0x1ac79  ldarg.3
0x1ac7a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x1ac7f  throw
0x1ac80  ldarg.0
0x1ac81  ldarg.1
0x1ac82  ldarg.2
0x1ac83  ldarg.3
0x1ac84  ldc.i4.0
0x1ac85  ldnull
0x1ac86  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x1ac8b  ldarg.s  5
0x1ac8d  brfalse.s loc_1AC9F
0x1ac8f  ldarg.0
0x1ac90  ldstr    aTransactioncur_1// "transactioncurrency"
0x1ac95  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ac9a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x1ac9f  ldarg.0
0x1aca0  ldstr    aCreatedby// "createdby"
0x1aca5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1acaa  ldarg.3
0x1acab  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.transactioncurrency::get_createdby()
0x1acb0  ldc.i4.0
0x1acb1  ldc.i4.0
0x1acb2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1acb7  ldarg.0
0x1acb8  ldstr    aCreatedon// "createdon"
0x1acbd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1acc2  ldarg.3
0x1acc3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.transactioncurrency::get_createdon()
0x1acc8  ldc.i4.0
0x1acc9  ldc.i4.0
0x1acca  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1accf  ldarg.0
0x1acd0  ldstr    aCurrencyname// "currencyname"
0x1acd5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1acda  ldarg.3
0x1acdb  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.transactioncurrency::get_currencyname()
0x1ace0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1ace5  ldarg.0
0x1ace6  ldstr    aCurrencysymbol// "currencysymbol"
0x1aceb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1acf0  ldarg.3
0x1acf1  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.transactioncurrency::get_currencysymbol()
0x1acf6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1acfb  ldarg.0
0x1acfc  ldstr    aExchangerate// "exchangerate"
0x1ad01  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ad06  ldarg.3
0x1ad07  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.transactioncurrency::get_exchangerate()
0x1ad0c  ldc.i4.0
0x1ad0d  ldc.i4.0
0x1ad0e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write137_CrmDecimal(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal o, bool isNullable, bool needType)
0x1ad13  ldarg.0
0x1ad14  ldstr    aImportsequence// "importsequencenumber"
0x1ad19  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ad1e  ldarg.3
0x1ad1f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.transactioncurrency::get_importsequencenumber()
0x1ad24  ldc.i4.0
0x1ad25  ldc.i4.0
0x1ad26  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1ad2b  ldarg.0
0x1ad2c  ldstr    aIsocurrencycod// "isocurrencycode"
0x1ad31  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ad36  ldarg.3
0x1ad37  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.transactioncurrency::get_isocurrencycode()
0x1ad3c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1ad41  ldarg.0
0x1ad42  ldstr    aModifiedby// "modifiedby"
0x1ad47  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ad4c  ldarg.3
0x1ad4d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.transactioncurrency::get_modifiedby()
0x1ad52  ldc.i4.0
0x1ad53  ldc.i4.0
0x1ad54  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1ad59  ldarg.0
0x1ad5a  ldstr    aModifiedon// "modifiedon"
0x1ad5f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ad64  ldarg.3
0x1ad65  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.transactioncurrency::get_modifiedon()
0x1ad6a  ldc.i4.0
0x1ad6b  ldc.i4.0
0x1ad6c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1ad71  ldarg.0
0x1ad72  ldstr    aOrganizationid// "organizationid"
0x1ad77  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ad7c  ldarg.3
0x1ad7d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.transactioncurrency::get_organizationid()
0x1ad82  ldc.i4.0
0x1ad83  ldc.i4.0
0x1ad84  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1ad89  ldarg.0
0x1ad8a  ldstr    aOverriddencrea// "overriddencreatedon"
0x1ad8f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ad94  ldarg.3
0x1ad95  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.transactioncurrency::get_overriddencreatedon()
0x1ad9a  ldc.i4.0
0x1ad9b  ldc.i4.0
0x1ad9c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1ada1  ldarg.0
0x1ada2  ldstr    aStatecode// "statecode"
0x1ada7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1adac  ldarg.3
0x1adad  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.TransactionCurrencyStateInfo [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.transactioncurrency::get_statecode()
0x1adb2  ldc.i4.0
0x1adb3  ldc.i4.0
0x1adb4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write188_TransactionCurrencyStateInfo(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.TransactionCurrencyStateInfo o, bool isNullable, bool needType)
0x1adb9  ldarg.0
0x1adba  ldstr    aStatuscode// "statuscode"
0x1adbf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1adc4  ldarg.3
0x1adc5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.transactioncurrency::get_statuscode()
0x1adca  ldc.i4.0
0x1adcb  ldc.i4.0
0x1adcc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write144_Status(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status o, bool isNullable, bool needType)
0x1add1  ldarg.0
0x1add2  ldstr    aTransactioncur_0// "transactioncurrencyid"
0x1add7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1addc  ldarg.3
0x1addd  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.transactioncurrency::get_transactioncurrencyid()
0x1ade2  ldc.i4.0
0x1ade3  ldc.i4.0
0x1ade4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x1ade9  ldarg.0
0x1adea  ldarg.3
0x1adeb  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x1adf0  ret
```
