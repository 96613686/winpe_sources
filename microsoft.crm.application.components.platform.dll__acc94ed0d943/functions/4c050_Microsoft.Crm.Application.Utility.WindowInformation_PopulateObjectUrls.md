# Microsoft.Crm.Application.Utility.WindowInformation::PopulateObjectUrls

- ea: `0x4c050`
- end: `0x4c73b`
- name: `Microsoft.Crm.Application.Utility.WindowInformation::PopulateObjectUrls`
- size: `1771`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x4bf20`

## callees

- `0x4c050`

## string_xrefs

- `0x4c09a`: `sm/workplans/dialogs/serviceavailability.aspx`
- `0x4c162`: `cs/articles/comment/edit.aspx`
- `0x4c177`: `tools/kbtemplateeditor/kbtemplateeditor.aspx`
- `0x4c18c`: `tools/emailtemplateeditor/emailtemplateeditor.aspx`
- `0x4c234`: `biz/fieldsecurityprofiles/edit.aspx`
- `0x4c4dd`: `_common/error/dlg_scripterror.aspx`
- `0x4c4f2`: `_common/error/dlg_scripterrordetails.aspx`
- `0x4c531`: `tools/bulkdeletewizard/bulkdeletewizard.aspx`
- `0x4c585`: `tools/bulkdelete/edit.aspx`
- `0x4c5c4`: `tools/solution/exportwizard/welcomepage.aspx`
- `0x4c62d`: `cs/articles/lookup_template.aspx`
- `0x4c642`: `activities/dlg_create.aspx`

## pseudocode

```c

