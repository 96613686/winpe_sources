# Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::CreateDescriptionWithDefaults

- ea: `0x332a0`
- end: `0x33b2f`
- name: `Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::CreateDescriptionWithDefaults`
- size: `2191`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x302e0`
- `0x33210`
- `0x332a0`
- `0x6fd60`
- `0x6fe90`

## string_xrefs

- `0x3356b`: `isrenameable`
- `0x335af`: `ismergeenabledsolutioncomponent`
- `0x33995`: `isdocumentrecommendationsenabled`
- `0x33ad5`: `availableforcreate`
- `0x33ae2`: `availableforcreate`
- `0x33af3`: `availableforupdate`
- `0x33b00`: `availableforupdate`
- `0x33b11`: `availablefordelete`
- `0x33b1e`: `availablefordelete`
- `0x332e1`: `issecurityintersect`
- `0x333be`: `mobileaccesslevelmask`
- `0x333f1`: `isreadonlyinmobileclient`
- `0x334d2`: `isairupdated`
- `0x3368c`: `parentcomponenttype`
- `0x336ae`: `isreadingpaneenabled`
- `0x3358d`: `hasidstable`
- `0x336bf`: `autocreateaccessteams`
- `0x336d0`: `isquickcreateenabled`
- `0x33714`: `canmodifymobileclientreadonly`
- `0x33787`: `cancreateattributes`
- `0x337cb`: `cancreateforms`
- `0x337dc`: `cancreatecharts`
- `0x337ed`: `cancreateviews`

## pseudocode

```c

