# Microsoft.Crm.Application.Controls.LookupGridDataProvider::AddCustomCriteria

- ea: `0x5a380`
- end: `0x5a926`
- name: `Microsoft.Crm.Application.Controls.LookupGridDataProvider::AddCustomCriteria`
- size: `1446`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x59ff0`

## callees

- `0x5a380`

## string_xrefs

- `0x5a7da`: `composite`
- `0x5a508`: `createdfromcode`
- `0x5a61f`: `ReportLink`
- `0x5a638`: `linkedreportname`
- `0x5a854`: `templatetypecode`

## pseudocode

```c

```

## disassembly

```asm
0x5a380  ldarg.0
0x5a381  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.View [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_CurrentView()
0x5a386  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.View::get_ObjectType()
0x5a38b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5a390  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x5a395  stloc.0
0x5a396  ldloc.0
0x5a397  ldc.i4   0x125F
0x5a39c  beq      loc_5A449
0x5a3a1  ldarg.0
0x5a3a2  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x5a3a7  ldstr    aCurrentid// "currentid"
0x5a3ac  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5a3b1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5a3b6  brtrue   loc_5A449
0x5a3bb  ldarg.0
0x5a3bc  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x5a3c1  ldstr    aCurrentid// "currentid"
0x5a3c6  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5a3cb  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Parse(string)
0x5a3d0  stloc.3
0x5a3d1  ldloca.s 3
0x5a3d3  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5a3d8  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0x5a3dd  brtrue.s loc_5A449
0x5a3df  ldarg.0
0x5a3e0  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x5a3e5  ldstr    aCurrentobjectt// "currentObjectType"
0x5a3ea  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5a3ef  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5a3f4  brtrue.s loc_5A41C
0x5a3f6  ldarg.0
0x5a3f7  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x5a3fc  ldstr    aCurrentobjectt// "currentObjectType"
0x5a401  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5a406  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5a40b  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x5a410  stloc.s  4
0x5a412  ldloca.s 4
0x5a414  ldloc.0
0x5a415  call     instance bool [mscorlib]System.Int32::Equals(int32)
0x5a41a  brfalse.s loc_5A449
0x5a41c  ldarg.1
0x5a41d  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ApplicationQuery [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.QueryBuilder::get_Query()
0x5a422  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ApplicationQuery::get_CurrentExpression()
0x5a427  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x5a42c  ldarg.2
0x5a42d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x5a432  ldc.i4.1
0x5a433  ldarg.0
0x5a434  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x5a439  ldstr    aCurrentid// "currentid"
0x5a43e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5a443  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x5a448  pop
0x5a449  ldarg.0
0x5a44a  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x5a44f  ldstr    aFilteruser// "filteruser"
0x5a454  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5a459  ldloca.s 1
0x5a45b  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x5a460  brfalse.s loc_5A482
0x5a462  ldloc.1
0x5a463  brfalse.s loc_5A482
0x5a465  ldarg.1
0x5a466  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ApplicationQuery [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.QueryBuilder::get_Query()
0x5a46b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ApplicationQuery::get_CurrentExpression()
0x5a470  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x5a475  ldstr    aOwnerid// "ownerid"
0x5a47a  ldc.i4.s 0x29
0x5a47c  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0x5a481  pop
0x5a482  ldarg.0
0x5a483  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x5a488  ldstr    aMembertypecode// "membertypecode"
0x5a48d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5a492  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5a497  brtrue   loc_5A565
0x5a49c  ldarg.0
0x5a49d  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x5a4a2  ldstr    aMembertypecode// "membertypecode"
0x5a4a7  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5a4ac  ldc.i4.7
0x5a4ad  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5a4b2  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x5a4b7  stloc.s  5
0x5a4b9  ldloc.0
0x5a4ba  ldc.i4   0x10CC
0x5a4bf  beq.s    loc_5A4D6
0x5a4c1  ldloc.0
0x5a4c2  ldc.i4   0x125F
0x5a4c7  beq.s    loc_5A51D
0x5a4c9  ldloc.0
0x5a4ca  ldc.i4   0x2582
0x5a4cf  beq.s    loc_5A542
0x5a4d1  br       loc_5A565
0x5a4d6  ldarg.1
0x5a4d7  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ApplicationQuery [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.QueryBuilder::get_Query()
0x5a4dc  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ApplicationQuery::get_CurrentExpression()
0x5a4e1  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x5a4e6  ldstr    aLockstatus// "lockstatus"
0x5a4eb  ldc.i4.0
0x5a4ec  ldc.i4.0
0x5a4ed  box      [mscorlib]System.Boolean
0x5a4f2  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x5a4f7  pop
0x5a4f8  ldarg.1
0x5a4f9  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ApplicationQuery [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.QueryBuilder::get_Query()
0x5a4fe  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ApplicationQuery::get_CurrentExpression()
0x5a503  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x5a508  ldstr    aCreatedfromcod// "createdfromcode"
0x5a50d  ldc.i4.0
0x5a50e  ldloc.s  5
0x5a510  box      [mscorlib]System.Int32
0x5a515  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x5a51a  pop
0x5a51b  br.s     loc_5A565
0x5a51d  ldarg.1
0x5a51e  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ApplicationQuery [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.QueryBuilder::get_Query()
0x5a523  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ApplicationQuery::get_CurrentExpression()
0x5a528  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x5a52d  ldstr    aPrimaryentity_0// "primaryentity"
0x5a532  ldc.i4.0
0x5a533  ldloc.s  5
0x5a535  box      [mscorlib]System.Int32
0x5a53a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x5a53f  pop
0x5a540  br.s     loc_5A565
0x5a542  ldarg.1
0x5a543  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ApplicationQuery [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.QueryBuilder::get_Query()
0x5a548  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ApplicationQuery::get_CurrentExpression()
0x5a54d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x5a552  ldstr    aQueryentitytyp// "queryentitytype"
0x5a557  ldc.i4.0
0x5a558  ldloc.s  5
0x5a55a  box      [mscorlib]System.Int32
0x5a55f  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x5a564  pop
0x5a565  ldarg.0
0x5a566  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x5a56b  ldstr    aListtype// "listType"
0x5a570  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5a575  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5a57a  brtrue.s loc_5A5BA
0x5a57c  ldarg.0
0x5a57d  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x5a582  ldstr    aListtype// "listType"
0x5a587  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5a58c  ldstr    aStatic// "static"
0x5a591  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5a596  brfalse.s loc_5A5BA
0x5a598  ldarg.1
0x5a599  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ApplicationQuery [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.QueryBuilder::get_Query()
0x5a59e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ApplicationQuery::get_CurrentExpression()
0x5a5a3  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x5a5a8  ldstr    aType// "type"
0x5a5ad  ldc.i4.0
0x5a5ae  ldc.i4.0
0x5a5af  box      [mscorlib]System.Boolean
0x5a5b4  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x5a5b9  pop
0x5a5ba  ldarg.0
0x5a5bb  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x5a5c0  ldstr    aTerritoryid_0// "territoryId"
0x5a5c5  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5a5ca  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5a5cf  brtrue.s loc_5A5FD
0x5a5d1  ldarg.1
0x5a5d2  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ApplicationQuery [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.QueryBuilder::get_Query()
0x5a5d7  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ApplicationQuery::get_CurrentExpression()
0x5a5dc  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x5a5e1  ldstr    aTerritoryid// "territoryid"
0x5a5e6  ldc.i4.0
0x5a5e7  ldarg.0
0x5a5e8  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x5a5ed  ldstr    aTerritoryid_0// "territoryId"
0x5a5f2  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5a5f7  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x5a5fc  pop
0x5a5fd  ldarg.0
0x5a5fe  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x5a603  ldstr    aReportname// "reportname"
0x5a608  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5a60d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5a612  brtrue.s loc_5A654
0x5a614  ldarg.1
0x5a615  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ApplicationQuery [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.QueryBuilder::get_Query()
0x5a61a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ApplicationQuery::get_CurrentExpression()
0x5a61f  ldstr    aReportlink// "ReportLink"
0x5a624  ldstr    aReportid// "reportid"
0x5a629  ldstr    aReportid// "reportid"
0x5a62e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::AddLinkEntity(string, string, string)
0x5a633  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_LinkCriteria()
0x5a638  ldstr    aLinkedreportna// "linkedreportname"
0x5a63d  ldc.i4.0
0x5a63e  ldarg.0
0x5a63f  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x5a644  ldstr    aReportname// "reportname"
0x5a649  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5a64e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x5a653  pop
0x5a654  ldarg.0
0x5a655  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x5a65a  ldstr    aFilterdefault// "filterdefault"
0x5a65f  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5a664  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5a669  brtrue.s loc_5A692
0x5a66b  ldloc.0
0x5a66c  ldc.i4.s 9
0x5a66e  bne.un.s loc_5A692
0x5a670  ldarg.1
0x5a671  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ApplicationQuery [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.QueryBuilder::get_Query()
0x5a676  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ApplicationQuery::get_CurrentExpression()
0x5a67b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x5a680  ldstr    aIsdefault// "isdefault"
0x5a685  ldc.i4.0
0x5a686  ldc.i4.0
0x5a687  box      [mscorlib]System.Boolean
0x5a68c  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x5a691  pop
0x5a692  ldarg.0
0x5a693  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x5a698  ldstr    aTransactioncur_0// "transactioncurrencyid"
0x5a69d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5a6a2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5a6a7  brtrue.s loc_5A71F
0x5a6a9  ldloc.0
0x5a6aa  ldc.i4   0x438
0x5a6af  bne.un.s loc_5A6F3
0x5a6b1  ldarg.1
0x5a6b2  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ApplicationQuery [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.QueryBuilder::get_Query()
0x5a6b7  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ApplicationQuery::get_CurrentExpression()
0x5a6bc  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x5a6c1  ldc.i4.1
0x5a6c2  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddFilter(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0x5a6c7  dup
0x5a6c8  ldstr    aTransactioncur_0// "transactioncurrencyid"
0x5a6cd  ldc.i4.0
0x5a6ce  ldarg.0
0x5a6cf  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x5a6d4  ldstr    aTransactioncur_0// "transactioncurrencyid"
0x5a6d9  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5a6de  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x5a6e3  pop
0x5a6e4  ldstr    aTransactioncur_0// "transactioncurrencyid"
0x5a6e9  ldc.i4.s 0xC
0x5a6eb  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0x5a6f0  pop
0x5a6f1  br.s     loc_5A71F
0x5a6f3  ldarg.1
0x5a6f4  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ApplicationQuery [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.QueryBuilder::get_Query()
0x5a6f9  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ApplicationQuery::get_CurrentExpression()
0x5a6fe  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x5a703  ldstr    aTransactioncur_0// "transactioncurrencyid"
0x5a708  ldc.i4.0
0x5a709  ldarg.0
0x5a70a  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x5a70f  ldstr    aTransactioncur_0// "transactioncurrencyid"
0x5a714  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5a719  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x5a71e  pop
0x5a71f  ldarg.0
0x5a720  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x5a725  ldstr    aParentid_1// "parentId"
0x5a72a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5a72f  stloc.2
0x5a730  ldloc.0
0x5a731  ldc.i4   0x3F2
0x5a736  bgt.s    loc_5A748
0x5a738  ldloc.0
0x5a739  ldc.i4.8
0x5a73a  beq      loc_5A8C2
0x5a73f  ldloc.0
0x5a740  ldc.i4   0x3F2
0x5a745  beq.s    loc_5A764
0x5a747  ret
0x5a748  ldloc.0
0x5a749  ldc.i4   0x41F
0x5a74e  beq.s    loc_5A78D
0x5a750  ldloc.0
0x5a751  ldc.i4   0x42F
0x5a756  beq.s    loc_5A7B6
0x5a758  ldloc.0
0x5a759  ldc.i4   0x2392
0x5a75e  beq      loc_5A810
0x5a763  ret
0x5a764  ldloc.2
0x5a765  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5a76a  brtrue   loc_5A925
0x5a76f  ldarg.1
0x5a770  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ApplicationQuery [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.QueryBuilder::get_Query()
0x5a775  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ApplicationQuery::get_CurrentExpression()
0x5a77a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x5a77f  ldstr    aCustomerid// "customerid"
0x5a784  ldc.i4.0
0x5a785  ldloc.2
0x5a786  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x5a78b  pop
0x5a78c  ret
0x5a78d  ldloc.2
  ... truncated ...
```
