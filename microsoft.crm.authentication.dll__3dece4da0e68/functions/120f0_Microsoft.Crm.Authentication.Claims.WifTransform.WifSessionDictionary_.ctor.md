# Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::.ctor

- ea: `0x120f0`
- end: `0x12548`
- name: `Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::.ctor`
- size: `1112`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x12550`

## string_xrefs

- `0x12109`: `SecurityContextToken`
- `0x1235c`: `SessionToken`
- `0x1236d`: `SessionTokenCookie`
- `0x1237e`: `BootStrapToken`
- `0x1244a`: `WindowsSidClaim`
- `0x1245b`: `DenyOnlySidClaim`
- `0x124b0`: `RsaClaim`
- `0x1223b`: `http://schemas.xmlsoap.org/ws/2005/05/identity/issuer/self`

## pseudocode

```c

```

## disassembly

```asm
0x120f0  ldarg.0
0x120f1  call     instance void [System.Runtime.Serialization]System.Xml.XmlDictionary::.ctor()
0x120f6  ldarg.0
0x120f7  ldarg.0
0x120f8  ldstr    aClaim// "Claim"
0x120fd  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x12102  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_claim
0x12107  ldarg.0
0x12108  ldarg.0
0x12109  ldstr    aSecuritycontex// "SecurityContextToken"
0x1210e  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x12113  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_sct
0x12118  ldarg.0
0x12119  ldarg.0
0x1211a  ldstr    aVersion_0// "Version"
0x1211f  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x12124  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_version
0x12129  ldarg.0
0x1212a  ldarg.0
0x1212b  ldstr    aSecureconversa// "SecureConversationVersion"
0x12130  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x12135  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_scVersion
0x1213a  ldarg.0
0x1213b  ldarg.0
0x1213c  ldstr    aIssuer// "Issuer"
0x12141  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x12146  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_issuer
0x1214b  ldarg.0
0x1214c  ldarg.0
0x1214d  ldstr    aOriginalissuer// "OriginalIssuer"
0x12152  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x12157  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_originalIssuer
0x1215c  ldarg.0
0x1215d  ldarg.0
0x1215e  ldstr    aIssuerref// "IssuerRef"
0x12163  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x12168  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_issuerRef
0x1216d  ldarg.0
0x1216e  ldarg.0
0x1216f  ldstr    aClaimcollectio// "ClaimCollection"
0x12174  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x12179  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_claimCollection
0x1217e  ldarg.0
0x1217f  ldarg.0
0x12180  ldstr    aActor// "Actor"
0x12185  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x1218a  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_actor
0x1218f  ldarg.0
0x12190  ldarg.0
0x12191  ldstr    aClaimproperty// "ClaimProperty"
0x12196  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x1219b  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_claimProperty
0x121a0  ldarg.0
0x121a1  ldarg.0
0x121a2  ldstr    aClaimpropertie// "ClaimProperties"
0x121a7  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x121ac  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_claimProperties
0x121b1  ldarg.0
0x121b2  ldarg.0
0x121b3  ldstr    aValue_0// "Value"
0x121b8  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x121bd  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_value
0x121c2  ldarg.0
0x121c3  ldarg.0
0x121c4  ldstr    aValuetype// "ValueType"
0x121c9  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x121ce  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_valueType
0x121d3  ldarg.0
0x121d4  ldarg.0
0x121d5  ldstr    aLabel// "Label"
0x121da  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x121df  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_label
0x121e4  ldarg.0
0x121e5  ldarg.0
0x121e6  ldstr    aType// "Type"
0x121eb  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x121f0  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_type
0x121f5  ldarg.0
0x121f6  ldarg.0
0x121f7  ldstr    aSubjectid// "subjectID"
0x121fc  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x12201  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_subjectId
0x12206  ldarg.0
0x12207  ldarg.0
0x12208  ldstr    aClaimpropertyn// "ClaimPropertyName"
0x1220d  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x12212  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_claimPropertyName
0x12217  ldarg.0
0x12218  ldarg.0
0x12219  ldstr    aClaimpropertyv// "ClaimPropertyValue"
0x1221e  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x12223  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_claimPropertyValue
0x12228  ldarg.0
0x12229  ldarg.0
0x1222a  ldstr    aHttpWwwW3Org20_2// "http://www.w3.org/2005/08/addressing/an"...
0x1222f  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x12234  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_anonymousIssued
0x12239  ldarg.0
0x1223a  ldarg.0
0x1223b  ldstr    aHttpSchemasXml_2// "http://schemas.xmlsoap.org/ws/2005/05/i"...
0x12240  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x12245  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_selfIssued
0x1224a  ldarg.0
0x1224b  ldarg.0
0x1224c  ldstr    aAuthentication_17// "AuthenticationType"
0x12251  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x12256  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_authenticationType
0x1225b  ldarg.0
0x1225c  ldarg.0
0x1225d  ldstr    aNameclaimtype// "NameClaimType"
0x12262  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x12267  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_nameClaimType
0x1226c  ldarg.0
0x1226d  ldarg.0
0x1226e  ldstr    aRoleclaimtype// "RoleClaimType"
0x12273  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x12278  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_roleClaimType
0x1227d  ldarg.0
0x1227e  ldarg.0
0x1227f  ldstr    aNull// "Null"
0x12284  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x12289  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_nullValue
0x1228e  ldarg.0
0x1228f  ldarg.0
0x12290  ldsfld   string [mscorlib]System.String::Empty
0x12295  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x1229a  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_emptyString
0x1229f  ldarg.0
0x122a0  ldarg.0
0x122a1  ldstr    aKey// "Key"
0x122a6  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x122ab  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_key
0x122b0  ldarg.0
0x122b1  ldarg.0
0x122b2  ldstr    aEffectivetime// "EffectiveTime"
0x122b7  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x122bc  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_effectiveTime
0x122c1  ldarg.0
0x122c2  ldarg.0
0x122c3  ldstr    aExpirytime// "ExpiryTime"
0x122c8  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x122cd  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_expiryTime
0x122d2  ldarg.0
0x122d3  ldarg.0
0x122d4  ldstr    aKeygeneration// "KeyGeneration"
0x122d9  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x122de  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_keyGeneration
0x122e3  ldarg.0
0x122e4  ldarg.0
0x122e5  ldstr    aKeyeffectiveti// "KeyEffectiveTime"
0x122ea  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x122ef  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_keyEffectiveTime
0x122f4  ldarg.0
0x122f5  ldarg.0
0x122f6  ldstr    aKeyexpirytime// "KeyExpiryTime"
0x122fb  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x12300  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_keyExpiryTime
0x12305  ldarg.0
0x12306  ldarg.0
0x12307  ldstr    aSessionid// "SessionId"
0x1230c  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x12311  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_sessionId
0x12316  ldarg.0
0x12317  ldarg.0
0x12318  ldstr    aId// "Id"
0x1231d  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x12322  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_id
0x12327  ldarg.0
0x12328  ldarg.0
0x12329  ldstr    aValidfrom// "ValidFrom"
0x1232e  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x12333  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_validFrom
0x12338  ldarg.0
0x12339  ldarg.0
0x1233a  ldstr    aValidto// "ValidTo"
0x1233f  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x12344  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_validTo
0x12349  ldarg.0
0x1234a  ldarg.0
0x1234b  ldstr    aContextid// "ContextId"
0x12350  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x12355  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_contextId
0x1235a  ldarg.0
0x1235b  ldarg.0
0x1235c  ldstr    aSessiontoken// "SessionToken"
0x12361  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x12366  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_sesionToken
0x1236b  ldarg.0
0x1236c  ldarg.0
0x1236d  ldstr    aSessiontokenco// "SessionTokenCookie"
0x12372  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x12377  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_sesionTokenCookie
0x1237c  ldarg.0
0x1237d  ldarg.0
0x1237e  ldstr    aBootstraptoken// "BootStrapToken"
0x12383  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x12388  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_bootStrapToken
0x1238d  ldarg.0
0x1238e  ldarg.0
0x1238f  ldstr    aContext_0// "Context"
0x12394  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x12399  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_context
0x1239e  ldarg.0
0x1239f  ldarg.0
0x123a0  ldstr    aClaimsprincipa_0// "ClaimsPrincipal"
0x123a5  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x123aa  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_claimsPrincipal
0x123af  ldarg.0
0x123b0  ldarg.0
0x123b1  ldstr    aWindowsprincip// "WindowsPrincipal"
0x123b6  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x123bb  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_windowsPrincipal
0x123c0  ldarg.0
0x123c1  ldarg.0
0x123c2  ldstr    aWindowidentity// "WindowIdentity"
0x123c7  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x123cc  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_windowsIdentity
0x123d1  ldarg.0
0x123d2  ldarg.0
0x123d3  ldstr    aIdentity// "Identity"
0x123d8  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x123dd  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_identity
0x123e2  ldarg.0
0x123e3  ldarg.0
0x123e4  ldstr    aIdentities// "Identities"
0x123e9  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x123ee  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_identities
0x123f3  ldarg.0
0x123f4  ldarg.0
0x123f5  ldstr    aWindowslogonna// "WindowsLogonName"
0x123fa  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x123ff  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_windowsLogOnName
0x12404  ldarg.0
0x12405  ldarg.0
0x12406  ldstr    aPersistenttrue// "PersistentTrue"
0x1240b  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x12410  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_persistentTrue
0x12415  ldarg.0
0x12416  ldarg.0
0x12417  ldstr    aSctauthorizati// "SctAuthorizationPolicy"
0x1241c  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x12421  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_sctAuthorizationPolicy
0x12426  ldarg.0
0x12427  ldarg.0
0x12428  ldstr    aRight// "Right"
0x1242d  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x12432  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_right
0x12437  ldarg.0
0x12438  ldarg.0
0x12439  ldstr    aEndpointid// "EndpointId"
0x1243e  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x12443  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_endpointId
0x12448  ldarg.0
0x12449  ldarg.0
0x1244a  ldstr    aWindowssidclai// "WindowsSidClaim"
0x1244f  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x12454  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_windowsSidClaim
0x12459  ldarg.0
0x1245a  ldarg.0
0x1245b  ldstr    aDenyonlysidcla// "DenyOnlySidClaim"
0x12460  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x12465  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_denyOnlySidClaim
0x1246a  ldarg.0
0x1246b  ldarg.0
0x1246c  ldstr    aX500distinguis// "X500DistinguishedNameClaim"
0x12471  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x12476  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_x500DistinguishedNameClaim
0x1247b  ldarg.0
0x1247c  ldarg.0
0x1247d  ldstr    aX509thumbprint// "X509ThumbprintClaim"
0x12482  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x12487  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_x509ThumbprintClaim
0x1248c  ldarg.0
0x1248d  ldarg.0
0x1248e  ldstr    aNameclaim// "NameClaim"
0x12493  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x12498  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_nameClaim
0x1249d  ldarg.0
0x1249e  ldarg.0
0x1249f  ldstr    aDnsclaim// "DnsClaim"
0x124a4  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x124a9  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_dnsClaim
0x124ae  ldarg.0
0x124af  ldarg.0
0x124b0  ldstr    aRsaclaim// "RsaClaim"
0x124b5  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x124ba  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_rsaClaim
0x124bf  ldarg.0
0x124c0  ldarg.0
0x124c1  ldstr    aMailaddresscla// "MailAddressClaim"
0x124c6  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x124cb  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_mailAddressClaim
0x124d0  ldarg.0
0x124d1  ldarg.0
0x124d2  ldstr    aSystemclaim// "SystemClaim"
0x124d7  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x124dc  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::_systemClaim
0x124e1  ldarg.0
0x124e2  ldarg.0
0x124e3  ldstr    aHashclaim// "HashClaim"
  ... truncated ...
```
