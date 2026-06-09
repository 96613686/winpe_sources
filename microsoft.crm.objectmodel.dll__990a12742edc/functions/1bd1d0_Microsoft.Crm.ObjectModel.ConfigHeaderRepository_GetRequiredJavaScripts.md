# Microsoft.Crm.ObjectModel.ConfigHeaderRepository::GetRequiredJavaScripts

- ea: `0x1bd1d0`
- end: `0x1bd5bf`
- name: `Microsoft.Crm.ObjectModel.ConfigHeaderRepository::GetRequiredJavaScripts`
- size: `1007`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x9a200`

## callees

- `0x1bd1d0`

## string_xrefs

- `0x1bd1d7`: `/_static/_common/scripts/BusinessRulesExecution.js`
- `0x1bd20b`: `/_static/_common/scripts/SalesCrmSoapProxyService.js`
- `0x1bd216`: `/_static/_common/scripts/SalesCommonFramework.js`
- `0x1bd221`: `/_static/_common/scripts/SalesCommonImported.js`
- `0x1bd4a2`: `/_static/_common/scripts/formevt.js`
- `0x1bd4ad`: `/_static/entities/servicerefreshutilities.js`
- `0x1bd503`: `/_static/sfa/comps/comps.js`
- `0x1bd58e`: `/_static/_common/scripts/QOIDetail.js`

## pseudocode

```c

