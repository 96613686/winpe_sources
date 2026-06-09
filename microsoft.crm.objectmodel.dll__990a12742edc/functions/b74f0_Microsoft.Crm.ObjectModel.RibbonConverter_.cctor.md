# Microsoft.Crm.ObjectModel.RibbonConverter::.cctor

- ea: `0xb74f0`
- end: `0xb7671`
- name: `Microsoft.Crm.ObjectModel.RibbonConverter::.cctor`
- size: `385`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0xb7538`: `Mscrm.Modern.PinCommand`
- `0xb7517`: `Mscrm.DeleteSelectedRecord`
- `0xb750c`: `Mscrm.DeletePrimaryRecord`
- `0xb7522`: `Mscrm.Modern.resizeHandlesCommand`
- `0xb752d`: `Mscrm.Modern.refreshCommand`
- `0xb7543`: `Mscrm.Modern.ChangeControlCommand`
- `0xb7564`: `Mscrm.DynamicMenu.Subgrid.NewActivityMenu.task`
- `0xb7585`: `Mscrm.CreateTask`
- `0xb7590`: `Mscrm.CreatePhoneCall`
- `0xb759b`: `Mscrm.CreateAppointment`
- `0xb75b1`: `Mscrm.SavePrimaryActivityAsComplete`

## pseudocode

```c

```

## disassembly

```asm
0xb74f0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0xb74f5  dup
0xb74f6  ldstr    aMscrmNewrecord// "Mscrm.NewRecordFromForm"
0xb74fb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xb7500  dup
0xb7501  ldstr    aMscrmNewrecord_0// "Mscrm.NewRecordFromGrid"
0xb7506  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xb750b  dup
0xb750c  ldstr    aMscrmDeletepri// "Mscrm.DeletePrimaryRecord"
0xb7511  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xb7516  dup
0xb7517  ldstr    aMscrmDeletesel// "Mscrm.DeleteSelectedRecord"
0xb751c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xb7521  dup
0xb7522  ldstr    aMscrmModernRes// "Mscrm.Modern.resizeHandlesCommand"
0xb7527  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xb752c  dup
0xb752d  ldstr    aMscrmModernRef// "Mscrm.Modern.refreshCommand"
0xb7532  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xb7537  dup
0xb7538  ldstr    aMscrmModernPin// "Mscrm.Modern.PinCommand"
0xb753d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xb7542  dup
0xb7543  ldstr    aMscrmModernCha// "Mscrm.Modern.ChangeControlCommand"
0xb7548  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xb754d  dup
0xb754e  ldstr    aMscrmAddnewrec// "Mscrm.AddNewRecordFromSubGridStandard"
0xb7553  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xb7558  dup
0xb7559  ldstr    aMscrmAddexisti// "Mscrm.AddExistingRecordFromSubGridStand"...
0xb755e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xb7563  dup
0xb7564  ldstr    aMscrmDynamicme_6// "Mscrm.DynamicMenu.Subgrid.NewActivityMe"...
0xb7569  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xb756e  dup
0xb756f  ldstr    aMscrmDynamicme_7// "Mscrm.DynamicMenu.Subgrid.NewActivityMe"...
0xb7574  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xb7579  dup
0xb757a  ldstr    aMscrmDynamicme_8// "Mscrm.DynamicMenu.Subgrid.NewActivityMe"...
0xb757f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xb7584  dup
0xb7585  ldstr    aMscrmCreatetas// "Mscrm.CreateTask"
0xb758a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xb758f  dup
0xb7590  ldstr    aMscrmCreatepho// "Mscrm.CreatePhoneCall"
0xb7595  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xb759a  dup
0xb759b  ldstr    aMscrmCreateapp// "Mscrm.CreateAppointment"
0xb75a0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xb75a5  dup
0xb75a6  ldstr    aMscrmFormLeadC// "Mscrm.Form.lead.ConvertQuick"
0xb75ab  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xb75b0  dup
0xb75b1  ldstr    aMscrmSaveprima// "Mscrm.SavePrimaryActivityAsComplete"
0xb75b6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xb75bb  dup
0xb75bc  ldstr    aMscrmHomepageg_0// "Mscrm.HomepageGrid.opportunity.MarkAsWo"...
0xb75c1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xb75c6  dup
0xb75c7  ldstr    aMscrmFormOppor// "Mscrm.Form.opportunity.MarkAsWon"
0xb75cc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xb75d1  dup
0xb75d2  ldstr    aMscrmHomepageg_1// "Mscrm.HomepageGrid.opportunity.MarkAsLo"...
0xb75d7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xb75dc  dup
0xb75dd  ldstr    aMscrmFormOppor_0// "Mscrm.Form.opportunity.MarkAsLost"
0xb75e2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xb75e7  dup
0xb75e8  ldstr    aMscrmFormConve// "Mscrm.Form.ConvertToOpportunity"
0xb75ed  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xb75f2  dup
0xb75f3  ldstr    aMscrmFormIncid// "Mscrm.Form.incident.Resolve"
0xb75f8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xb75fd  dup
0xb75fe  ldstr    aMscrmHomepageg_2// "Mscrm.HomepageGrid.incident.Resolve"
0xb7603  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xb7608  dup
0xb7609  ldstr    aMscrmHomepageg_3// "Mscrm.HomepageGrid.lead.ConvertQuick"
0xb760e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xb7613  dup
0xb7614  ldstr    aMscrmDynamicme_9// "Mscrm.DynamicMenu.Form.DisqualifyAs.4.0"
0xb7619  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xb761e  dup
0xb761f  ldstr    aMscrmDynamicme_10// "Mscrm.DynamicMenu.Form.DisqualifyAs.5.1"
0xb7624  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xb7629  dup
0xb762a  ldstr    aMscrmDynamicme_11// "Mscrm.DynamicMenu.Form.DisqualifyAs.6.2"
0xb762f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xb7634  dup
0xb7635  ldstr    aMscrmDynamicme_12// "Mscrm.DynamicMenu.Form.DisqualifyAs.7.3"
0xb763a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xb763f  dup
0xb7640  ldstr    aMscrmDynamicme_13// "Mscrm.DynamicMenu.Grid.DisqualifyAs.4.0"
0xb7645  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xb764a  dup
0xb764b  ldstr    aMscrmDynamicme_14// "Mscrm.DynamicMenu.Grid.DisqualifyAs.5.1"
0xb7650  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xb7655  dup
0xb7656  ldstr    aMscrmDynamicme_15// "Mscrm.DynamicMenu.Grid.DisqualifyAs.6.2"
0xb765b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xb7660  dup
0xb7661  ldstr    aMscrmDynamicme_16// "Mscrm.DynamicMenu.Grid.DisqualifyAs.7.3"
0xb7666  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xb766b  stsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.ObjectModel.RibbonConverter::commandsEnabledForMocaOffline
0xb7670  ret
```
