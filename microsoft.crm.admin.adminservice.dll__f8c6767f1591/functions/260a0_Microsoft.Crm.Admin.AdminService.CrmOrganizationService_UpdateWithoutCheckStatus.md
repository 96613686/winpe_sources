# Microsoft.Crm.Admin.AdminService.CrmOrganizationService::UpdateWithoutCheckStatus

- ea: `0x260a0`
- end: `0x26419`
- name: `Microsoft.Crm.Admin.AdminService.CrmOrganizationService::UpdateWithoutCheckStatus`
- size: `889`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1f040`
- `0x27020`

## callees

- `0x18790`
- `0x260a0`
- `0x26420`
- `0x3c9c0`

## string_xrefs

- `0x262ad`: `PostProvisionComplete`
- `0x2626e`: `IsRemoteReportServerConfigured`
- `0x263cf`: `Organization property [{0}] can not be updated without checking the org state.`

## pseudocode

```c

```

## disassembly

```asm
0x260a0  ldarg.1
0x260a1  ldstr    aOrganizationda_6// "organizationData"
0x260a6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x260ab  ldarg.1
0x260ac  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x260b1  callvirt instance class [mscorlib]System.Collections.IEnumerable [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_PropertyEntries()
0x260b6  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x260bb  stloc.0
0x260bc  br       loc_263EF
0x260c1  ldloc.0
0x260c2  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x260c7  unbox.any [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyEntry
0x260cc  stloc.1
0x260cd  ldloca.s 1
0x260cf  call     instance string [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyEntry::get_Name()
0x260d4  stloc.2
0x260d5  ldloc.2
0x260d6  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x260db  stloc.3
0x260dc  ldloc.3
0x260dd  ldc.i4   0xA009CEE5
0x260e2  bgt.un   loc_2618C
0x260e7  ldloc.3
0x260e8  ldc.i4   0x373FC01A
0x260ed  bgt.un.s loc_26138
0x260ef  ldloc.3
0x260f0  ldc.i4   0x2D6455E4
0x260f5  bgt.un.s loc_26112
0x260f7  ldloc.3
0x260f8  ldc.i4   0x1BF726EA
0x260fd  beq      loc_26243
0x26102  ldloc.3
0x26103  ldc.i4   0x2D6455E4
0x26108  beq      loc_26372
0x2610d  br       loc_263CA
0x26112  ldloc.3
0x26113  ldc.i4   0x33478642
0x26118  beq      loc_26390
0x2611d  ldloc.3
0x2611e  ldc.i4   0x36E8B900
0x26123  beq      loc_2622E
0x26128  ldloc.3
0x26129  ldc.i4   0x373FC01A
0x2612e  beq      loc_26282
0x26133  br       loc_263CA
0x26138  ldloc.3
0x26139  ldc.i4   0x6E86F52F
0x2613e  bgt.un.s loc_26166
0x26140  ldloc.3
0x26141  ldc.i4   0x3A95320B
0x26146  beq      loc_26363
0x2614b  ldloc.3
0x2614c  ldc.i4   0x46C15F69
0x26151  beq      loc_26300
0x26156  ldloc.3
0x26157  ldc.i4   0x6E86F52F
0x2615c  beq      loc_26381
0x26161  br       loc_263CA
0x26166  ldloc.3
0x26167  ldc.i4   0x78E80FE3
0x2616c  beq      loc_2633F
0x26171  ldloc.3
0x26172  ldc.i4   0x7A49FDE4
0x26177  beq      loc_26258
0x2617c  ldloc.3
0x2617d  ldc.i4   0xA009CEE5
0x26182  beq      loc_2639F
0x26187  br       loc_263CA
0x2618c  ldloc.3
0x2618d  ldc.i4   0xB6BD254E
0x26192  bgt.un.s loc_261DD
0x26194  ldloc.3
0x26195  ldc.i4   0xA964A5FA
0x2619a  bgt.un.s loc_261B7
0x2619c  ldloc.3
0x2619d  ldc.i4   0xA93968B9
0x261a2  beq      loc_263AE
0x261a7  ldloc.3
0x261a8  ldc.i4   0xA964A5FA
0x261ad  beq      loc_2632A
0x261b2  br       loc_263CA
0x261b7  ldloc.3
0x261b8  ldc.i4   0xACA56C2D
0x261bd  beq      loc_262AC
0x261c2  ldloc.3
0x261c3  ldc.i4   0xAD28C4AD
0x261c8  beq      loc_262EB
0x261cd  ldloc.3
0x261ce  ldc.i4   0xB6BD254E
0x261d3  beq      loc_26351
0x261d8  br       loc_263CA
0x261dd  ldloc.3
0x261de  ldc.i4   0xE0A7F821
0x261e3  bgt.un.s loc_2620B
0x261e5  ldloc.3
0x261e6  ldc.i4   0xBA3858AE
0x261eb  beq      loc_26315
0x261f0  ldloc.3
0x261f1  ldc.i4   0xCEEF9B1F
0x261f6  beq      loc_262C1
0x261fb  ldloc.3
0x261fc  ldc.i4   0xE0A7F821
0x26201  beq      loc_26297
0x26206  br       loc_263CA
0x2620b  ldloc.3
0x2620c  ldc.i4   0xE9CA7673
0x26211  beq      loc_262D6
0x26216  ldloc.3
0x26217  ldc.i4   0xF2B35536
0x2621c  beq      loc_263BD
0x26221  ldloc.3
0x26222  ldc.i4   0xFED56A42
0x26227  beq.s    loc_2626D
0x26229  br       loc_263CA
0x2622e  ldloc.2
0x2622f  ldstr    aId// "Id"
0x26234  call     bool [mscorlib]System.String::op_Equality(string, string)
0x26239  brtrue   loc_263EF
0x2623e  br       loc_263CA
0x26243  ldloc.2
0x26244  ldstr    aSrsurl// "SrsUrl"
0x26249  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2624e  brtrue   loc_263EF
0x26253  br       loc_263CA
0x26258  ldloc.2
0x26259  ldstr    aIslocalreportb// "IsLocalReportBacklogPresent"
0x2625e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x26263  brtrue   loc_263EF
0x26268  br       loc_263CA
0x2626d  ldloc.2
0x2626e  ldstr    aIsremotereport// "IsRemoteReportServerConfigured"
0x26273  call     bool [mscorlib]System.String::op_Equality(string, string)
0x26278  brtrue   loc_263EF
0x2627d  br       loc_263CA
0x26282  ldloc.2
0x26283  ldstr    aArereportspubl// "AreReportsPublished"
0x26288  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2628d  brtrue   loc_263EF
0x26292  br       loc_263CA
0x26297  ldloc.2
0x26298  ldstr    aHelpcontentser// "HelpContentServerUrl"
0x2629d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x262a2  brtrue   loc_263EF
0x262a7  br       loc_263CA
0x262ac  ldloc.2
0x262ad  ldstr    aPostprovisionc// "PostProvisionComplete"
0x262b2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x262b7  brtrue   loc_263EF
0x262bc  br       loc_263CA
0x262c1  ldloc.2
0x262c2  ldstr    aUserlicensespu// "UserLicensesPurchased"
0x262c7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x262cc  brtrue   loc_263EF
0x262d1  br       loc_263CA
0x262d6  ldloc.2
0x262d7  ldstr    aStoragelicense// "StorageLicensesPurchased"
0x262dc  call     bool [mscorlib]System.String::op_Equality(string, string)
0x262e1  brtrue   loc_263EF
0x262e6  br       loc_263CA
0x262eb  ldloc.2
0x262ec  ldstr    aExternalidfora// "ExternalIdForAccountConversion"
0x262f1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x262f6  brtrue   loc_263EF
0x262fb  br       loc_263CA
0x26300  ldloc.2
0x26301  ldstr    aOfferconversio// "OfferConversionInProgress"
0x26306  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2630b  brtrue   loc_263EF
0x26310  br       loc_263CA
0x26315  ldloc.2
0x26316  ldstr    aOfferconversio_0// "OfferConversionValidationBypass"
0x2631b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x26320  brtrue   loc_263EF
0x26325  br       loc_263CA
0x2632a  ldloc.2
0x2632b  ldstr    aDatabasemirror// "DatabaseMirroringSetupInProgress"
0x26330  call     bool [mscorlib]System.String::op_Equality(string, string)
0x26335  brtrue   loc_263EF
0x2633a  br       loc_263CA
0x2633f  ldloc.2
0x26340  ldstr    aOffermodifiedo// "OfferModifiedOn"
0x26345  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2634a  brtrue   loc_263EF
0x2634f  br.s     loc_263CA
0x26351  ldloc.2
0x26352  ldstr    aTracecategorie// "TraceCategories"
0x26357  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2635c  brtrue   loc_263EF
0x26361  br.s     loc_263CA
0x26363  ldloc.2
0x26364  ldstr    aTraceenabled// "TraceEnabled"
0x26369  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2636e  brtrue.s loc_263EF
0x26370  br.s     loc_263CA
0x26372  ldloc.2
0x26373  ldstr    aTracescenario// "TraceScenario"
0x26378  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2637d  brtrue.s loc_263EF
0x2637f  br.s     loc_263CA
0x26381  ldloc.2
0x26382  ldstr    aTraceexpiratio// "TraceExpiration"
0x26387  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2638c  brtrue.s loc_263EF
0x2638e  br.s     loc_263CA
0x26390  ldloc.2
0x26391  ldstr    aSuspended// "Suspended"
0x26396  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2639b  brtrue.s loc_263EF
0x2639d  br.s     loc_263CA
0x2639f  ldloc.2
0x263a0  ldstr    aUserlicensespu_0// "UserLicensesPurchasedModifiedOn"
0x263a5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x263aa  brtrue.s loc_263EF
0x263ac  br.s     loc_263CA
0x263ae  ldloc.2
0x263af  ldstr    aStoragelicense_0// "StorageLicensesPurchasedModifiedOn"
0x263b4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x263b9  brtrue.s loc_263EF
0x263bb  br.s     loc_263CA
0x263bd  ldloc.2
0x263be  ldstr    aUsecloudsyncap// "UseCloudSyncApi"
0x263c3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x263c8  brtrue.s loc_263EF
0x263ca  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x263cf  ldstr    aOrganizationPr// "Organization property [{0}] can not be "...
0x263d4  ldc.i4.1
0x263d5  newarr   [mscorlib]System.Object
0x263da  dup
0x263db  ldc.i4.0
0x263dc  ldloca.s 1
0x263de  call     instance string [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyEntry::get_Name()
0x263e3  stelem.ref
0x263e4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x263e9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x263ee  throw
0x263ef  ldloc.0
0x263f0  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x263f5  brtrue   loc_260C1
0x263fa  leave.s  loc_26410
0x263fc  ldloc.0
0x263fd  isinst   [mscorlib]System.IDisposable
0x26402  stloc.s  4
0x26404  ldloc.s  4
0x26406  brfalse.s loc_2640F
0x26408  ldloc.s  4
0x2640a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2640f  endfinally
0x26410  ldarg.0
0x26411  ldarg.1
0x26412  ldc.i4.0
0x26413  call     instance void Microsoft.Crm.Admin.AdminService.CrmOrganizationService::InternalUpdate(class Microsoft.Crm.Admin.AdminService.OrganizationData organizationData, bool checkOrgDisabled)
0x26418  ret
```
