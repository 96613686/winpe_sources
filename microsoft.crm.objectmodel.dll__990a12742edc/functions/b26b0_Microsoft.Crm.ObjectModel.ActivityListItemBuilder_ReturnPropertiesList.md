# Microsoft.Crm.ObjectModel.ActivityListItemBuilder::ReturnPropertiesList

- ea: `0xb26b0`
- end: `0xb29db`
- name: `Microsoft.Crm.ObjectModel.ActivityListItemBuilder::ReturnPropertiesList`
- size: `811`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0xb29e0`

## callees

- `0xb1320`
- `0xb26b0`
- `0xb3610`
- `0xb4010`
- `0xb58d0`
- `0xb5a70`
- `0xbdb40`

## string_xrefs

- `0xb26c2`: `scheduledstart`
- `0xb26dc`: `scheduledstart`
- `0xb28ab`: `scheduledstart`
- `0xb26ec`: `scheduledend`
- `0xb2706`: `scheduledend`
- `0xb28bc`: `scheduledend`
- `0xb26bd`: `ScheduledStartTime`
- `0xb26e7`: `ScheduledEndTime`
- `0xb27f5`: `LastOpenedTime`
- `0xb27fa`: `email_engagement.lastopenedtime`
- `0xb2814`: `lastopenedtime`

## pseudocode

```c

