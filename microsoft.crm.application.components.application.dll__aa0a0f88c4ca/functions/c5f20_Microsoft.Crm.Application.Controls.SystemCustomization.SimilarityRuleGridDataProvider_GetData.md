# Microsoft.Crm.Application.Controls.SystemCustomization.SimilarityRuleGridDataProvider::GetData

- ea: `0xc5f20`
- end: `0xc6168`
- name: `Microsoft.Crm.Application.Controls.SystemCustomization.SimilarityRuleGridDataProvider::GetData`
- size: `584`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0xc5f20`
- `0xc6170`
- `0xf4210`

## string_xrefs

- `0xc5f98`: `createdon`
- `0xc60c8`: `createdon`
- `0xc6141`: `createdon`

## pseudocode

```c

```

## disassembly

```asm
0xc5f20  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0xc5f25  stloc.0
0xc5f26  ldtoken  Filter
0xc5f2b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc5f30  ldarg.0
0xc5f31  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0xc5f36  ldstr    aSimilarityfilt// "similarityFilter"
0xc5f3b  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xc5f40  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0xc5f45  unbox.any Filter
0xc5f4a  stloc.1
0xc5f4b  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_ReadSimilarityRule()
0xc5f50  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc5f55  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc5f5a  brfalse  loc_C6110
0xc5f5f  ldstr    aSimilarityrule// "similarityrule"
0xc5f64  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0xc5f69  stloc.2
0xc5f6a  ldloc.2
0xc5f6b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0xc5f70  ldc.i4.6
0xc5f71  newarr   [mscorlib]System.String
0xc5f76  dup
0xc5f77  ldc.i4.0
0xc5f78  ldstr    aName// "name"
0xc5f7d  stelem.ref
0xc5f7e  dup
0xc5f7f  ldc.i4.1
0xc5f80  ldstr    aSimilarityrule_0// "similarityruleid"
0xc5f85  stelem.ref
0xc5f86  dup
0xc5f87  ldc.i4.2
0xc5f88  ldstr    aStatecode// "statecode"
0xc5f8d  stelem.ref
0xc5f8e  dup
0xc5f8f  ldc.i4.3
0xc5f90  ldstr    aMatchingentity// "matchingentityname"
0xc5f95  stelem.ref
0xc5f96  dup
0xc5f97  ldc.i4.4
0xc5f98  ldstr    aCreatedon// "createdon"
0xc5f9d  stelem.ref
0xc5f9e  dup
0xc5f9f  ldc.i4.5
0xc5fa0  ldstr    aModifiedon// "modifiedon"
0xc5fa5  stelem.ref
0xc5fa6  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumns(string[])
0xc5fab  ldloc.2
0xc5fac  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0xc5fb1  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0xc5fb6  ldstr    aBaseentitytype// "baseentitytypecode"
0xc5fbb  ldc.i4.0
0xc5fbc  ldarg.0
0xc5fbd  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0xc5fc2  ldstr    aEntityotc// "entityotc"
0xc5fc7  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xc5fcc  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xc5fd1  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0xc5fd6  ldloc.1
0xc5fd7  ldc.i4.1
0xc5fd8  bne.un.s loc_C5FFB
0xc5fda  ldloc.2
0xc5fdb  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0xc5fe0  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0xc5fe5  ldstr    aStatecode// "statecode"
0xc5fea  ldc.i4.0
0xc5feb  ldc.i4.1
0xc5fec  box      [mscorlib]System.Int32
0xc5ff1  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xc5ff6  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0xc5ffb  ldloc.1
0xc5ffc  ldc.i4.2
0xc5ffd  bne.un.s loc_C6020
0xc5fff  ldloc.2
0xc6000  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0xc6005  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0xc600a  ldstr    aStatecode// "statecode"
0xc600f  ldc.i4.0
0xc6010  ldc.i4.0
0xc6011  box      [mscorlib]System.Int32
0xc6016  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xc601b  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0xc6020  ldarg.0
0xc6021  ldloc.2
0xc6022  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Application.Controls.SystemCustomization.SimilarityRuleGridDataProvider::GetSimilarityRules(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression queryExpression)
0xc6027  stloc.3
0xc6028  ldc.i4.0
0xc6029  stloc.s  4
0xc602b  br       loc_C6103
0xc6030  ldloc.3
0xc6031  ldloc.s  4
0xc6033  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0xc6038  ldstr    aStatecode// "statecode"
0xc603d  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xc6042  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc6047  call     string [mscorlib]System.Convert::ToString(object, class [mscorlib]System.IFormatProvider)
0xc604c  stloc.s  5
0xc604e  ldloc.0
0xc604f  ldc.i4.7
0xc6050  newarr   [mscorlib]System.String
0xc6055  dup
0xc6056  ldc.i4.0
0xc6057  ldloc.3
0xc6058  ldloc.s  4
0xc605a  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0xc605f  ldstr    aSimilarityrule_0// "similarityruleid"
0xc6064  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xc6069  callvirt instance string [mscorlib]System.Object::ToString()
0xc606e  stelem.ref
0xc606f  dup
0xc6070  ldc.i4.1
0xc6071  ldc.i4   0x26DF
0xc6076  stloc.s  6
0xc6078  ldloca.s 6
0xc607a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc607f  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xc6084  stelem.ref
0xc6085  dup
0xc6086  ldc.i4.2
0xc6087  ldloc.3
0xc6088  ldloc.s  4
0xc608a  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0xc608f  ldstr    aName// "name"
0xc6094  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xc6099  callvirt instance string [mscorlib]System.Object::ToString()
0xc609e  stelem.ref
0xc609f  dup
0xc60a0  ldc.i4.3
0xc60a1  ldloc.s  5
0xc60a3  stelem.ref
0xc60a4  dup
0xc60a5  ldc.i4.4
0xc60a6  ldloc.3
0xc60a7  ldloc.s  4
0xc60a9  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0xc60ae  ldstr    aMatchingentity// "matchingentityname"
0xc60b3  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xc60b8  callvirt instance string [mscorlib]System.Object::ToString()
0xc60bd  stelem.ref
0xc60be  dup
0xc60bf  ldc.i4.5
0xc60c0  ldloc.3
0xc60c1  ldloc.s  4
0xc60c3  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0xc60c8  ldstr    aCreatedon// "createdon"
0xc60cd  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xc60d2  callvirt instance string [mscorlib]System.Object::ToString()
0xc60d7  stelem.ref
0xc60d8  dup
0xc60d9  ldc.i4.6
0xc60da  ldloc.3
0xc60db  ldloc.s  4
0xc60dd  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0xc60e2  ldstr    aModifiedon// "modifiedon"
0xc60e7  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xc60ec  callvirt instance string [mscorlib]System.Object::ToString()
0xc60f1  stelem.ref
0xc60f2  newobj   instance void Row::.ctor(string[] columns)
0xc60f7  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xc60fc  pop
0xc60fd  ldloc.s  4
0xc60ff  ldc.i4.1
0xc6100  add
0xc6101  stloc.s  4
0xc6103  ldloc.s  4
0xc6105  ldloc.3
0xc6106  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0xc610b  blt      loc_C6030
0xc6110  ldarg.1
0xc6111  ldc.i4.7
0xc6112  newarr   [mscorlib]System.String
0xc6117  dup
0xc6118  ldc.i4.0
0xc6119  ldstr    aOid// "oid"
0xc611e  stelem.ref
0xc611f  dup
0xc6120  ldc.i4.1
0xc6121  ldstr    aMoid// "moid"
0xc6126  stelem.ref
0xc6127  dup
0xc6128  ldc.i4.2
0xc6129  ldstr    aName// "name"
0xc612e  stelem.ref
0xc612f  dup
0xc6130  ldc.i4.3
0xc6131  ldstr    aStatecode// "statecode"
0xc6136  stelem.ref
0xc6137  dup
0xc6138  ldc.i4.4
0xc6139  ldstr    aMatchingrecord// "matchingrecordname"
0xc613e  stelem.ref
0xc613f  dup
0xc6140  ldc.i4.5
0xc6141  ldstr    aCreatedon// "createdon"
0xc6146  stelem.ref
0xc6147  dup
0xc6148  ldc.i4.6
0xc6149  ldstr    aModifiedon// "modifiedon"
0xc614e  stelem.ref
0xc614f  stind.ref
0xc6150  ldarg.2
0xc6151  ldloc.0
0xc6152  ldtoken  Row
0xc6157  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc615c  callvirt instance class [mscorlib]System.Array [mscorlib]System.Collections.ArrayList::ToArray(class [mscorlib]System.Type)
0xc6161  castclass class Row[]
0xc6166  stind.ref
0xc6167  ret
```
