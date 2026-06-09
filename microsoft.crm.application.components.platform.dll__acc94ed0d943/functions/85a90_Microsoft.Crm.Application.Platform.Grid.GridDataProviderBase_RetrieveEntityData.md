# Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::RetrieveEntityData

- ea: `0x85a90`
- end: `0x85fd4`
- name: `Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::RetrieveEntityData`
- size: `1348`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x859c0`

## callees

- `0x30e50`
- `0x3aa00`
- `0x59800`
- `0x5b8b0`
- `0x5bb40`
- `0x5be20`
- `0x5e470`
- `0x5e490`
- `0x71300`
- `0x85700`
- `0x85720`
- `0x85a90`
- `0x85fe0`
- `0x860a0`
- `0x87600`

## string_xrefs

- `0x85b20`: `community`
- `0x85c89`: `community`
- `0x85ea5`: `community`

## pseudocode

```c

```

## disassembly

```asm
0x85a90  ldarg.3
0x85a91  ldc.i4   0x1070
0x85a96  bgt.s    loc_85AA9
0x85a98  ldarg.3
0x85a99  ldc.i4   0x106A
0x85a9e  beq.s    loc_85AC2
0x85aa0  ldarg.3
0x85aa1  ldc.i4   0x1070
0x85aa6  beq.s    loc_85AD2
0x85aa8  ret
0x85aa9  ldarg.3
0x85aaa  ldc.i4   0x1072
0x85aaf  beq.s    loc_85ABA
0x85ab1  ldarg.3
0x85ab2  ldc.i4   0x1078
0x85ab7  beq.s    loc_85ACA
0x85ab9  ret
0x85aba  ldstr    aPhonecall// "phonecall"
0x85abf  stloc.0
0x85ac0  br.s     loc_85AD8
0x85ac2  ldstr    aEmail// "email"
0x85ac7  stloc.0
0x85ac8  br.s     loc_85AD8
0x85aca  ldstr    aSocialactivity// "socialactivity"
0x85acf  stloc.0
0x85ad0  br.s     loc_85AD8
0x85ad2  ldstr    aOpportunityclo// "opportunityclose"
0x85ad7  stloc.0
0x85ad8  ldarg.2
0x85ad9  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x85ade  ldc.i4.0
0x85adf  ble      loc_85FD3
0x85ae4  ldloc.0
0x85ae5  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor(string)
0x85aea  stloc.1
0x85aeb  ldloc.1
0x85aec  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x85af1  ldstr    aActivityid// "activityid"
0x85af6  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x85afb  ldloc.1
0x85afc  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x85b01  ldstr    aActivityid// "activityid"
0x85b06  ldc.i4.8
0x85b07  ldarg.2
0x85b08  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::ToArray()
0x85b0d  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x85b12  ldarg.3
0x85b13  ldc.i4   0x1078
0x85b18  bne.un.s loc_85B7C
0x85b1a  ldloc.1
0x85b1b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x85b20  ldstr    aCommunity// "community"
0x85b25  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x85b2a  ldloc.1
0x85b2b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x85b30  ldstr    aPostfromprofil// "postfromprofileid"
0x85b35  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x85b3a  ldloc.1
0x85b3b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x85b40  ldstr    aPosturl// "posturl"
0x85b45  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x85b4a  ldloc.1
0x85b4b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x85b50  ldstr    aSentimentvalue// "sentimentvalue"
0x85b55  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x85b5a  ldloc.1
0x85b5b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x85b60  ldstr    aPostmessagetyp// "postmessagetype"
0x85b65  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x85b6a  ldloc.1
0x85b6b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x85b70  ldstr    aDescription_0// "description"
0x85b75  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x85b7a  br.s     loc_85BBE
0x85b7c  ldarg.3
0x85b7d  ldc.i4   0x1070
0x85b82  bne.un.s loc_85B96
0x85b84  ldloc.1
0x85b85  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x85b8a  ldstr    aActualrevenue// "actualrevenue"
0x85b8f  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x85b94  br.s     loc_85BBE
0x85b96  ldloc.1
0x85b97  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x85b9c  ldstr    aDirectioncode// "directioncode"
0x85ba1  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x85ba6  ldarg.3
0x85ba7  ldc.i4   0x106A
0x85bac  bne.un.s loc_85BBE
0x85bae  ldloc.1
0x85baf  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x85bb4  ldstr    aAttachmentcoun// "attachmentcount"
0x85bb9  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x85bbe  ldloc.1
0x85bbf  ldarg.0
0x85bc0  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_OrganizationContext()
0x85bc5  call     class Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression query, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x85bca  stloc.2
0x85bcb  ldloc.2
0x85bcc  brfalse  loc_85FD3
0x85bd1  ldloc.2
0x85bd2  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x85bd7  ldc.i4.0
0x85bd8  ble      loc_85FD3
0x85bdd  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x85be2  stloc.3
0x85be3  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x85be8  stloc.s  4
0x85bea  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x85bef  stloc.s  5
0x85bf1  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x85bf6  stloc.s  6
0x85bf8  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x85bfd  stloc.s  7
0x85bff  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x85c04  stloc.s  8
0x85c06  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x85c0b  stloc.s  9
0x85c0d  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x85c12  stloc.s  0xA
0x85c14  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x85c19  stloc.s  0xB
0x85c1b  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x85c20  stloc.s  0xC
0x85c22  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x85c27  stloc.s  0xD
0x85c29  ldloc.2
0x85c2a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.Entity>::GetEnumerator()
0x85c2f  stloc.s  0xE
0x85c31  br       loc_85E3C
0x85c36  ldloc.s  0xE
0x85c38  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Application.Platform.Entity>::get_Current()
0x85c3d  stloc.s  0xF
0x85c3f  ldloc.3
0x85c40  ldloc.s  0xF
0x85c42  callvirt instance string Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x85c47  ldloc.s  0xF
0x85c49  ldstr    aDirectioncode// "directioncode"
0x85c4e  ldc.i4.0
0x85c4f  callvirt instance bool Microsoft.Crm.Application.Platform.EntityProxy::GetAttributeValueAsBoolean(string name, bool defaultValue)
0x85c54  box      [mscorlib]System.Boolean
0x85c59  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x85c5e  ldloc.s  4
0x85c60  ldloc.s  0xF
0x85c62  callvirt instance string Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x85c67  ldloc.s  0xF
0x85c69  ldstr    aAttachmentcoun// "attachmentcount"
0x85c6e  ldc.i4.0
0x85c6f  callvirt instance int32 Microsoft.Crm.Application.Platform.EntityProxy::GetAttributeValueAsNumber(string name, int32 defaultValue)
0x85c74  box      [mscorlib]System.Int32
0x85c79  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x85c7e  ldloc.s  5
0x85c80  ldloc.s  0xF
0x85c82  callvirt instance string Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x85c87  ldloc.s  0xF
0x85c89  ldstr    aCommunity// "community"
0x85c8e  ldc.i4.m1
0x85c8f  callvirt instance int32 Microsoft.Crm.Application.Platform.EntityProxy::GetAttributeValueAsNumber(string name, int32 defaultValue)
0x85c94  box      [mscorlib]System.Int32
0x85c99  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x85c9e  ldloc.s  6
0x85ca0  ldloc.s  0xF
0x85ca2  callvirt instance string Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x85ca7  ldarg.0
0x85ca8  ldloc.s  5
0x85caa  ldloc.s  0xF
0x85cac  callvirt instance string Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x85cb1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x85cb6  unbox.any [mscorlib]System.Int32
0x85cbb  call     instance string Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::CheckCommunitytoIconUrlDictionary(int32 community)
0x85cc0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x85cc5  ldloc.s  0xF
0x85cc7  ldstr    aPostfromprofil// "postfromprofileid"
0x85ccc  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x85cd1  castclass Microsoft.Crm.Application.Types.LookupValue
0x85cd6  stloc.s  0x10
0x85cd8  ldloc.s  0x10
0x85cda  brfalse.s loc_85D0B
0x85cdc  ldloc.s  7
0x85cde  ldloc.s  0xF
0x85ce0  callvirt instance string Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x85ce5  ldloc.s  0x10
0x85ce7  callvirt instance string Microsoft.Crm.Application.Types.LookupValue::get_Name()
0x85cec  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x85cf1  ldloc.s  0x10
0x85cf3  ldc.i4.0
0x85cf4  newobj   instance void Microsoft.Crm.Application.Platform.Grid.LookupInformation::.ctor(class Microsoft.Crm.Application.Types.LookupValue lookup, bool needsIconRendering)
0x85cf9  stloc.s  0x12
0x85cfb  ldloc.s  8
0x85cfd  ldloc.s  0xF
0x85cff  callvirt instance string Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x85d04  ldloc.s  0x12
0x85d06  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x85d0b  ldloc.s  9
0x85d0d  ldloc.s  0xF
0x85d0f  callvirt instance string Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x85d14  ldloc.s  0xF
0x85d16  ldstr    aPosturl// "posturl"
0x85d1b  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x85d20  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x85d25  ldloc.s  0xA
0x85d27  ldloc.s  0xF
0x85d29  callvirt instance string Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x85d2e  ldloc.s  0xF
0x85d30  ldstr    aSentimentvalue// "sentimentvalue"
0x85d35  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x85d3a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x85d3f  ldc.i4.m1
0x85d40  stloc.s  0x11
0x85d42  ldloc.s  0xF
0x85d44  ldstr    aPostmessagetyp// "postmessagetype"
0x85d49  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x85d4e  brfalse.s loc_85D63
0x85d50  ldloc.s  0xF
0x85d52  ldstr    aPostmessagetyp// "postmessagetype"
0x85d57  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x85d5c  unbox.any [mscorlib]System.Int32
0x85d61  stloc.s  0x11
0x85d63  ldloc.s  0x11
0x85d65  ldc.i4.m1
0x85d66  beq.s    loc_85DCE
0x85d68  ldarg.0
0x85d69  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_GridMetadataCache()
0x85d6e  ldc.i4   0x1078
0x85d73  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x85d78  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x85d7d  ldstr    aPostmessagetyp// "postmessagetype"
0x85d82  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Item(!!T0)
0x85d87  call     class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x85d8c  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x85d91  ldarg.0
0x85d92  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_OrganizationContext()
0x85d97  call     class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Platform.PicklistUtility::GetEnumOptions(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attribMetadata, int32 langCode, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x85d9c  stloc.s  0x13
0x85d9e  ldloc.s  0x13
0x85da0  brfalse.s loc_85DCE
0x85da2  ldloc.s  0x13
0x85da4  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::get_Count()
0x85da9  ldc.i4.0
0x85daa  ble.s    loc_85DCE
0x85dac  ldloc.s  0x13
0x85dae  ldloc.s  0x11
0x85db0  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::ContainsKey(var<u1>)
0x85db5  brfalse.s loc_85DCE
0x85db7  ldloc.s  0xB
0x85db9  ldloc.s  0xF
0x85dbb  callvirt instance string Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x85dc0  ldloc.s  0x13
0x85dc2  ldloc.s  0x11
0x85dc4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::get_Item(void)
0x85dc9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x85dce  ldloc.s  0xC
0x85dd0  ldloc.s  0xF
0x85dd2  callvirt instance string Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x85dd7  ldloc.s  0xF
0x85dd9  ldstr    aDescription_0// "description"
0x85dde  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x85de3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x85de8  ldloc.s  0xF
0x85dea  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Application.Platform.EntityBase::get_InnerEntity()
0x85def  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.FormattedValueCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_FormattedValues()
0x85df4  ldstr    aActualrevenue// "actualrevenue"
0x85df9  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, string>::Contains(var<u1>)
0x85dfe  brfalse.s loc_85E3C
0x85e00  ldloc.s  0xF
0x85e02  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Application.Platform.EntityBase::get_InnerEntity()
0x85e07  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.FormattedValueCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_FormattedValues()
0x85e0c  ldstr    aActualrevenue// "actualrevenue"
0x85e11  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, string>::get_Item(void)
0x85e16  brfalse.s loc_85E3C
0x85e18  ldloc.s  0xD
0x85e1a  ldloc.s  0xF
0x85e1c  callvirt instance string Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x85e21  ldloc.s  0xF
0x85e23  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Application.Platform.EntityBase::get_InnerEntity()
0x85e28  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.FormattedValueCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_FormattedValues()
0x85e2d  ldstr    aActualrevenue// "actualrevenue"
0x85e32  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, string>::get_Item(void)
0x85e37  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x85e3c  ldloc.s  0xE
0x85e3e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x85e43  brtrue   loc_85C36
0x85e48  leave.s  loc_85E56
0x85e4a  ldloc.s  0xE
0x85e4c  brfalse.s loc_85E55
0x85e4e  ldloc.s  0xE
0x85e50  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x85e55  endfinally
0x85e56  ldarg.0
0x85e57  ldarg.1
0x85e58  ldloc.3
0x85e59  ldstr    aDirectioncode// "directioncode"
0x85e5e  ldc.i4.2
0x85e5f  newarr   [mscorlib]System.Int32
0x85e64  dup
0x85e65  ldc.i4.0
0x85e66  ldc.i4   0x1072
0x85e6b  stelem.i4
0x85e6c  dup
0x85e6d  ldc.i4.1
  ... truncated ...
```
