# Microsoft.Crm.CrmException::WriteDetailToXml

- ea: `0x1ac60`
- end: `0x1ae4a`
- name: `Microsoft.Crm.CrmException::WriteDetailToXml`
- size: `490`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1ac60`
- `0x1ae50`
- `0x1f510`

## string_xrefs

- `0x1ace1`: `DataContractSerializer.WriteObject() failed with: EXCEPTION: `
- `0x1ad4d`: `Detail (can not be showed in XML form): {0}.`
- `0x1adae`: `Detail (can not be showed in XML form): {0}.`
- `0x1add6`: `Detail can not be showed. DataContractSerializer.WriteObject() failed with: EXCEPTION: {0}. Message: {1}`
- `0x1ae05`: `Detail can not be showed. DataContractSerializer.WriteObject() failed with: EXCEPTION: {0}. Message: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x1ac60  ldtoken  mvar<u1>
0x1ac65  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1ac6a  newobj   instance void [System.Runtime.Serialization]System.Runtime.Serialization.DataContractSerializer::.ctor(class [mscorlib]System.Type)
0x1ac6f  stloc.0
0x1ac70  newobj   instance void [System.Xml]System.Xml.XmlWriterSettings::.ctor()
0x1ac75  stloc.1
0x1ac76  ldloc.1
0x1ac77  ldc.i4.1
0x1ac78  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_Indent(bool)
0x1ac7d  ldloc.1
0x1ac7e  ldc.i4.1
0x1ac7f  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_OmitXmlDeclaration(bool)
0x1ac84  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1ac89  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.IFormatProvider)
0x1ac8e  stloc.2
0x1ac8f  ldloc.2
0x1ac90  ldloc.1
0x1ac91  call     class [System.Xml]System.Xml.XmlWriter [System.Xml]System.Xml.XmlWriter::Create(class [mscorlib]System.IO.TextWriter, class [System.Xml]System.Xml.XmlWriterSettings)
0x1ac96  stloc.3
0x1ac97  ldloc.0
0x1ac98  ldloc.3
0x1ac99  ldarg.0
0x1ac9a  castclass class [System.ServiceModel]System.ServiceModel.FaultException`1<mvar<u1>>
0x1ac9f  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<mvar<u1>>::get_Detail()
0x1aca4  box      mvar<u1>
0x1aca9  callvirt instance void [System.Runtime.Serialization]System.Runtime.Serialization.XmlObjectSerializer::WriteObject(class [System.Xml]System.Xml.XmlWriter, object)
0x1acae  ldloc.3
0x1acaf  callvirt instance void [System.Xml]System.Xml.XmlWriter::Flush()
0x1acb4  ldarg.1
0x1acb5  ldloc.2
0x1acb6  callvirt instance string [mscorlib]System.Object::ToString()
0x1acbb  stind.ref
0x1acbc  leave    loc_1AE40
0x1acc1  stloc.s  4
0x1acc3  ldloc.s  4
0x1acc5  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1acca  ldc.i4.s 0x14
0x1accc  ldstr    a0// "{0}"
0x1acd1  ldc.i4.1
0x1acd2  newarr   [mscorlib]System.Object
0x1acd7  dup
0x1acd8  ldc.i4.0
0x1acd9  ldc.i4.4
0x1acda  newarr   [mscorlib]System.Object
0x1acdf  dup
0x1ace0  ldc.i4.0
0x1ace1  ldstr    aDatacontractse// "DataContractSerializer.WriteObject() fa"...
0x1ace6  stelem.ref
0x1ace7  dup
0x1ace8  ldc.i4.1
0x1ace9  ldloc.s  4
0x1aceb  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x1acf0  stelem.ref
0x1acf1  dup
0x1acf2  ldc.i4.2
0x1acf3  ldstr    asc_7CC52// ": "
0x1acf8  stelem.ref
0x1acf9  dup
0x1acfa  ldc.i4.3
0x1acfb  ldloc.s  4
0x1acfd  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1ad02  stelem.ref
0x1ad03  call     string [mscorlib]System.String::Concat(object[])
0x1ad08  stelem.ref
0x1ad09  call     void Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x1ad0e  ldtoken  mvar<u1>
0x1ad13  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1ad18  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault
0x1ad1d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1ad22  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1ad27  brfalse.s loc_1AD72
0x1ad29  ldarg.0
0x1ad2a  castclass class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>
0x1ad2f  stloc.s  5
0x1ad31  ldloc.s  5
0x1ad33  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x1ad38  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_Message()
0x1ad3d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1ad42  brtrue   loc_1ADFB
0x1ad47  ldarg.1
0x1ad48  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1ad4d  ldstr    aDetailCanNotBe// "Detail (can not be showed in XML form):"...
0x1ad52  ldc.i4.1
0x1ad53  newarr   [mscorlib]System.Object
0x1ad58  dup
0x1ad59  ldc.i4.0
0x1ad5a  ldloc.s  5
0x1ad5c  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x1ad61  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_Message()
0x1ad66  stelem.ref
0x1ad67  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1ad6c  stind.ref
0x1ad6d  br       loc_1ADFB
0x1ad72  ldtoken  mvar<u1>
0x1ad77  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1ad7c  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DiscoveryServiceFault
0x1ad81  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1ad86  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1ad8b  brfalse.s loc_1ADD0
0x1ad8d  ldarg.0
0x1ad8e  castclass class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DiscoveryServiceFault>
0x1ad93  stloc.s  6
0x1ad95  ldloc.s  6
0x1ad97  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DiscoveryServiceFault>::get_Detail()
0x1ad9c  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_Message()
0x1ada1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1ada6  brtrue.s loc_1ADFB
0x1ada8  ldarg.1
0x1ada9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1adae  ldstr    aDetailCanNotBe// "Detail (can not be showed in XML form):"...
0x1adb3  ldc.i4.1
0x1adb4  newarr   [mscorlib]System.Object
0x1adb9  dup
0x1adba  ldc.i4.0
0x1adbb  ldloc.s  6
0x1adbd  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DiscoveryServiceFault>::get_Detail()
0x1adc2  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_Message()
0x1adc7  stelem.ref
0x1adc8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1adcd  stind.ref
0x1adce  br.s     loc_1ADFB
0x1add0  ldarg.1
0x1add1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1add6  ldstr    aDetailCanNotBe_0// "Detail can not be showed. DataContractS"...
0x1addb  ldc.i4.2
0x1addc  newarr   [mscorlib]System.Object
0x1ade1  dup
0x1ade2  ldc.i4.0
0x1ade3  ldloc.s  4
0x1ade5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x1adea  stelem.ref
0x1adeb  dup
0x1adec  ldc.i4.1
0x1aded  ldloc.s  4
0x1adef  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1adf4  stelem.ref
0x1adf5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1adfa  stind.ref
0x1adfb  leave.s  loc_1AE40
0x1adfd  stloc.s  7
0x1adff  ldarg.1
0x1ae00  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1ae05  ldstr    aDetailCanNotBe_0// "Detail can not be showed. DataContractS"...
0x1ae0a  ldc.i4.2
0x1ae0b  newarr   [mscorlib]System.Object
0x1ae10  dup
0x1ae11  ldc.i4.0
0x1ae12  ldloc.s  7
0x1ae14  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x1ae19  stelem.ref
0x1ae1a  dup
0x1ae1b  ldc.i4.1
0x1ae1c  ldloc.s  7
0x1ae1e  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1ae23  stelem.ref
0x1ae24  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1ae29  stind.ref
0x1ae2a  leave.s  loc_1AE40
0x1ae2c  ldloc.3
0x1ae2d  brfalse.s loc_1AE35
0x1ae2f  ldloc.3
0x1ae30  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1ae35  endfinally
0x1ae36  ldloc.2
0x1ae37  brfalse.s loc_1AE3F
0x1ae39  ldloc.2
0x1ae3a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1ae3f  endfinally
0x1ae40  ldarg.1
0x1ae41  ldarg.1
0x1ae42  ldind.ref
0x1ae43  call     string Microsoft.Crm.CrmException::XmlCharacterAllowedList(string value)
0x1ae48  stind.ref
0x1ae49  ret
```