```

## disassembly

```asm
0x1bd1d0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x1bd1d5  stloc.0
0x1bd1d6  ldloc.0
0x1bd1d7  ldstr    aStaticCommonSc_0// "/_static/_common/scripts/BusinessRulesE"...
0x1bd1dc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd1e1  ldarg.0
0x1bd1e2  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsActivity()
0x1bd1e7  brfalse.s loc_1BD22B
0x1bd1e9  ldloc.0
0x1bd1ea  ldstr    aStaticActiviti// "/_static/activities/activity.js"
0x1bd1ef  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd1f4  ldloc.0
0x1bd1f5  ldstr    aStaticControls// "/_static/_controls/PageHandler/EntityPa"...
0x1bd1fa  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd1ff  ldloc.0
0x1bd200  ldstr    aStaticControls_0// "/_static/_controls/startendduration/sta"...
0x1bd205  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd20a  ldloc.0
0x1bd20b  ldstr    aStaticCommonSc_1// "/_static/_common/scripts/SalesCrmSoapPr"...
0x1bd210  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd215  ldloc.0
0x1bd216  ldstr    aStaticCommonSc_2// "/_static/_common/scripts/SalesCommonFra"...
0x1bd21b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd220  ldloc.0
0x1bd221  ldstr    aStaticCommonSc_3// "/_static/_common/scripts/SalesCommonImp"...
0x1bd226  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd22b  ldarg.0
0x1bd22c  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x1bd231  stloc.1
0x1bd232  ldloc.1
0x1bd233  ldc.i4   0x443
0x1bd238  bgt      loc_1BD2C3
0x1bd23d  ldloc.1
0x1bd23e  ldc.i4.s 0x70
0x1bd240  bgt.s    loc_1BD27B
0x1bd242  ldloc.1
0x1bd243  ldc.i4.1
0x1bd244  sub
0x1bd245  switch   loc_1BD43F, loc_1BD465, loc_1BD4D7, loc_1BD4BC, loc_1BD5BD, loc_1BD5BD, loc_1BD5BD, loc_1BD5BD, loc_1BD4F2
0x1bd26e  ldloc.1
0x1bd26f  ldc.i4.s 0x70
0x1bd271  beq      loc_1BD48B
0x1bd276  br       loc_1BD5BD
0x1bd27b  ldloc.1
0x1bd27c  ldc.i4.s 0x7B
0x1bd27e  beq      loc_1BD502
0x1bd283  ldloc.1
0x1bd284  ldc.i4   0x400
0x1bd289  beq      loc_1BD52D
0x1bd28e  ldloc.1
0x1bd28f  ldc.i4   0x43B
0x1bd294  sub
0x1bd295  switch   loc_1BD51D, loc_1BD545, loc_1BD58D, loc_1BD5BD, loc_1BD5BD, loc_1BD55D, loc_1BD58D, loc_1BD575, loc_1BD58D
0x1bd2be  br       loc_1BD5BD
0x1bd2c3  ldloc.1
0x1bd2c4  ldc.i4   0x109B
0x1bd2c9  bgt.s    loc_1BD323
0x1bd2cb  ldloc.1
0x1bd2cc  ldc.i4   0x1069
0x1bd2d1  sub
0x1bd2d2  switch   loc_1BD34B, loc_1BD392, loc_1BD5BD, loc_1BD3A2, loc_1BD5BD, loc_1BD5BD, loc_1BD3B2
0x1bd2f3  ldloc.1
0x1bd2f4  ldc.i4   0x1072
0x1bd2f9  sub
0x1bd2fa  switch   loc_1BD3C2, loc_1BD5BD, loc_1BD5BD, loc_1BD5BD, loc_1BD424
0x1bd313  ldloc.1
0x1bd314  ldc.i4   0x109B
0x1bd319  beq      loc_1BD3D2
0x1bd31e  br       loc_1BD5BD
0x1bd323  ldloc.1
0x1bd324  ldc.i4   0x10CC
0x1bd329  beq      loc_1BD59A
0x1bd32e  ldloc.1
0x1bd32f  ldc.i4   0x1130
0x1bd334  sub
0x1bd335  ldc.i4.2
0x1bd336  ble.un   loc_1BD59A
0x1bd33b  ldloc.1
0x1bd33c  ldc.i4   0x2454
0x1bd341  beq      loc_1BD5B2
0x1bd346  br       loc_1BD5BD
0x1bd34b  ldloc.0
0x1bd34c  ldstr    aStaticActiviti_0// "/_static/activities/recurringappointmen"...
0x1bd351  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd356  ldloc.0
0x1bd357  ldstr    aStaticActiviti_1// "/_static/activities/recurrencedialog/re"...
0x1bd35c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd361  ldloc.0
0x1bd362  ldstr    aStaticActiviti_2// "/_static/activities/recurrenceutil/recu"...
0x1bd367  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd36c  ldloc.0
0x1bd36d  ldstr    aStaticActiviti_3// "/_static/activities/activityscheduling."...
0x1bd372  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd377  ldloc.0
0x1bd378  ldstr    aStaticSmActivi// "/_static/sm/activityscheduling/activity"...
0x1bd37d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd382  ldloc.0
0x1bd383  ldstr    aStaticActiviti_4// "/_static/activities/appointmentnotifica"...
0x1bd388  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd38d  br       loc_1BD5BD
0x1bd392  ldloc.0
0x1bd393  ldstr    aStaticActiviti_5// "/_static/activities/email.js"
0x1bd398  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd39d  br       loc_1BD5BD
0x1bd3a2  ldloc.0
0x1bd3a3  ldstr    aStaticActiviti_6// "/_static/activities/fax.js"
0x1bd3a8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd3ad  br       loc_1BD5BD
0x1bd3b2  ldloc.0
0x1bd3b3  ldstr    aStaticActiviti_7// "/_static/activities/letter.js"
0x1bd3b8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd3bd  br       loc_1BD5BD
0x1bd3c2  ldloc.0
0x1bd3c3  ldstr    aStaticActiviti_8// "/_static/activities/phonecall.js"
0x1bd3c8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd3cd  br       loc_1BD5BD
0x1bd3d2  ldloc.0
0x1bd3d3  ldstr    aStaticActiviti_3// "/_static/activities/activityscheduling."...
0x1bd3d8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd3dd  ldloc.0
0x1bd3de  ldstr    aStaticActiviti_9// "/_static/activities/recurringappointmen"...
0x1bd3e3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd3e8  ldloc.0
0x1bd3e9  ldstr    aStaticSmActivi// "/_static/sm/activityscheduling/activity"...
0x1bd3ee  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd3f3  ldloc.0
0x1bd3f4  ldstr    aStaticActiviti_1// "/_static/activities/recurrencedialog/re"...
0x1bd3f9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd3fe  ldloc.0
0x1bd3ff  ldstr    aStaticActiviti_0// "/_static/activities/recurringappointmen"...
0x1bd404  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd409  ldloc.0
0x1bd40a  ldstr    aStaticActiviti_2// "/_static/activities/recurrenceutil/recu"...
0x1bd40f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd414  ldloc.0
0x1bd415  ldstr    aStaticActiviti_4// "/_static/activities/appointmentnotifica"...
0x1bd41a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd41f  br       loc_1BD5BD
0x1bd424  ldloc.0
0x1bd425  ldstr    aStaticSmActivi// "/_static/sm/activityscheduling/activity"...
0x1bd42a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd42f  ldloc.0
0x1bd430  ldstr    aStaticActiviti_3// "/_static/activities/activityscheduling."...
0x1bd435  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd43a  br       loc_1BD5BD
0x1bd43f  ldloc.0
0x1bd440  ldstr    aStaticSfaAccts// "/_static/sfa/accts/account.js"
0x1bd445  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd44a  ldloc.0
0x1bd44b  ldstr    aStaticGridActi// "/_static/_grid/action.js"
0x1bd450  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd455  ldloc.0
0x1bd456  ldstr    aStaticSfaSfaut// "/_static/sfa/sfautil.js"
0x1bd45b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd460  br       loc_1BD5BD
0x1bd465  ldloc.0
0x1bd466  ldstr    aStaticSfaConta// "/_static/sfa/contacts/contact.js"
0x1bd46b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd470  ldloc.0
0x1bd471  ldstr    aStaticGridActi// "/_static/_grid/action.js"
0x1bd476  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd47b  ldloc.0
0x1bd47c  ldstr    aStaticSfaSfaut// "/_static/sfa/sfautil.js"
0x1bd481  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd486  br       loc_1BD5BD
0x1bd48b  ldloc.0
0x1bd48c  ldstr    aStaticCsCasesC// "/_static/cs/cases/cases.js"
0x1bd491  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd496  ldloc.0
0x1bd497  ldstr    aStaticControls_1// "/_static/_controls/lookup/lookup.js"
0x1bd49c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd4a1  ldloc.0
0x1bd4a2  ldstr    aStaticCommonSc_4// "/_static/_common/scripts/formevt.js"
0x1bd4a7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd4ac  ldloc.0
0x1bd4ad  ldstr    aStaticEntities// "/_static/entities/servicerefreshutiliti"...
0x1bd4b2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd4b7  br       loc_1BD5BD
0x1bd4bc  ldloc.0
0x1bd4bd  ldstr    aStaticSfaLeads// "/_static/sfa/leads/lead.js"
0x1bd4c2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd4c7  ldloc.0
0x1bd4c8  ldstr    aStaticGridActi// "/_static/_grid/action.js"
0x1bd4cd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd4d2  br       loc_1BD5BD
0x1bd4d7  ldloc.0
0x1bd4d8  ldstr    aStaticSfaOppsO// "/_static/sfa/opps/opps.js"
0x1bd4dd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd4e2  ldloc.0
0x1bd4e3  ldstr    aStaticEntities_0// "/_static/entities/ProductDetail.js"
0x1bd4e8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd4ed  br       loc_1BD5BD
0x1bd4f2  ldloc.0
0x1bd4f3  ldstr    aStaticEntities_1// "/_static/Entities/Team.js"
0x1bd4f8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd4fd  br       loc_1BD5BD
0x1bd502  ldloc.0
0x1bd503  ldstr    aStaticSfaComps// "/_static/sfa/comps/comps.js"
0x1bd508  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd50d  ldloc.0
0x1bd50e  ldstr    aStaticGridActi// "/_static/_grid/action.js"
0x1bd513  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd518  br       loc_1BD5BD
0x1bd51d  ldloc.0
0x1bd51e  ldstr    aStaticSfaQuote// "/_static/sfa/quotes/qoi_script.js"
0x1bd523  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd528  br       loc_1BD5BD
0x1bd52d  ldloc.0
0x1bd52e  ldstr    aStaticEntities_2// "/_static/entities/product.js"
0x1bd533  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd538  ldloc.0
0x1bd539  ldstr    aStaticGridActi// "/_static/_grid/action.js"
0x1bd53e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd543  br.s     loc_1BD5BD
0x1bd545  ldloc.0
0x1bd546  ldstr    aStaticSfaQuote_0// "/_static/SFA/quotes/quote.js"
0x1bd54b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd550  ldloc.0
0x1bd551  ldstr    aStaticEntities_0// "/_static/entities/ProductDetail.js"
0x1bd556  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd55b  br.s     loc_1BD5BD
0x1bd55d  ldloc.0
0x1bd55e  ldstr    aStaticSfaSales// "/_static/sfa/salesorder/salesorder.js"
0x1bd563  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd568  ldloc.0
0x1bd569  ldstr    aStaticEntities_0// "/_static/entities/ProductDetail.js"
0x1bd56e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd573  br.s     loc_1BD5BD
0x1bd575  ldloc.0
0x1bd576  ldstr    aStaticSfaInvoi// "/_static/sfa/Invoice/invoice.js"
0x1bd57b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd580  ldloc.0
0x1bd581  ldstr    aStaticEntities_0// "/_static/entities/ProductDetail.js"
0x1bd586  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd58b  br.s     loc_1BD5BD
0x1bd58d  ldloc.0
0x1bd58e  ldstr    aStaticCommonSc_5// "/_static/_common/scripts/QOIDetail.js"
0x1bd593  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd598  br.s     loc_1BD5BD
0x1bd59a  ldloc.0
0x1bd59b  ldstr    aStaticControls_1// "/_static/_controls/lookup/lookup.js"
0x1bd5a0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd5a5  ldloc.0
0x1bd5a6  ldstr    aStaticGridActi// "/_static/_grid/action.js"
0x1bd5ab  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd5b0  br.s     loc_1BD5BD
0x1bd5b2  ldloc.0
0x1bd5b3  ldstr    aStaticControls_2// "/_static/_controls/editableselect/edita"...
0x1bd5b8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1bd5bd  ldloc.0
0x1bd5be  ret
```
