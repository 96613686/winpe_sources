# Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.EntityBpfMetadataInformationDataBuilder::BuildBpfOptions

- ea: `0xe7700`
- end: `0xe7829`
- name: `Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.EntityBpfMetadataInformationDataBuilder::BuildBpfOptions`
- size: `297`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0xe76a0`

## callees

- `0xe7700`
- `0xe7940`
- `0xf4a60`

## string_xrefs

- `0xe7810`: `ProcessId`
- `0xe7742`: `processid`
- `0xe77d5`: `processid`

## pseudocode

```c

```

## disassembly

```asm
0xe7700  newobj   instance void StringComparerNoConflicts::.ctor()
0xe7705  newobj   instance void class [System]System.Collections.Generic.SortedList`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EnumOptionJsonWrapper>::.ctor(class [mscorlib]System.Collections.Generic.IComparer`1<var<u1>>)
0xe770a  stloc.0
0xe770b  ldarg.0
0xe770c  ldarg.1
0xe770d  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.EntityBpfMetadataInformationDataBuilder::BuildQueryExpression(int32 entityTypeCode)
0xe7712  ldc.i4.0
0xe7713  ldc.i4.1
0xe7714  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xe7719  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression, bool, bool, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xe771e  stloc.1
0xe771f  ldc.i4.0
0xe7720  stloc.s  4
0xe7722  br.s     loc_E7781
0xe7724  ldloc.1
0xe7725  ldloc.s  4
0xe7727  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0xe772c  stloc.s  5
0xe772e  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EnumOptionJsonWrapper::.ctor()
0xe7733  stloc.s  6
0xe7735  ldloc.s  6
0xe7737  ldloc.s  4
0xe7739  stfld    int32 [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EnumOptionJsonWrapper::Value
0xe773e  ldloc.s  6
0xe7740  ldloc.s  5
0xe7742  ldstr    aProcessid_0// "processid"
0xe7747  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xe774c  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0xe7751  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_Name()
0xe7756  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EnumOptionJsonWrapper::Label
0xe775b  ldloc.0
0xe775c  ldloc.s  6
0xe775e  ldfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EnumOptionJsonWrapper::Label
0xe7763  ldloc.s  6
0xe7765  ldfld    int32 [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EnumOptionJsonWrapper::Value
0xe776a  box      [mscorlib]System.Int32
0xe776f  call     string [mscorlib]System.String::Concat(object, object)
0xe7774  ldloc.s  6
0xe7776  callvirt instance void class [System]System.Collections.Generic.SortedList`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EnumOptionJsonWrapper>::Add(var<u1>, !!T0)
0xe777b  ldloc.s  4
0xe777d  ldc.i4.1
0xe777e  add
0xe777f  stloc.s  4
0xe7781  ldloc.s  4
0xe7783  ldloc.1
0xe7784  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0xe7789  blt.s    loc_E7724
0xe778b  ldloc.0
0xe778c  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<var<u1>> class [System]System.Collections.Generic.SortedList`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EnumOptionJsonWrapper>::get_Values()
0xe7791  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EnumOptionJsonWrapper>::get_Count()
0xe7796  newarr   [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EnumOptionJsonWrapper
0xe779b  stloc.2
0xe779c  ldloc.0
0xe779d  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<var<u1>> class [System]System.Collections.Generic.SortedList`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EnumOptionJsonWrapper>::get_Values()
0xe77a2  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EnumOptionJsonWrapper>::get_Count()
0xe77a7  newarr   [mscorlib]System.String
0xe77ac  stloc.3
0xe77ad  ldc.i4.0
0xe77ae  stloc.s  7
0xe77b0  br.s     loc_E77FB
0xe77b2  ldloc.2
0xe77b3  ldloc.s  7
0xe77b5  ldloc.0
0xe77b6  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<var<u1>> class [System]System.Collections.Generic.SortedList`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EnumOptionJsonWrapper>::get_Values()
0xe77bb  ldloc.s  7
0xe77bd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EnumOptionJsonWrapper>::get_Item(!!T0)
0xe77c2  stelem.ref
0xe77c3  ldloc.3
0xe77c4  ldloc.s  7
0xe77c6  ldloc.1
0xe77c7  ldloc.2
0xe77c8  ldloc.s  7
0xe77ca  ldelem.ref
0xe77cb  ldfld    int32 [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EnumOptionJsonWrapper::Value
0xe77d0  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0xe77d5  ldstr    aProcessid_0// "processid"
0xe77da  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xe77df  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0xe77e4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0xe77e9  stelem.ref
0xe77ea  ldloc.2
0xe77eb  ldloc.s  7
0xe77ed  ldelem.ref
0xe77ee  ldloc.s  7
0xe77f0  stfld    int32 [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EnumOptionJsonWrapper::Value
0xe77f5  ldloc.s  7
0xe77f7  ldc.i4.1
0xe77f8  add
0xe77f9  stloc.s  7
0xe77fb  ldloc.s  7
0xe77fd  ldloc.0
0xe77fe  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<var<u1>> class [System]System.Collections.Generic.SortedList`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EnumOptionJsonWrapper>::get_Values()
0xe7803  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EnumOptionJsonWrapper>::get_Count()
0xe7808  blt.s    loc_E77B2
0xe780a  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.BpfAttributeMetadataJsonWrapper::.ctor()
0xe780f  dup
0xe7810  ldstr    aProcessid// "ProcessId"
0xe7815  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.BpfAttributeMetadataJsonWrapper::BpfAttributeType
0xe781a  dup
0xe781b  ldloc.2
0xe781c  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EnumOptionJsonWrapper[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.BpfAttributeMetadataJsonWrapper::Options
0xe7821  dup
0xe7822  ldloc.3
0xe7823  stfld    string[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.BpfAttributeMetadataJsonWrapper::Ids
0xe7828  ret
```
