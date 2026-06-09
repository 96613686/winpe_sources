# Microsoft.Crm.BusinessEntities.SoapContext::Initialize

- ea: `0x78a60`
- end: `0x78b46`
- name: `Microsoft.Crm.BusinessEntities.SoapContext::Initialize`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x78540`

## callees

- `0x78a60`

## string_xrefs

- `0x78a99`: `/MSCRMServices/`
- `0x78a9f`: `/XRMServices/`
- `0x78af5`: `Url does not contain MSCRMServices or XRMServices`

## pseudocode

```c

```

## disassembly

```asm
0x78a60  ldarg.2
0x78a61  ldnull
0x78a62  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x78a67  brtrue.s loc_78A76
0x78a69  ldarg.2
0x78a6a  callvirt instance string [mscorlib]System.Object::ToString()
0x78a6f  callvirt instance int32 [mscorlib]System.String::get_Length()
0x78a74  brtrue.s loc_78A86
0x78a76  ldstr    aUrlNotSpecifie// "Url not specified in the SOAP request"
0x78a7b  ldc.i4   0x80040203
0x78a80  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x78a85  throw
0x78a86  ldarg.0
0x78a87  ldarg.2
0x78a88  callvirt instance string [mscorlib]System.Object::ToString()
0x78a8d  stfld    string Microsoft.Crm.BusinessEntities.SoapContext::_address
0x78a92  ldarg.0
0x78a93  ldarg.3
0x78a94  stfld    string Microsoft.Crm.BusinessEntities.SoapContext::_crmMethodName
0x78a99  ldstr    aMscrmservices// "/MSCRMServices/"
0x78a9e  stloc.0
0x78a9f  ldstr    aXrmservices// "/XRMServices/"
0x78aa4  stloc.1
0x78aa5  ldarg.2
0x78aa6  callvirt instance string [System]System.Uri::get_AbsolutePath()
0x78aab  ldloc.0
0x78aac  ldc.i4.5
0x78aad  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x78ab2  brfalse.s loc_78ACD
0x78ab4  ldarg.0
0x78ab5  ldarg.2
0x78ab6  callvirt instance string [System]System.Uri::get_AbsolutePath()
0x78abb  ldloc.0
0x78abc  callvirt instance int32 [mscorlib]System.String::get_Length()
0x78ac1  callvirt instance string [mscorlib]System.String::Substring(int32)
0x78ac6  stfld    string Microsoft.Crm.BusinessEntities.SoapContext::_endpoint
0x78acb  br.s     loc_78B05
0x78acd  ldarg.2
0x78ace  callvirt instance string [System]System.Uri::get_AbsolutePath()
0x78ad3  ldloc.1
0x78ad4  ldc.i4.5
0x78ad5  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x78ada  brfalse.s loc_78AF5
0x78adc  ldarg.0
0x78add  ldarg.2
0x78ade  callvirt instance string [System]System.Uri::get_AbsolutePath()
0x78ae3  ldloc.1
0x78ae4  callvirt instance int32 [mscorlib]System.String::get_Length()
0x78ae9  callvirt instance string [mscorlib]System.String::Substring(int32)
0x78aee  stfld    string Microsoft.Crm.BusinessEntities.SoapContext::_endpoint
0x78af3  br.s     loc_78B05
0x78af5  ldstr    aUrlDoesNotCont// "Url does not contain MSCRMServices or X"...
0x78afa  ldc.i4   0x80040203
0x78aff  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x78b04  throw
0x78b05  ldarg.1
0x78b06  brfalse.s loc_78B10
0x78b08  ldarg.1
0x78b09  callvirt instance int32 [mscorlib]System.String::get_Length()
0x78b0e  brtrue.s loc_78B20
0x78b10  ldstr    aSoapactionHead// "SOAPAction header not specified in the "...
0x78b15  ldc.i4   0x80040203
0x78b1a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x78b1f  throw
0x78b20  ldarg.0
0x78b21  ldstr    aSoapaction// "SOAPAction: "
0x78b26  ldarg.1
0x78b27  ldstr    asc_CA1D0// "\r\n"
0x78b2c  call     string [mscorlib]System.String::Concat(string, string, string)
0x78b31  stfld    string Microsoft.Crm.BusinessEntities.SoapContext::_httpHeader
0x78b36  ldarg.0
0x78b37  ldarg.s  4
0x78b39  stfld    string Microsoft.Crm.BusinessEntities.SoapContext::_soapXml
0x78b3e  ldarg.0
0x78b3f  ldc.i4.0
0x78b40  stfld    bool Microsoft.Crm.BusinessEntities.SoapContext::_isCaptured
0x78b45  ret
```
