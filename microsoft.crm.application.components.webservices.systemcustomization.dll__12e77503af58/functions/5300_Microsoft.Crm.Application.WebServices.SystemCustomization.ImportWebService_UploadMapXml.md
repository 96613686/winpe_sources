# Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::UploadMapXml

- ea: `0x5300`
- end: `0x5484`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::UploadMapXml`
- size: `388`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x5300`

## string_xrefs

- `0x531e`: `Not a well formed Xml`

## pseudocode

```c

```

## disassembly

```asm
0x5300  ldarg.2
0x5301  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5306  brtrue.s loc_5374
0x5308  ldarg.1
0x5309  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x530e  stloc.0
0x530f  leave.s  loc_534C
0x5311  stloc.1
0x5312  ldloc.1
0x5313  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x5318  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0x531d  ldc.i4.0
0x531e  ldstr    aNotAWellFormed// "Not a well formed Xml"
0x5323  ldc.i4.2
0x5324  newarr   [mscorlib]System.Object
0x5329  dup
0x532a  ldc.i4.0
0x532b  ldloc.1
0x532c  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5331  stelem.ref
0x5332  dup
0x5333  ldc.i4.1
0x5334  ldloc.1
0x5335  stelem.ref
0x5336  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x533b  ldc.i4   0x80048426
0x5340  ldc.i4.0
0x5341  newarr   [mscorlib]System.Object
0x5346  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x534b  throw
0x534c  ldloc.0
0x534d  ldstr    aMap// "/Map"
0x5352  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x5357  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x535c  ldstr    aName_0// "Name"
0x5361  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x5366  ldarg.2
0x5367  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x536c  ldloc.0
0x536d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x5372  starg.s  1
0x5374  ldarg.1
0x5375  ldc.i4.1
0x5376  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x537b  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.ImportMappingCommand::.ctor(string, bool, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5380  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.ImportMappingCommand::Execute()
0x5385  stloc.2
0x5386  leave    loc_5482
0x538b  stloc.3
0x538c  ldloc.3
0x538d  isinst   [Microsoft.Crm.Core]Microsoft.Crm.CrmException
0x5392  stloc.s  4
0x5394  ldloc.s  4
0x5396  brfalse  loc_547A
0x539b  ldloc.s  4
0x539d  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<object, object> [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_CrmExceptionData()
0x53a2  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<object, object>::get_Count()
0x53a7  ldc.i4.0
0x53a8  ble      loc_547A
0x53ad  ldloc.3
0x53ae  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x53b3  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorInformation::.ctor(class [mscorlib]System.Exception, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x53b8  stloc.s  5
0x53ba  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x53bf  stloc.s  6
0x53c1  ldloc.s  4
0x53c3  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<object, object> [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_CrmExceptionData()
0x53c8  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<object, object>::GetEnumerator()
0x53cd  stloc.s  9
0x53cf  br.s     loc_5425
0x53d1  ldloca.s 9
0x53d3  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<object, object>::get_Current()
0x53d8  stloc.s  0xA
0x53da  ldloca.s 0xA
0x53dc  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, object>::get_Key()
0x53e1  isinst   [mscorlib]System.String
0x53e6  stloc.s  0xB
0x53e8  ldloca.s 0xA
0x53ea  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, object>::get_Value()
0x53ef  isinst   [mscorlib]System.String
0x53f4  stloc.s  0xC
0x53f6  ldloc.s  0xB
0x53f8  brfalse.s loc_5425
0x53fa  ldloc.s  0xC
0x53fc  brfalse.s loc_5425
0x53fe  ldloc.s  0xB
0x5400  ldstr    aCallstack// "CallStack"
0x5405  ldc.i4.4
0x5406  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x540b  brfalse.s loc_5425
0x540d  ldloc.s  0xB
0x540f  ldstr    aOperationstatu// "OperationStatus"
0x5414  ldc.i4.4
0x5415  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x541a  brfalse.s loc_5425
0x541c  ldloc.s  6
0x541e  ldloc.s  0xC
0x5420  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5425  ldloca.s 9
0x5427  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<object, object>::MoveNext()
0x542c  brtrue.s loc_53D1
0x542e  leave.s  loc_543E
0x5430  ldloca.s 9
0x5432  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<object, object>
0x5438  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x543d  endfinally
0x543e  ldloc.s  6
0x5440  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x5445  newarr   [mscorlib]System.String
0x544a  stloc.s  7
0x544c  ldloc.s  6
0x544e  ldloc.s  7
0x5450  ldc.i4.0
0x5451  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::CopyTo(var<u1>[], !!T0)
0x5456  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x545b  ldloc.s  5
0x545d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorInformation::get_DisplayText()
0x5462  ldloc.s  7
0x5464  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5469  stloc.s  8
0x546b  ldarg.0
0x546c  ldloc.s  8
0x546e  ldc.i4.0
0x546f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x5474  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x5479  throw
0x547a  ldarg.0
0x547b  ldloc.3
0x547c  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x5481  throw
0x5482  ldloc.2
0x5483  ret
```
