# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read832_EntityName

- ea: `0x97ea0`
- end: `0x98a36`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read832_EntityName`
- size: `2966`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x71080`
- `0x7c020`
- `0x1202e0`
- `0x1206a0`
- `0x160c10`
- `0x160f80`

## callees

- `0x97ea0`

## string_xrefs

- `0x97f38`: `bulkdeletefailure`
- `0x97f45`: `bulkdeleteoperation`
- `0x97f6c`: `businesstask`
- `0x97ffb`: `competitor`
- `0x9803c`: `contracttemplate`
- `0x98181`: `isvconfig`
- `0x9819b`: `kbarticlecomment`
- `0x981a8`: `kbarticletemplate`
- `0x98203`: `mailmergetemplate`
- `0x9829f`: `pluginassembly`
- `0x982ac`: `plugintype`
- `0x982c6`: `privilege`
- `0x9837c`: `reportlink`
- `0x9843f`: `sdkmessageprocessingstepsecureconfig`
- `0x98459`: `service`
- `0x98466`: `serviceappointment`
- `0x984db`: `template`
- `0x985b6`: `wizardaccessprivilege`

## pseudocode

```c

```

## disassembly

```asm
0x97ea0  ldarg.1
0x97ea1  dup
0x97ea2  stloc.0
0x97ea3  brfalse  loc_98A24
0x97ea8  volatile.
0x97eaa  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{2A7F62EC-DA79-4395-A090-8A18F3452A43}::$$method0x60006e1-1
0x97eaf  brtrue   loc_9860C
0x97eb4  ldc.i4   0x8D
0x97eb9  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x97ebe  dup
0x97ebf  ldstr    aNone_0// "none"
0x97ec4  ldc.i4.0
0x97ec5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x97eca  dup
0x97ecb  ldstr    aAccount// "account"
0x97ed0  ldc.i4.1
0x97ed1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x97ed6  dup
0x97ed7  ldstr    aActivitymimeat// "activitymimeattachment"
0x97edc  ldc.i4.2
0x97edd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x97ee2  dup
0x97ee3  ldstr    aActivityparty// "activityparty"
0x97ee8  ldc.i4.3
0x97ee9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x97eee  dup
0x97eef  ldstr    aActivitypointe// "activitypointer"
0x97ef4  ldc.i4.4
0x97ef5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x97efa  dup
0x97efb  ldstr    aAnnotation// "annotation"
0x97f00  ldc.i4.5
0x97f01  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x97f06  dup
0x97f07  ldstr    aAnnualfiscalca// "annualfiscalcalendar"
0x97f0c  ldc.i4.6
0x97f0d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x97f12  dup
0x97f13  ldstr    aAppointment_0// "appointment"
0x97f18  ldc.i4.7
0x97f19  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x97f1e  dup
0x97f1f  ldstr    aAsyncoperation_0// "asyncoperation"
0x97f24  ldc.i4.8
0x97f25  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x97f2a  dup
0x97f2b  ldstr    aAttributemap// "attributemap"
0x97f30  ldc.i4.s 9
0x97f32  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x97f37  dup
0x97f38  ldstr    aBulkdeletefail// "bulkdeletefailure"
0x97f3d  ldc.i4.s 0xA
0x97f3f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x97f44  dup
0x97f45  ldstr    aBulkdeleteoper// "bulkdeleteoperation"
0x97f4a  ldc.i4.s 0xB
0x97f4c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x97f51  dup
0x97f52  ldstr    aBulkoperation// "bulkoperation"
0x97f57  ldc.i4.s 0xC
0x97f59  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x97f5e  dup
0x97f5f  ldstr    aBulkoperationl// "bulkoperationlog"
0x97f64  ldc.i4.s 0xD
0x97f66  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x97f6b  dup
0x97f6c  ldstr    aBusinesstask// "businesstask"
0x97f71  ldc.i4.s 0xE
0x97f73  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x97f78  dup
0x97f79  ldstr    aBusinessunit// "businessunit"
0x97f7e  ldc.i4.s 0xF
0x97f80  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x97f85  dup
0x97f86  ldstr    aBusinessunitne// "businessunitnewsarticle"
0x97f8b  ldc.i4.s 0x10
0x97f8d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x97f92  dup
0x97f93  ldstr    aCalendar// "calendar"
0x97f98  ldc.i4.s 0x11
0x97f9a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x97f9f  dup
0x97fa0  ldstr    aCalendarrule// "calendarrule"
0x97fa5  ldc.i4.s 0x12
0x97fa7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x97fac  dup
0x97fad  ldstr    aCampaign// "campaign"
0x97fb2  ldc.i4.s 0x13
0x97fb4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x97fb9  dup
0x97fba  ldstr    aCampaignactivi_0// "campaignactivity"
0x97fbf  ldc.i4.s 0x14
0x97fc1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x97fc6  dup
0x97fc7  ldstr    aCampaignactivi_1// "campaignactivityitem"
0x97fcc  ldc.i4.s 0x15
0x97fce  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x97fd3  dup
0x97fd4  ldstr    aCampaignitem// "campaignitem"
0x97fd9  ldc.i4.s 0x16
0x97fdb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x97fe0  dup
0x97fe1  ldstr    aCampaignrespon_0// "campaignresponse"
0x97fe6  ldc.i4.s 0x17
0x97fe8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x97fed  dup
0x97fee  ldstr    aColumnmapping// "columnmapping"
0x97ff3  ldc.i4.s 0x18
0x97ff5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x97ffa  dup
0x97ffb  ldstr    aCompetitor// "competitor"
0x98000  ldc.i4.s 0x19
0x98002  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x98007  dup
0x98008  ldstr    aConstraintbase// "constraintbasedgroup"
0x9800d  ldc.i4.s 0x1A
0x9800f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x98014  dup
0x98015  ldstr    aContact// "contact"
0x9801a  ldc.i4.s 0x1B
0x9801c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x98021  dup
0x98022  ldstr    aContract// "contract"
0x98027  ldc.i4.s 0x1C
0x98029  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9802e  dup
0x9802f  ldstr    aContractdetail_0// "contractdetail"
0x98034  ldc.i4.s 0x1D
0x98036  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9803b  dup
0x9803c  ldstr    aContracttempla// "contracttemplate"
0x98041  ldc.i4.s 0x1E
0x98043  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x98048  dup
0x98049  ldstr    aCustomeraddres// "customeraddress"
0x9804e  ldc.i4.s 0x1F
0x98050  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x98055  dup
0x98056  ldstr    aCustomeropport// "customeropportunityrole"
0x9805b  ldc.i4.s 0x20
0x9805d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x98062  dup
0x98063  ldstr    aCustomerrelati// "customerrelationship"
0x98068  ldc.i4.s 0x21
0x9806a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9806f  dup
0x98070  ldstr    aDiscount// "discount"
0x98075  ldc.i4.s 0x22
0x98077  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9807c  dup
0x9807d  ldstr    aDiscounttype// "discounttype"
0x98082  ldc.i4.s 0x23
0x98084  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x98089  dup
0x9808a  ldstr    aDisplaystring// "displaystring"
0x9808f  ldc.i4.s 0x24
0x98091  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x98096  dup
0x98097  ldstr    aDuplicaterecor// "duplicaterecord"
0x9809c  ldc.i4.s 0x25
0x9809e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x980a3  dup
0x980a4  ldstr    aDuplicaterule// "duplicaterule"
0x980a9  ldc.i4.s 0x26
0x980ab  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x980b0  dup
0x980b1  ldstr    aDuplicaterulec// "duplicaterulecondition"
0x980b6  ldc.i4.s 0x27
0x980b8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x980bd  dup
0x980be  ldstr    aEmail_0// "email"
0x980c3  ldc.i4.s 0x28
0x980c5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x980ca  dup
0x980cb  ldstr    aEntitymap// "entitymap"
0x980d0  ldc.i4.s 0x29
0x980d2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x980d7  dup
0x980d8  ldstr    aEquipment// "equipment"
0x980dd  ldc.i4.s 0x2A
0x980df  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x980e4  dup
0x980e5  ldstr    aFax// "fax"
0x980ea  ldc.i4.s 0x2B
0x980ec  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x980f1  dup
0x980f2  ldstr    aFixedmonthlyfi// "fixedmonthlyfiscalcalendar"
0x980f7  ldc.i4.s 0x2C
0x980f9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x980fe  dup
0x980ff  ldstr    aImport// "import"
0x98104  ldc.i4.s 0x2D
0x98106  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9810b  dup
0x9810c  ldstr    aImportdata// "importdata"
0x98111  ldc.i4.s 0x2E
0x98113  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x98118  dup
0x98119  ldstr    aImportfile// "importfile"
0x9811e  ldc.i4.s 0x2F
0x98120  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x98125  dup
0x98126  ldstr    aImportjob// "importjob"
0x9812b  ldc.i4.s 0x30
0x9812d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x98132  dup
0x98133  ldstr    aImportlog// "importlog"
0x98138  ldc.i4.s 0x31
0x9813a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9813f  dup
0x98140  ldstr    aImportmap// "importmap"
0x98145  ldc.i4.s 0x32
0x98147  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9814c  dup
0x9814d  ldstr    aIncident// "incident"
0x98152  ldc.i4.s 0x33
0x98154  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x98159  dup
0x9815a  ldstr    aIncidentresolu_0// "incidentresolution"
0x9815f  ldc.i4.s 0x34
0x98161  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x98166  dup
0x98167  ldstr    aInvoice// "invoice"
0x9816c  ldc.i4.s 0x35
0x9816e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x98173  dup
0x98174  ldstr    aInvoicedetail// "invoicedetail"
0x98179  ldc.i4.s 0x36
0x9817b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x98180  dup
0x98181  ldstr    aIsvconfig// "isvconfig"
0x98186  ldc.i4.s 0x37
0x98188  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9818d  dup
0x9818e  ldstr    aKbarticle// "kbarticle"
0x98193  ldc.i4.s 0x38
0x98195  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9819a  dup
0x9819b  ldstr    aKbarticlecomme// "kbarticlecomment"
0x981a0  ldc.i4.s 0x39
0x981a2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x981a7  dup
0x981a8  ldstr    aKbarticletempl// "kbarticletemplate"
0x981ad  ldc.i4.s 0x3A
0x981af  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x981b4  dup
0x981b5  ldstr    aLead// "lead"
0x981ba  ldc.i4.s 0x3B
0x981bc  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x981c1  dup
0x981c2  ldstr    aLetter// "letter"
0x981c7  ldc.i4.s 0x3C
0x981c9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x981ce  dup
0x981cf  ldstr    aLicense// "license"
0x981d4  ldc.i4.s 0x3D
0x981d6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x981db  dup
0x981dc  ldstr    aList// "list"
0x981e1  ldc.i4.s 0x3E
0x981e3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x981e8  dup
0x981e9  ldstr    aListmember// "listmember"
0x981ee  ldc.i4.s 0x3F
0x981f0  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x981f5  dup
0x981f6  ldstr    aLookupmapping// "lookupmapping"
0x981fb  ldc.i4.s 0x40
0x981fd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x98202  dup
0x98203  ldstr    aMailmergetempl_0// "mailmergetemplate"
0x98208  ldc.i4.s 0x41
0x9820a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9820f  dup
0x98210  ldstr    aMonthlyfiscalc// "monthlyfiscalcalendar"
0x98215  ldc.i4.s 0x42
0x98217  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9821c  dup
0x9821d  ldstr    aNotification// "notification"
0x98222  ldc.i4.s 0x43
0x98224  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x98229  dup
0x9822a  ldstr    aOpportunity// "opportunity"
0x9822f  ldc.i4.s 0x44
0x98231  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x98236  dup
0x98237  ldstr    aOpportunityclo_0// "opportunityclose"
0x9823c  ldc.i4.s 0x45
0x9823e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x98243  dup
0x98244  ldstr    aOpportunitypro// "opportunityproduct"
0x98249  ldc.i4.s 0x46
0x9824b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x98250  dup
0x98251  ldstr    aOrderclose// "orderclose"
0x98256  ldc.i4.s 0x47
0x98258  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9825d  dup
0x9825e  ldstr    aOrganization// "organization"
0x98263  ldc.i4.s 0x48
  ... truncated ...
```
