# Microsoft.Crm.Caching.EmailServerProfileData::Initialize

- ea: `0x83560`
- end: `0x83b49`
- name: `Microsoft.Crm.Caching.EmailServerProfileData::Initialize`
- size: `1513`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x81f50`
- `0x81f60`
- `0x83560`

## string_xrefs

- `0x839e6`: `createdon`
- `0x839f4`: `createdon`
- `0x8368a`: `incomingserverlocation`
- `0x83698`: `incomingserverlocation`
- `0x836ad`: `incomingusername`
- `0x836bb`: `incomingusername`
- `0x836d0`: `incomingpassword`
- `0x836de`: `incomingpassword`
- `0x836f8`: `incomingcredentialretrieval`
- `0x83706`: `incomingcredentialretrieval`
- `0x83725`: `incomingportnumber`
- `0x83733`: `incomingportnumber`
- `0x83748`: `incomingusessl`
- `0x83756`: `incomingusessl`
- `0x8376b`: `incomingauthenticationprotocol`
- `0x83779`: `incomingauthenticationprotocol`
- `0x8378e`: `incominguseimpersonation`
- `0x8379c`: `incominguseimpersonation`
- `0x837b1`: `moveundeliveredemails`
- `0x837bf`: `moveundeliveredemails`
- `0x838ab`: `outgoingauthenticationprotocol`
- `0x838b9`: `outgoingauthenticationprotocol`
- `0x83914`: `outgoinguseimpersonation`
- `0x83922`: `outgoinguseimpersonation`
- `0x83937`: `outgoingautograntdelegateaccess`
- `0x83945`: `outgoingautograntdelegateaccess`
- `0x8395a`: `incomingpartnerapplication`
- `0x83968`: `incomingpartnerapplication`
- `0x83a2c`: `timeoutmailboxconnectionafteramount`
- `0x83a3a`: `timeoutmailboxconnectionafteramount`

## pseudocode

```c