```

## disassembly

```asm
0x4c050  ldarg.0
0x4c051  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c056  ldc.i4   0x11D7
0x4c05b  ldstr    aToolsAuditAudi// "tools/audit/audit_details.aspx"
0x4c060  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c065  ldarg.0
0x4c066  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c06b  ldc.i4   0xFA7
0x4c070  ldstr    aSmResourcegrou// "sm/resourcegroups/edit.aspx"
0x4c075  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c07a  ldarg.0
0x4c07b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c080  ldc.i4   0xFA6
0x4c085  ldstr    aSmResourcespec// "sm/resourcespecs/edit.aspx"
0x4c08a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c08f  ldarg.0
0x4c090  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c095  ldc.i4   0x138B
0x4c09a  ldstr    aSmWorkplansDia// "sm/workplans/dialogs/serviceavailabilit"...
0x4c09f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c0a4  ldarg.0
0x4c0a5  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c0aa  ldc.i4   0x138E
0x4c0af  ldstr    aSmWorkplansDia_0// "sm/workplans/dialogs/occurrence.aspx"
0x4c0b4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c0b9  ldarg.0
0x4c0ba  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c0bf  ldc.i4   0x138F
0x4c0c4  ldstr    aSmWorkplansDia_1// "sm/workplans/dialogs/recurrencerule.asp"...
0x4c0c9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c0ce  ldarg.0
0x4c0cf  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c0d4  ldc.i4   0x1390
0x4c0d9  ldstr    aSmWorkplansDia_2// "sm/workplans/dialogs/timesheet.aspx"
0x4c0de  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c0e3  ldarg.0
0x4c0e4  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c0e9  ldc.i4   0xFA3
0x4c0ee  ldstr    aSmWorkplansEdi// "sm/workplans/edit.aspx"
0x4c0f3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c0f8  ldarg.0
0x4c0f9  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c0fe  ldc.i4   0x1197
0x4c103  ldstr    aSfaCustomeropp// "sfa/customeropportunityrole/edit.aspx"
0x4c108  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c10d  ldarg.0
0x4c10e  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c113  ldc.i4   0x2475
0x4c118  ldstr    aMainAspxEtc933// "main.aspx?etc=9333&pagetype=webresource"...
0x4c11d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c122  ldarg.0
0x4c123  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c128  ldc.i4.5
0x4c129  ldstr    aNotesEditAspx// "notes/edit.aspx"
0x4c12e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c133  ldarg.0
0x4c134  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c139  ldc.i4.s 0xA
0x4c13b  ldstr    aBizBusinessEdi// "biz/business/edit.aspx"
0x4c140  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c145  ldarg.0
0x4c146  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c14b  ldc.i4.s 0x7E
0x4c14d  ldstr    aCsArticlesView_0// "cs/articles/viewer/default.aspx"
0x4c152  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c157  ldarg.0
0x4c158  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c15d  ldc.i4   0x43A
0x4c162  ldstr    aCsArticlesComm// "cs/articles/comment/edit.aspx"
0x4c167  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c16c  ldarg.0
0x4c16d  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c172  ldc.i4   0x3F8
0x4c177  ldstr    aToolsKbtemplat_2// "tools/kbtemplateeditor/kbtemplateeditor"...
0x4c17c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c181  ldarg.0
0x4c182  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c187  ldc.i4   0x7DA
0x4c18c  ldstr    aToolsEmailtemp// "tools/emailtemplateeditor/emailtemplate"...
0x4c191  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c196  ldarg.0
0x4c197  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c19c  ldc.i4   0x270D
0x4c1a1  ldstr    aToolsEmailsign// "tools/emailsignatureeditor/emailsignatu"...
0x4c1a6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c1ab  ldarg.0
0x4c1ac  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c1b1  ldc.i4   0x81
0x4c1b6  ldstr    aToolsSubjectma// "tools/subjectmanager/dialogs/edit.aspx"
0x4c1bb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c1c0  ldarg.0
0x4c1c1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c1c6  ldc.i4   0x84
0x4c1cb  ldstr    aToolsNewsedito// "tools/newseditor/edit.aspx"
0x4c1d0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c1d5  ldarg.0
0x4c1d6  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c1db  ldc.i4   0x3E9
0x4c1e0  ldstr    aActivitiesAtta// "activities/attachment/edit.aspx"
0x4c1e5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c1ea  ldarg.0
0x4c1eb  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c1f0  ldc.i4   0xC9F
0x4c1f5  ldstr    aConnectionsCon// "connections/connectionroles/edit.aspx"
0x4c1fa  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c1ff  ldarg.0
0x4c200  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c205  ldc.i4   0x42E
0x4c20a  ldstr    aSfaSaleslitAtt// "sfa/saleslit/attachment_edit.aspx"
0x4c20f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c214  ldarg.0
0x4c215  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c21a  ldc.i4   0x40C
0x4c21f  ldstr    aBizRolesEditAs// "biz/roles/edit.aspx"
0x4c224  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c229  ldarg.0
0x4c22a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c22f  ldc.i4   0x4B0
0x4c234  ldstr    aBizFieldsecuri// "biz/fieldsecurityprofiles/edit.aspx"
0x4c239  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c23e  ldarg.0
0x4c23f  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c244  ldc.i4   0x40F
0x4c249  ldstr    aToolsViewedito// "tools/vieweditor/viewmanager.aspx"
0x4c24e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c253  ldarg.0
0x4c254  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c259  ldc.i4   0x457
0x4c25e  ldstr    aToolsVisualiza_0// "tools/visualizationdesigner/visualizati"...
0x4c263  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c268  ldarg.0
0x4c269  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c26e  ldc.i4   0x1070
0x4c273  ldstr    aSfaOppsCloseop// "sfa/opps/closeopp.aspx"
0x4c278  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c27d  ldarg.0
0x4c27e  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c283  ldc.i4   0x1071
0x4c288  ldstr    aSfaSalesorderC// "sfa/salesorder/cancelorder.aspx"
0x4c28d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c292  ldarg.0
0x4c293  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c298  ldc.i4   0x1073
0x4c29d  ldstr    aSfaQuotesClose// "sfa/quotes/closequote.aspx"
0x4c2a2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c2a7  ldarg.0
0x4c2a8  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c2ad  ldc.i4   0x1196
0x4c2b2  ldstr    aSfaCustomerrel// "sfa/customerrelationships/edit.aspx"
0x4c2b7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c2bc  ldarg.0
0x4c2bd  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c2c2  ldc.i4   0x2391
0x4c2c7  ldstr    aBizTransaction// "biz/transactioncurrencies/edit.aspx"
0x4c2cc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c2d1  ldarg.0
0x4c2d2  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c2d7  ldc.i4   0x2392
0x4c2dc  ldstr    aToolsMailmerge// "tools/mailmerge/edit.aspx"
0x4c2e1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c2e6  ldarg.0
0x4c2e7  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c2ec  ldc.i4   0x1194
0x4c2f1  ldstr    aToolsRelations// "tools/relationshiproleeditor/edit.aspx"
0x4c2f6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c2fb  ldarg.0
0x4c2fc  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c301  ldc.i4   0x238C
0x4c306  ldstr    aCrmreportsView// "crmreports/viewer/viewer.aspx"
0x4c30b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c310  ldarg.0
0x4c311  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c316  ldc.i4   0x238B
0x4c31b  ldstr    aCrmreportsRepo// "crmreports/reportproperty.aspx"
0x4c320  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c325  ldarg.0
0x4c326  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c32b  ldc.i4   0x138C
0x4c330  ldstr    aSmWorkplansDia_3// "sm/workplans/dialogs/timeoff.aspx"
0x4c335  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c33a  ldarg.0
0x4c33b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c340  ldc.i4   0x138D
0x4c345  ldstr    aSmWorkplansDia_4// "sm/workplans/dialogs/holiday.aspx"
0x4c34a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c34f  ldarg.0
0x4c350  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c355  ldc.i4   0x1391
0x4c35a  ldstr    aSmWorkplansEdi// "sm/workplans/edit.aspx"
0x4c35f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c364  ldarg.0
0x4c365  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c36a  ldc.i4   0x1392
0x4c36f  ldstr    aSmWorkplansEdi// "sm/workplans/edit.aspx"
0x4c374  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c379  ldarg.0
0x4c37a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c37f  ldc.i4   0x7D4
0x4c384  ldstr    aGridCmdsDlgAdd// "_grid/cmds/dlg_addquota.aspx"
0x4c389  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c38e  ldarg.0
0x4c38f  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c394  ldc.i4   0x7D3
0x4c399  ldstr    aGridCmdsDlgAdd// "_grid/cmds/dlg_addquota.aspx"
0x4c39e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c3a3  ldarg.0
0x4c3a4  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c3a9  ldc.i4   0x7D2
0x4c3ae  ldstr    aGridCmdsDlgAdd// "_grid/cmds/dlg_addquota.aspx"
0x4c3b3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c3b8  ldarg.0
0x4c3b9  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c3be  ldc.i4   0x7D1
0x4c3c3  ldstr    aGridCmdsDlgAdd// "_grid/cmds/dlg_addquota.aspx"
0x4c3c8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c3cd  ldarg.0
0x4c3ce  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c3d3  ldc.i4   0x7D0
0x4c3d8  ldstr    aGridCmdsDlgAdd// "_grid/cmds/dlg_addquota.aspx"
0x4c3dd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c3e2  ldarg.0
0x4c3e3  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c3e8  ldc.i4   0x1086
0x4c3ed  ldstr    aAdvancedfindAd_0// "advancedfind/advfind.aspx"
0x4c3f2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c3f7  ldarg.0
0x4c3f8  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c3fd  ldc.i4   0x232C
0x4c402  ldstr    aToolsOfflineda// "tools/offlinedata/offlinefilter.aspx"
0x4c407  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c40c  ldarg.0
0x4c40d  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c412  ldc.i4   0x1006
0x4c417  ldstr    aToolsSystemcus// "tools/systemcustomization/displaystring"...
0x4c41c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c421  ldarg.0
0x4c422  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c427  ldc.i4   0x1393
0x4c42c  ldstr    aSmActivitysche// "sm/activityscheduling/schedulingdialog."...
0x4c431  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c436  ldarg.0
0x4c437  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c43c  ldc.i4   0x125F
0x4c441  ldstr    aSfaWorkflowEdi// "sfa/workflow/edit.aspx"
0x4c446  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c44b  ldarg.0
0x4c44c  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c451  ldc.i4   0x125C
0x4c456  ldstr    aToolsAsyncoper// "tools/asyncoperation/edit.aspx"
0x4c45b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c460  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x4c465  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x4c46a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_UnifiedProcessDesignerV2()
0x4c46f  ldarg.0
0x4c470  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Utility.WindowInformation::_context
0x4c475  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4c47a  brfalse.s loc_4C4A8
0x4c47c  ldarg.0
0x4c47d  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c482  ldc.i4   0x232D
0x4c487  ldstr    aToolsSystemcus_0// "tools/systemcustomization/processdesign"...
0x4c48c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c491  ldarg.0
0x4c492  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c497  ldc.i4   0x1266
0x4c49c  ldstr    aToolsSystemcus_1// "tools/systemcustomization/processdesign"...
0x4c4a1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c4a6  br.s     loc_4C4D2
0x4c4a8  ldarg.0
0x4c4a9  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c4ae  ldc.i4   0x232D
0x4c4b3  ldstr    aToolsWorkflowi// "tools/workflowinstance/edit.aspx"
0x4c4b8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c4bd  ldarg.0
0x4c4be  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c4c3  ldc.i4   0x1266
0x4c4c8  ldstr    aSfaWorkflowses// "sfa/workflowsession/edit.aspx"
0x4c4cd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c4d2  ldarg.0
0x4c4d3  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c4d8  ldc.i4   0x23F0
0x4c4dd  ldstr    aCommonErrorDlg// "_common/error/dlg_scripterror.aspx"
0x4c4e2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c4e7  ldarg.0
0x4c4e8  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c4ed  ldc.i4   0x23F1
0x4c4f2  ldstr    aCommonErrorDlg_0// "_common/error/dlg_scripterrordetails.as"...
0x4c4f7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c4fc  ldarg.0
0x4c4fd  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c502  ldc.i4   0x23F5
0x4c507  ldstr    aToolsImportwiz// "tools/importwizard/importwizard.aspx"
0x4c50c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c511  ldarg.0
0x4c512  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
0x4c517  ldc.i4   0x23F3
0x4c51c  ldstr    aToolsDuplicate// "tools/duplicatedetection/systemwidedupl"...
0x4c521  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x4c526  ldarg.0
0x4c527  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Application.Utility.WindowInformation::_objectUrls
  ... truncated ...
```
