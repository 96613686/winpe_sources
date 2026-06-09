# Microsoft.Crm.Application.Utility.MetadataHelper::RetrieveXrmEntityMetadataAndFilterAttributes

- ea: `0x3bce0`
- end: `0x3bf8f`
- name: `Microsoft.Crm.Application.Utility.MetadataHelper::RetrieveXrmEntityMetadataAndFilterAttributes`
- size: `687`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x5e00`

## callees

- `0x3bce0`
- `0x938b0`
- `0x938c0`

## string_xrefs

- `0x3be6c`: `IsValidForCreate`
- `0x3be75`: `IsValidForRead`
- `0x3be7e`: `IsValidForUpdate`

## pseudocode

```c

```

## disassembly

```asm
0x3bce0  ldstr    aLogicalname_0// "LogicalName"
0x3bce5  ldc.i4.0
0x3bce6  ldarg.0
0x3bce7  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataConditionOperator, object)
0x3bcec  stloc.0
0x3bced  ldc.i4.0
0x3bcee  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataFilterExpression::.ctor(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0x3bcf3  stloc.1
0x3bcf4  ldloc.1
0x3bcf5  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataFilterExpression::get_Conditions()
0x3bcfa  ldloc.0
0x3bcfb  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataConditionExpression>::Add(var<u1>)
0x3bd00  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.EntityQueryExpression::.ctor()
0x3bd05  dup
0x3bd06  ldloc.1
0x3bd07  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataQueryExpression::set_Criteria(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataFilterExpression)
0x3bd0c  stloc.2
0x3bd0d  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMetadataChangesRequest::.ctor()
0x3bd12  dup
0x3bd13  ldloc.2
0x3bd14  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMetadataChangesRequest::set_Query(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.EntityQueryExpression)
0x3bd19  dup
0x3bd1a  ldnull
0x3bd1b  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMetadataChangesRequest::set_ClientVersionStamp(string)
0x3bd20  ldarg.3
0x3bd21  newobj   instance void Microsoft.Crm.Application.Platform.ServiceCommands.ExecuteCommand::.ctor(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest request, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x3bd26  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse Microsoft.Crm.Application.Platform.ServiceCommands.ExecuteCommand::Execute()
0x3bd2b  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMetadataChangesResponse
0x3bd30  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadataCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMetadataChangesResponse::get_EntityMetadata()
0x3bd35  call     T0x2B00006A
0x3bd3a  stloc.3
0x3bd3b  ldloc.3
0x3bd3c  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_PrimaryNameAttribute()
0x3bd41  brfalse.s loc_3BD5D
0x3bd43  ldarg.1
0x3bd44  ldloc.3
0x3bd45  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_PrimaryNameAttribute()
0x3bd4a  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x3bd4f  brtrue.s loc_3BD5D
0x3bd51  ldarg.1
0x3bd52  ldloc.3
0x3bd53  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_PrimaryNameAttribute()
0x3bd58  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3bd5d  ldloc.3
0x3bd5e  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_PrimaryIdAttribute()
0x3bd63  brfalse.s loc_3BD7F
0x3bd65  ldarg.1
0x3bd66  ldloc.3
0x3bd67  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_PrimaryIdAttribute()
0x3bd6c  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x3bd71  brtrue.s loc_3BD7F
0x3bd73  ldarg.1
0x3bd74  ldloc.3
0x3bd75  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_PrimaryIdAttribute()
0x3bd7a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3bd7f  ldloc.3
0x3bd80  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_PrimaryImageAttribute()
0x3bd85  brfalse.s loc_3BDA1
0x3bd87  ldarg.1
0x3bd88  ldloc.3
0x3bd89  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_PrimaryImageAttribute()
0x3bd8e  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x3bd93  brtrue.s loc_3BDA1
0x3bd95  ldarg.1
0x3bd96  ldloc.3
0x3bd97  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_PrimaryImageAttribute()
0x3bd9c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3bda1  ldarg.1
0x3bda2  ldstr    aStatecode// "statecode"
0x3bda7  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x3bdac  brtrue.s loc_3BDB9
0x3bdae  ldarg.1
0x3bdaf  ldstr    aStatecode// "statecode"
0x3bdb4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3bdb9  ldarg.1
0x3bdba  ldstr    aStatuscode// "statuscode"
0x3bdbf  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x3bdc4  brtrue.s loc_3BDD1
0x3bdc6  ldarg.1
0x3bdc7  ldstr    aStatuscode// "statuscode"
0x3bdcc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3bdd1  ldstr    aLogicalname_0// "LogicalName"
0x3bdd6  ldc.i4.2
0x3bdd7  ldarg.1
0x3bdd8  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
0x3bddd  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataConditionOperator, object)
0x3bde2  stloc.s  4
0x3bde4  ldc.i4.0
0x3bde5  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataFilterExpression::.ctor(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0x3bdea  stloc.s  5
0x3bdec  ldloc.s  5
0x3bdee  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataFilterExpression::get_Conditions()
0x3bdf3  ldloc.s  4
0x3bdf5  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataConditionExpression>::Add(var<u1>)
0x3bdfa  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataPropertiesExpression::.ctor()
0x3bdff  dup
0x3be00  ldc.i4.0
0x3be01  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataPropertiesExpression::set_AllProperties(bool)
0x3be06  stloc.s  6
0x3be08  ldc.i4.s 0x21
0x3be0a  newarr   [mscorlib]System.String
0x3be0f  dup
0x3be10  ldc.i4.0
0x3be11  ldstr    aAttributetype// "AttributeType"
0x3be16  stelem.ref
0x3be17  dup
0x3be18  ldc.i4.1
0x3be19  ldstr    aDefaultformval// "DefaultFormValue"
0x3be1e  stelem.ref
0x3be1f  dup
0x3be20  ldc.i4.2
0x3be21  ldstr    aDefaultvalue// "DefaultValue"
0x3be26  stelem.ref
0x3be27  dup
0x3be28  ldc.i4.3
0x3be29  ldstr    aDisplayname_0// "DisplayName"
0x3be2e  stelem.ref
0x3be2f  dup
0x3be30  ldc.i4.4
0x3be31  ldstr    aEntitylogicaln_0// "EntityLogicalName"
0x3be36  stelem.ref
0x3be37  dup
0x3be38  ldc.i4.5
0x3be39  ldstr    aFormat// "Format"
0x3be3e  stelem.ref
0x3be3f  dup
0x3be40  ldc.i4.6
0x3be41  ldstr    aFormatname// "FormatName"
0x3be46  stelem.ref
0x3be47  dup
0x3be48  ldc.i4.7
0x3be49  ldstr    aDatetimebehavi// "DateTimeBehavior"
0x3be4e  stelem.ref
0x3be4f  dup
0x3be50  ldc.i4.8
0x3be51  ldstr    aImemode// "ImeMode"
0x3be56  stelem.ref
0x3be57  dup
0x3be58  ldc.i4.s 9
0x3be5a  ldstr    aIsbasecurrency// "IsBaseCurrency"
0x3be5f  stelem.ref
0x3be60  dup
0x3be61  ldc.i4.s 0xA
0x3be63  ldstr    aIssecured// "IsSecured"
0x3be68  stelem.ref
0x3be69  dup
0x3be6a  ldc.i4.s 0xB
0x3be6c  ldstr    aIsvalidforcrea// "IsValidForCreate"
0x3be71  stelem.ref
0x3be72  dup
0x3be73  ldc.i4.s 0xC
0x3be75  ldstr    aIsvalidforread// "IsValidForRead"
0x3be7a  stelem.ref
0x3be7b  dup
0x3be7c  ldc.i4.s 0xD
0x3be7e  ldstr    aIsvalidforupda// "IsValidForUpdate"
0x3be83  stelem.ref
0x3be84  dup
0x3be85  ldc.i4.s 0xE
0x3be87  ldstr    aIssortableenab// "IsSortableEnabled"
0x3be8c  stelem.ref
0x3be8d  dup
0x3be8e  ldc.i4.s 0xF
0x3be90  ldstr    aInheritsfrom// "InheritsFrom"
0x3be95  stelem.ref
0x3be96  dup
0x3be97  ldc.i4.s 0x10
0x3be99  ldstr    aLogicalname_0// "LogicalName"
0x3be9e  stelem.ref
0x3be9f  dup
0x3bea0  ldc.i4.s 0x11
0x3bea2  ldstr    aMaxlength// "MaxLength"
0x3bea7  stelem.ref
0x3bea8  dup
0x3bea9  ldc.i4.s 0x12
0x3beab  ldstr    aMaxvalue// "MaxValue"
0x3beb0  stelem.ref
0x3beb1  dup
0x3beb2  ldc.i4.s 0x13
0x3beb4  ldstr    aMinvalue// "MinValue"
0x3beb9  stelem.ref
0x3beba  dup
0x3bebb  ldc.i4.s 0x14
0x3bebd  ldstr    aOptionset// "OptionSet"
0x3bec2  stelem.ref
0x3bec3  dup
0x3bec4  ldc.i4.s 0x15
0x3bec6  ldstr    aPrecision// "Precision"
0x3becb  stelem.ref
0x3becc  dup
0x3becd  ldc.i4.s 0x16
0x3becf  ldstr    aPrecisionsourc// "PrecisionSource"
0x3bed4  stelem.ref
0x3bed5  dup
0x3bed6  ldc.i4.s 0x17
0x3bed8  ldstr    aRequiredlevel// "RequiredLevel"
0x3bedd  stelem.ref
0x3bede  dup
0x3bedf  ldc.i4.s 0x18
0x3bee1  ldstr    aSourcetype// "SourceType"
0x3bee6  stelem.ref
0x3bee7  dup
0x3bee8  ldc.i4.s 0x19
0x3beea  ldstr    aStatecode_0// "StateCode"
0x3beef  stelem.ref
0x3bef0  dup
0x3bef1  ldc.i4.s 0x1A
0x3bef3  ldstr    aTargets// "Targets"
0x3bef8  stelem.ref
0x3bef9  dup
0x3befa  ldc.i4.s 0x1B
0x3befc  ldstr    aAttributeof// "AttributeOf"
0x3bf01  stelem.ref
0x3bf02  dup
0x3bf03  ldc.i4.s 0x1C
0x3bf05  ldstr    aDescription_1// "Description"
0x3bf0a  stelem.ref
0x3bf0b  dup
0x3bf0c  ldc.i4.s 0x1D
0x3bf0e  ldstr    aIsauditenabled// "IsAuditEnabled"
0x3bf13  stelem.ref
0x3bf14  dup
0x3bf15  ldc.i4.s 0x1E
0x3bf17  ldstr    aIscustomattrib// "IsCustomAttribute"
0x3bf1c  stelem.ref
0x3bf1d  dup
0x3bf1e  ldc.i4.s 0x1F
0x3bf20  ldstr    aIsprimaryid// "IsPrimaryId"
0x3bf25  stelem.ref
0x3bf26  dup
0x3bf27  ldc.i4.s 0x20
0x3bf29  ldstr    aIsprimaryname// "IsPrimaryName"
0x3bf2e  stelem.ref
0x3bf2f  stloc.s  7
0x3bf31  ldloc.s  6
0x3bf33  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<string> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataPropertiesExpression::get_PropertyNames()
0x3bf38  ldloc.s  7
0x3bf3a  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<string>::AddRange(var<u1>[])
0x3bf3f  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.EntityQueryExpression::.ctor()
0x3bf44  dup
0x3bf45  ldloc.1
0x3bf46  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataQueryExpression::set_Criteria(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataFilterExpression)
0x3bf4b  dup
0x3bf4c  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.AttributeQueryExpression::.ctor()
0x3bf51  dup
0x3bf52  ldloc.s  5
0x3bf54  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataQueryExpression::set_Criteria(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.MetadataFilterExpression)
0x3bf59  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.EntityQueryExpression::set_AttributeQuery(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.AttributeQueryExpression)
0x3bf5e  stloc.s  8
0x3bf60  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMetadataChangesRequest::.ctor()
0x3bf65  dup
0x3bf66  ldloc.s  8
0x3bf68  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMetadataChangesRequest::set_Query(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.EntityQueryExpression)
0x3bf6d  dup
0x3bf6e  ldnull
0x3bf6f  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMetadataChangesRequest::set_ClientVersionStamp(string)
0x3bf74  ldarg.3
0x3bf75  newobj   instance void Microsoft.Crm.Application.Platform.ServiceCommands.ExecuteCommand::.ctor(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest request, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x3bf7a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse Microsoft.Crm.Application.Platform.ServiceCommands.ExecuteCommand::Execute()
0x3bf7f  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMetadataChangesResponse
0x3bf84  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadataCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMetadataChangesResponse::get_EntityMetadata()
0x3bf89  call     T0x2B00006A
0x3bf8e  ret
```