```

## disassembly

```asm
0x332a0  ldarg.1
0x332a1  newobj   instance void Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x332a6  dup
0x332a7  callvirt instance class Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::get_InnerEntityData()
0x332ac  stloc.0
0x332ad  ldloc.0
0x332ae  ldstr    aEntityid_1// "entityid"
0x332b3  ldarg.0
0x332b4  box      [mscorlib]System.Guid
0x332b9  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x332be  ldloc.0
0x332bf  ldstr    aObjecttypecode_0// "objecttypecode"
0x332c4  ldc.i4.0
0x332c5  box      [mscorlib]System.Int32
0x332ca  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x332cf  ldloc.0
0x332d0  ldstr    aIsintersect_0// "isintersect"
0x332d5  ldc.i4.0
0x332d6  box      [mscorlib]System.Boolean
0x332db  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x332e0  ldloc.0
0x332e1  ldstr    aIssecurityinte_0// "issecurityintersect"
0x332e6  ldc.i4.0
0x332e7  box      [mscorlib]System.Boolean
0x332ec  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x332f1  ldloc.0
0x332f2  ldstr    aIslookuptable_0// "islookuptable"
0x332f7  ldc.i4.0
0x332f8  box      [mscorlib]System.Boolean
0x332fd  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x33302  ldloc.0
0x33303  ldstr    aEventmask_0// "eventmask"
0x33308  ldc.i4.0
0x33309  box      [mscorlib]System.Int32
0x3330e  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x33313  ldloc.0
0x33314  ldstr    aIslogicalentit_0// "islogicalentity"
0x33319  ldc.i4.0
0x3331a  box      [mscorlib]System.Boolean
0x3331f  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x33324  ldloc.0
0x33325  ldstr    aIscustomizable_0// "iscustomizable"
0x3332a  ldc.i4.0
0x3332b  box      [mscorlib]System.Boolean
0x33330  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x33335  ldloc.0
0x33336  ldstr    aIscollaboratio_0// "iscollaboration"
0x3333b  ldc.i4.0
0x3333c  box      [mscorlib]System.Boolean
0x33341  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x33346  ldloc.0
0x33347  ldstr    aIsconnectionse_0// "isconnectionsenabled"
0x3334c  ldc.i4.0
0x3334d  box      [mscorlib]System.Boolean
0x33352  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x33357  ldloc.0
0x33358  ldstr    aIsactivity_0// "isactivity"
0x3335d  ldc.i4.0
0x3335e  box      [mscorlib]System.Boolean
0x33363  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x33368  ldloc.0
0x33369  ldstr    aIsmappable_0// "ismappable"
0x3336e  ldc.i4.0
0x3336f  box      [mscorlib]System.Boolean
0x33374  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x33379  ldloc.0
0x3337a  ldstr    aIsduplicateche_0// "isduplicatechecksupported"
0x3337f  ldc.i4.0
0x33380  box      [mscorlib]System.Boolean
0x33385  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x3338a  ldloc.0
0x3338b  ldstr    aIsdocumentmana_0// "isdocumentmanagementenabled"
0x33390  ldc.i4.0
0x33391  box      [mscorlib]System.Boolean
0x33396  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x3339b  ldloc.0
0x3339c  ldstr    aActivitytypema_0// "activitytypemask"
0x333a1  ldc.i4.0
0x333a2  box      [mscorlib]System.Int32
0x333a7  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x333ac  ldloc.0
0x333ad  ldstr    aOwnershiptypem_0// "ownershiptypemask"
0x333b2  ldc.i4.0
0x333b3  box      [mscorlib]System.Int32
0x333b8  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x333bd  ldloc.0
0x333be  ldstr    aMobileaccessle_0// "mobileaccesslevelmask"
0x333c3  ldc.i4.0
0x333c4  box      [mscorlib]System.Int32
0x333c9  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x333ce  ldloc.0
0x333cf  ldstr    aIsvisibleinmob_1// "isvisibleinmobile"
0x333d4  ldc.i4.0
0x333d5  box      [mscorlib]System.Boolean
0x333da  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x333df  ldloc.0
0x333e0  ldstr    aIsvisibleinmob_2// "isvisibleinmobileclient"
0x333e5  ldc.i4.0
0x333e6  box      [mscorlib]System.Boolean
0x333eb  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x333f0  ldloc.0
0x333f1  ldstr    aIsreadonlyinmo_0// "isreadonlyinmobileclient"
0x333f6  ldc.i4.0
0x333f7  box      [mscorlib]System.Boolean
0x333fc  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x33401  ldloc.0
0x33402  ldstr    aIsofflineinmob_0// "isofflineinmobileclient"
0x33407  callvirt instance bool Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNameValid(string propertyName)
0x3340c  brfalse.s loc_3341F
0x3340e  ldloc.0
0x3340f  ldstr    aIsofflineinmob_0// "isofflineinmobileclient"
0x33414  ldc.i4.0
0x33415  box      [mscorlib]System.Boolean
0x3341a  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x3341f  ldloc.0
0x33420  ldstr    aDayssincerecor_0// "dayssincerecordlastmodified"
0x33425  callvirt instance bool Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNameValid(string propertyName)
0x3342a  brfalse.s loc_3343D
0x3342c  ldloc.0
0x3342d  ldstr    aDayssincerecor_0// "dayssincerecordlastmodified"
0x33432  ldc.i4.0
0x33433  box      [mscorlib]System.Int32
0x33438  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x3343d  ldloc.0
0x3343e  ldstr    aMobileofflinef_0// "mobileofflinefilters"
0x33443  callvirt instance bool Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNameValid(string propertyName)
0x33448  brfalse.s loc_3345A
0x3344a  ldloc.0
0x3344b  ldstr    aMobileofflinef_0// "mobileofflinefilters"
0x33450  ldstr    asc_B967C// ""
0x33455  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x3345a  ldloc.0
0x3345b  ldstr    aIsbusinessproc_0// "isbusinessprocessenabled"
0x33460  ldc.i4.0
0x33461  box      [mscorlib]System.Boolean
0x33466  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x3346b  ldloc.0
0x3346c  ldstr    aIsaudited_0// "isaudited"
0x33471  ldc.i4.0
0x33472  box      [mscorlib]System.Boolean
0x33477  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x3347c  ldloc.0
0x3347d  ldstr    aIsauditenabled_0// "isauditenabled"
0x33482  ldc.i4.0
0x33483  box      [mscorlib]System.Boolean
0x33488  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x3348d  ldloc.0
0x3348e  ldstr    aUsesfullnameco_1// "usesfullnameconventionrules"
0x33493  ldc.i4.0
0x33494  box      [mscorlib]System.Boolean
0x33499  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x3349e  ldloc.0
0x3349f  ldstr    aIsparented_0// "isparented"
0x334a4  ldc.i4.0
0x334a5  box      [mscorlib]System.Boolean
0x334aa  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x334af  ldloc.0
0x334b0  ldstr    aEntitymask_0// "entitymask"
0x334b5  ldc.i4.0
0x334b6  box      [mscorlib]System.Int32
0x334bb  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x334c0  ldloc.0
0x334c1  ldstr    aIsreplicated_0// "isreplicated"
0x334c6  ldc.i4.0
0x334c7  box      [mscorlib]System.Boolean
0x334cc  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x334d1  ldloc.0
0x334d2  ldstr    aIsairupdated_0// "isairupdated"
0x334d7  ldc.i4.0
0x334d8  box      [mscorlib]System.Boolean
0x334dd  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x334e2  ldloc.0
0x334e3  ldstr    aIsreplicationu_0// "isreplicationuserfiltered"
0x334e8  ldc.i4.0
0x334e9  box      [mscorlib]System.Boolean
0x334ee  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x334f3  ldloc.0
0x334f4  ldstr    aIschildentity_0// "ischildentity"
0x334f9  ldc.i4.0
0x334fa  box      [mscorlib]System.Boolean
0x334ff  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x33504  ldloc.0
0x33505  ldstr    aIscustomentity_1// "iscustomentity"
0x3350a  ldc.i4.0
0x3350b  box      [mscorlib]System.Boolean
0x33510  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x33515  ldloc.0
0x33516  ldstr    aIsactivitypart_0// "isactivityparty"
0x3351b  ldc.i4.0
0x3351c  box      [mscorlib]System.Boolean
0x33521  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x33526  ldloc.0
0x33527  ldstr    aIsenabledforch_0// "isenabledforcharts"
0x3352c  ldc.i4.0
0x3352d  box      [mscorlib]System.Boolean
0x33532  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x33537  ldloc.0
0x33538  ldstr    aIsenabledfortr_0// "isenabledfortrace"
0x3353d  ldc.i4.0
0x3353e  box      [mscorlib]System.Boolean
0x33543  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x33548  ldloc.0
0x33549  ldstr    aIsvalidforadva_0// "isvalidforadvancedfind"
0x3354e  ldc.i4.0
0x3354f  box      [mscorlib]System.Boolean
0x33554  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x33559  ldloc.0
0x3355a  ldstr    aIsrequiredoffl_0// "isrequiredoffline"
0x3355f  ldc.i4.0
0x33560  box      [mscorlib]System.Boolean
0x33565  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x3356a  ldloc.0
0x3356b  ldstr    aIsrenameable_0// "isrenameable"
0x33570  ldc.i4.0
0x33571  box      [mscorlib]System.Boolean
0x33576  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x3357b  ldloc.0
0x3357c  ldstr    aIsshareableacr_0// "isshareableacrossorgs"
0x33581  ldc.i4.0
0x33582  box      [mscorlib]System.Boolean
0x33587  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x3358c  ldloc.0
0x3358d  ldstr    aHasidstable_0// "hasidstable"
0x33592  ldc.i4.0
0x33593  box      [mscorlib]System.Boolean
0x33598  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x3359d  ldloc.0
0x3359e  ldstr    aIssolutionawar_0// "issolutionaware"
0x335a3  ldc.i4.0
0x335a4  box      [mscorlib]System.Boolean
0x335a9  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x335ae  ldloc.0
0x335af  ldstr    aIsmergeenabled_0// "ismergeenabledsolutioncomponent"
0x335b4  ldc.i4.0
0x335b5  box      [mscorlib]System.Boolean
0x335ba  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x335bf  ldloc.0
0x335c0  ldstr    aIspublishable_0// "ispublishable"
0x335c5  ldc.i4.0
0x335c6  box      [mscorlib]System.Boolean
0x335cb  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x335d0  ldloc.0
0x335d1  ldstr    aCantriggerwork_0// "cantriggerworkflow"
0x335d6  ldc.i4.0
0x335d7  box      [mscorlib]System.Boolean
0x335dc  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x335e1  ldloc.0
0x335e2  ldstr    aWorkflowsuppor_0// "workflowsupport"
0x335e7  ldc.i4.0
0x335e8  box      [mscorlib]System.Int32
0x335ed  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x335f2  ldloc.0
0x335f3  ldstr    aIsimportable_0// "isimportable"
0x335f8  ldc.i4.0
0x335f9  box      [mscorlib]System.Boolean
0x335fe  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x33603  ldloc.0
0x33604  ldstr    aCanbechildincu_0// "canbechildincustomrelationship"
0x33609  ldc.i4.0
0x3360a  box      [mscorlib]System.Boolean
0x3360f  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x33614  ldloc.0
0x33615  ldstr    aCanbeincustome_0// "canbeincustomentityassociation"
0x3361a  ldc.i4.0
0x3361b  box      [mscorlib]System.Boolean
0x33620  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x33625  ldloc.0
0x33626  ldstr    aCanbeincustomr_0// "canbeincustomreflexiverelationship"
0x3362b  ldc.i4.0
0x3362c  box      [mscorlib]System.Boolean
0x33631  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x33636  ldloc.0
0x33637  ldstr    aIsmailmergeena_0// "ismailmergeenabled"
0x3363c  ldc.i4.0
0x3363d  box      [mscorlib]System.Boolean
0x33642  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x33647  ldloc.0
0x33648  ldstr    aIsinheritedfro_0// "isinheritedfrom"
0x3364d  ldc.i4.0
0x3364e  box      [mscorlib]System.Boolean
0x33653  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x33658  ldloc.0
0x33659  ldstr    aIsmultiplequeu_0// "ismultiplequeueenabled"
0x3365e  ldc.i4.0
0x3365f  box      [mscorlib]System.Boolean
0x33664  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x33669  ldloc.0
0x3366a  ldstr    aAutoroutetoown_0// "autoroutetoownerqueue"
0x3366f  ldc.i4.0
0x33670  box      [mscorlib]System.Boolean
0x33675  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x3367a  ldloc.0
0x3367b  ldstr    aCanbesecured_0// "canbesecured"
0x33680  ldc.i4.0
0x33681  box      [mscorlib]System.Boolean
0x33686  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x3368b  ldloc.0
0x3368c  ldstr    aParentcomponen_0// "parentcomponenttype"
0x33691  ldc.i4.0
0x33692  box      [mscorlib]System.Int32
  ... truncated ...
```
