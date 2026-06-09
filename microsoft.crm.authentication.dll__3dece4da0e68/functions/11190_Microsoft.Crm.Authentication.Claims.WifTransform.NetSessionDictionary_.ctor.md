# Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::.ctor

- ea: `0x11190`
- end: `0x115c6`
- name: `Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::.ctor`
- size: `1078`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x115d0`

## string_xrefs

- `0x111a9`: `SecurityContextToken`
- `0x113da`: `SessionToken`
- `0x113eb`: `SessionTokenCookie`
- `0x113fc`: `BootStrapToken`
- `0x114c8`: `WindowsSidClaim`
- `0x114d9`: `DenyOnlySidClaim`
- `0x1152e`: `RsaClaim`

## pseudocode

```c

```

## disassembly

```asm
0x11190  ldarg.0
0x11191  call     instance void [System.Runtime.Serialization]System.Xml.XmlDictionary::.ctor()
0x11196  ldarg.0
0x11197  ldarg.0
0x11198  ldstr    aClaim// "Claim"
0x1119d  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x111a2  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_claim
0x111a7  ldarg.0
0x111a8  ldarg.0
0x111a9  ldstr    aSecuritycontex// "SecurityContextToken"
0x111ae  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x111b3  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_sct
0x111b8  ldarg.0
0x111b9  ldarg.0
0x111ba  ldstr    aVersion_0// "Version"
0x111bf  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x111c4  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_version
0x111c9  ldarg.0
0x111ca  ldarg.0
0x111cb  ldstr    aSecureconversa// "SecureConversationVersion"
0x111d0  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x111d5  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_scVersion
0x111da  ldarg.0
0x111db  ldarg.0
0x111dc  ldstr    aIssuer// "Issuer"
0x111e1  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x111e6  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_issuer
0x111eb  ldarg.0
0x111ec  ldarg.0
0x111ed  ldstr    aOriginalissuer// "OriginalIssuer"
0x111f2  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x111f7  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_originalIssuer
0x111fc  ldarg.0
0x111fd  ldarg.0
0x111fe  ldstr    aIssuerref// "IssuerRef"
0x11203  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x11208  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_issuerRef
0x1120d  ldarg.0
0x1120e  ldarg.0
0x1120f  ldstr    aClaimcollectio// "ClaimCollection"
0x11214  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x11219  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_claimCollection
0x1121e  ldarg.0
0x1121f  ldarg.0
0x11220  ldstr    aActor// "Actor"
0x11225  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x1122a  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_actor
0x1122f  ldarg.0
0x11230  ldarg.0
0x11231  ldstr    aClaimproperty// "ClaimProperty"
0x11236  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x1123b  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_claimProperty
0x11240  ldarg.0
0x11241  ldarg.0
0x11242  ldstr    aClaimpropertie// "ClaimProperties"
0x11247  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x1124c  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_claimProperties
0x11251  ldarg.0
0x11252  ldarg.0
0x11253  ldstr    aValue_0// "Value"
0x11258  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x1125d  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_value
0x11262  ldarg.0
0x11263  ldarg.0
0x11264  ldstr    aValuetype// "ValueType"
0x11269  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x1126e  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_valueType
0x11273  ldarg.0
0x11274  ldarg.0
0x11275  ldstr    aLabel// "Label"
0x1127a  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x1127f  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_label
0x11284  ldarg.0
0x11285  ldarg.0
0x11286  ldstr    aType// "Type"
0x1128b  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x11290  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_type
0x11295  ldarg.0
0x11296  ldarg.0
0x11297  ldstr    aSubjectid// "subjectID"
0x1129c  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x112a1  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_subjectId
0x112a6  ldarg.0
0x112a7  ldarg.0
0x112a8  ldstr    aClaimpropertyn// "ClaimPropertyName"
0x112ad  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x112b2  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_claimPropertyName
0x112b7  ldarg.0
0x112b8  ldarg.0
0x112b9  ldstr    aClaimpropertyv// "ClaimPropertyValue"
0x112be  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x112c3  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_claimPropertyValue
0x112c8  ldarg.0
0x112c9  ldarg.0
0x112ca  ldstr    aAuthentication_17// "AuthenticationType"
0x112cf  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x112d4  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_authenticationType
0x112d9  ldarg.0
0x112da  ldarg.0
0x112db  ldstr    aNameclaimtype// "NameClaimType"
0x112e0  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x112e5  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_nameClaimType
0x112ea  ldarg.0
0x112eb  ldarg.0
0x112ec  ldstr    aRoleclaimtype// "RoleClaimType"
0x112f1  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x112f6  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_roleClaimType
0x112fb  ldarg.0
0x112fc  ldarg.0
0x112fd  ldstr    aNull// "Null"
0x11302  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x11307  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_nullValue
0x1130c  ldarg.0
0x1130d  ldarg.0
0x1130e  ldsfld   string [mscorlib]System.String::Empty
0x11313  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x11318  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_emptyString
0x1131d  ldarg.0
0x1131e  ldarg.0
0x1131f  ldstr    aKey// "Key"
0x11324  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x11329  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_key
0x1132e  ldarg.0
0x1132f  ldarg.0
0x11330  ldstr    aEffectivetime// "EffectiveTime"
0x11335  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x1133a  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_effectiveTime
0x1133f  ldarg.0
0x11340  ldarg.0
0x11341  ldstr    aExpirytime// "ExpiryTime"
0x11346  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x1134b  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_expiryTime
0x11350  ldarg.0
0x11351  ldarg.0
0x11352  ldstr    aKeygeneration// "KeyGeneration"
0x11357  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x1135c  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_keyGeneration
0x11361  ldarg.0
0x11362  ldarg.0
0x11363  ldstr    aKeyeffectiveti// "KeyEffectiveTime"
0x11368  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x1136d  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_keyEffectiveTime
0x11372  ldarg.0
0x11373  ldarg.0
0x11374  ldstr    aKeyexpirytime// "KeyExpiryTime"
0x11379  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x1137e  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_keyExpiryTime
0x11383  ldarg.0
0x11384  ldarg.0
0x11385  ldstr    aSessionid// "SessionId"
0x1138a  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x1138f  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_sessionId
0x11394  ldarg.0
0x11395  ldarg.0
0x11396  ldstr    aId// "Id"
0x1139b  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x113a0  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_id
0x113a5  ldarg.0
0x113a6  ldarg.0
0x113a7  ldstr    aValidfrom// "ValidFrom"
0x113ac  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x113b1  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_validFrom
0x113b6  ldarg.0
0x113b7  ldarg.0
0x113b8  ldstr    aValidto// "ValidTo"
0x113bd  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x113c2  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_validTo
0x113c7  ldarg.0
0x113c8  ldarg.0
0x113c9  ldstr    aContextid// "ContextId"
0x113ce  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x113d3  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_contextId
0x113d8  ldarg.0
0x113d9  ldarg.0
0x113da  ldstr    aSessiontoken// "SessionToken"
0x113df  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x113e4  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_sesionToken
0x113e9  ldarg.0
0x113ea  ldarg.0
0x113eb  ldstr    aSessiontokenco// "SessionTokenCookie"
0x113f0  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x113f5  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_sesionTokenCookie
0x113fa  ldarg.0
0x113fb  ldarg.0
0x113fc  ldstr    aBootstraptoken// "BootStrapToken"
0x11401  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x11406  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_bootStrapToken
0x1140b  ldarg.0
0x1140c  ldarg.0
0x1140d  ldstr    aContext_0// "Context"
0x11412  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x11417  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_context
0x1141c  ldarg.0
0x1141d  ldarg.0
0x1141e  ldstr    aClaimsprincipa_0// "ClaimsPrincipal"
0x11423  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x11428  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_claimsPrincipal
0x1142d  ldarg.0
0x1142e  ldarg.0
0x1142f  ldstr    aWindowsprincip// "WindowsPrincipal"
0x11434  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x11439  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_windowsPrincipal
0x1143e  ldarg.0
0x1143f  ldarg.0
0x11440  ldstr    aWindowidentity// "WindowIdentity"
0x11445  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x1144a  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_windowsIdentity
0x1144f  ldarg.0
0x11450  ldarg.0
0x11451  ldstr    aIdentity// "Identity"
0x11456  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x1145b  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_identity
0x11460  ldarg.0
0x11461  ldarg.0
0x11462  ldstr    aIdentities// "Identities"
0x11467  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x1146c  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_identities
0x11471  ldarg.0
0x11472  ldarg.0
0x11473  ldstr    aWindowslogonna// "WindowsLogonName"
0x11478  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x1147d  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_windowsLogonName
0x11482  ldarg.0
0x11483  ldarg.0
0x11484  ldstr    aPersistenttrue// "PersistentTrue"
0x11489  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x1148e  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_persistentTrue
0x11493  ldarg.0
0x11494  ldarg.0
0x11495  ldstr    aSctauthorizati// "SctAuthorizationPolicy"
0x1149a  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x1149f  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_sctAuthorizationPolicy
0x114a4  ldarg.0
0x114a5  ldarg.0
0x114a6  ldstr    aRight// "Right"
0x114ab  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x114b0  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_right
0x114b5  ldarg.0
0x114b6  ldarg.0
0x114b7  ldstr    aEndpointid// "EndpointId"
0x114bc  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x114c1  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_endpointId
0x114c6  ldarg.0
0x114c7  ldarg.0
0x114c8  ldstr    aWindowssidclai// "WindowsSidClaim"
0x114cd  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x114d2  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_windowsSidClaim
0x114d7  ldarg.0
0x114d8  ldarg.0
0x114d9  ldstr    aDenyonlysidcla// "DenyOnlySidClaim"
0x114de  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x114e3  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_denyOnlySidClaim
0x114e8  ldarg.0
0x114e9  ldarg.0
0x114ea  ldstr    aX500distinguis// "X500DistinguishedNameClaim"
0x114ef  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x114f4  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_x500DistinguishedNameClaim
0x114f9  ldarg.0
0x114fa  ldarg.0
0x114fb  ldstr    aX509thumbprint// "X509ThumbprintClaim"
0x11500  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x11505  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_x509ThumbprintClaim
0x1150a  ldarg.0
0x1150b  ldarg.0
0x1150c  ldstr    aNameclaim// "NameClaim"
0x11511  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x11516  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_nameClaim
0x1151b  ldarg.0
0x1151c  ldarg.0
0x1151d  ldstr    aDnsclaim// "DnsClaim"
0x11522  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x11527  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_dnsClaim
0x1152c  ldarg.0
0x1152d  ldarg.0
0x1152e  ldstr    aRsaclaim// "RsaClaim"
0x11533  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x11538  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_rsaClaim
0x1153d  ldarg.0
0x1153e  ldarg.0
0x1153f  ldstr    aMailaddresscla// "MailAddressClaim"
0x11544  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x11549  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_mailAddressClaim
0x1154e  ldarg.0
0x1154f  ldarg.0
0x11550  ldstr    aSystemclaim// "SystemClaim"
0x11555  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x1155a  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_systemClaim
0x1155f  ldarg.0
0x11560  ldarg.0
0x11561  ldstr    aHashclaim// "HashClaim"
0x11566  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x1156b  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_hashClaim
0x11570  ldarg.0
0x11571  ldarg.0
0x11572  ldstr    aSpnclaim// "SpnClaim"
0x11577  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.Runtime.Serialization]System.Xml.XmlDictionary::Add(string)
0x1157c  stfld    class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::_spnClaim
0x11581  ldarg.0
0x11582  ldarg.0
0x11583  ldstr    aUpnclaim// "UpnClaim"
  ... truncated ...
```
