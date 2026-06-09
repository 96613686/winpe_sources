# Microsoft.Crm.Extensibility.PrimaryEntityFieldMetadataFactory::.ctor

- ea: `0x223b0`
- end: `0x22695`
- name: `Microsoft.Crm.Extensibility.PrimaryEntityFieldMetadataFactory::.ctor`
- size: `741`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x22780`

## callees

- `0x22740`

## string_xrefs

- `0x223e8`: `Create`
- `0x22518`: `Update`
- `0x223fb`: `Delete`
- `0x22689`: `TemplateId`
- `0x2240e`: `DeliverIncoming`
- `0x22434`: `GrantAccess`
- `0x2246d`: `ModifyAccess`
- `0x224a6`: `RetrievePrincipalAccess`
- `0x224b9`: `RetrieveSharedPrincipalsAndAccess`
- `0x224cc`: `RevokeAccess`
- `0x225b2`: `AddMembersByFetchXml`
- `0x225e0`: `RemoveItem`
- `0x225f7`: `RemoveItem`
- `0x2260e`: `RemoveMember`
- `0x22625`: `RemoveMembers`
- `0x22639`: `RemoveMembersByFetchXml`

## pseudocode

```c

```

## disassembly

```asm
0x223b0  ldarg.0
0x223b1  call     instance void [mscorlib]System.Object::.ctor()
0x223b6  ldarg.0
0x223b7  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class PrimaryEntityFieldMetadataKey, class Microsoft.Crm.Extensibility.PrimaryEntityFieldMetadata>::.ctor()
0x223bc  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class PrimaryEntityFieldMetadataKey, class Microsoft.Crm.Extensibility.PrimaryEntityFieldMetadata> Microsoft.Crm.Extensibility.PrimaryEntityFieldMetadataFactory::_keyToMetadata
0x223c1  ldarg.0
0x223c2  ldstr    aAssign// "Assign"
0x223c7  ldc.i4.0
0x223c8  ldc.i4.0
0x223c9  ldstr    aTarget// "Target"
0x223ce  ldc.i4.2
0x223cf  call     instance void Microsoft.Crm.Extensibility.PrimaryEntityFieldMetadataFactory::AddMapping(string messageName, int32 primaryEntityObjectType, valuetype Microsoft.Crm.Extensibility.SourcePropertyBag sourcePropertyBag, string fieldName, int32 entityImageType)
0x223d4  ldarg.0
0x223d5  ldstr    aBook// "Book"
0x223da  ldc.i4.0
0x223db  ldc.i4.1
0x223dc  ldstr    aValidationresu// "ValidationResult"
0x223e1  ldc.i4.2
0x223e2  call     instance void Microsoft.Crm.Extensibility.PrimaryEntityFieldMetadataFactory::AddMapping(string messageName, int32 primaryEntityObjectType, valuetype Microsoft.Crm.Extensibility.SourcePropertyBag sourcePropertyBag, string fieldName, int32 entityImageType)
0x223e7  ldarg.0
0x223e8  ldstr    aCreate// "Create"
0x223ed  ldc.i4.0
0x223ee  ldc.i4.1
0x223ef  ldstr    aId// "id"
0x223f4  ldc.i4.1
0x223f5  call     instance void Microsoft.Crm.Extensibility.PrimaryEntityFieldMetadataFactory::AddMapping(string messageName, int32 primaryEntityObjectType, valuetype Microsoft.Crm.Extensibility.SourcePropertyBag sourcePropertyBag, string fieldName, int32 entityImageType)
0x223fa  ldarg.0
0x223fb  ldstr    aDelete// "Delete"
0x22400  ldc.i4.0
0x22401  ldc.i4.0
0x22402  ldstr    aTarget// "Target"
0x22407  ldc.i4.0
0x22408  call     instance void Microsoft.Crm.Extensibility.PrimaryEntityFieldMetadataFactory::AddMapping(string messageName, int32 primaryEntityObjectType, valuetype Microsoft.Crm.Extensibility.SourcePropertyBag sourcePropertyBag, string fieldName, int32 entityImageType)
0x2240d  ldarg.0
0x2240e  ldstr    aDeliverincomin// "DeliverIncoming"
0x22413  ldc.i4.0
0x22414  ldc.i4.1
0x22415  ldstr    aEmailid// "EmailId"
0x2241a  ldc.i4.2
0x2241b  call     instance void Microsoft.Crm.Extensibility.PrimaryEntityFieldMetadataFactory::AddMapping(string messageName, int32 primaryEntityObjectType, valuetype Microsoft.Crm.Extensibility.SourcePropertyBag sourcePropertyBag, string fieldName, int32 entityImageType)
0x22420  ldarg.0
0x22421  ldstr    aDeliverpromote// "DeliverPromote"
0x22426  ldc.i4.0
0x22427  ldc.i4.1
0x22428  ldstr    aEmailid// "EmailId"
0x2242d  ldc.i4.2
0x2242e  call     instance void Microsoft.Crm.Extensibility.PrimaryEntityFieldMetadataFactory::AddMapping(string messageName, int32 primaryEntityObjectType, valuetype Microsoft.Crm.Extensibility.SourcePropertyBag sourcePropertyBag, string fieldName, int32 entityImageType)
0x22433  ldarg.0
0x22434  ldstr    aGrantaccess// "GrantAccess"
0x22439  ldc.i4.0
0x2243a  ldc.i4.0
0x2243b  ldstr    aTarget// "Target"
0x22440  ldc.i4.2
0x22441  call     instance void Microsoft.Crm.Extensibility.PrimaryEntityFieldMetadataFactory::AddMapping(string messageName, int32 primaryEntityObjectType, valuetype Microsoft.Crm.Extensibility.SourcePropertyBag sourcePropertyBag, string fieldName, int32 entityImageType)
0x22446  ldarg.0
0x22447  ldstr    aHandle// "Handle"
0x2244c  ldc.i4.0
0x2244d  ldc.i4.0
0x2244e  ldstr    aTarget// "Target"
0x22453  ldc.i4.2
0x22454  call     instance void Microsoft.Crm.Extensibility.PrimaryEntityFieldMetadataFactory::AddMapping(string messageName, int32 primaryEntityObjectType, valuetype Microsoft.Crm.Extensibility.SourcePropertyBag sourcePropertyBag, string fieldName, int32 entityImageType)
0x22459  ldarg.0
0x2245a  ldstr    aMerge// "Merge"
0x2245f  ldc.i4.0
0x22460  ldc.i4.0
0x22461  ldstr    aTarget// "Target"
0x22466  ldc.i4.2
0x22467  call     instance void Microsoft.Crm.Extensibility.PrimaryEntityFieldMetadataFactory::AddMapping(string messageName, int32 primaryEntityObjectType, valuetype Microsoft.Crm.Extensibility.SourcePropertyBag sourcePropertyBag, string fieldName, int32 entityImageType)
0x2246c  ldarg.0
0x2246d  ldstr    aModifyaccess// "ModifyAccess"
0x22472  ldc.i4.0
0x22473  ldc.i4.0
0x22474  ldstr    aTarget// "Target"
0x22479  ldc.i4.2
0x2247a  call     instance void Microsoft.Crm.Extensibility.PrimaryEntityFieldMetadataFactory::AddMapping(string messageName, int32 primaryEntityObjectType, valuetype Microsoft.Crm.Extensibility.SourcePropertyBag sourcePropertyBag, string fieldName, int32 entityImageType)
0x2247f  ldarg.0
0x22480  ldstr    aReschedule// "Reschedule"
0x22485  ldc.i4.0
0x22486  ldc.i4.0
0x22487  ldstr    aTarget// "Target"
0x2248c  ldc.i4.2
0x2248d  call     instance void Microsoft.Crm.Extensibility.PrimaryEntityFieldMetadataFactory::AddMapping(string messageName, int32 primaryEntityObjectType, valuetype Microsoft.Crm.Extensibility.SourcePropertyBag sourcePropertyBag, string fieldName, int32 entityImageType)
0x22492  ldarg.0
0x22493  ldstr    aRetrieve// "Retrieve"
0x22498  ldc.i4.0
0x22499  ldc.i4.0
0x2249a  ldstr    aTarget// "Target"
0x2249f  ldc.i4.2
0x224a0  call     instance void Microsoft.Crm.Extensibility.PrimaryEntityFieldMetadataFactory::AddMapping(string messageName, int32 primaryEntityObjectType, valuetype Microsoft.Crm.Extensibility.SourcePropertyBag sourcePropertyBag, string fieldName, int32 entityImageType)
0x224a5  ldarg.0
0x224a6  ldstr    aRetrieveprinci// "RetrievePrincipalAccess"
0x224ab  ldc.i4.0
0x224ac  ldc.i4.0
0x224ad  ldstr    aTarget// "Target"
0x224b2  ldc.i4.2
0x224b3  call     instance void Microsoft.Crm.Extensibility.PrimaryEntityFieldMetadataFactory::AddMapping(string messageName, int32 primaryEntityObjectType, valuetype Microsoft.Crm.Extensibility.SourcePropertyBag sourcePropertyBag, string fieldName, int32 entityImageType)
0x224b8  ldarg.0
0x224b9  ldstr    aRetrieveshared// "RetrieveSharedPrincipalsAndAccess"
0x224be  ldc.i4.0
0x224bf  ldc.i4.0
0x224c0  ldstr    aTarget// "Target"
0x224c5  ldc.i4.2
0x224c6  call     instance void Microsoft.Crm.Extensibility.PrimaryEntityFieldMetadataFactory::AddMapping(string messageName, int32 primaryEntityObjectType, valuetype Microsoft.Crm.Extensibility.SourcePropertyBag sourcePropertyBag, string fieldName, int32 entityImageType)
0x224cb  ldarg.0
0x224cc  ldstr    aRevokeaccess// "RevokeAccess"
0x224d1  ldc.i4.0
0x224d2  ldc.i4.0
0x224d3  ldstr    aTarget// "Target"
0x224d8  ldc.i4.2
0x224d9  call     instance void Microsoft.Crm.Extensibility.PrimaryEntityFieldMetadataFactory::AddMapping(string messageName, int32 primaryEntityObjectType, valuetype Microsoft.Crm.Extensibility.SourcePropertyBag sourcePropertyBag, string fieldName, int32 entityImageType)
0x224de  ldarg.0
0x224df  ldstr    aRoute// "Route"
0x224e4  ldc.i4.0
0x224e5  ldc.i4.0
0x224e6  ldstr    aTarget// "Target"
0x224eb  ldc.i4.2
0x224ec  call     instance void Microsoft.Crm.Extensibility.PrimaryEntityFieldMetadataFactory::AddMapping(string messageName, int32 primaryEntityObjectType, valuetype Microsoft.Crm.Extensibility.SourcePropertyBag sourcePropertyBag, string fieldName, int32 entityImageType)
0x224f1  ldarg.0
0x224f2  ldstr    aSetstate// "SetState"
0x224f7  ldc.i4.0
0x224f8  ldc.i4.0
0x224f9  ldstr    aEntitymoniker// "EntityMoniker"
0x224fe  ldc.i4.2
0x224ff  call     instance void Microsoft.Crm.Extensibility.PrimaryEntityFieldMetadataFactory::AddMapping(string messageName, int32 primaryEntityObjectType, valuetype Microsoft.Crm.Extensibility.SourcePropertyBag sourcePropertyBag, string fieldName, int32 entityImageType)
0x22504  ldarg.0
0x22505  ldstr    aSetstatedynami// "SetStateDynamicEntity"
0x2250a  ldc.i4.0
0x2250b  ldc.i4.0
0x2250c  ldstr    aEntitymoniker// "EntityMoniker"
0x22511  ldc.i4.2
0x22512  call     instance void Microsoft.Crm.Extensibility.PrimaryEntityFieldMetadataFactory::AddMapping(string messageName, int32 primaryEntityObjectType, valuetype Microsoft.Crm.Extensibility.SourcePropertyBag sourcePropertyBag, string fieldName, int32 entityImageType)
0x22517  ldarg.0
0x22518  ldstr    aUpdate// "Update"
0x2251d  ldc.i4.0
0x2251e  ldc.i4.0
0x2251f  ldstr    aTarget// "Target"
0x22524  ldc.i4.2
0x22525  call     instance void Microsoft.Crm.Extensibility.PrimaryEntityFieldMetadataFactory::AddMapping(string messageName, int32 primaryEntityObjectType, valuetype Microsoft.Crm.Extensibility.SourcePropertyBag sourcePropertyBag, string fieldName, int32 entityImageType)
0x2252a  ldarg.0
0x2252b  ldstr    aAdditem// "AddItem"
0x22530  ldc.i4   0x1130
0x22535  ldc.i4.0
0x22536  ldstr    aCampaignid// "CampaignId"
0x2253b  ldc.i4.2
0x2253c  call     instance void Microsoft.Crm.Extensibility.PrimaryEntityFieldMetadataFactory::AddMapping(string messageName, int32 primaryEntityObjectType, valuetype Microsoft.Crm.Extensibility.SourcePropertyBag sourcePropertyBag, string fieldName, int32 entityImageType)
0x22541  ldarg.0
0x22542  ldstr    aAdditem// "AddItem"
0x22547  ldc.i4   0x1132
0x2254c  ldc.i4.0
0x2254d  ldstr    aCampaignactivi// "CampaignActivityId"
0x22552  ldc.i4.2
0x22553  call     instance void Microsoft.Crm.Extensibility.PrimaryEntityFieldMetadataFactory::AddMapping(string messageName, int32 primaryEntityObjectType, valuetype Microsoft.Crm.Extensibility.SourcePropertyBag sourcePropertyBag, string fieldName, int32 entityImageType)
0x22558  ldarg.0
0x22559  ldstr    aAddmember// "AddMember"
0x2255e  ldc.i4   0x10CC
0x22563  ldc.i4.0
0x22564  ldstr    aListid// "ListId"
0x22569  ldc.i4.2
0x2256a  call     instance void Microsoft.Crm.Extensibility.PrimaryEntityFieldMetadataFactory::AddMapping(string messageName, int32 primaryEntityObjectType, valuetype Microsoft.Crm.Extensibility.SourcePropertyBag sourcePropertyBag, string fieldName, int32 entityImageType)
0x2256f  ldarg.0
0x22570  ldstr    aAddlistmembers// "AddListMembers"
0x22575  ldc.i4   0x10CC
0x2257a  ldc.i4.0
0x2257b  ldstr    aListid// "ListId"
0x22580  ldc.i4.2
0x22581  call     instance void Microsoft.Crm.Extensibility.PrimaryEntityFieldMetadataFactory::AddMapping(string messageName, int32 primaryEntityObjectType, valuetype Microsoft.Crm.Extensibility.SourcePropertyBag sourcePropertyBag, string fieldName, int32 entityImageType)
0x22586  ldarg.0
0x22587  ldstr    aQualifymember// "QualifyMember"
0x2258c  ldc.i4   0x10CC
0x22591  ldc.i4.0
0x22592  ldstr    aListid// "ListId"
0x22597  ldc.i4.2
0x22598  call     instance void Microsoft.Crm.Extensibility.PrimaryEntityFieldMetadataFactory::AddMapping(string messageName, int32 primaryEntityObjectType, valuetype Microsoft.Crm.Extensibility.SourcePropertyBag sourcePropertyBag, string fieldName, int32 entityImageType)
0x2259d  ldarg.0
0x2259e  ldstr    aAddmembers// "AddMembers"
0x225a3  ldc.i4.s 9
0x225a5  ldc.i4.0
0x225a6  ldstr    aTeamid// "TeamId"
0x225ab  ldc.i4.2
0x225ac  call     instance void Microsoft.Crm.Extensibility.PrimaryEntityFieldMetadataFactory::AddMapping(string messageName, int32 primaryEntityObjectType, valuetype Microsoft.Crm.Extensibility.SourcePropertyBag sourcePropertyBag, string fieldName, int32 entityImageType)
0x225b1  ldarg.0
0x225b2  ldstr    aAddmembersbyfe// "AddMembersByFetchXml"
0x225b7  ldc.i4   0x10CC
0x225bc  ldc.i4.0
0x225bd  ldstr    aListid// "ListId"
0x225c2  ldc.i4.2
0x225c3  call     instance void Microsoft.Crm.Extensibility.PrimaryEntityFieldMetadataFactory::AddMapping(string messageName, int32 primaryEntityObjectType, valuetype Microsoft.Crm.Extensibility.SourcePropertyBag sourcePropertyBag, string fieldName, int32 entityImageType)
0x225c8  ldarg.0
0x225c9  ldstr    aClone// "Clone"
0x225ce  ldc.i4   0x3F2
0x225d3  ldc.i4.0
0x225d4  ldstr    aContractid// "ContractId"
0x225d9  ldc.i4.2
0x225da  call     instance void Microsoft.Crm.Extensibility.PrimaryEntityFieldMetadataFactory::AddMapping(string messageName, int32 primaryEntityObjectType, valuetype Microsoft.Crm.Extensibility.SourcePropertyBag sourcePropertyBag, string fieldName, int32 entityImageType)
0x225df  ldarg.0
0x225e0  ldstr    aRemoveitem// "RemoveItem"
0x225e5  ldc.i4   0x1130
0x225ea  ldc.i4.0
0x225eb  ldstr    aCampaignid// "CampaignId"
0x225f0  ldc.i4.2
0x225f1  call     instance void Microsoft.Crm.Extensibility.PrimaryEntityFieldMetadataFactory::AddMapping(string messageName, int32 primaryEntityObjectType, valuetype Microsoft.Crm.Extensibility.SourcePropertyBag sourcePropertyBag, string fieldName, int32 entityImageType)
0x225f6  ldarg.0
0x225f7  ldstr    aRemoveitem// "RemoveItem"
0x225fc  ldc.i4   0x1132
0x22601  ldc.i4.0
0x22602  ldstr    aCampaignactivi// "CampaignActivityId"
0x22607  ldc.i4.2
0x22608  call     instance void Microsoft.Crm.Extensibility.PrimaryEntityFieldMetadataFactory::AddMapping(string messageName, int32 primaryEntityObjectType, valuetype Microsoft.Crm.Extensibility.SourcePropertyBag sourcePropertyBag, string fieldName, int32 entityImageType)
0x2260d  ldarg.0
0x2260e  ldstr    aRemovemember// "RemoveMember"
0x22613  ldc.i4   0x10CC
0x22618  ldc.i4.0
0x22619  ldstr    aListid// "ListId"
0x2261e  ldc.i4.2
0x2261f  call     instance void Microsoft.Crm.Extensibility.PrimaryEntityFieldMetadataFactory::AddMapping(string messageName, int32 primaryEntityObjectType, valuetype Microsoft.Crm.Extensibility.SourcePropertyBag sourcePropertyBag, string fieldName, int32 entityImageType)
0x22624  ldarg.0
0x22625  ldstr    aRemovemembers// "RemoveMembers"
0x2262a  ldc.i4.s 9
0x2262c  ldc.i4.0
0x2262d  ldstr    aTeamid// "TeamId"
0x22632  ldc.i4.2
0x22633  call     instance void Microsoft.Crm.Extensibility.PrimaryEntityFieldMetadataFactory::AddMapping(string messageName, int32 primaryEntityObjectType, valuetype Microsoft.Crm.Extensibility.SourcePropertyBag sourcePropertyBag, string fieldName, int32 entityImageType)
0x22638  ldarg.0
0x22639  ldstr    aRemovemembersb// "RemoveMembersByFetchXml"
0x2263e  ldc.i4   0x10CC
0x22643  ldc.i4.0
0x22644  ldstr    aListid// "ListId"
0x22649  ldc.i4.2
0x2264a  call     instance void Microsoft.Crm.Extensibility.PrimaryEntityFieldMetadataFactory::AddMapping(string messageName, int32 primaryEntityObjectType, valuetype Microsoft.Crm.Extensibility.SourcePropertyBag sourcePropertyBag, string fieldName, int32 entityImageType)
0x2264f  ldarg.0
0x22650  ldstr    aSend// "Send"
0x22655  ldc.i4   0x106C
0x2265a  ldc.i4.0
0x2265b  ldstr    aFaxid// "FaxId"
0x22660  ldc.i4.2
0x22661  call     instance void Microsoft.Crm.Extensibility.PrimaryEntityFieldMetadataFactory::AddMapping(string messageName, int32 primaryEntityObjectType, valuetype Microsoft.Crm.Extensibility.SourcePropertyBag sourcePropertyBag, string fieldName, int32 entityImageType)
0x22666  ldarg.0
0x22667  ldstr    aSend// "Send"
0x2266c  ldc.i4   0x106A
0x22671  ldc.i4.0
0x22672  ldstr    aEmailid// "EmailId"
0x22677  ldc.i4.2
0x22678  call     instance void Microsoft.Crm.Extensibility.PrimaryEntityFieldMetadataFactory::AddMapping(string messageName, int32 primaryEntityObjectType, valuetype Microsoft.Crm.Extensibility.SourcePropertyBag sourcePropertyBag, string fieldName, int32 entityImageType)
0x2267d  ldarg.0
0x2267e  ldstr    aSend// "Send"
0x22683  ldc.i4   0x7DA
0x22688  ldc.i4.0
0x22689  ldstr    aTemplateid// "TemplateId"
0x2268e  ldc.i4.2
0x2268f  call     instance void Microsoft.Crm.Extensibility.PrimaryEntityFieldMetadataFactory::AddMapping(string messageName, int32 primaryEntityObjectType, valuetype Microsoft.Crm.Extensibility.SourcePropertyBag sourcePropertyBag, string fieldName, int32 entityImageType)
0x22694  ret
```
