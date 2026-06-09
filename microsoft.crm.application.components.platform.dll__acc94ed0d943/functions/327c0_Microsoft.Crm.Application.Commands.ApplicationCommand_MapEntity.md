# Microsoft.Crm.Application.Commands.ApplicationCommand::MapEntity

- ea: `0x327c0`
- end: `0x32afc`
- name: `Microsoft.Crm.Application.Commands.ApplicationCommand::MapEntity`
- size: `828`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x2fb90`
- `0x327a0`
- `0x327c0`
- `0x32c80`
- `0x32cb0`
- `0x3afc0`
- `0x3b070`
- `0x3b0a0`
- `0x3b0e0`
- `0x6a2a0`
- `0x6a330`
- `0x9ca50`

## string_xrefs

- `0x3293f`: `serviceappointment`
- `0x32a61`: `serviceappointment`
- `0x32ae3`: `_CreateFromId`
- `0x32aef`: `_CreateFromType`

## pseudocode

```c

```

## disassembly

```asm
0x327c0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Utility.EntityAttributeMapBase>::.ctor()
0x327c5  stloc.0
0x327c6  ldarg.1
0x327c7  callvirt instance string[] [System]System.Collections.Specialized.NameValueCollection::get_AllKeys()
0x327cc  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x327d1  stloc.1
0x327d2  ldnull
0x327d3  stloc.2
0x327d4  ldarg.0
0x327d5  callvirt instance string Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x327da  ldstr    aCampaignrespon_0// "campaignresponse"
0x327df  call     bool [mscorlib]System.String::op_Equality(string, string)
0x327e4  brfalse.s loc_32810
0x327e6  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x327eb  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x327f0  ldstr    aCampaignrespon_0// "campaignresponse"
0x327f5  ldc.i4.1
0x327f6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x327fb  brfalse.s loc_32810
0x327fd  ldloc.0
0x327fe  call     class Microsoft.Crm.Application.Commands.ICampaignResponseMap Microsoft.Crm.Application.Commands.ApplicationCommand::get_ObjectCampaignResponseMap()
0x32803  ldarg.0
0x32804  callvirt instance class Microsoft.Crm.Application.Utility.EntityAttributeMapBase Microsoft.Crm.Application.Commands.ICampaignResponseMap::CreateInstance(class Microsoft.Crm.Application.Platform.EntityType entityType)
0x32809  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Application.Utility.EntityAttributeMapBase>::Add(var<u1>)
0x3280e  br.s     loc_3281C
0x32810  ldloc.0
0x32811  ldarg.0
0x32812  newobj   instance void Microsoft.Crm.Application.Utility.PlatformEntityMap::.ctor(class Microsoft.Crm.Application.Platform.EntityType targetEntityType)
0x32817  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Application.Utility.EntityAttributeMapBase>::Add(var<u1>)
0x3281c  ldarg.0
0x3281d  callvirt instance string Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x32822  stloc.3
0x32823  ldloc.3
0x32824  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x32829  stloc.s  4
0x3282b  ldloc.s  4
0x3282d  ldc.i4   0x82EBAD3A
0x32832  bgt.un.s loc_32871
0x32834  ldloc.s  4
0x32836  ldc.i4   0x31C00640
0x3283b  bgt.un.s loc_32857
0x3283d  ldloc.s  4
0x3283f  ldc.i4   0x964BC5D
0x32844  beq      loc_328FF
0x32849  ldloc.s  4
0x3284b  ldc.i4   0x31C00640
0x32850  beq.s    loc_328C0
0x32852  br       loc_32A82
0x32857  ldloc.s  4
0x32859  ldc.i4   0x358B1F11
0x3285e  beq      loc_3293E
0x32863  ldloc.s  4
0x32865  ldc.i4   0x82EBAD3A
0x3286a  beq.s    loc_328AB
0x3286c  br       loc_32A82
0x32871  ldloc.s  4
0x32873  ldc.i4   0xB2F80A30
0x32878  bgt.un.s loc_32891
0x3287a  ldloc.s  4
0x3287c  ldc.i4   0x8A8753C7
0x32881  beq.s    loc_328D5
0x32883  ldloc.s  4
0x32885  ldc.i4   0xB2F80A30
0x3288a  beq.s    loc_328EA
0x3288c  br       loc_32A82
0x32891  ldloc.s  4
0x32893  ldc.i4   0xD6FABDD3
0x32898  beq      loc_32929
0x3289d  ldloc.s  4
0x3289f  ldc.i4   0xF8963A7F
0x328a4  beq.s    loc_32914
0x328a6  br       loc_32A82
0x328ab  ldloc.3
0x328ac  ldstr    aAppointment// "appointment"
0x328b1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x328b6  brtrue   loc_32953
0x328bb  br       loc_32A82
0x328c0  ldloc.3
0x328c1  ldstr    aCampaignrespon_0// "campaignresponse"
0x328c6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x328cb  brtrue   loc_3296C
0x328d0  br       loc_32A82
0x328d5  ldloc.3
0x328d6  ldstr    aEmail// "email"
0x328db  call     bool [mscorlib]System.String::op_Equality(string, string)
0x328e0  brtrue   loc_3299F
0x328e5  br       loc_32A82
0x328ea  ldloc.3
0x328eb  ldstr    aFax// "fax"
0x328f0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x328f5  brtrue   loc_329B8
0x328fa  br       loc_32A82
0x328ff  ldloc.3
0x32900  ldstr    aLetter// "letter"
0x32905  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3290a  brtrue   loc_329E5
0x3290f  br       loc_32A82
0x32914  ldloc.3
0x32915  ldstr    aPhonecall// "phonecall"
0x3291a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3291f  brtrue   loc_32A13
0x32924  br       loc_32A82
0x32929  ldloc.3
0x3292a  ldstr    aRecurringappoi// "recurringappointmentmaster"
0x3292f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x32934  brtrue   loc_32A41
0x32939  br       loc_32A82
0x3293e  ldloc.3
0x3293f  ldstr    aServiceappoint// "serviceappointment"
0x32944  call     bool [mscorlib]System.String::op_Equality(string, string)
0x32949  brtrue   loc_32A57
0x3294e  br       loc_32A82
0x32953  ldloc.0
0x32954  ldarg.2
0x32955  ldc.i4.1
0x32956  ldarg.0
0x32957  ldstr    aRequiredattend// "requiredattendees"
0x3295c  ldnull
0x3295d  callvirt instance class Microsoft.Crm.Application.Utility.EntityAttributeMapBase Microsoft.Crm.Application.Commands.IMapEntityFactory::RetrieveMapEntity(valuetype Microsoft.Crm.Application.Commands.EntityValidator entityValue, class Microsoft.Crm.Application.Platform.EntityType targetEntityType, string partyParticipationTypeName, string type)
0x32962  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Application.Utility.EntityAttributeMapBase>::Add(var<u1>)
0x32967  br       loc_32A82
0x3296c  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x32971  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x32976  ldstr    aCampaignrespon_0// "campaignresponse"
0x3297b  ldc.i4.1
0x3297c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x32981  brfalse  loc_32A82
0x32986  ldloc.0
0x32987  ldarg.2
0x32988  ldc.i4.2
0x32989  ldarg.0
0x3298a  ldstr    aCustomer// "customer"
0x3298f  ldnull
0x32990  callvirt instance class Microsoft.Crm.Application.Utility.EntityAttributeMapBase Microsoft.Crm.Application.Commands.IMapEntityFactory::RetrieveMapEntity(valuetype Microsoft.Crm.Application.Commands.EntityValidator entityValue, class Microsoft.Crm.Application.Platform.EntityType targetEntityType, string partyParticipationTypeName, string type)
0x32995  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Application.Utility.EntityAttributeMapBase>::Add(var<u1>)
0x3299a  br       loc_32A82
0x3299f  ldloc.0
0x329a0  ldarg.2
0x329a1  ldc.i4.3
0x329a2  ldarg.0
0x329a3  ldstr    aTo// "to"
0x329a8  ldnull
0x329a9  callvirt instance class Microsoft.Crm.Application.Utility.EntityAttributeMapBase Microsoft.Crm.Application.Commands.IMapEntityFactory::RetrieveMapEntity(valuetype Microsoft.Crm.Application.Commands.EntityValidator entityValue, class Microsoft.Crm.Application.Platform.EntityType targetEntityType, string partyParticipationTypeName, string type)
0x329ae  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Application.Utility.EntityAttributeMapBase>::Add(var<u1>)
0x329b3  br       loc_32A82
0x329b8  ldloc.0
0x329b9  ldarg.2
0x329ba  ldc.i4.4
0x329bb  ldarg.0
0x329bc  ldstr    aTo// "to"
0x329c1  ldnull
0x329c2  callvirt instance class Microsoft.Crm.Application.Utility.EntityAttributeMapBase Microsoft.Crm.Application.Commands.IMapEntityFactory::RetrieveMapEntity(valuetype Microsoft.Crm.Application.Commands.EntityValidator entityValue, class Microsoft.Crm.Application.Platform.EntityType targetEntityType, string partyParticipationTypeName, string type)
0x329c7  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Application.Utility.EntityAttributeMapBase>::Add(var<u1>)
0x329cc  ldloc.0
0x329cd  ldarg.2
0x329ce  ldc.i4.4
0x329cf  ldarg.0
0x329d0  ldnull
0x329d1  ldstr    aFaxnumber// "faxnumber"
0x329d6  callvirt instance class Microsoft.Crm.Application.Utility.EntityAttributeMapBase Microsoft.Crm.Application.Commands.IMapEntityFactory::RetrieveMapEntity(valuetype Microsoft.Crm.Application.Commands.EntityValidator entityValue, class Microsoft.Crm.Application.Platform.EntityType targetEntityType, string partyParticipationTypeName, string type)
0x329db  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Application.Utility.EntityAttributeMapBase>::Add(var<u1>)
0x329e0  br       loc_32A82
0x329e5  ldloc.0
0x329e6  ldarg.2
0x329e7  ldc.i4.5
0x329e8  ldarg.0
0x329e9  ldstr    aTo// "to"
0x329ee  ldstr    aDonotpostalmai// "donotpostalmail"
0x329f3  callvirt instance class Microsoft.Crm.Application.Utility.EntityAttributeMapBase Microsoft.Crm.Application.Commands.IMapEntityFactory::RetrieveMapEntity(valuetype Microsoft.Crm.Application.Commands.EntityValidator entityValue, class Microsoft.Crm.Application.Platform.EntityType targetEntityType, string partyParticipationTypeName, string type)
0x329f8  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Application.Utility.EntityAttributeMapBase>::Add(var<u1>)
0x329fd  ldloc.0
0x329fe  ldarg.2
0x329ff  ldc.i4.5
0x32a00  ldarg.0
0x32a01  ldnull
0x32a02  ldstr    aAddress// "address"
0x32a07  callvirt instance class Microsoft.Crm.Application.Utility.EntityAttributeMapBase Microsoft.Crm.Application.Commands.IMapEntityFactory::RetrieveMapEntity(valuetype Microsoft.Crm.Application.Commands.EntityValidator entityValue, class Microsoft.Crm.Application.Platform.EntityType targetEntityType, string partyParticipationTypeName, string type)
0x32a0c  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Application.Utility.EntityAttributeMapBase>::Add(var<u1>)
0x32a11  br.s     loc_32A82
0x32a13  ldloc.0
0x32a14  ldarg.2
0x32a15  ldc.i4.6
0x32a16  ldarg.0
0x32a17  ldstr    aTo// "to"
0x32a1c  ldstr    aDonotphone// "donotphone"
0x32a21  callvirt instance class Microsoft.Crm.Application.Utility.EntityAttributeMapBase Microsoft.Crm.Application.Commands.IMapEntityFactory::RetrieveMapEntity(valuetype Microsoft.Crm.Application.Commands.EntityValidator entityValue, class Microsoft.Crm.Application.Platform.EntityType targetEntityType, string partyParticipationTypeName, string type)
0x32a26  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Application.Utility.EntityAttributeMapBase>::Add(var<u1>)
0x32a2b  ldloc.0
0x32a2c  ldarg.2
0x32a2d  ldc.i4.6
0x32a2e  ldarg.0
0x32a2f  ldnull
0x32a30  ldstr    aPhonenumber// "phonenumber"
0x32a35  callvirt instance class Microsoft.Crm.Application.Utility.EntityAttributeMapBase Microsoft.Crm.Application.Commands.IMapEntityFactory::RetrieveMapEntity(valuetype Microsoft.Crm.Application.Commands.EntityValidator entityValue, class Microsoft.Crm.Application.Platform.EntityType targetEntityType, string partyParticipationTypeName, string type)
0x32a3a  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Application.Utility.EntityAttributeMapBase>::Add(var<u1>)
0x32a3f  br.s     loc_32A82
0x32a41  ldloc.0
0x32a42  ldarg.2
0x32a43  ldc.i4.7
0x32a44  ldarg.0
0x32a45  ldstr    aRequiredattend// "requiredattendees"
0x32a4a  ldnull
0x32a4b  callvirt instance class Microsoft.Crm.Application.Utility.EntityAttributeMapBase Microsoft.Crm.Application.Commands.IMapEntityFactory::RetrieveMapEntity(valuetype Microsoft.Crm.Application.Commands.EntityValidator entityValue, class Microsoft.Crm.Application.Platform.EntityType targetEntityType, string partyParticipationTypeName, string type)
0x32a50  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Application.Utility.EntityAttributeMapBase>::Add(var<u1>)
0x32a55  br.s     loc_32A82
0x32a57  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x32a5c  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x32a61  ldstr    aServiceappoint// "serviceappointment"
0x32a66  ldc.i4.1
0x32a67  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x32a6c  brfalse.s loc_32A82
0x32a6e  ldloc.0
0x32a6f  ldarg.2
0x32a70  ldc.i4.8
0x32a71  ldarg.0
0x32a72  ldstr    aCustomers// "customers"
0x32a77  ldnull
0x32a78  callvirt instance class Microsoft.Crm.Application.Utility.EntityAttributeMapBase Microsoft.Crm.Application.Commands.IMapEntityFactory::RetrieveMapEntity(valuetype Microsoft.Crm.Application.Commands.EntityValidator entityValue, class Microsoft.Crm.Application.Platform.EntityType targetEntityType, string partyParticipationTypeName, string type)
0x32a7d  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Application.Utility.EntityAttributeMapBase>::Add(var<u1>)
0x32a82  ldarg.0
0x32a83  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Application.Platform.EntityType::get_Metadata()
0x32a88  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsActivity()
0x32a8d  brfalse.s loc_32A9F
0x32a8f  ldloc.0
0x32a90  ldarg.2
0x32a91  ldc.i4.0
0x32a92  ldarg.0
0x32a93  ldnull
0x32a94  ldnull
0x32a95  callvirt instance class Microsoft.Crm.Application.Utility.EntityAttributeMapBase Microsoft.Crm.Application.Commands.IMapEntityFactory::RetrieveMapEntity(valuetype Microsoft.Crm.Application.Commands.EntityValidator entityValue, class Microsoft.Crm.Application.Platform.EntityType targetEntityType, string partyParticipationTypeName, string type)
0x32a9a  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Application.Utility.EntityAttributeMapBase>::Add(var<u1>)
0x32a9f  ldloc.0
0x32aa0  ldarg.0
0x32aa1  newobj   instance void Microsoft.Crm.Application.Utility.EntityAttributeMap::.ctor(class Microsoft.Crm.Application.Platform.EntityType targetEntityType)
0x32aa6  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Application.Utility.EntityAttributeMapBase>::Add(var<u1>)
0x32aab  ldloc.0
0x32aac  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Application.Utility.EntityAttributeMapBase>::GetEnumerator()
0x32ab1  stloc.s  5
0x32ab3  br.s     loc_32ACB
0x32ab5  ldloc.s  5
0x32ab7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Application.Utility.EntityAttributeMapBase>::get_Current()
0x32abc  dup
0x32abd  ldloc.2
0x32abe  ldloc.1
0x32abf  ldarg.1
0x32ac0  callvirt instance void Microsoft.Crm.Application.Utility.EntityAttributeMapBase::ProcessParameters(class Microsoft.Crm.Application.Platform.Entity targetEntity, class [System.Core]System.Collections.Generic.HashSet`1<string> keys, class [System]System.Collections.Specialized.NameValueCollection parameters)
0x32ac5  callvirt instance class Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Utility.EntityAttributeMapBase::get_TargetEntity()
0x32aca  stloc.2
0x32acb  ldloc.s  5
0x32acd  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x32ad2  brtrue.s loc_32AB5
0x32ad4  leave.s  loc_32AE2
0x32ad6  ldloc.s  5
0x32ad8  brfalse.s loc_32AE1
0x32ada  ldloc.s  5
0x32adc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x32ae1  endfinally
0x32ae2  ldloc.1
0x32ae3  ldstr    aCreatefromid// "_CreateFromId"
0x32ae8  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Remove(var<u1>)
0x32aed  pop
0x32aee  ldloc.1
0x32aef  ldstr    aCreatefromtype// "_CreateFromType"
0x32af4  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Remove(var<u1>)
0x32af9  pop
0x32afa  ldloc.2
0x32afb  ret
```
