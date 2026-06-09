# Microsoft.Crm.Protocols.WSTrust.Bindings.IssuedTokenWSTrustBinding::AddAlgorithmParameters

- ea: `0xf30`
- end: `0xff4`
- name: `Microsoft.Crm.Protocols.WSTrust.Bindings.IssuedTokenWSTrustBinding::AddAlgorithmParameters`
- size: `196`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x11e0`

## callees

- `0xf30`
- `0x1020`
- `0x10a0`
- `0x1120`
- `0x11a0`
- `0x12f0`

## pseudocode

```c

```

## disassembly

```asm
0xf30  ldarg.s  4
0xf32  ldind.ref
0xf33  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Xml]System.Xml.XmlElement> [System.ServiceModel]System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters::get_AdditionalRequestParameters()
0xf38  ldc.i4.0
0xf39  ldarg.0
0xf3a  ldarg.1
0xf3b  callvirt instance string [System.ServiceModel]System.ServiceModel.Security.SecurityAlgorithmSuite::get_DefaultEncryptionAlgorithm()
0xf40  call     instance class [System.Xml]System.Xml.XmlElement Microsoft.Crm.Protocols.WSTrust.Bindings.IssuedTokenWSTrustBinding::CreateEncryptionAlgorithmElement(string encryptionAlgorithm)
0xf45  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Xml]System.Xml.XmlElement>::Insert(int32, var<u1>)
0xf4a  ldarg.s  4
0xf4c  ldind.ref
0xf4d  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Xml]System.Xml.XmlElement> [System.ServiceModel]System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters::get_AdditionalRequestParameters()
0xf52  ldc.i4.0
0xf53  ldarg.0
0xf54  ldarg.1
0xf55  callvirt instance string [System.ServiceModel]System.ServiceModel.Security.SecurityAlgorithmSuite::get_DefaultCanonicalizationAlgorithm()
0xf5a  call     instance class [System.Xml]System.Xml.XmlElement Microsoft.Crm.Protocols.WSTrust.Bindings.IssuedTokenWSTrustBinding::CreateCanonicalizationAlgorithmElement(string canonicalizationAlgorithm)
0xf5f  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Xml]System.Xml.XmlElement>::Insert(int32, var<u1>)
0xf64  ldnull
0xf65  stloc.0
0xf66  ldnull
0xf67  stloc.1
0xf68  ldarg.3
0xf69  switch   loc_F7C, loc_F8C, loc_F9C
0xf7a  br.s     loc_F9D
0xf7c  ldarg.1
0xf7d  callvirt instance string [System.ServiceModel]System.ServiceModel.Security.SecurityAlgorithmSuite::get_DefaultSymmetricSignatureAlgorithm()
0xf82  stloc.0
0xf83  ldarg.1
0xf84  callvirt instance string [System.ServiceModel]System.ServiceModel.Security.SecurityAlgorithmSuite::get_DefaultEncryptionAlgorithm()
0xf89  stloc.1
0xf8a  br.s     loc_FA8
0xf8c  ldarg.1
0xf8d  callvirt instance string [System.ServiceModel]System.ServiceModel.Security.SecurityAlgorithmSuite::get_DefaultAsymmetricSignatureAlgorithm()
0xf92  stloc.0
0xf93  ldarg.1
0xf94  callvirt instance string [System.ServiceModel]System.ServiceModel.Security.SecurityAlgorithmSuite::get_DefaultAsymmetricKeyWrapAlgorithm()
0xf99  stloc.1
0xf9a  br.s     loc_FA8
0xf9c  ret
0xf9d  ldstr    aKeytype// "keyType"
0xfa2  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0xfa7  throw
0xfa8  ldarg.s  4
0xfaa  ldind.ref
0xfab  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Xml]System.Xml.XmlElement> [System.ServiceModel]System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters::get_AdditionalRequestParameters()
0xfb0  ldc.i4.0
0xfb1  ldarg.0
0xfb2  ldloc.0
0xfb3  call     instance class [System.Xml]System.Xml.XmlElement Microsoft.Crm.Protocols.WSTrust.Bindings.IssuedTokenWSTrustBinding::CreateSignWithElement(string signatureAlgorithm)
0xfb8  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Xml]System.Xml.XmlElement>::Insert(int32, var<u1>)
0xfbd  ldarg.s  4
0xfbf  ldind.ref
0xfc0  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Xml]System.Xml.XmlElement> [System.ServiceModel]System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters::get_AdditionalRequestParameters()
0xfc5  ldc.i4.0
0xfc6  ldarg.0
0xfc7  ldloc.1
0xfc8  call     instance class [System.Xml]System.Xml.XmlElement Microsoft.Crm.Protocols.WSTrust.Bindings.IssuedTokenWSTrustBinding::CreateEncryptWithElement(string encryptionAlgorithm)
0xfcd  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Xml]System.Xml.XmlElement>::Insert(int32, var<u1>)
0xfd2  ldarg.2
0xfd3  call     class [System.ServiceModel]System.ServiceModel.Security.TrustVersion [System.ServiceModel]System.ServiceModel.Security.TrustVersion::get_WSTrustFeb2005()
0xfd8  beq.s    loc_FF3
0xfda  ldarg.s  4
0xfdc  ldind.ref
0xfdd  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Xml]System.Xml.XmlElement> [System.ServiceModel]System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters::get_AdditionalRequestParameters()
0xfe2  ldc.i4.0
0xfe3  ldarg.1
0xfe4  callvirt instance string [System.ServiceModel]System.ServiceModel.Security.SecurityAlgorithmSuite::get_DefaultAsymmetricKeyWrapAlgorithm()
0xfe9  call     class [System.Xml]System.Xml.XmlElement Microsoft.Crm.Protocols.WSTrust.Bindings.IssuedTokenWSTrustBinding::CreateKeyWrapAlgorithmElement(string keyWrapAlgorithm)
0xfee  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Xml]System.Xml.XmlElement>::Insert(int32, var<u1>)
0xff3  ret
```