```

## disassembly

```asm
0x83560  ldarg.1
0x83561  ldstr    aEmailserverpro// "emailserverprofileid"
0x83566  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x8356b  brtrue.s loc_83583
0x8356d  ldarg.0
0x8356e  ldarg.1
0x8356f  ldstr    aEmailserverpro// "emailserverprofileid"
0x83574  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x83579  unbox.any [mscorlib]System.Guid
0x8357e  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Caching.EmailServerProfileData::_emailServerProfileId
0x83583  ldarg.1
0x83584  ldstr    aName_0// "name"
0x83589  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x8358e  brtrue.s loc_835A6
0x83590  ldarg.0
0x83591  ldarg.1
0x83592  ldstr    aName_0// "name"
0x83597  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x8359c  castclass [mscorlib]System.String
0x835a1  stfld    string Microsoft.Crm.Caching.EmailServerProfileData::_name
0x835a6  ldarg.1
0x835a7  ldstr    aStatecode// "statecode"
0x835ac  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x835b1  brtrue.s loc_835CF
0x835b3  ldarg.0
0x835b4  ldarg.1
0x835b5  ldstr    aStatecode// "statecode"
0x835ba  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x835bf  unbox.any [mscorlib]System.Int32
0x835c4  brfalse.s loc_835C9
0x835c6  ldc.i4.0
0x835c7  br.s     loc_835CA
0x835c9  ldc.i4.1
0x835ca  stfld    bool Microsoft.Crm.Caching.EmailServerProfileData::_isActive
0x835cf  ldarg.1
0x835d0  ldstr    aServertype// "servertype"
0x835d5  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x835da  brtrue.s loc_835F2
0x835dc  ldarg.0
0x835dd  ldarg.1
0x835de  ldstr    aServertype// "servertype"
0x835e3  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x835e8  unbox.any Microsoft.Crm.Caching.EmailServerType
0x835ed  stfld    valuetype Microsoft.Crm.Caching.EmailServerType Microsoft.Crm.Caching.EmailServerProfileData::_serverType
0x835f2  ldarg.1
0x835f3  ldstr    aExchangeversio// "exchangeversion"
0x835f8  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x835fd  brtrue.s loc_83615
0x835ff  ldarg.0
0x83600  ldarg.1
0x83601  ldstr    aExchangeversio// "exchangeversion"
0x83606  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x8360b  unbox.any Microsoft.Crm.Caching.ExchangeServerVersion
0x83610  stfld    valuetype Microsoft.Crm.Caching.ExchangeServerVersion Microsoft.Crm.Caching.EmailServerProfileData::_exchangeServerVersion
0x83615  ldarg.1
0x83616  ldstr    aUseautodiscove// "useautodiscover"
0x8361b  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x83620  brtrue.s loc_83638
0x83622  ldarg.0
0x83623  ldarg.1
0x83624  ldstr    aUseautodiscove// "useautodiscover"
0x83629  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x8362e  unbox.any [mscorlib]System.Boolean
0x83633  stfld    bool Microsoft.Crm.Caching.EmailServerProfileData::_useAutoDiscover
0x83638  ldarg.1
0x83639  ldstr    aMaxconcurrentc// "maxconcurrentconnections"
0x8363e  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x83643  brtrue.s loc_83660
0x83645  ldarg.0
0x83646  ldarg.1
0x83647  ldstr    aMaxconcurrentc// "maxconcurrentconnections"
0x8364c  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x83651  unbox.any [mscorlib]System.Int32
0x83656  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x8365b  stfld    valuetype [mscorlib]System.Nullable`1<int32> Microsoft.Crm.Caching.EmailServerProfileData::_maxConcurrentConnections
0x83660  ldarg.1
0x83661  ldstr    aMinpollinginte// "minpollingintervalinminutes"
0x83666  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x8366b  brtrue.s loc_83689
0x8366d  ldarg.0
0x8366e  ldarg.1
0x8366f  ldstr    aMinpollinginte// "minpollingintervalinminutes"
0x83674  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x83679  unbox.any [mscorlib]System.Int32
0x8367e  conv.r8
0x8367f  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0x83684  stfld    valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Caching.EmailServerProfileData::_minPollingInterval
0x83689  ldarg.1
0x8368a  ldstr    aIncomingserver// "incomingserverlocation"
0x8368f  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x83694  brtrue.s loc_836AC
0x83696  ldarg.0
0x83697  ldarg.1
0x83698  ldstr    aIncomingserver// "incomingserverlocation"
0x8369d  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x836a2  castclass [mscorlib]System.String
0x836a7  stfld    string Microsoft.Crm.Caching.EmailServerProfileData::_incomingServerLocation
0x836ac  ldarg.1
0x836ad  ldstr    aIncominguserna// "incomingusername"
0x836b2  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x836b7  brtrue.s loc_836CF
0x836b9  ldarg.0
0x836ba  ldarg.1
0x836bb  ldstr    aIncominguserna// "incomingusername"
0x836c0  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x836c5  castclass [mscorlib]System.String
0x836ca  stfld    string Microsoft.Crm.Caching.EmailServerProfileData::_incomingEmailUserName
0x836cf  ldarg.1
0x836d0  ldstr    aIncomingpasswo// "incomingpassword"
0x836d5  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x836da  brtrue.s loc_836F7
0x836dc  ldarg.0
0x836dd  ldarg.1
0x836de  ldstr    aIncomingpasswo// "incomingpassword"
0x836e3  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x836e8  castclass [mscorlib]System.String
0x836ed  call     class [mscorlib]System.Security.SecureString [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmUtility::StringToSecureString(string)
0x836f2  stfld    class [mscorlib]System.Security.SecureString Microsoft.Crm.Caching.EmailServerProfileData::_incomingPassword
0x836f7  ldarg.1
0x836f8  ldstr    aIncomingcreden// "incomingcredentialretrieval"
0x836fd  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x83702  brtrue.s loc_83724
0x83704  ldarg.0
0x83705  ldarg.1
0x83706  ldstr    aIncomingcreden// "incomingcredentialretrieval"
0x8370b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x83710  call     instance string [mscorlib]System.String::ToString(class [mscorlib]System.IFormatProvider)
0x83715  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x8371a  unbox.any Microsoft.Crm.Caching.CredentialRetrievalMethod
0x8371f  stfld    valuetype Microsoft.Crm.Caching.CredentialRetrievalMethod Microsoft.Crm.Caching.EmailServerProfileData::_incomingCredentialRetrievalMethod
0x83724  ldarg.1
0x83725  ldstr    aIncomingportnu// "incomingportnumber"
0x8372a  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x8372f  brtrue.s loc_83747
0x83731  ldarg.0
0x83732  ldarg.1
0x83733  ldstr    aIncomingportnu// "incomingportnumber"
0x83738  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x8373d  unbox.any [mscorlib]System.Int32
0x83742  stfld    int32 Microsoft.Crm.Caching.EmailServerProfileData::_incomingPortNumber
0x83747  ldarg.1
0x83748  ldstr    aIncomingusessl// "incomingusessl"
0x8374d  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x83752  brtrue.s loc_8376A
0x83754  ldarg.0
0x83755  ldarg.1
0x83756  ldstr    aIncomingusessl// "incomingusessl"
0x8375b  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x83760  unbox.any [mscorlib]System.Boolean
0x83765  stfld    bool Microsoft.Crm.Caching.EmailServerProfileData::_incomingUseSsl
0x8376a  ldarg.1
0x8376b  ldstr    aIncomingauthen// "incomingauthenticationprotocol"
0x83770  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x83775  brtrue.s loc_8378D
0x83777  ldarg.0
0x83778  ldarg.1
0x83779  ldstr    aIncomingauthen// "incomingauthenticationprotocol"
0x8377e  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x83783  unbox.any Microsoft.Crm.Caching.AuthenticationProtocol
0x83788  stfld    valuetype Microsoft.Crm.Caching.AuthenticationProtocol Microsoft.Crm.Caching.EmailServerProfileData::_incomingAuthenticationProtocol
0x8378d  ldarg.1
0x8378e  ldstr    aIncominguseimp// "incominguseimpersonation"
0x83793  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x83798  brtrue.s loc_837B0
0x8379a  ldarg.0
0x8379b  ldarg.1
0x8379c  ldstr    aIncominguseimp// "incominguseimpersonation"
0x837a1  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x837a6  unbox.any [mscorlib]System.Boolean
0x837ab  stfld    bool Microsoft.Crm.Caching.EmailServerProfileData::_incomingUseImpersonation
0x837b0  ldarg.1
0x837b1  ldstr    aMoveundelivere// "moveundeliveredemails"
0x837b6  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x837bb  brtrue.s loc_837D3
0x837bd  ldarg.0
0x837be  ldarg.1
0x837bf  ldstr    aMoveundelivere// "moveundeliveredemails"
0x837c4  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x837c9  unbox.any [mscorlib]System.Boolean
0x837ce  stfld    bool Microsoft.Crm.Caching.EmailServerProfileData::_moveUndeliveredEmails
0x837d3  ldarg.1
0x837d4  ldstr    aOutgoingserver// "outgoingserverlocation"
0x837d9  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x837de  brtrue.s loc_837F6
0x837e0  ldarg.0
0x837e1  ldarg.1
0x837e2  ldstr    aOutgoingserver// "outgoingserverlocation"
0x837e7  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x837ec  castclass [mscorlib]System.String
0x837f1  stfld    string Microsoft.Crm.Caching.EmailServerProfileData::_outgoingServerLocation
0x837f6  ldarg.1
0x837f7  ldstr    aOutgoinguserna// "outgoingusername"
0x837fc  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x83801  brtrue.s loc_83819
0x83803  ldarg.0
0x83804  ldarg.1
0x83805  ldstr    aOutgoinguserna// "outgoingusername"
0x8380a  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x8380f  castclass [mscorlib]System.String
0x83814  stfld    string Microsoft.Crm.Caching.EmailServerProfileData::_outgoingUserName
0x83819  ldarg.1
0x8381a  ldstr    aOutgoingpasswo// "outgoingpassword"
0x8381f  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x83824  brtrue.s loc_83841
0x83826  ldarg.0
0x83827  ldarg.1
0x83828  ldstr    aOutgoingpasswo// "outgoingpassword"
0x8382d  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x83832  castclass [mscorlib]System.String
0x83837  call     class [mscorlib]System.Security.SecureString [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmUtility::StringToSecureString(string)
0x8383c  stfld    class [mscorlib]System.Security.SecureString Microsoft.Crm.Caching.EmailServerProfileData::_outgoingPassword
0x83841  ldarg.1
0x83842  ldstr    aOutgoingcreden// "outgoingcredentialretrieval"
0x83847  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x8384c  brtrue.s loc_83864
0x8384e  ldarg.0
0x8384f  ldarg.1
0x83850  ldstr    aOutgoingcreden// "outgoingcredentialretrieval"
0x83855  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x8385a  unbox.any Microsoft.Crm.Caching.CredentialRetrievalMethod
0x8385f  stfld    valuetype Microsoft.Crm.Caching.CredentialRetrievalMethod Microsoft.Crm.Caching.EmailServerProfileData::_outgoingCredentialRetrievalMethod
0x83864  ldarg.1
0x83865  ldstr    aOutgoingportnu// "outgoingportnumber"
0x8386a  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x8386f  brtrue.s loc_83887
0x83871  ldarg.0
0x83872  ldarg.1
0x83873  ldstr    aOutgoingportnu// "outgoingportnumber"
0x83878  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x8387d  unbox.any [mscorlib]System.Int32
0x83882  stfld    int32 Microsoft.Crm.Caching.EmailServerProfileData::_outgoingPortNumber
0x83887  ldarg.1
0x83888  ldstr    aOutgoingusessl// "outgoingusessl"
0x8388d  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x83892  brtrue.s loc_838AA
0x83894  ldarg.0
0x83895  ldarg.1
0x83896  ldstr    aOutgoingusessl// "outgoingusessl"
0x8389b  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x838a0  unbox.any [mscorlib]System.Boolean
0x838a5  stfld    bool Microsoft.Crm.Caching.EmailServerProfileData::_outgoingUseSsl
0x838aa  ldarg.1
0x838ab  ldstr    aOutgoingauthen// "outgoingauthenticationprotocol"
0x838b0  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x838b5  brtrue.s loc_838CD
0x838b7  ldarg.0
0x838b8  ldarg.1
0x838b9  ldstr    aOutgoingauthen// "outgoingauthenticationprotocol"
0x838be  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x838c3  unbox.any Microsoft.Crm.Caching.AuthenticationProtocol
0x838c8  stfld    valuetype Microsoft.Crm.Caching.AuthenticationProtocol Microsoft.Crm.Caching.EmailServerProfileData::_outgoingAuthenticationProtocol
0x838cd  ldarg.1
0x838ce  ldstr    aEncodingcodepa// "encodingcodepage"
0x838d3  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x838d8  brtrue.s loc_838F0
0x838da  ldarg.0
0x838db  ldarg.1
0x838dc  ldstr    aEncodingcodepa// "encodingcodepage"
0x838e1  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x838e6  castclass [mscorlib]System.String
0x838eb  stfld    string Microsoft.Crm.Caching.EmailServerProfileData::_encodingCodePage
0x838f0  ldarg.1
0x838f1  ldstr    aProcessemailsr// "processemailsreceivedafter"
0x838f6  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x838fb  brtrue.s loc_83913
0x838fd  ldarg.0
0x838fe  ldarg.1
0x838ff  ldstr    aProcessemailsr// "processemailsreceivedafter"
0x83904  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x83909  unbox.any [mscorlib]System.DateTime
0x8390e  stfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Caching.EmailServerProfileData::_processEmailsReceivedAfter
0x83913  ldarg.1
0x83914  ldstr    aOutgoinguseimp// "outgoinguseimpersonation"
0x83919  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x8391e  brtrue.s loc_83936
0x83920  ldarg.0
0x83921  ldarg.1
0x83922  ldstr    aOutgoinguseimp// "outgoinguseimpersonation"
0x83927  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x8392c  unbox.any [mscorlib]System.Boolean
0x83931  stfld    bool Microsoft.Crm.Caching.EmailServerProfileData::_outgoingUseImpersonation
0x83936  ldarg.1
0x83937  ldstr    aOutgoingautogr// "outgoingautograntdelegateaccess"
0x8393c  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x83941  brtrue.s loc_83959
0x83943  ldarg.0
0x83944  ldarg.1
0x83945  ldstr    aOutgoingautogr// "outgoingautograntdelegateaccess"
0x8394a  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x8394f  unbox.any [mscorlib]System.Boolean
0x83954  stfld    bool Microsoft.Crm.Caching.EmailServerProfileData::_outgoingAutoGrantDelegateAccess
0x83959  ldarg.1
0x8395a  ldstr    aIncomingpartne// "incomingpartnerapplication"
0x8395f  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x83964  brtrue.s loc_8397C
0x83966  ldarg.0
0x83967  ldarg.1
0x83968  ldstr    aIncomingpartne// "incomingpartnerapplication"
0x8396d  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x83972  unbox.any [mscorlib]System.Guid
  ... truncated ...
```