```

## disassembly

```asm
0xb26b0  newobj   instance void class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.List`1<string>::.ctor()
0xb26b5  stloc.0
0xb26b6  newobj   instance void class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor>::.ctor()
0xb26bb  stloc.1
0xb26bc  ldloc.1
0xb26bd  ldstr    aScheduledstart_0// "ScheduledStartTime"
0xb26c2  ldstr    aScheduledstart// "scheduledstart"
0xb26c7  ldsfld   string [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.FieldFormat::Raw
0xb26cc  call     string [mscorlib]System.String::Concat(string, string)
0xb26d1  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ReferencePropertyDescriptor::.ctor(string, string)
0xb26d6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor>::Add(var<u1>)
0xb26db  ldloc.0
0xb26dc  ldstr    aScheduledstart// "scheduledstart"
0xb26e1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xb26e6  ldloc.1
0xb26e7  ldstr    aScheduledendti// "ScheduledEndTime"
0xb26ec  ldstr    aScheduledend// "scheduledend"
0xb26f1  ldsfld   string [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.FieldFormat::Raw
0xb26f6  call     string [mscorlib]System.String::Concat(string, string)
0xb26fb  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ReferencePropertyDescriptor::.ctor(string, string)
0xb2700  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor>::Add(var<u1>)
0xb2705  ldloc.0
0xb2706  ldstr    aScheduledend// "scheduledend"
0xb270b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xb2710  ldloc.1
0xb2711  ldstr    aActivitystate// "ActivityState"
0xb2716  ldstr    aStatecode// "statecode"
0xb271b  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ReferencePropertyDescriptor::.ctor(string, string)
0xb2720  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor>::Add(var<u1>)
0xb2725  ldloc.0
0xb2726  ldstr    aStatecode// "statecode"
0xb272b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xb2730  ldloc.1
0xb2731  ldstr    aActivitytype// "ActivityType"
0xb2736  ldstr    aActivitytypeco// "activitytypecode"
0xb273b  ldsfld   string [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.FieldFormat::Raw
0xb2740  call     string [mscorlib]System.String::Concat(string, string)
0xb2745  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ReferencePropertyDescriptor::.ctor(string, string)
0xb274a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor>::Add(var<u1>)
0xb274f  ldloc.0
0xb2750  ldstr    aActivitytypeco// "activitytypecode"
0xb2755  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xb275a  ldloc.1
0xb275b  ldstr    aStaterequestac// "StateRequestActionProvider"
0xb2760  ldstr    aActionprovider// "ActionProvider"
0xb2765  ldstr    aSetstatereques// "SetStateRequest"
0xb276a  ldnull
0xb276b  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.QueryDescriptor::.ctor(string, object)
0xb2770  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ActionProviderPropertyDescriptor::.ctor(string, string, object)
0xb2775  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor>::Add(var<u1>)
0xb277a  ldarg.1
0xb277b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_MetadataCache()
0xb2780  ldarg.0
0xb2781  callvirt instance int32 Microsoft.Crm.ObjectModel.ListQueryWrapper::get_AssociatedEntityType()
0xb2786  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(int32)
0xb278b  stloc.2
0xb278c  ldloc.2
0xb278d  brfalse  loc_B29D1
0xb2792  ldloc.2
0xb2793  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryField()
0xb2798  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Name()
0xb279d  stloc.3
0xb279e  ldloc.1
0xb279f  ldstr    aSubject_0// "Subject"
0xb27a4  ldloc.3
0xb27a5  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ReferencePropertyDescriptor::.ctor(string, string)
0xb27aa  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor>::Add(var<u1>)
0xb27af  ldloc.0
0xb27b0  ldloc.3
0xb27b1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xb27b6  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::GetOrganizationGuid()
0xb27bb  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0xb27c0  call     bool Microsoft.Crm.ObjectModel.FeatureControlUtilities::IsEmailEngagementFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0xb27c5  brfalse  loc_B289C
0xb27ca  ldloc.1
0xb27cb  ldstr    aIsemailfollowe_0// "IsEmailFollowed"
0xb27d0  ldstr    aEmailEngagemen_0// "email_engagement.isemailfollowed"
0xb27d5  ldsfld   string [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.FieldFormat::Raw
0xb27da  call     string [mscorlib]System.String::Concat(string, string)
0xb27df  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ReferencePropertyDescriptor::.ctor(string, string)
0xb27e4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor>::Add(var<u1>)
0xb27e9  ldloc.0
0xb27ea  ldstr    aIsemailfollowe// "isemailfollowed"
0xb27ef  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xb27f4  ldloc.1
0xb27f5  ldstr    aLastopenedtime// "LastOpenedTime"
0xb27fa  ldstr    aEmailEngagemen_1// "email_engagement.lastopenedtime"
0xb27ff  ldsfld   string [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.FieldFormat::Raw
0xb2804  call     string [mscorlib]System.String::Concat(string, string)
0xb2809  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ReferencePropertyDescriptor::.ctor(string, string)
0xb280e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor>::Add(var<u1>)
0xb2813  ldloc.0
0xb2814  ldstr    aLastopenedtime_0// "lastopenedtime"
0xb2819  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xb281e  ldloc.1
0xb281f  ldstr    aSenton// "SentOn"
0xb2824  ldstr    aSenton_0// "senton"
0xb2829  ldsfld   string [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.FieldFormat::Raw
0xb282e  call     string [mscorlib]System.String::Concat(string, string)
0xb2833  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ReferencePropertyDescriptor::.ctor(string, string)
0xb2838  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor>::Add(var<u1>)
0xb283d  ldloc.0
0xb283e  ldstr    aSenton// "SentOn"
0xb2843  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xb2848  ldloc.1
0xb2849  ldstr    aDelayedemailse_0// "DelayedEmailSendTime"
0xb284e  ldstr    aEmailEngagemen_2// "email_engagement.delayedemailsendtime"
0xb2853  ldsfld   string [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.FieldFormat::Raw
0xb2858  call     string [mscorlib]System.String::Concat(string, string)
0xb285d  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ReferencePropertyDescriptor::.ctor(string, string)
0xb2862  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor>::Add(var<u1>)
0xb2867  ldloc.0
0xb2868  ldstr    aDelayedemailse_1// "delayedEmailSendTime"
0xb286d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xb2872  ldloc.1
0xb2873  ldstr    aStatuscode_0// "StatusCode"
0xb2878  ldstr    aStatuscode// "statuscode"
0xb287d  ldsfld   string [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Framework.FieldFormat::Raw
0xb2882  call     string [mscorlib]System.String::Concat(string, string)
0xb2887  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ReferencePropertyDescriptor::.ctor(string, string)
0xb288c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor>::Add(var<u1>)
0xb2891  ldloc.0
0xb2892  ldstr    aStatuscode// "statuscode"
0xb2897  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xb289c  ldc.i4.0
0xb289d  newarr   [mscorlib]System.Object
0xb28a2  newobj   instance void [Microsoft.Crm.Client.Shared]System.Dictionary::.ctor(object[])
0xb28a7  stloc.s  4
0xb28a9  ldloc.s  4
0xb28ab  ldstr    aScheduledstart// "scheduledstart"
0xb28b0  ldstr    aSet// "Set"
0xb28b5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xb28ba  ldloc.s  4
0xb28bc  ldstr    aScheduledend// "scheduledend"
0xb28c1  ldstr    aSet// "Set"
0xb28c6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xb28cb  ldloc.s  4
0xb28cd  ldstr    aStatecode// "statecode"
0xb28d2  ldstr    aSet// "Set"
0xb28d7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xb28dc  ldloc.s  4
0xb28de  ldstr    aActivitytypeco// "activitytypecode"
0xb28e3  ldstr    aSet// "Set"
0xb28e8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xb28ed  ldarg.0
0xb28ee  call     class [System.Xml]System.Xml.XmlNodeList Microsoft.Crm.ObjectModel.ListItemBuilder::RetrieveFieldNodes(class Microsoft.Crm.ObjectModel.ListQueryWrapper listQuery)
0xb28f3  stloc.s  5
0xb28f5  ldc.i4.0
0xb28f6  stloc.s  6
0xb28f8  br       loc_B29C3
0xb28fd  ldloc.s  5
0xb28ff  ldloc.s  6
0xb2901  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0xb2906  call     bool Microsoft.Crm.ObjectModel.ListItemBuilder::IsFieldHidden(class [System.Xml]System.Xml.XmlNode field)
0xb290b  brtrue   loc_B29BD
0xb2910  ldloc.s  5
0xb2912  ldloc.s  6
0xb2914  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0xb2919  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xb291e  ldstr    aName// "name"
0xb2923  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xb2928  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xb292d  stloc.s  7
0xb292f  ldloc.s  7
0xb2931  ldloc.3
0xb2932  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xb2937  brfalse  loc_B29BD
0xb293c  ldloc.s  4
0xb293e  ldloc.s  7
0xb2940  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0xb2945  brtrue.s loc_B29BD
0xb2947  ldnull
0xb2948  stloc.s  0xA
0xb294a  ldarg.0
0xb294b  ldloc.2
0xb294c  ldloc.s  7
0xb294e  ldarg.1
0xb294f  ldloca.s 8
0xb2951  ldloca.s 9
0xb2953  callvirt instance bool Microsoft.Crm.ObjectModel.ListQueryWrapper::TryGetFieldAttribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata, string fieldName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [out] class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata& attributeMetadata, [out] string& displayName)
0xb2958  brfalse.s loc_B29BD
0xb295a  ldloc.2
0xb295b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_EntityInfo()
0xb2960  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription::get_LogicalName()
0xb2965  ldstr    aActivitypointe_1// "activitypointer"
0xb296a  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb296f  brtrue.s loc_B2988
0xb2971  ldloc.2
0xb2972  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_EntityInfo()
0xb2977  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription::get_LogicalName()
0xb297c  ldstr    aEmail// "email"
0xb2981  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb2986  brfalse.s loc_B2996
0xb2988  ldloc.s  7
0xb298a  ldstr    aDescription// "description"
0xb298f  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb2994  brtrue.s loc_B29BD
0xb2996  ldloc.s  7
0xb2998  ldloc.s  8
0xb299a  call     string Microsoft.Crm.ObjectModel.AttributeMetadataHelper::GetReadOnlyBindingPath(string bindingPath, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attributeMetadata)
0xb299f  stloc.s  0xA
0xb29a1  ldloc.1
0xb29a2  ldstr    aFirstproperty// "FirstProperty"
0xb29a7  ldloc.s  0xA
0xb29a9  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.ReferencePropertyDescriptor::.ctor(string, string)
0xb29ae  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.Descriptors.ViewModel.PropertyDescriptor>::Add(var<u1>)
0xb29b3  ldloc.0
0xb29b4  ldloc.s  7
0xb29b6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xb29bb  br.s     loc_B29D1
0xb29bd  ldloc.s  6
0xb29bf  ldc.i4.1
0xb29c0  add
0xb29c1  stloc.s  6
0xb29c3  ldloc.s  6
0xb29c5  ldloc.s  5
0xb29c7  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0xb29cc  blt      loc_B28FD
0xb29d1  ldarg.2
0xb29d2  ldloc.0
0xb29d3  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
0xb29d8  stind.ref
0xb29d9  ldloc.1
0xb29da  ret
```
